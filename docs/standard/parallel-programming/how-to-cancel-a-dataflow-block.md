---
title: '방법: 데이터 흐름 블록 취소'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Task Parallel Library, dataflows
- dataflow blocks, canceling in TPL
- TPL dataflow library,canceling dataflow blocks
ms.assetid: fbddda0d-da3b-4ec8-a1d6-67ab8573fcd7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2684473f82eb156bf8762c9797503324f318632d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-cancel-a-dataflow-block"></a><span data-ttu-id="ca91c-102">방법: 데이터 흐름 블록 취소</span><span class="sxs-lookup"><span data-stu-id="ca91c-102">How to: Cancel a Dataflow Block</span></span>
<span data-ttu-id="ca91c-103">이 문서에서는 응용 프로그램에서 취소를 사용하도록 설정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ca91c-103">This document demonstrates how to enable cancellation in your application.</span></span> <span data-ttu-id="ca91c-104">이 예제에서는 Windows Forms를 사용하여 데이터 흐름 파이프라인에서 작업 항목이 활성 상태인 위치뿐만 아니라 취소의 효과도 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ca91c-104">This example uses Windows Forms to show where work items are active in a dataflow pipeline and also the effects of cancellation.</span></span>  

[!INCLUDE [tpl-install-instructions](../../../includes/tpl-install-instructions.md)]
  
## <a name="to-create-the-windows-forms-application"></a><span data-ttu-id="ca91c-105">Windows Forms 응용 프로그램을 만들려면</span><span class="sxs-lookup"><span data-stu-id="ca91c-105">To Create the Windows Forms Application</span></span>  
  
1.  <span data-ttu-id="ca91c-106">C# 또는 Visual Basic **Windows Forms 응용 프로그램** 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ca91c-106">Create a C# or Visual Basic **Windows Forms Application** project.</span></span> <span data-ttu-id="ca91c-107">다음 단계에서 프로젝트의 이름은 `CancellationWinForms`입니다.</span><span class="sxs-lookup"><span data-stu-id="ca91c-107">In the following steps, the project is named `CancellationWinForms`.</span></span>  
  
2.  <span data-ttu-id="ca91c-108">기본 폼인 Form1.cs(Visual Basic에서는 Form1.vb)의 폼 디자이너에서 <xref:System.Windows.Forms.ToolStrip> 컨트롤을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ca91c-108">On the form designer for the main form, Form1.cs (Form1.vb for Visual Basic), add a <xref:System.Windows.Forms.ToolStrip> control.</span></span>  
  
3.  <span data-ttu-id="ca91c-109"><xref:System.Windows.Forms.ToolStripButton> 컨트롤을 <xref:System.Windows.Forms.ToolStrip> 컨트롤에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ca91c-109">Add a <xref:System.Windows.Forms.ToolStripButton> control to the <xref:System.Windows.Forms.ToolStrip> control.</span></span> <span data-ttu-id="ca91c-110"><xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> 속성을 <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> 및 <xref:System.Windows.Forms.ToolStripItem.Text%2A> 속성으로 설정하여 **작업 항목을 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="ca91c-110">Set the <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> property to <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> and the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property to **Add Work Items**.</span></span>  
  
4.  <span data-ttu-id="ca91c-111">두 번째 <xref:System.Windows.Forms.ToolStripButton> 컨트롤을 <xref:System.Windows.Forms.ToolStrip> 컨트롤에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ca91c-111">Add a second <xref:System.Windows.Forms.ToolStripButton> control to the <xref:System.Windows.Forms.ToolStrip> control.</span></span> <span data-ttu-id="ca91c-112"><xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> 속성을 <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text>로 설정하고, <xref:System.Windows.Forms.ToolStripItem.Text%2A> 속성을 **취소**로 설정하고, <xref:System.Windows.Forms.ToolStripItem.Enabled%2A> 속성을 `False`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ca91c-112">Set the <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> property to <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text>, the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property to **Cancel**, and the <xref:System.Windows.Forms.ToolStripItem.Enabled%2A> property to `False`.</span></span>  
  
5.  <span data-ttu-id="ca91c-113">4개의 <xref:System.Windows.Forms.ToolStripProgressBar> 개체를 <xref:System.Windows.Forms.ToolStrip> 컨트롤에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ca91c-113">Add four <xref:System.Windows.Forms.ToolStripProgressBar> objects to the <xref:System.Windows.Forms.ToolStrip> control.</span></span>  
  
## <a name="creating-the-dataflow-pipeline"></a><span data-ttu-id="ca91c-114">데이터 흐름 파이프라인 만들기</span><span class="sxs-lookup"><span data-stu-id="ca91c-114">Creating the Dataflow Pipeline</span></span>  
 <span data-ttu-id="ca91c-115">이 섹션에서는 작업 항목을 처리하고 진행률 표시줄을 업데이트하는 데이터 흐름 파이프라인을 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ca91c-115">This section describes how to create the dataflow pipeline that processes work items and updates the progress bars.</span></span>  
  
