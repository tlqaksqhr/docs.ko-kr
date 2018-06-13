---
title: Bookmarks1
ms.date: 03/30/2017
ms.assetid: 9b51a346-09ae-455c-a70a-e2264ddeb9e2
ms.openlocfilehash: 8b7ca9549327087e30d6c72a8b784aa37ad09f3c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33515570"
---
# <a name="bookmarks"></a><span data-ttu-id="56ee4-102">책갈피</span><span class="sxs-lookup"><span data-stu-id="56ee4-102">Bookmarks</span></span>
<span data-ttu-id="56ee4-103">책갈피는 활동이 워크플로 스레드에 그대로 유지되지 않고 입력을 수동적으로 기다릴 수 있도록 하는 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="56ee4-103">Bookmarks are the mechanism that enables an activity to passively wait for input without holding onto a workflow thread.</span></span> <span data-ttu-id="56ee4-104">활동에서 자극을 기다리고 있음을 알릴 때 책갈피를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56ee4-104">When an activity signals that it is waiting for stimulus, it can create a bookmark.</span></span> <span data-ttu-id="56ee4-105">이는 현재 실행 중인 메서드(<xref:System.Activities.Bookmark>를 만든 메서드)에서 반환되더라도 활동 실행이 완료된 것으로 간주해서는 안 된다는 것을 런타임에 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="56ee4-105">This indicates to the runtime that the activity’s execution should not be considered complete even when the currently executing method (which created the <xref:System.Activities.Bookmark>) returns.</span></span>  
  
## <a name="bookmark-basics"></a><span data-ttu-id="56ee4-106">책갈피 기본 사항</span><span class="sxs-lookup"><span data-stu-id="56ee4-106">Bookmark Basics</span></span>  
 <span data-ttu-id="56ee4-107"><xref:System.Activities.Bookmark>는 워크플로 인스턴스 내에서 실행을 다시 시작하고 입력을 전달할 수 있는 지점을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="56ee4-107">A <xref:System.Activities.Bookmark> represents a point at which execution can be resumed (and through which input can be delivered) within a workflow instance.</span></span> <span data-ttu-id="56ee4-108">일반적으로 <xref:System.Activities.Bookmark>에는 이름이 지정되며 외부(호스트 또는 확장) 코드를 사용하여 관련 데이터로 책갈피를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="56ee4-108">Typically, a <xref:System.Activities.Bookmark> is given a name and external (host or extension) code is responsible for resuming the bookmark with relevant data.</span></span> <span data-ttu-id="56ee4-109"><xref:System.Activities.Bookmark>가 다시 시작되면 워크플로 런타임은 생성 시 해당 <xref:System.Activities.BookmarkCallback>와 연결된 <xref:System.Activities.Bookmark> 대리자를 예약합니다.</span><span class="sxs-lookup"><span data-stu-id="56ee4-109">When a <xref:System.Activities.Bookmark> is resumed, the workflow runtime schedules the <xref:System.Activities.BookmarkCallback> delegate that was associated with that <xref:System.Activities.Bookmark> at the time of its creation.</span></span>  
  
## <a name="bookmark-options"></a><span data-ttu-id="56ee4-110">책갈피 옵션</span><span class="sxs-lookup"><span data-stu-id="56ee4-110">Bookmark Options</span></span>  
 <span data-ttu-id="56ee4-111"><xref:System.Activities.BookmarkOptions> 클래스는 생성되는 <xref:System.Activities.Bookmark>의 유형을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="56ee4-111">The <xref:System.Activities.BookmarkOptions> class specifies the type of <xref:System.Activities.Bookmark> being created.</span></span> <span data-ttu-id="56ee4-112">함께 사용할 수 있는 값은 <xref:System.Activities.BookmarkOptions.None>, <xref:System.Activities.BookmarkOptions.MultipleResume> 및 <xref:System.Activities.BookmarkOptions.NonBlocking>입니다.</span><span class="sxs-lookup"><span data-stu-id="56ee4-112">The possible non mutually-exclusive values are <xref:System.Activities.BookmarkOptions.None>, <xref:System.Activities.BookmarkOptions.MultipleResume>, and <xref:System.Activities.BookmarkOptions.NonBlocking>.</span></span> <span data-ttu-id="56ee4-113">정확히 한 번 다시 시작될 것으로 예상되는 <xref:System.Activities.BookmarkOptions.None>를 만들 경우 기본값인 <xref:System.Activities.Bookmark>을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="56ee4-113">Use <xref:System.Activities.BookmarkOptions.None>, the default, when creating a <xref:System.Activities.Bookmark> that is expected to be resumed exactly once.</span></span> <span data-ttu-id="56ee4-114">여러 번 다시 시작될 수 있는 <xref:System.Activities.BookmarkOptions.MultipleResume>를 만들 경우 <xref:System.Activities.Bookmark>을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="56ee4-114">Use <xref:System.Activities.BookmarkOptions.MultipleResume> when creating a <xref:System.Activities.Bookmark> that can be resumed multiple times.</span></span> <span data-ttu-id="56ee4-115">다시 시작되지 않을 <xref:System.Activities.BookmarkOptions.NonBlocking>를 만들 경우 <xref:System.Activities.Bookmark>을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="56ee4-115">Use <xref:System.Activities.BookmarkOptions.NonBlocking> when creating a <xref:System.Activities.Bookmark> that might never be resumed.</span></span> <span data-ttu-id="56ee4-116">기본 <xref:System.Activities.BookmarkOptions>를 사용하여 만든 책갈피와는 달리, <xref:System.Activities.BookmarkOptions.NonBlocking> 책갈피는 활동 완료를 제한하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="56ee4-116">Unlike bookmarks created using the default <xref:System.Activities.BookmarkOptions>, <xref:System.Activities.BookmarkOptions.NonBlocking> bookmarks do not prevent an activity from completing.</span></span>  
  
