---
title: 워크플로 실행 속성
ms.date: 03/30/2017
ms.assetid: a50e088e-3a45-4267-bd51-1a3e6c2d246d
ms.openlocfilehash: 2681152ba89baa2f65d5402a8c8c9d872cadb65b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33518646"
---
# <a name="workflow-execution-properties"></a><span data-ttu-id="0bcdb-102">워크플로 실행 속성</span><span class="sxs-lookup"><span data-stu-id="0bcdb-102">Workflow Execution Properties</span></span>
<span data-ttu-id="0bcdb-103">CLR은 TLS(스레드 로컬 저장소)를 통해 각 스레드의 실행 컨텍스트를 유지 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="0bcdb-103">Through thread local storage (TLS), the CLR maintains an execution context for each thread.</span></span> <span data-ttu-id="0bcdb-104">이 실행 컨텍스트는 스레드 ID, 앰비언트 트랜잭션 및 현재 권한 집합과 같은 잘 알려진 스레드 속성은 물론 명명된 슬롯과 같은 사용자 정의 스레드 속성을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="0bcdb-104">This execution context governs well-known thread properties such as the thread identity, the ambient transaction, and the current permission set in addition to user-defined thread properties like named slots.</span></span>  
  
 <span data-ttu-id="0bcdb-105">CLR을 직접 대상으로 하는 프로그램과 달리 워크플로 프로그램은 스레드를 알 수 없는 환경에서 실행되는 계층적 범위의 활동 트리입니다.</span><span class="sxs-lookup"><span data-stu-id="0bcdb-105">Unlike programs directly targeting the CLR, workflow programs are hierarchically scoped trees of activities that execute in a thread-agnostic environment.</span></span> <span data-ttu-id="0bcdb-106">이는 표준 TLS 메커니즘을 직접 사용하여 제공된 작업 항목 범위에 있는 컨텍스트를 확인할 수 없음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="0bcdb-106">This implies that the standard TLS mechanisms cannot directly be used to determine what context is in scope for a given work item.</span></span> <span data-ttu-id="0bcdb-107">예를 들어 두 개의 병렬 실행 분기는 서로 다른 트랜잭션을 사용할 수 있지만 스케줄러는 동일한 CLR 스레드에서 해당 실행을 인터리브할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bcdb-107">For example, two parallel branches of execution might use different transactions, yet the scheduler might interleave their execution on the same CLR thread.</span></span>  
  
 <span data-ttu-id="0bcdb-108">워크플로 실행 속성은 활동 환경에 컨텍스트별 속성을 추가하는 메커니즘을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0bcdb-108">Workflow execution properties provide a mechanism to add context specific properties to an activity’s environment.</span></span> <span data-ttu-id="0bcdb-109">이 실행 속성을 통해 활동에서 해당 하위 트리 범위의 속성을 선언할 수 있을 뿐 아니라 CLR 개체와의 적절한 상호 작용을 위해 TLS를 설정 및 중지하는 후크를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bcdb-109">This allows an activity to declare which properties are in scope for its sub-tree and also provides hooks for setting up and tearing down TLS to properly interoperate with CLR objects.</span></span>  
  
