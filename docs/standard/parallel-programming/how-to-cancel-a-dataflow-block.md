---
title: "방법: 데이터 흐름 블록 취소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Task Parallel Library, dataflows
- dataflow blocks, canceling in TPL
- TPL dataflow library,canceling dataflow blocks
ms.assetid: fbddda0d-da3b-4ec8-a1d6-67ab8573fcd7
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4d6fbde31cd4b4b5d0c6404b8baf23230f2bda77
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-cancel-a-dataflow-block"></a><span data-ttu-id="4e464-102">방법: 데이터 흐름 블록 취소</span><span class="sxs-lookup"><span data-stu-id="4e464-102">How to: Cancel a Dataflow Block</span></span>
<span data-ttu-id="4e464-103">이 문서에서는 응용 프로그램에서 취소를 사용하도록 설정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4e464-103">This document demonstrates how to enable cancellation in your application.</span></span> <span data-ttu-id="4e464-104">이 예제에서는 Windows Forms를 사용하여 데이터 흐름 파이프라인에서 작업 항목이 활성 상태인 위치뿐만 아니라 취소의 효과도 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4e464-104">This example uses Windows Forms to show where work items are active in a dataflow pipeline and also the effects of cancellation.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="4e464-105">TPL 데이터 흐름 라이브러리(<xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType> 네임스페이스)는 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]와 함께 배포되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4e464-105">The TPL Dataflow Library (<xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType> namespace) is not distributed with the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span></span> <span data-ttu-id="4e464-106">설치 하는 <xref:System.Threading.Tasks.Dataflow> 네임 스페이스에서 프로젝트를 열고 [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], 선택 **NuGet 패키지 관리** 프로젝트 메뉴에 대 한 온라인 검색에서는 `Microsoft.Tpl.Dataflow` 패키지 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e464-106">To install the <xref:System.Threading.Tasks.Dataflow> namespace, open your project in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], choose **Manage NuGet Packages** from the Project menu, and search online for the `Microsoft.Tpl.Dataflow` package.</span></span>  
  
### <a name="to-create-the-windows-forms-application"></a><span data-ttu-id="4e464-107">Windows Forms 응용 프로그램을 만들려면</span><span class="sxs-lookup"><span data-stu-id="4e464-107">To Create the Windows Forms Application</span></span>  
  
1.  <span data-ttu-id="4e464-108">C# 또는 Visual Basic **Windows Forms 응용 프로그램** 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4e464-108">Create a C# or Visual Basic **Windows Forms Application** project.</span></span> <span data-ttu-id="4e464-109">다음 단계에서 프로젝트의 이름은 `CancellationWinForms`입니다.</span><span class="sxs-lookup"><span data-stu-id="4e464-109">In the following steps, the project is named `CancellationWinForms`.</span></span>  
  
2.  <span data-ttu-id="4e464-110">기본 폼인 Form1.cs의 폼 디자이너에서 (Form1.vb [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]), 추가 <xref:System.Windows.Forms.ToolStrip> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e464-110">On the form designer for the main form, Form1.cs (Form1.vb for [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]), add a <xref:System.Windows.Forms.ToolStrip> control.</span></span>  
  
3.  <span data-ttu-id="4e464-111">추가 <xref:System.Windows.Forms.ToolStripButton> 컨트롤을 <xref:System.Windows.Forms.ToolStrip> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e464-111">Add a <xref:System.Windows.Forms.ToolStripButton> control to the <xref:System.Windows.Forms.ToolStrip> control.</span></span> <span data-ttu-id="4e464-112">설정의 <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> 속성을 <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> 및 <xref:System.Windows.Forms.ToolStripItem.Text%2A> 속성을 **작업 항목 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="4e464-112">Set the <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> property to <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text> and the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property to **Add Work Items**.</span></span>  
  
