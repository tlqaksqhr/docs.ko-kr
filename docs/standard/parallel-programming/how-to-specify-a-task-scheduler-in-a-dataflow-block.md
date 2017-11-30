---
title: "방법: 데이터 흐름 블록의 작업 Scheduler 지정"
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
- TPL dataflow library, linking to task scheduler in TPL
- Task Parallel Library, dataflows
- task scheduler, linking from TPL
ms.assetid: 27ece374-ed5b-49ef-9cec-b20db34a65e8
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 20faebc8bda3b50c4f762615d84b7a449ae61c6f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-specify-a-task-scheduler-in-a-dataflow-block"></a><span data-ttu-id="98b3e-102">방법: 데이터 흐름 블록의 작업 Scheduler 지정</span><span class="sxs-lookup"><span data-stu-id="98b3e-102">How to: Specify a Task Scheduler in a Dataflow Block</span></span>
<span data-ttu-id="98b3e-103">이 문서에서는 응용 프로그램에서 데이터 흐름을 사용하는 경우 특정 작업 스케줄러를 연결하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="98b3e-103">This document demonstrates how to associate a specific task scheduler when you use dataflow in your application.</span></span> <span data-ttu-id="98b3e-104">예제에서는 Windows Forms 응용 프로그램에서 <xref:System.Threading.Tasks.ConcurrentExclusiveSchedulerPair?displayProperty=nameWithType> 클래스를 사용하여 판독기 작업이 활성화된 경우와 작성기 작업이 활성화된 경우를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="98b3e-104">The example uses the <xref:System.Threading.Tasks.ConcurrentExclusiveSchedulerPair?displayProperty=nameWithType> class in a Windows Forms application to show when reader tasks are active and when a writer task is active.</span></span> <span data-ttu-id="98b3e-105">또한 <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType> 메서드를 사용하여 데이터 흐름 블록이 사용자 인터페이스 스레드에서 실행될 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="98b3e-105">It also uses the <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType> method to enable a dataflow block to run on the user-interface thread.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="98b3e-106">TPL 데이터 흐름 라이브러리(<xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType> 네임스페이스)는 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]와 함께 배포되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="98b3e-106">The TPL Dataflow Library (<xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType> namespace) is not distributed with the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span></span> <span data-ttu-id="98b3e-107">설치 하는 <xref:System.Threading.Tasks.Dataflow> 네임 스페이스에서 프로젝트를 열고 [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], 선택 **NuGet 패키지 관리** 프로젝트 메뉴에 대 한 온라인 검색에서는 `Microsoft.Tpl.Dataflow` 패키지 합니다.</span><span class="sxs-lookup"><span data-stu-id="98b3e-107">To install the <xref:System.Threading.Tasks.Dataflow> namespace, open your project in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], choose **Manage NuGet Packages** from the Project menu, and search online for the `Microsoft.Tpl.Dataflow` package.</span></span>  
  
### <a name="to-create-the-windows-forms-application"></a><span data-ttu-id="98b3e-108">Windows Forms 응용 프로그램을 만들려면</span><span class="sxs-lookup"><span data-stu-id="98b3e-108">To Create the Windows Forms Application</span></span>  
  
1.  <span data-ttu-id="98b3e-109">만들기는 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)] 또는 Visual Basic **Windows Forms 응용 프로그램** 프로젝트.</span><span class="sxs-lookup"><span data-stu-id="98b3e-109">Create a [!INCLUDE[csprcs](../../../includes/csprcs-md.md)] or Visual Basic **Windows Forms Application** project.</span></span> <span data-ttu-id="98b3e-110">다음 단계에서 프로젝트의 이름은 `WriterReadersWinForms`입니다.</span><span class="sxs-lookup"><span data-stu-id="98b3e-110">In the following steps, the project is named `WriterReadersWinForms`.</span></span>  
  
