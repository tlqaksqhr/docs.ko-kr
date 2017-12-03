---
title: "워크플로 및 활동과 XAML 간 serialize"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 37685b32-24e3-4d72-88d8-45d5fcc49ec2
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3be1c85a87896c176d5e81d2938418194d28b93b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="serializing-workflows-and-activities-to-and-from-xaml"></a><span data-ttu-id="236e1-102">워크플로 및 활동과 XAML 간 serialize</span><span class="sxs-lookup"><span data-stu-id="236e1-102">Serializing Workflows and Activities to and from XAML</span></span>
<span data-ttu-id="236e1-103">어셈블리에 포함되어 있는 형식으로 컴파일하는 것 외에 워크플로 정의를 XAML로 serialize할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="236e1-103">In addition to being compiled into types that are contained in assemblies, workflow definitions can also be serialized to XAML.</span></span> <span data-ttu-id="236e1-104">serialize된 이 정의를 다시 로드하여 편집 또는 검사하거나, 빌드 시스템에 전달하여 컴파일하거나, 로드 및 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="236e1-104">These serialized definitions can be reloaded for editing or inspection, passed to a build system for compilation, or loaded and invoked.</span></span> <span data-ttu-id="236e1-105">이 항목에서는 워크플로 정의의 serialize와 XAML 워크플로 정의의 사용에 대해 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="236e1-105">This topic provides an overview of serializing workflow definitions and working with XAML workflow definitions.</span></span>  
  