4.  <span data-ttu-id="4e464-113">두 번째 추가 <xref:System.Windows.Forms.ToolStripButton> 컨트롤을 <xref:System.Windows.Forms.ToolStrip> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e464-113">Add a second <xref:System.Windows.Forms.ToolStripButton> control to the <xref:System.Windows.Forms.ToolStrip> control.</span></span> <span data-ttu-id="4e464-114">설정의 <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> 속성을 <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text>, <xref:System.Windows.Forms.ToolStripItem.Text%2A> 속성을 **취소**, 및 <xref:System.Windows.Forms.ToolStripItem.Enabled%2A> 속성을 `False`합니다.</span><span class="sxs-lookup"><span data-stu-id="4e464-114">Set the <xref:System.Windows.Forms.ToolStripItem.DisplayStyle%2A> property to <xref:System.Windows.Forms.ToolStripItemDisplayStyle.Text>, the <xref:System.Windows.Forms.ToolStripItem.Text%2A> property to **Cancel**, and the <xref:System.Windows.Forms.ToolStripItem.Enabled%2A> property to `False`.</span></span>  
  
5.  <span data-ttu-id="4e464-115">4 개 추가 <xref:System.Windows.Forms.ToolStripProgressBar> 개체는 <xref:System.Windows.Forms.ToolStrip> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e464-115">Add four <xref:System.Windows.Forms.ToolStripProgressBar> objects to the <xref:System.Windows.Forms.ToolStrip> control.</span></span>  
  
## <a name="creating-the-dataflow-pipeline"></a><span data-ttu-id="4e464-116">데이터 흐름 파이프라인 만들기</span><span class="sxs-lookup"><span data-stu-id="4e464-116">Creating the Dataflow Pipeline</span></span>  
 <span data-ttu-id="4e464-117">이 섹션에서는 작업 항목을 처리하고 진행률 표시줄을 업데이트하는 데이터 흐름 파이프라인을 만드는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4e464-117">This section describes how to create the dataflow pipeline that processes work items and updates the progress bars.</span></span>  
  
#### <a name="to-create-the-dataflow-pipeline"></a><span data-ttu-id="4e464-118">데이터 흐름 파이프라인을 만들려면</span><span class="sxs-lookup"><span data-stu-id="4e464-118">To Create the Dataflow Pipeline</span></span>  
  
1.  <span data-ttu-id="4e464-119">프로젝트에서 System.Threading.Tasks.Dataflow.dll에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4e464-119">In your project, add a reference to System.Threading.Tasks.Dataflow.dll.</span></span>  
  