2.  <span data-ttu-id="98b3e-111">기본 폼인 Form1.cs([!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]에서는 Form1.vb)의 폼 디자이너에서 네 가지 <xref:System.Windows.Forms.CheckBox> 컨트롤을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="98b3e-111">On the form designer for the main form, Form1.cs (Form1.vb for [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]), add four <xref:System.Windows.Forms.CheckBox> controls.</span></span> <span data-ttu-id="98b3e-112">설정의 <xref:System.Windows.Forms.Control.Text%2A> 속성을 **Reader 1** 에 대 한 `checkBox1`, **Reader 2** 에 대 한 `checkBox2`, **Reader 3** 에 대 한 `checkBox3`, 및  **기록기** 에 대 한 `checkBox4`합니다.</span><span class="sxs-lookup"><span data-stu-id="98b3e-112">Set the <xref:System.Windows.Forms.Control.Text%2A> property to **Reader 1** for `checkBox1`, **Reader 2** for `checkBox2`, **Reader 3** for `checkBox3`, and **Writer** for `checkBox4`.</span></span> <span data-ttu-id="98b3e-113">각 컨트롤의 <xref:System.Windows.Forms.Control.Enabled%2A> 속성을 `False`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="98b3e-113">Set the <xref:System.Windows.Forms.Control.Enabled%2A> property for each control to `False`.</span></span>  
  
3.  <span data-ttu-id="98b3e-114">폼에 <xref:System.Windows.Forms.Timer> 컨트롤을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="98b3e-114">Add a <xref:System.Windows.Forms.Timer> control to the form.</span></span> <span data-ttu-id="98b3e-115"><xref:System.Windows.Forms.Timer.Interval%2A> 속성을 `2500`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="98b3e-115">Set the <xref:System.Windows.Forms.Timer.Interval%2A> property to `2500`.</span></span>  
  
## <a name="adding-dataflow-functionality"></a><span data-ttu-id="98b3e-116">데이터 흐름 기능 추가</span><span class="sxs-lookup"><span data-stu-id="98b3e-116">Adding Dataflow Functionality</span></span>  
 <span data-ttu-id="98b3e-117">이 단원에서는 응용 프로그램에 참여하는 데이터 흐름 블록을 만드는 방법과 각 데이터 흐름 블록을 작업 스케줄러와 연결하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="98b3e-117">This section describes how to create the dataflow blocks that participate in the application and how to associate each one with a task scheduler.</span></span>  
  
#### <a name="to-add-dataflow-functionality-to-the-application"></a><span data-ttu-id="98b3e-118">응용 프로그램에 데이터 흐름 기능을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="98b3e-118">To Add Dataflow Functionality to the Application</span></span>  
  
1.  <span data-ttu-id="98b3e-119">프로젝트에서 System.Threading.Tasks.Dataflow.dll에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="98b3e-119">In your project, add a reference to System.Threading.Tasks.Dataflow.dll.</span></span>  
  