## <a name="bookmark-resumption"></a><span data-ttu-id="56ee4-117">책갈피 다시 시작</span><span class="sxs-lookup"><span data-stu-id="56ee4-117">Bookmark Resumption</span></span>  
 <span data-ttu-id="56ee4-118"><xref:System.Activities.WorkflowApplication.ResumeBookmark%2A> 오버로드 중 하나를 사용하여 워크플로 외부에서 코드를 통해 책갈피를 다시 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56ee4-118">Bookmarks can be resumed by code outside of a workflow using one of the <xref:System.Activities.WorkflowApplication.ResumeBookmark%2A> overloads.</span></span> <span data-ttu-id="56ee4-119">이 예제에서는 `ReadLine` 활동을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="56ee4-119">In this example, a `ReadLine` activity is created.</span></span> <span data-ttu-id="56ee4-120">`ReadLine` 활동이 실행되면 <xref:System.Activities.Bookmark>를 만들고 콜백을 등록한 다음 <xref:System.Activities.Bookmark>가 다시 시작될 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="56ee4-120">When executed, the `ReadLine` activity creates a <xref:System.Activities.Bookmark>, registers a callback, and then waits for the <xref:System.Activities.Bookmark> to be resumed.</span></span> <span data-ttu-id="56ee4-121">책갈피가 다시 시작되면 `ReadLine` 활동은 <xref:System.Activities.Bookmark>와 함께 전달된 데이터를 해당 <xref:System.Activities.Activity%601.Result%2A> 인수에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="56ee4-121">When it is resumed, the `ReadLine` activity assigns the data that was passed with the <xref:System.Activities.Bookmark> to its <xref:System.Activities.Activity%601.Result%2A> argument.</span></span>  
  
```csharp  
public sealed class ReadLine : NativeActivity<string>  
{  
    [RequiredArgument]  
    public  InArgument<string> BookmarkName { get; set; }  
  
    protected override void Execute(NativeActivityContext context)  
    {  
        // Create a Bookmark and wait for it to be resumed.  
        context.CreateBookmark(BookmarkName.Get(context),   
            new BookmarkCallback(OnResumeBookmark));  
    }  
  
    // NativeActivity derived activities that do asynchronous operations by calling   
    // one of the CreateBookmark overloads defined on System.Activities.NativeActivityContext   
    // must override the CanInduceIdle property and return true.  
    protected override bool CanInduceIdle  
    {  
        get { return true; }  
    }  
  
    public void OnResumeBookmark(NativeActivityContext context, Bookmark bookmark, object obj)  
    {  
        // When the Bookmark is resumed, assign its value to  
        // the Result argument.  
        Result.Set(context, (string)obj);  
    }  
}  
```  
  
 <span data-ttu-id="56ee4-122">이 예제에서는 `ReadLine` 활동을 사용하여 사용자 이름을 수집하고 콘솔 창에 표시하는 워크플로를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="56ee4-122">In this example, a workflow is created that uses the `ReadLine` activity to gather the user’s name and display it to the console window.</span></span> <span data-ttu-id="56ee4-123">호스트 응용 프로그램에서는 실제로 입력을 수집하는 작업을 수행하고 <xref:System.Activities.Bookmark>를 다시 시작하여 이를 워크플로에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="56ee4-123">The host application performs the actual work of gathering the input and passes it to the workflow by resuming the <xref:System.Activities.Bookmark>.</span></span>  
  