2.  <span data-ttu-id="4e464-120">Form1.cs([!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]에서는 Form1.vb)에 다음 `using`(`Imports`에서는 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) 문이 포함되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4e464-120">Ensure that Form1.cs (Form1.vb for [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) contains the following `using` statements (`Imports` in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]).</span></span>  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#1)]
     [!code-vb[TPLDataflow_CancellationWinForms#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#1)]  
  
3.  <span data-ttu-id="4e464-121">`WorkItem` 클래스를 `Form1` 클래스의 내부 형식으로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4e464-121">Add the `WorkItem` class as an inner type of the `Form1` class.</span></span>  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#2)]
     [!code-vb[TPLDataflow_CancellationWinForms#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#2)]  
  
4.  <span data-ttu-id="4e464-122">`Form1` 클래스에 다음 데이터 멤버를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4e464-122">Add the following data members to the `Form1` class.</span></span>  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#3)]
     [!code-vb[TPLDataflow_CancellationWinForms#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#3)]  
  
5.  <span data-ttu-id="4e464-123">다음 `CreatePipeline` 메서드를 `Form1` 클래스에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4e464-123">Add the following method, `CreatePipeline`, to the `Form1` class.</span></span>  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#4)]
     [!code-vb[TPLDataflow_CancellationWinForms#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#4)]  
  
 <span data-ttu-id="4e464-124">`incrementProgress` 및 `decrementProgress` 데이터 흐름 블록이 사용자 인터페이스에서 작동하기 때문에 이러한 작업은 사용자 인터페이스 스레드에서 발생해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e464-124">Because the `incrementProgress` and `decrementProgress` dataflow blocks act on the user interface, it is important that these actions occur on the user-interface thread.</span></span> <span data-ttu-id="4e464-125">이를 위해 생성 되는 동안 각 제공 이러한 개체는 <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions> 있는 개체는 <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.TaskScheduler%2A> 속성이로 설정 <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="4e464-125">To accomplish this, during construction these objects each provide a <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions> object that has the <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.TaskScheduler%2A> property set to <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="4e464-126"><xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType> 메서드는 현재 동기화 컨텍스트에서 작업을 수행하는 <xref:System.Threading.Tasks.TaskScheduler> 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4e464-126">The <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType> method creates a <xref:System.Threading.Tasks.TaskScheduler> object that performs work on the current synchronization context.</span></span> <span data-ttu-id="4e464-127">`Form1` 생성자가 사용자 인터페이스 스레드에서 호출되기 때문에 `incrementProgress` 및 `decrementProgress` 데이터 흐름 블록에 대한 작업도 사용자 인터페이스 스레드에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e464-127">Because the `Form1` constructor is called from the user-interface thread, the actions for the `incrementProgress` and `decrementProgress` dataflow blocks also run on the user-interface thread.</span></span>  
  
 <span data-ttu-id="4e464-128">설정 하는이 예제는 <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> 파이프라인의 멤버를 만들 때 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="4e464-128">This example sets the <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> property when it constructs the members of the pipeline.</span></span> <span data-ttu-id="4e464-129">때문에 <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> 속성은 영구적으로 데이터 흐름 블록 실행을 취소, 사용자가 작업을 취소 하 고 파이프라인에 작업 항목을 더 추가 하려는 후 전체 파이프라인을 다시 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4e464-129">Because the <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.CancellationToken%2A> property permanently cancels dataflow block execution, the whole pipeline must be recreated after the user cancels the operation and then wants to add more work items to the pipeline.</span></span> <span data-ttu-id="4e464-130">작업이 취소된 후 다른 작업을 수행할 수 있도록 데이터 흐름 블록을 취소하는 대체 방법을 보여 주는 예제는 [연습: Windows Forms 응용 프로그램에서 데이터 흐름 사용](../../../docs/standard/parallel-programming/walkthrough-using-dataflow-in-a-windows-forms-application.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4e464-130">For an example that demonstrates an alternative way to cancel a dataflow block so that other work can be performed after an operation is canceled, see [Walkthrough: Using Dataflow in a Windows Forms Application](../../../docs/standard/parallel-programming/walkthrough-using-dataflow-in-a-windows-forms-application.md).</span></span>  
  
## <a name="connecting-the-dataflow-pipeline-to-the-user-interface"></a><span data-ttu-id="4e464-131">사용자 인터페이스에 데이터 흐름 파이프라인 연결</span><span class="sxs-lookup"><span data-stu-id="4e464-131">Connecting the Dataflow Pipeline to the User Interface</span></span>  
 <span data-ttu-id="4e464-132">이 섹션에서는 사용자 인터페이스에 데이터 흐름 파이프라인을 연결하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4e464-132">This section describes how to connect the dataflow pipeline to the user interface.</span></span> <span data-ttu-id="4e464-133">파이프라인을 만들고 파이프라인에 작업 항목을 추가하는 작업은 모두 **작업 항목 추가** 단추의 이벤트 처리기에서 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e464-133">Both creating the pipeline and adding work items to the pipeline are controlled by the event handler for the **Add Work Items** button.</span></span> <span data-ttu-id="4e464-134">취소는 **취소** 단추를 클릭하면 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e464-134">Cancellation is initiated by the **Cancel** button.</span></span> <span data-ttu-id="4e464-135">사용자가 이러한 단추 중 하나를 클릭하면 적절한 작업이 비동기식으로 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e464-135">When the user clicks either of these buttons, the appropriate action is initiated in an asynchronous manner.</span></span>  
  
#### <a name="to-connect-the-dataflow-pipeline-to-the-user-interface"></a><span data-ttu-id="4e464-136">사용자 인터페이스에 데이터 흐름 파이프라인을 연결하려면</span><span class="sxs-lookup"><span data-stu-id="4e464-136">To Connect the Dataflow Pipeline to the User Interface</span></span>  
  
1.  <span data-ttu-id="4e464-137">기본 폼의 폼 디자이너에서에 대 한 이벤트 처리기를 만들고는 <xref:System.Windows.Forms.ToolStripItem.Click> 에 대 한 이벤트는 **작업 항목 추가** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="4e464-137">On the form designer for the main form, create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event for the **Add Work Items** button.</span></span>  
  
2.  <span data-ttu-id="4e464-138">구현 된 <xref:System.Windows.Forms.ToolStripItem.Click> 에 대 한 이벤트는 **작업 항목 추가** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="4e464-138">Implement the <xref:System.Windows.Forms.ToolStripItem.Click> event for the **Add Work Items** button.</span></span>  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#5)]
     [!code-vb[TPLDataflow_CancellationWinForms#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#5)]  
  
3.  <span data-ttu-id="4e464-139">기본 폼의 폼 디자이너에서에 대 한 이벤트 처리기를 만들고는 <xref:System.Windows.Forms.ToolStripItem.Click> 에 대 한 이벤트 처리기는 **취소** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="4e464-139">On the form designer for the main form, create an event handler for the <xref:System.Windows.Forms.ToolStripItem.Click> event handler for the **Cancel** button.</span></span>  
  
4.  <span data-ttu-id="4e464-140">구현 된 <xref:System.Windows.Forms.ToolStripItem.Click> 에 대 한 이벤트 처리기는 **취소** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="4e464-140">Implement the <xref:System.Windows.Forms.ToolStripItem.Click> event handler for the **Cancel** button.</span></span>  
  
     [!code-csharp[TPLDataflow_CancellationWinForms#6](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#6)]
     [!code-vb[TPLDataflow_CancellationWinForms#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#6)]  
  
## <a name="example"></a><span data-ttu-id="4e464-141">예제</span><span class="sxs-lookup"><span data-stu-id="4e464-141">Example</span></span>  
 <span data-ttu-id="4e464-142">다음 예제에서는 Form1.cs([!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]에서는 Form1.vb)의 전체 코드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4e464-142">The following example shows the complete code for Form1.cs (Form1.vb for [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]).</span></span>  
  
 [!code-csharp[TPLDataflow_CancellationWinForms#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_cancellationwinforms/cs/cancellationwinforms/form1.cs#100)]
 [!code-vb[TPLDataflow_CancellationWinForms#100](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_cancellationwinforms/vb/cancellationwinforms/form1.vb#100)]  
  
 <span data-ttu-id="4e464-143">다음 그림에서는 실행 중인 응용 프로그램을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4e464-143">The following illustration shows the running application.</span></span>  
  
 <span data-ttu-id="4e464-144">![Windows Forms 응용 프로그램](../../../docs/standard/parallel-programming/media/tpldataflow-cancellation.png "TPLDataflow_Cancellation")</span><span class="sxs-lookup"><span data-stu-id="4e464-144">![The Windows Forms Application](../../../docs/standard/parallel-programming/media/tpldataflow-cancellation.png "TPLDataflow_Cancellation")</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="4e464-145">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="4e464-145">Robust Programming</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e464-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4e464-146">See Also</span></span>  
 [<span data-ttu-id="4e464-147">데이터 흐름</span><span class="sxs-lookup"><span data-stu-id="4e464-147">Dataflow</span></span>](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