## <a name="creating-and-using-workflow-execution-properties"></a><span data-ttu-id="0bcdb-110">워크플로 실행 속성 만들기 및 사용</span><span class="sxs-lookup"><span data-stu-id="0bcdb-110">Creating and Using Workflow Execution Properties</span></span>  
 <span data-ttu-id="0bcdb-111">워크플로 실행 속성은 보통<xref:System.Activities.IExecutionProperty> 인터페이스를 구현하고, 메시징에 중점을 둔 속성을 통해 대신 <xref:System.ServiceModel.Activities.ISendMessageCallback> 및 <xref:System.ServiceModel.Activities.IReceiveMessageCallback>을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="0bcdb-111">Workflow execution properties usually implement the <xref:System.Activities.IExecutionProperty> interface, though properties focused on messaging may implement <xref:System.ServiceModel.Activities.ISendMessageCallback> and <xref:System.ServiceModel.Activities.IReceiveMessageCallback> instead.</span></span> <span data-ttu-id="0bcdb-112">워크플로 실행 속성을 만들려면 <xref:System.Activities.IExecutionProperty> 인터페이스를 구현하는 클래스를 만들고 멤버 <xref:System.Activities.IExecutionProperty.SetupWorkflowThread%2A> 및 <xref:System.Activities.IExecutionProperty.CleanupWorkflowThread%2A>를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="0bcdb-112">To create a workflow execution property, create a class that implements the <xref:System.Activities.IExecutionProperty> interface and implement the members <xref:System.Activities.IExecutionProperty.SetupWorkflowThread%2A> and <xref:System.Activities.IExecutionProperty.CleanupWorkflowThread%2A>.</span></span> <span data-ttu-id="0bcdb-113">이 멤버는 자식 활동을 비롯하여 속성이 포함된 활동의 각 작업 펄스 중 스레드 로컬 저장소를 올바르게 설정하고 중지할 기회를 실행 속성에 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0bcdb-113">These members provide the execution property with an opportunity to properly set up and tear down the thread local storage during each pulse of work of the activity that contains the property, including any child activities.</span></span> <span data-ttu-id="0bcdb-114">이 예제에서는 `ConsoleColorProperty`를 설정하는 `Console.ForegroundColor`를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0bcdb-114">In this example, a `ConsoleColorProperty` is created that sets the `Console.ForegroundColor`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0bcdb-115">이 항목의 다음 예제 코드는 기반는 [실행 속성](../../../docs/framework/windows-workflow-foundation/samples/execution-properties.md) 샘플.</span><span class="sxs-lookup"><span data-stu-id="0bcdb-115">The following example code in this topic is based on the [Execution Properties](../../../docs/framework/windows-workflow-foundation/samples/execution-properties.md) sample.</span></span>  
  
```csharp  
class ConsoleColorProperty : IExecutionProperty  
{  
    public const string Name = "ConsoleColorProperty";  
  
    ConsoleColor original;  
    ConsoleColor color;  
  
    public ConsoleColorProperty(ConsoleColor color)  
    {  
        this.color = color;  
    }  
  
    void IExecutionProperty.SetupWorkflowThread()  
    {  
        original = Console.ForegroundColor;  
        Console.ForegroundColor = color;  
    }  
  
    void IExecutionProperty.CleanupWorkflowThread()  
    {  
        Console.ForegroundColor = original;  
    }  
}  
```  
  
 <span data-ttu-id="0bcdb-116">활동 작성자는 활동 실행 재정의에 이 속성을 등록하여 속성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bcdb-116">Activity authors can use this property by registering it in the activity’s execute override.</span></span> <span data-ttu-id="0bcdb-117">이 예제에서는 `ConsoleColorScope`를 현재 `ConsoleColorProperty`의 <xref:System.Activities.NativeActivityContext.Properties%2A> 컬렉션에 추가하여 등록하는 <xref:System.Activities.NativeActivityContext> 활동을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0bcdb-117">In this example, a `ConsoleColorScope` activity is defined that registers the `ConsoleColorProperty` by adding it to the <xref:System.Activities.NativeActivityContext.Properties%2A> collection of the current <xref:System.Activities.NativeActivityContext>.</span></span>  
  