## <a name="working-with-xaml-workflow-definitions"></a><span data-ttu-id="236e1-106">XAML 워크플로 정의 사용</span><span class="sxs-lookup"><span data-stu-id="236e1-106">Working with XAML Workflow Definitions</span></span>  
 <span data-ttu-id="236e1-107"><xref:System.Activities.ActivityBuilder> 클래스를 사용하여 serialization에 대한 워크플로 정의를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="236e1-107">To create a workflow definition for serialization, the <xref:System.Activities.ActivityBuilder> class is used.</span></span> <span data-ttu-id="236e1-108"><xref:System.Activities.ActivityBuilder>를 만드는 방법은 <xref:System.Activities.DynamicActivity>를 만드는 방법과 매우 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="236e1-108">Creating an <xref:System.Activities.ActivityBuilder> is very similar to creating a <xref:System.Activities.DynamicActivity>.</span></span> <span data-ttu-id="236e1-109">필요한 모든 인수를 지정하고 동작을 구성하는 활동을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="236e1-109">Any desired arguments are specified, and the activities that constitute the behavior are configured.</span></span> <span data-ttu-id="236e1-110">다음 예제에서는 두 개의 인수를 가져와서 두 인수를 함께 추가하고 결과를 반환하는 `Add` 활동을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="236e1-110">In the following example, an `Add` activity is created that takes two input arguments, adds them together, and returns the result.</span></span> <span data-ttu-id="236e1-111">이 활동은 결과를 반환하므로 제네릭 <xref:System.Activities.ActivityBuilder%601> 클래스가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="236e1-111">Because this activity returns a result, the generic <xref:System.Activities.ActivityBuilder%601> class is used.</span></span>  
  
 [!code-csharp[CFX_WorkflowApplicationExample#41](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#41)]  
  
 <span data-ttu-id="236e1-112">각각의 <xref:System.Activities.DynamicActivityProperty> 인스턴스는 워크플로에 대한 입력 인수 중 하나를 나타내며 <xref:System.Activities.ActivityBuilder.Implementation%2A>에는 워크플로의 논리를 구성하는 활동이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="236e1-112">Each of the <xref:System.Activities.DynamicActivityProperty> instances represents one of the input arguments to the workflow, and the <xref:System.Activities.ActivityBuilder.Implementation%2A> contains the activities that make up the logic of the workflow.</span></span> <span data-ttu-id="236e1-113">이 예제의 r-value 식은 Visual Basic 식입니다.</span><span class="sxs-lookup"><span data-stu-id="236e1-113">Note that the r-value expressions in this example are Visual Basic expressions.</span></span> <span data-ttu-id="236e1-114">람다 식은 <xref:System.Activities.Expressions.ExpressionServices.Convert%2A>를 사용하지 않으면 XAML로 serialize할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="236e1-114">Lambda expressions are not serializable to XAML unless <xref:System.Activities.Expressions.ExpressionServices.Convert%2A> is used.</span></span> <span data-ttu-id="236e1-115">serialize된 워크플로를 워크플로 디자이너에서 열거나 편집하려고 할 경우 Visual Basic 식을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="236e1-115">If the serialized workflows are intended to be opened or edited in the workflow designer then Visual Basic expressions should be used.</span></span> [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="236e1-116">[워크플로, 활동 및 명령적 코드를 사용 하 여 식을 작성](../../../docs/framework/windows-workflow-foundation/authoring-workflows-activities-and-expressions-using-imperative-code.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="236e1-116"> [Authoring Workflows, Activities, and Expressions Using Imperative Code](../../../docs/framework/windows-workflow-foundation/authoring-workflows-activities-and-expressions-using-imperative-code.md).</span></span>  
  
 <span data-ttu-id="236e1-117"><xref:System.Activities.ActivityBuilder> 인스턴스가 나타내는 워크플로 정의를 XAML로 serialize하려면 <xref:System.Activities.XamlIntegration.ActivityXamlServices>를 사용하여 <xref:System.Xaml.XamlWriter>를 만든 다음, <xref:System.Xaml.XamlServices>를 사용하여 <xref:System.Xaml.XamlWriter>를 통해 워크플로 정의를 serialize합니다.</span><span class="sxs-lookup"><span data-stu-id="236e1-117">To serialize the workflow definition represented by the <xref:System.Activities.ActivityBuilder> instance to XAML, use <xref:System.Activities.XamlIntegration.ActivityXamlServices> to create a <xref:System.Xaml.XamlWriter>, and then use <xref:System.Xaml.XamlServices> to serialize the workflow definition by using the <xref:System.Xaml.XamlWriter>.</span></span> <span data-ttu-id="236e1-118"><xref:System.Activities.XamlIntegration.ActivityXamlServices>에는 <xref:System.Activities.ActivityBuilder> 인스턴스와 XAML 간을 매핑하고, XAML 워크플로를 로드하고, 호출 가능한 <xref:System.Activities.DynamicActivity>를 반환하는 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="236e1-118"><xref:System.Activities.XamlIntegration.ActivityXamlServices> has methods to map <xref:System.Activities.ActivityBuilder> instances to and from XAML, and to load XAML workflows and return a <xref:System.Activities.DynamicActivity> that can be invoked.</span></span> <span data-ttu-id="236e1-119">다음 예제에서는 이전 예제의 <xref:System.Activities.ActivityBuilder> 인스턴스를 문자열로 serialize하고 파일로 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="236e1-119">In the following example, the <xref:System.Activities.ActivityBuilder> instance from the previous example is serialized to a string, and also saved to a file.</span></span>  
  
```csharp  
// Serialize the workflow to XAML and store it in a string.  
StringBuilder sb = new StringBuilder();  
StringWriter tw = new StringWriter(sb);  
XamlWriter xw = ActivityXamlServices.CreateBuilderWriter(new XamlXmlWriter(tw, new XamlSchemaContext()));  
XamlServices.Save(xw , ab);  
string serializedAB = sb.ToString();  
  
// Display the XAML to the console.  
Console.WriteLine(serializedAB);  
  
// Serialize the workflow to XAML and save it to a file.  
StreamWriter sw = File.CreateText(@"C:\Workflows\add.xaml");  
XamlWriter xw2 = ActivityXamlServices.CreateBuilderWriter(new XamlXmlWriter(sw, new XamlSchemaContext()));  
XamlServices.Save(xw2, ab);  
sw.Close();  
```  
  
 <span data-ttu-id="236e1-120">다음 예제에서는 serialize된 워크플로를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="236e1-120">The following example represents the serialized workflow.</span></span>  
  
```xaml  
<Activity   
  x:TypeArguments="x:Int32"   
  x:Class="Add"   
  xmlns="http://schemas.microsoft.com/netfx/2009/xaml/activities"   
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">  
  <x:Members>  
    <x:Property Name="Operand1" Type="InArgument(x:Int32)" />  
    <x:Property Name="Operand2" Type="InArgument(x:Int32)" />  
  </x:Members>  
  <Sequence>  
    <WriteLine Text="[Operand1.ToString() + " + " + Operand2.ToString()]" />  
    <Assign x:TypeArguments="x:Int32" Value="[Operand1 + Operand2]">  
      <Assign.To>  
        <OutArgument x:TypeArguments="x:Int32">  
          <ArgumentReference x:TypeArguments="x:Int32" ArgumentName="Result" />  
          </OutArgument>  
      </Assign.To>  
    </Assign>  
  </Sequence>  
</Activity>  
```  
  
 <span data-ttu-id="236e1-121">Serialize 된 워크플로 로드 하는 <xref:System.Activities.XamlIntegration.ActivityXamlServices> <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A> 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="236e1-121">To load a serialized workflow, the <xref:System.Activities.XamlIntegration.ActivityXamlServices> <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A> method is used.</span></span> <span data-ttu-id="236e1-122">이 메서드는 serialize된 워크플로 정의를 사용하고 워크플로 정의를 나타내는 <xref:System.Activities.DynamicActivity>를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="236e1-122">This takes the serialized workflow definition and returns a <xref:System.Activities.DynamicActivity> that represents the workflow definition.</span></span> <span data-ttu-id="236e1-123">유효성 검사 프로세스가 진행되는 동안 <xref:System.Activities.Activity.CacheMetadata%2A>의 본문에서 <xref:System.Activities.DynamicActivity>를 호출할 때까지는 XAML이 deserialize되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="236e1-123">Note that the XAML is not deserialized until <xref:System.Activities.Activity.CacheMetadata%2A> is called on the body of the <xref:System.Activities.DynamicActivity> during the validation process.</span></span> <span data-ttu-id="236e1-124">유효성 검사를 명시적으로 호출하지 않으면 워크플로가 호출될 때 유효성 검사가 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="236e1-124">If validation is not explicitly called then it is performed when the workflow is invoked.</span></span> <span data-ttu-id="236e1-125">XAML 워크플로 정의가 잘못된 경우 <xref:System.Argument> 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="236e1-125">If the XAML workflow definition is invalid, then an <xref:System.Argument> exception is thrown.</span></span> <span data-ttu-id="236e1-126"><xref:System.Activities.Activity.CacheMetadata%2A>에서 throw된 예외는 모두 <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>에 대한 호출에서 이스케이프되며 호출자가 처리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="236e1-126">Any exceptions thrown from <xref:System.Activities.Activity.CacheMetadata%2A> escape from the call to <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> and must be handled by the caller.</span></span> <span data-ttu-id="236e1-127">다음 예제에서는 이전 예제에서 serialize된 워크플로를 로드하고 <xref:System.Activities.WorkflowInvoker>를 사용하여 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="236e1-127">In the following example, the serialized workflow from the previous example is loaded and invoked by using <xref:System.Activities.WorkflowInvoker>.</span></span>  
  
 [!code-csharp[CFX_WorkflowApplicationExample#43](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#43)]  
  
 <span data-ttu-id="236e1-128">이 워크플로가 호출되면 다음 출력이 콘솔에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="236e1-128">When this workflow is invoked, the following output is displayed to the console.</span></span>  
  
 <span data-ttu-id="236e1-129">**25 + 15**</span><span class="sxs-lookup"><span data-stu-id="236e1-129">**25 + 15**</span></span>  
<span data-ttu-id="236e1-130">**40**</span><span class="sxs-lookup"><span data-stu-id="236e1-130">**40**</span></span>    
> [!NOTE]
>  [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="236e1-131">참조 입력 및 출력 인수를 사용 하는 워크플로 호출 [를 사용 하 여 WorkflowInvoker 및 WorkflowApplication](../../../docs/framework/windows-workflow-foundation/using-workflowinvoker-and-workflowapplication.md) 및 <xref:System.Activities.WorkflowInvoker.Invoke%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="236e1-131"> invoking workflows with input and output arguments, see [Using WorkflowInvoker and WorkflowApplication](../../../docs/framework/windows-workflow-foundation/using-workflowinvoker-and-workflowapplication.md) and <xref:System.Activities.WorkflowInvoker.Invoke%2A>.</span></span>  
  
 <span data-ttu-id="236e1-132">Serialize 된 워크플로에 C# 식이 있을 경우 아니라면 <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings> 인스턴스를 함께 해당 <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> 속성이로 설정 `true` 에 대 한 매개 변수로 전달 되어야 합니다 <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A?displayProperty=nameWithType>, 그렇지 않으면는 <xref:System.NotSupportedException> 와 비슷한 오류 메시지가 throw 됩니다는 다음: `Expression Activity type 'CSharpValue`1' 컴파일 실행 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="236e1-132">If the serialized workflow contains C# expressions, then an <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings> instance with its <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> property set to `true` must be passed as a parameter to <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A?displayProperty=nameWithType>, otherwise a <xref:System.NotSupportedException> will be thrown with a message similar to the following: `Expression Activity type 'CSharpValue`1' requires compilation in order to run.</span></span>  <span data-ttu-id="236e1-133">워크플로가 컴파일 되었는지 확인 하십시오.'</span><span class="sxs-lookup"><span data-stu-id="236e1-133">Please ensure that the workflow has been compiled.\`</span></span>  
  
```csharp  
ActivityXamlServicesSettings settings = new ActivityXamlServicesSettings  
{  
    CompileExpressions = true  
};  
  
DynamicActivity<int> wf = ActivityXamlServices.Load(new StringReader(serializedAB), settings) as DynamicActivity<int>;  
```  
  
 [!INCLUDE[crdefault](../../../includes/crdefault-md.md)]<span data-ttu-id="236e1-134">[C# 식을](../../../docs/framework/windows-workflow-foundation/csharp-expressions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="236e1-134"> [C# Expressions](../../../docs/framework/windows-workflow-foundation/csharp-expressions.md).</span></span>  
  
 <span data-ttu-id="236e1-135">Serialize 된 워크플로 정의에 로드할 수도 있습니다는 <xref:System.Activities.ActivityBuilder> 를 사용 하 여 인스턴스는 <xref:System.Activities.XamlIntegration.ActivityXamlServices> <xref:System.Activities.XamlIntegration.ActivityXamlServices.CreateBuilderReader%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="236e1-135">A serialized workflow definition can also be loaded into an <xref:System.Activities.ActivityBuilder> instance by using the <xref:System.Activities.XamlIntegration.ActivityXamlServices> <xref:System.Activities.XamlIntegration.ActivityXamlServices.CreateBuilderReader%2A> method.</span></span> <span data-ttu-id="236e1-136">serialize된 워크플로를 <xref:System.Activities.ActivityBuilder> 인스턴스로 로드한 후 검사하고 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="236e1-136">After a serialized workflow is loaded into an <xref:System.Activities.ActivityBuilder> instance it can be inspected and modified.</span></span> <span data-ttu-id="236e1-137">이 방법은 사용자 지정 Workflow Designer 작성자에게 유용하며, 디자인 프로세스가 진행되는 동안 워크플로 정의를 저장하고 다시 로드하기 위한 메커니즘을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="236e1-137">This is useful for custom workflow designer authors and provides a mechanism for saving and reloading workflow definitions during the design process.</span></span> <span data-ttu-id="236e1-138">다음 예제에서는 이전 예제에서 serialize된 워크플로 정의를 로드하고 해당 속성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="236e1-138">In the following example, the serialized workflow definition from the previous example is loaded and its properties are inspected.</span></span>  
  
 [!code-csharp[CFX_WorkflowApplicationExample#44](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#44)]