```csharp  
Variable<string> name = new Variable<string>  
{  
    Name = "name"  
};  
  
Activity wf = new Sequence  
{  
    Variables =  
    {  
        name  
    },  
    Activities =  
    {  
        new WriteLine()  
        {  
            Text = "What is your name?"  
        },  
        new ReadLine()  
        {  
            BookmarkName = "UserName",  
            Result = name  
        },  
        new WriteLine()  
        {  
            Text = new InArgument<string>((env) => "Hello, " + name.Get(env))  
        }  
    }  
};  
  
AutoResetEvent syncEvent = new AutoResetEvent(false);  
  
// Create the WorkflowApplication using the desired  
// workflow definition.  
WorkflowApplication wfApp = new WorkflowApplication(wf);  
  
// Handle the desired lifecycle events.  
wfApp.Completed = delegate(WorkflowApplicationCompletedEventArgs e)  
{  
    // Signal the host that the workflow is complete.  
    syncEvent.Set();  
};  
  
// Start the workflow.  
wfApp.Run();  
  
// Collect the user's name and resume the bookmark.  
// Bookmark resumption only occurs when the workflow  
// is idle. If a call to ResumeBookmark is made and the workflow  
// is not idle, ResumeBookmark blocks until the workflow becomes  
// idle before resuming the bookmark.  
wfApp.ResumeBookmark("UserName", Console.ReadLine());  
  
// Wait for Completed to arrive and signal that  
// the workflow is complete.  
syncEvent.WaitOne();  
```  
  
 <span data-ttu-id="56ee4-124">`ReadLine` 활동이 실행되면 <xref:System.Activities.Bookmark>이라는 `UserName`를 만든 다음 책갈피가 다시 시작될 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="56ee4-124">When the `ReadLine` activity is executed, it creates a <xref:System.Activities.Bookmark> named `UserName` and then waits for the bookmark to be resumed.</span></span> <span data-ttu-id="56ee4-125">호스트는 원하는 데이터를 수집한 다음 <xref:System.Activities.Bookmark>를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="56ee4-125">The host collects the desired data and then resumes the <xref:System.Activities.Bookmark>.</span></span> <span data-ttu-id="56ee4-126">워크플로가 다시 시작되고 이름을 표시한 다음 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="56ee4-126">The workflow resumes, displays the name, and then completes.</span></span> <span data-ttu-id="56ee4-127">책갈피를 다시 시작하는 데는 동기화 코드가 필요 없습니다.</span><span class="sxs-lookup"><span data-stu-id="56ee4-127">Note that no synchronization code is required with regard to resuming the bookmark.</span></span> <span data-ttu-id="56ee4-128">워크플로가 유휴 상태일 때만 <xref:System.Activities.Bookmark>를 다시 시작할 수 있습니다. 워크플로가 유휴 상태가 아닌 경우 워크플로가 유휴 상태가 될 때까지 <xref:System.Activities.WorkflowApplication.ResumeBookmark%2A>에 대한 호출이 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="56ee4-128">A <xref:System.Activities.Bookmark> can only be resumed when the workflow is idle, and if the workflow is not idle, the call to <xref:System.Activities.WorkflowApplication.ResumeBookmark%2A> blocks until the workflow becomes idle.</span></span>  
  
## <a name="bookmark-resumption-result"></a><span data-ttu-id="56ee4-129">책갈피 다시 시작 결과</span><span class="sxs-lookup"><span data-stu-id="56ee4-129">Bookmark Resumption Result</span></span>  
 <span data-ttu-id="56ee4-130"><xref:System.Activities.WorkflowApplication.ResumeBookmark%2A>에서 책갈피 다시 시작 요청의 결과를 나타내는 <xref:System.Activities.BookmarkResumptionResult> 열거형 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="56ee4-130"><xref:System.Activities.WorkflowApplication.ResumeBookmark%2A> returns a <xref:System.Activities.BookmarkResumptionResult> enumeration value to indicate the results of the bookmark resumption request.</span></span> <span data-ttu-id="56ee4-131">가능한 반환 값은 <xref:System.Activities.BookmarkResumptionResult.Success>, <xref:System.Activities.BookmarkResumptionResult.NotReady> 및 <xref:System.Activities.BookmarkResumptionResult.NotFound>입니다.</span><span class="sxs-lookup"><span data-stu-id="56ee4-131">The possible return values are <xref:System.Activities.BookmarkResumptionResult.Success>, <xref:System.Activities.BookmarkResumptionResult.NotReady>, and <xref:System.Activities.BookmarkResumptionResult.NotFound>.</span></span> <span data-ttu-id="56ee4-132">호스트 및 확장 프로그램에서는 이 값을 사용하여 진행 방법을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="56ee4-132">Hosts and extensions can use this value to determine how to proceed.</span></span>