```csharp  
public sealed class ConsoleColorScope : NativeActivity  
{  
    public ConsoleColorScope()  
        : base()  
    {  
    }  
  
    public ConsoleColor Color { get; set; }  
    public Activity Body { get; set; }  
  
    protected override void Execute(NativeActivityContext context)  
    {  
        context.Properties.Add(ConsoleColorProperty.Name, new ConsoleColorProperty(this.Color));  
  
        if (this.Body != null)  
        {  
            context.ScheduleActivity(this.Body);  
        }  
    }  
}  
```  
  
 <span data-ttu-id="0bcdb-118">활동 본문이 작업 펄스를 시작하면 속성의 <xref:System.Activities.IExecutionProperty.SetupWorkflowThread%2A> 메서드가 호출되고 작업 펄스가 완료되면 <xref:System.Activities.IExecutionProperty.CleanupWorkflowThread%2A>가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bcdb-118">When the activity’s body starts a pulse of work, the <xref:System.Activities.IExecutionProperty.SetupWorkflowThread%2A> method of the property is called, and when the pulse of work is complete, the <xref:System.Activities.IExecutionProperty.CleanupWorkflowThread%2A> is called.</span></span> <span data-ttu-id="0bcdb-119">이 예제에서는 세 분기가 있는 <xref:System.Activities.Statements.Parallel> 활동을 사용하여 워크플로를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0bcdb-119">In this example, a workflow is created that uses a <xref:System.Activities.Statements.Parallel> activity with three branches.</span></span> <span data-ttu-id="0bcdb-120">처음 두 분기는 `ConsoleColorScope` 활동을 사용하고 세 번째 분기는 이 활동을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0bcdb-120">The first two branches use the `ConsoleColorScope` activity and the third branch does not.</span></span> <span data-ttu-id="0bcdb-121">세 분기에는 모두 <xref:System.Activities.Statements.WriteLine> 활동 두 개와 <xref:System.Activities.Statements.Delay> 활동 하나가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bcdb-121">All three branches contain two <xref:System.Activities.Statements.WriteLine> activities and a <xref:System.Activities.Statements.Delay> activity.</span></span> <span data-ttu-id="0bcdb-122"><xref:System.Activities.Statements.Parallel> 활동이 실행되면 분기에 포함된 활동이 인터리브 방식으로 실행되지만, 각 자식 활동이 실행되면 `ConsoleColorProperty`에서 올바른 콘솔 색상이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bcdb-122">When the <xref:System.Activities.Statements.Parallel> activity executes, the activities that are contained in the branches execute in an interleaved manner, but as each child activity executes the correct console color is applied by the `ConsoleColorProperty`.</span></span>  
  
```csharp  
Activity wf = new Parallel  
{  
    Branches =   
    {  
        new ConsoleColorScope  
        {  
            Color = ConsoleColor.Blue,  
            Body = new Sequence  
            {  
                Activities =   
                {  
                    new WriteLine  
                    {  
                        Text = "Start blue text."  
                    },  
                    new Delay  
                    {  
                        Duration = TimeSpan.FromSeconds(1)  
                    },  
                    new WriteLine  
                    {  
                        Text = "End blue text."  
                    }  
                }  
            }  
        },  
        new ConsoleColorScope  
        {  
            Color = ConsoleColor.Red,  
            Body = new Sequence  
            {  
                Activities =   
                {  
                    new WriteLine  
                    {  
                        Text = "Start red text."  
                    },  
                    new Delay  
                    {  
                        Duration = TimeSpan.FromSeconds(1)  
                    },  
                    new WriteLine  
                    {  
                        Text = "End red text."  
                    }  
                }  
            }  
        },  
        new Sequence  
        {  
            Activities =   
            {  
                new WriteLine  
                {  
                    Text = "Start default text."  
                },  
                new Delay  
                {  
                    Duration = TimeSpan.FromSeconds(1)  
                },  
                new WriteLine  
                {  
                    Text = "End default text."  
                }  
            }  
        }  
    }  
};  
  
WorkflowInvoker.Invoke(wf);  
```  
  
 <span data-ttu-id="0bcdb-123">워크플로가 호출되면 다음 출력이 콘솔 창에 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bcdb-123">When the workflow is invoked, the following output is written to the console window.</span></span>  
  
```  
Start blue text.  
Start red text.  
Start default text.  
End blue text.  
End red text.  
End default text.  
```  
  
> [!NOTE]
>  <span data-ttu-id="0bcdb-124">이전 출력에는 표시되지 않았지만 콘솔 창의 각 텍스트 행은 지정된 색상으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bcdb-124">Although it is not shown in the previous output, each line of text in the console window is displayed in the indicated color.</span></span>  
  
 <span data-ttu-id="0bcdb-125">워크플로 실행 속성은 사용자 지정 활동 작성자가 사용할 수 있으며, <xref:System.ServiceModel.Activities.CorrelationScope> 및 <xref:System.Activities.Statements.TransactionScope> 활동과 같은 활동의 처리 관리 메커니즘도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0bcdb-125">Workflow execution properties can be used by custom activity authors, and they also provide the mechanism for handle management for activities such as the <xref:System.ServiceModel.Activities.CorrelationScope> and <xref:System.Activities.Statements.TransactionScope> activities.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bcdb-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0bcdb-126">See Also</span></span>  
 <xref:System.Activities.IExecutionProperty>  
 <xref:System.Activities.IPropertyRegistrationCallback>  
 <xref:System.Activities.RegistrationContext>