2.  <span data-ttu-id="98b3e-120">Form1.cs([!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]에서는 Form1.vb)에 다음 `using`(`Imports`에서는 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) 문이 포함되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="98b3e-120">Ensure that Form1.cs (Form1.vb for [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) contains the following `using` statements (`Imports` in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]).</span></span>  
  
     [!code-csharp[TPLDataflow_WriterReadersWinForms#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/cs/writerreaderswinforms/form1.cs#1)]
     [!code-vb[TPLDataflow_WriterReadersWinForms#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/vb/writerreaderswinforms/form1.vb#1)]  
  
3.  <span data-ttu-id="98b3e-121"><xref:System.Threading.Tasks.Dataflow.BroadcastBlock%601> 클래스에 `Form1` 데이터 멤버를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="98b3e-121">Add a <xref:System.Threading.Tasks.Dataflow.BroadcastBlock%601> data member to the `Form1` class.</span></span>  
  
     [!code-csharp[TPLDataflow_WriterReadersWinForms#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/cs/writerreaderswinforms/form1.cs#2)]
     [!code-vb[TPLDataflow_WriterReadersWinForms#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/vb/writerreaderswinforms/form1.vb#2)]  
  
4.  <span data-ttu-id="98b3e-122">`Form1` 생성자에서 `InitializeComponent`를 호출한 후 <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> 개체의 상태를 전환하는 <xref:System.Windows.Forms.CheckBox> 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="98b3e-122">In the `Form1` constructor, after the call to `InitializeComponent`, create an <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> object that toggles the state of <xref:System.Windows.Forms.CheckBox> objects.</span></span>  
  
     [!code-csharp[TPLDataflow_WriterReadersWinForms#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/cs/writerreaderswinforms/form1.cs#3)]
     [!code-vb[TPLDataflow_WriterReadersWinForms#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/vb/writerreaderswinforms/form1.vb#3)]  
  
5.  <span data-ttu-id="98b3e-123">`Form1` 생성자에서 <xref:System.Threading.Tasks.ConcurrentExclusiveSchedulerPair> 개체와 4개의 <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> 개체를 만듭니다. 이때 각 <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> 개체에 대해 <xref:System.Windows.Forms.CheckBox> 개체를 하나씩 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="98b3e-123">In the `Form1` constructor, create a <xref:System.Threading.Tasks.ConcurrentExclusiveSchedulerPair> object and four <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> objects, one <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> object for each <xref:System.Windows.Forms.CheckBox> object.</span></span> <span data-ttu-id="98b3e-124">각 <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> 개체에 대해 <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions> 속성이 판독기의 경우 <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.TaskScheduler%2A> 속성으로 설정되고 작성기의 경우 <xref:System.Threading.Tasks.ConcurrentExclusiveSchedulerPair.ConcurrentScheduler%2A> 속성으로 설정된 <xref:System.Threading.Tasks.ConcurrentExclusiveSchedulerPair.ExclusiveScheduler%2A> 개체를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="98b3e-124">For each <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> object, specify a <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions> object that has the <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.TaskScheduler%2A> property set to the <xref:System.Threading.Tasks.ConcurrentExclusiveSchedulerPair.ConcurrentScheduler%2A> property for the readers, and the <xref:System.Threading.Tasks.ConcurrentExclusiveSchedulerPair.ExclusiveScheduler%2A> property for the writer.</span></span>  
  
     [!code-csharp[TPLDataflow_WriterReadersWinForms#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/cs/writerreaderswinforms/form1.cs#4)]
     [!code-vb[TPLDataflow_WriterReadersWinForms#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/vb/writerreaderswinforms/form1.vb#4)]  
  
6.  <span data-ttu-id="98b3e-125">`Form1` 생성자에서 <xref:System.Windows.Forms.Timer> 개체를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="98b3e-125">In the `Form1` constructor, start the <xref:System.Windows.Forms.Timer> object.</span></span>  
  
     [!code-csharp[TPLDataflow_WriterReadersWinForms#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/cs/writerreaderswinforms/form1.cs#5)]
     [!code-vb[TPLDataflow_WriterReadersWinForms#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/vb/writerreaderswinforms/form1.vb#5)]  
  
7.  <span data-ttu-id="98b3e-126">기본 폼의 폼 디자이너에서 타이머에 대한 <xref:System.Windows.Forms.Timer.Tick> 이벤트의 이벤트 처리기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="98b3e-126">On the form designer for the main form, create an event handler for the <xref:System.Windows.Forms.Timer.Tick> event for the timer.</span></span>  
  
8.  <span data-ttu-id="98b3e-127">타이머에 대한 <xref:System.Windows.Forms.Timer.Tick> 이벤트를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="98b3e-127">Implement the <xref:System.Windows.Forms.Timer.Tick> event for the timer.</span></span>  
  
     [!code-csharp[TPLDataflow_WriterReadersWinForms#6](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/cs/writerreaderswinforms/form1.cs#6)]
     [!code-vb[TPLDataflow_WriterReadersWinForms#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/vb/writerreaderswinforms/form1.vb#6)]  
  
 <span data-ttu-id="98b3e-128">`toggleCheckBox` 데이터 흐름 블록이 사용자 인터페이스에서 동작하기 때문에 이 작업은 사용자 인터페이스 스레드에서 발생해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98b3e-128">Because the `toggleCheckBox` dataflow block acts on the user interface, it is important that this action occur on the user-interface thread.</span></span> <span data-ttu-id="98b3e-129">이를 위해 생성 중에 이 개체는 <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions> 속성이 <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.TaskScheduler%2A>로 설정된 <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType> 개체를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="98b3e-129">To accomplish this, during construction this object provides a <xref:System.Threading.Tasks.Dataflow.ExecutionDataflowBlockOptions> object that has the <xref:System.Threading.Tasks.Dataflow.DataflowBlockOptions.TaskScheduler%2A> property set to <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="98b3e-130"><xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A> 메서드는 현재 동기화 컨텍스트에서 작업을 수행하는 <xref:System.Threading.Tasks.TaskScheduler> 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="98b3e-130">The <xref:System.Threading.Tasks.TaskScheduler.FromCurrentSynchronizationContext%2A> method creates a <xref:System.Threading.Tasks.TaskScheduler> object that performs work on the current synchronization context.</span></span> <span data-ttu-id="98b3e-131">`Form1` 생성자가 사용자 인터페이스 스레드에서 호출되기 때문에 `toggleCheckBox` 데이터 흐름 블록에 대한 작업도 사용자 인터페이스 스레드에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="98b3e-131">Because the `Form1` constructor is called from the user-interface thread, the action for the `toggleCheckBox` dataflow block also runs on the user-interface thread.</span></span>  
  
 <span data-ttu-id="98b3e-132">또한 이 예제에서는 <xref:System.Threading.Tasks.ConcurrentExclusiveSchedulerPair> 클래스를 사용하여 일부 데이터 흐름 블록이 동시에 동작할 수 있도록 하고 다른 데이터 흐름 블록이 동일한 <xref:System.Threading.Tasks.ConcurrentExclusiveSchedulerPair> 개체에서 실행되는 다른 모든 데이터 흐름 블록과 독립적으로 동작할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="98b3e-132">This example also uses the <xref:System.Threading.Tasks.ConcurrentExclusiveSchedulerPair> class to enable some dataflow blocks to act concurrently, and another dataflow block to act exclusive with respect to all other dataflow blocks that run on the same <xref:System.Threading.Tasks.ConcurrentExclusiveSchedulerPair> object.</span></span> <span data-ttu-id="98b3e-133">이 방법은 여러 데이터 흐름 블록이 리소스를 공유할 때 해당 리소스에 대한 액세스를 수동으로 동기화할 필요를 없애기 위해 일부 데이터 흐름 블록에 해당 리소스에 대한 배타적 액세스 권한이 필요한 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="98b3e-133">This technique is useful when multiple dataflow blocks share a resource and some require exclusive access to that resource, because it eliminates the requirement to manually synchronize access to that resource.</span></span> <span data-ttu-id="98b3e-134">수동 동기화를 제거하면 코드의 효율성이 향상될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98b3e-134">The elimination of manual synchronization can make code more efficient.</span></span>  
  
## <a name="example"></a><span data-ttu-id="98b3e-135">예제</span><span class="sxs-lookup"><span data-stu-id="98b3e-135">Example</span></span>  
 <span data-ttu-id="98b3e-136">다음 예제에서는 Form1.cs([!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]에서는 Form1.vb)의 전체 코드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="98b3e-136">The following example shows the complete code for Form1.cs (Form1.vb for [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]).</span></span>  
  
 [!code-csharp[TPLDataflow_WriterReadersWinForms#100](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/cs/writerreaderswinforms/form1.cs#100)]
 [!code-vb[TPLDataflow_WriterReadersWinForms#100](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_writerreaderswinforms/vb/writerreaderswinforms/form1.vb#100)]  
  
## <a name="see-also"></a><span data-ttu-id="98b3e-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="98b3e-137">See Also</span></span>  
 [<span data-ttu-id="98b3e-138">데이터 흐름</span><span class="sxs-lookup"><span data-stu-id="98b3e-138">Dataflow</span></span>](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