### <a name="to-create-the-dataflow-pipeline"></a><span data-ttu-id="ca91c-116">데이터 흐름 파이프라인을 만들려면</span><span class="sxs-lookup"><span data-stu-id="ca91c-116">To Create the Dataflow Pipeline</span></span>  
  
1.  <span data-ttu-id="ca91c-117">프로젝트에서 System.Threading.Tasks.Dataflow.dll에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ca91c-117">In your project, add a reference to System.Threading.Tasks.Dataflow.dll.</span></span>  
  
2.  <span data-ttu-id="ca91c-118">Form1.cs(Visual Basic에서는 Form1.vb)에 다음 `using` 명령문(Visual Basic에서는 `Imports`)이 포함되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ca91c-118">Ensure that Form1.cs (Form1.vb for Visual Basic) contains the following `using` statements (`Imports` in Visual Basic).</span></span>  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#1)]
     [!code-vb[TPLDataflow_CancellationWinForms#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#1)]  
  
3.  <span data-ttu-id="ca91c-119">`WorkItem` 클래스를 `Form1` 클래스의 내부 형식으로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ca91c-119">Add the `WorkItem` class as an inner type of the `Form1` class.</span></span>  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#2)]
     [!code-vb[TPLDataflow_CancellationWinForms#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#2)]  
  
4.  <span data-ttu-id="ca91c-120">`Form1` 클래스에 다음 데이터 멤버를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ca91c-120">Add the following data members to the `Form1` class.</span></span>  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#3)]
     [!code-vb[TPLDataflow_CancellationWinForms#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#3)]  
  
5.  <span data-ttu-id="ca91c-121">다음 `CreatePipeline` 메서드를 `Form1` 클래스에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ca91c-121">Add the following method, `CreatePipeline`, to the `Form1` class.</span></span>  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#4)]
     [!code-vb[TPLDataflow_CancellationWinForms#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#4)]  
  
 <span data-ttu-id="ca91c-122">`incrementProgress` 및 `decrementProgress` 데이터 흐름 블록이 사용자 인터페이스에서 작동하기 때문에 이러한 작업은 사용자 인터페이스 스레드에서 발생해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca91c-122">Because the `incrementProgress` and `decrementProgress` dataflow blocks act on the user interface, it is important that these actions occur on the user-interface thread.</span></span> <span data-ttu-id="ca91c-123">이를 위해 생성 중에 이러한 개체는 각각 <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.TaskScheduler%2A> 속성이 <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType>로 설정된 <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions> 개체를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ca91c-123">To accomplish this, during construction these objects each provide a <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions> object that has the <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.TaskScheduler%2A> property set to <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="ca91c-124"><xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType> 메서드는 현재 동기화 컨텍스트에서 작업을 수행하는 <xref:System.Threading.Tasks.TaskScheduler> 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ca91c-124">The <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType> method creates a <xref:System.Threading.Tasks.TaskScheduler> object that performs work on the current synchronization context.</span></span> <span data-ttu-id="ca91c-125">`Form1` 생성자가 사용자 인터페이스 스레드에서 호출되기 때문에 `incrementProgress` 및 `decrementProgress` 데이터 흐름 블록에 대한 작업도 사용자 인터페이스 스레드에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca91c-125">Because the `Form1` constructor is called from the user-interface thread, the actions for the `incrementProgress` and `decrementProgress` dataflow blocks also run on the user-interface thread.</span></span>  
  
 <span data-ttu-id="ca91c-126">이 예제에서는 파이프라인의 멤버를 생성할 때 <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ca91c-126">This example sets the <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> property when it constructs the members of the pipeline.</span></span> <span data-ttu-id="ca91c-127"><xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> 속성은 데이터 흐름 블록 실행을 영구적으로 취소하므로 사용자가 작업을 취소한 다음, 파이프라인에 더 많은 작업 항목을 추가하기를 원하면 전체 파이프라인을 다시 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca91c-127">Because the <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> property permanently cancels dataflow block execution, the whole pipeline must be recreated after the user cancels the operation and then wants to add more work items to the pipeline.</span></span> <span data-ttu-id="ca91c-128">작업이 취소된 후 다른 작업을 수행할 수 있도록 데이터 흐름 블록을 취소하는 대체 방법을 보여 주는 예제는 [연습: Windows Forms 응용 프로그램에서 데이터 흐름 사용](../../../docs/standard/parallel-programming/walkthrough-using-dataflow-in-a-windows-forms-application.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ca91c-128">For an example that demonstrates an alternative way to cancel a dataflow block so that other work can be performed after an operation is canceled, see [Walkthrough: Using Dataflow in a Windows Forms Application](../../../docs/standard/parallel-programming/walkthrough-using-dataflow-in-a-windows-forms-application.md).</span></span>  
  
## <a name="connecting-the-dataflow-pipeline-to-the-user-interface"></a><span data-ttu-id="ca91c-129">사용자 인터페이스에 데이터 흐름 파이프라인 연결</span><span class="sxs-lookup"><span data-stu-id="ca91c-129">Connecting the Dataflow Pipeline to the User Interface</span></span>  
 <span data-ttu-id="ca91c-130">이 섹션에서는 사용자 인터페이스에 데이터 흐름 파이프라인을 연결하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ca91c-130">This section describes how to connect the dataflow pipeline to the user interface.</span></span> <span data-ttu-id="ca91c-131">파이프라인을 만들고 파이프라인에 작업 항목을 추가하는 작업은 모두 **작업 항목 추가** 단추의 이벤트 처리기에서 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca91c-131">Both creating the pipeline and adding work items to the pipeline are controlled by the event handler for the **Add Work Items** button.</span></span> <span data-ttu-id="ca91c-132">취소는 **취소** 단추를 클릭하면 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca91c-132">Cancellation is initiated by the **Cancel** button.</span></span> <span data-ttu-id="ca91c-133">사용자가 이러한 단추 중 하나를 클릭하면 적절한 작업이 비동기식으로 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca91c-133">When the user clicks either of these buttons, the appropriate action is initiated in an asynchronous manner.</span></span>  
  
### <a name="to-connect-the-dataflow-pipeline-to-the-user-interface"></a><span data-ttu-id="ca91c-134">사용자 인터페이스에 데이터 흐름 파이프라인을 연결하려면</span><span class="sxs-lookup"><span data-stu-id="ca91c-134">To Connect the Dataflow Pipeline to the User Interface</span></span>  
  
1.  <span data-ttu-id="ca91c-135">기본 폼의 폼 디자이너에서 **작업 항목 추가** 단추에 대한 <xref:System.Windows.Forms.ToolStripItem.Click> 이벤트의 이벤트 처리기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ca91c-135">On the form designer for the main form, create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event for the **Add Work Items** button.</span></span>  
  
2.  <span data-ttu-id="ca91c-136">**작업 항목 추가** 단추에 대한 <xref:System.Windows.Forms.ToolStripItem.Click> 이벤트를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="ca91c-136">Implement the <xref:System.Windows.Forms.ToolStripItem.Click> event for the **Add Work Items** button.</span></span>  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#5)]
     [!code-vb[TPLDataflow_CancellationWinForms#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#5)]  
  
3.  <span data-ttu-id="ca91c-137">기본 폼의 폼 디자이너에서 **취소** 단추에 대한 <xref:System.Windows.Forms.ToolStripItem.Click> 이벤트 처리기의 이벤트 처리기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ca91c-137">On the form designer for the main form, create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event handler for the **Cancel** button.</span></span>  
  
4.  <span data-ttu-id="ca91c-138">**취소** 단추에 대한 <xref:System.Windows.Forms.ToolStripItem.Click> 이벤트 처리기를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="ca91c-138">Implement the <xref:System.Windows.Forms.ToolStripItem.Click> event handler for the **Cancel** button.</span></span>  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#6](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#6)]
     [!code-vb[TPLDataflow_CancellationWinForms#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#6)]  
  
## <a name="example"></a><span data-ttu-id="ca91c-139">예</span><span class="sxs-lookup"><span data-stu-id="ca91c-139">Example</span></span>  
 <span data-ttu-id="ca91c-140">다음 예제에서는 Form1.cs(Visual Basic에서는 Form1.vb)의 전체 코드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ca91c-140">The following example shows the complete code for Form1.cs (Form1.vb for Visual Basic).</span></span>  
  
 [!code-csharp[TPLDataflow_CancellationWinForms#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#100)]
 [!code-vb[TPLDataflow_CancellationWinForms#100](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#100)]  
  
 <span data-ttu-id="ca91c-141">다음 그림에서는 실행 중인 응용 프로그램을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ca91c-141">The following illustration shows the running application.</span></span>  
  
 <span data-ttu-id="ca91c-142">![Windows Forms 응용 프로그램](../../../docs/standard/parallel-programming/media/tpldataflow-cancellation.png "TPLDataflow_Cancellation")</span><span class="sxs-lookup"><span data-stu-id="ca91c-142">![The Windows Forms Application](../../../docs/standard/parallel-programming/media/tpldataflow-cancellation.png "TPLDataflow_Cancellation")</span></span>  

## <a name="see-also"></a><span data-ttu-id="ca91c-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ca91c-143">See Also</span></span>  
 [<span data-ttu-id="ca91c-144">데이터 흐름</span><span class="sxs-lookup"><span data-stu-id="ca91c-144">Dataflow</span></span>](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
