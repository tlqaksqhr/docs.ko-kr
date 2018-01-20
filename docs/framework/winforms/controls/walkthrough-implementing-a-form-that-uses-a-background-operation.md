---
title: "연습: 백그라운드 작업을 사용하는 폼 구현"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- threading [Windows Forms], forms
- BackgroundWorker component
- background tasks
- forms [Windows Forms], multithreading
- threading [Windows Forms], walkthroughs
- forms [Windows Forms], background operations
- threading [Windows Forms], background operations
- background operations
ms.assetid: 4691b796-9200-471a-89c3-ba4c7cc78c03
caps.latest.revision: "25"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: aaee6f1d650e6af57ab05ad56b5578e094ee50ef
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="walkthrough-implementing-a-form-that-uses-a-background-operation"></a><span data-ttu-id="662c8-102">연습: 백그라운드 작업을 사용하는 폼 구현</span><span class="sxs-lookup"><span data-stu-id="662c8-102">Walkthrough: Implementing a Form That Uses a Background Operation</span></span>
<span data-ttu-id="662c8-103">완료 하는 데 오랜 시간이 걸리는 작업이 있으며 및 하지 않으려는 경우 사용자 인터페이스 (UI) 응답 하지 않거나 사용할 수 있습니다 "중지"는 <xref:System.ComponentModel.BackgroundWorker> 다른 스레드에서 작업을 실행 하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="662c8-103">If you have an operation that will take a long time to complete, and you do not want your user interface (UI) to stop responding or "hang," you can use the <xref:System.ComponentModel.BackgroundWorker> class to execute the operation on another thread.</span></span>  
  
 <span data-ttu-id="662c8-104">이 연습에서는 사용 하는 방법을 <xref:System.ComponentModel.BackgroundWorker> "백그라운드"에서 시간이 많이 걸리는 계산을 수행 하는 클래스 사용자 인터페이스를 응답 가능한 상태로 유지 하는 동안 합니다.</span><span class="sxs-lookup"><span data-stu-id="662c8-104">This walkthrough illustrates how to use the <xref:System.ComponentModel.BackgroundWorker> class to perform time-consuming computations "in the background," while the user interface remains responsive.</span></span>  <span data-ttu-id="662c8-105">완료하면 피보나치 수를 비동기적으로 계산하는 응용 프로그램이 생깁니다.</span><span class="sxs-lookup"><span data-stu-id="662c8-105">When you are through, you will have an application that computes Fibonacci numbers asynchronously.</span></span> <span data-ttu-id="662c8-106">큰 피보나치 수를 계산하는 데는 상당한 시간이 걸릴 수도 있지만 이 지연으로 주 UI 스레드가 중단되지 않으며 계산 중에도 폼이 응답하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="662c8-106">Even though computing a large Fibonacci number can take a noticeable amount of time, the main UI thread will not be interrupted by this delay, and the form will be responsive during the calculation.</span></span>  
  
 <span data-ttu-id="662c8-107">이 연습에서 설명하는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="662c8-107">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="662c8-108">Windows 기반 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="662c8-108">Creating a Windows-based Application</span></span>  
  
-   <span data-ttu-id="662c8-109">만들기는 <xref:System.ComponentModel.BackgroundWorker> 양식에</span><span class="sxs-lookup"><span data-stu-id="662c8-109">Creating a <xref:System.ComponentModel.BackgroundWorker> in Your Form</span></span>  
  
-   <span data-ttu-id="662c8-110">비동기 이벤트 처리기 추가</span><span class="sxs-lookup"><span data-stu-id="662c8-110">Adding Asynchronous Event Handlers</span></span>  
  
-   <span data-ttu-id="662c8-111">진행률 보고 및 취소에 대한 지원 추가</span><span class="sxs-lookup"><span data-stu-id="662c8-111">Adding Progress Reporting and Support for Cancellation</span></span>  
  
 <span data-ttu-id="662c8-112">이 예제에 사용된 전체 코드 목록은 [방법: 백그라운드 작업을 사용하는 폼 구현](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="662c8-112">For a complete listing of the code used in this example, see [How to: Implement a Form That Uses a Background Operation](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="662c8-113">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="662c8-113">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="662c8-114">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="662c8-114">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="662c8-115">자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="662c8-115">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="662c8-116">프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="662c8-116">Creating the Project</span></span>  
 <span data-ttu-id="662c8-117">첫 번째 단계는 프로젝트를 만들고 폼을 설정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="662c8-117">The first step is to create the project and to set up the form.</span></span>  
  
#### <a name="to-create-a-form-that-uses-a-background-operation"></a><span data-ttu-id="662c8-118">백그라운드 작업을 사용하는 폼을 만들려면</span><span class="sxs-lookup"><span data-stu-id="662c8-118">To create a form that uses a background operation</span></span>  
  
1.  <span data-ttu-id="662c8-119">`BackgroundWorkerExample`이라는 Windows 기반 응용 프로그램 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="662c8-119">Create a Windows-based application project called `BackgroundWorkerExample`.</span></span> <span data-ttu-id="662c8-120">자세한 내용은 [방법: Windows 응용 프로그램 프로젝트 만들기](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="662c8-120">For details, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa).</span></span>  
  
2.  <span data-ttu-id="662c8-121">**솔루션 탐색기**에서 **Form1**을 마우스 오른쪽 단추로 클릭한 다음 바로 가기 메뉴에서 **이름 바꾸기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="662c8-121">In **Solution Explorer**, right-click **Form1** and select **Rename** from the shortcut menu.</span></span> <span data-ttu-id="662c8-122">파일 이름을 `FibonacciCalculator`로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="662c8-122">Change the file name to `FibonacciCalculator`.</span></span> <span data-ttu-id="662c8-123">코드 요소 '`Form1`'에 대한 모든 참조 이름을 변경할지 묻는 메시지가 표시되면 **예** 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="662c8-123">Click the **Yes** button when you are asked if you want to rename all references to the code element '`Form1`'.</span></span>  
  
3.  <span data-ttu-id="662c8-124">끌어서는 <xref:System.Windows.Forms.NumericUpDown> 에서 제어는 **도구 상자** 폼입니다.</span><span class="sxs-lookup"><span data-stu-id="662c8-124">Drag a <xref:System.Windows.Forms.NumericUpDown> control from the **Toolbox** onto the form.</span></span> <span data-ttu-id="662c8-125">설정의 <xref:System.Windows.Forms.NumericUpDown.Minimum%2A> 속성을 `1` 및 <xref:System.Windows.Forms.NumericUpDown.Maximum%2A> 속성을 `91`합니다.</span><span class="sxs-lookup"><span data-stu-id="662c8-125">Set the <xref:System.Windows.Forms.NumericUpDown.Minimum%2A> property to `1` and the <xref:System.Windows.Forms.NumericUpDown.Maximum%2A> property to `91`.</span></span>  
  
4.  <span data-ttu-id="662c8-126">두 개의 추가 <xref:System.Windows.Forms.Button> 폼에 컨트롤을 합니다.</span><span class="sxs-lookup"><span data-stu-id="662c8-126">Add two <xref:System.Windows.Forms.Button> controls to the form.</span></span>  
  
5.  <span data-ttu-id="662c8-127">첫 번째 이름 바꾸기 <xref:System.Windows.Forms.Button> 제어 `startAsyncButton` 설정 하 고는 <xref:System.Windows.Forms.Control.Text%2A> 속성을 `Start Async`합니다.</span><span class="sxs-lookup"><span data-stu-id="662c8-127">Rename the first <xref:System.Windows.Forms.Button> control `startAsyncButton` and set the <xref:System.Windows.Forms.Control.Text%2A> property to `Start Async`.</span></span> <span data-ttu-id="662c8-128">두 번째 이름 바꾸기 <xref:System.Windows.Forms.Button> 제어 `cancelAsyncButton`를 설정 하 고는 <xref:System.Windows.Forms.Control.Text%2A> 속성을 `Cancel Async`합니다.</span><span class="sxs-lookup"><span data-stu-id="662c8-128">Rename the second <xref:System.Windows.Forms.Button> control `cancelAsyncButton`, and set the <xref:System.Windows.Forms.Control.Text%2A> property to `Cancel Async`.</span></span> <span data-ttu-id="662c8-129">설정의 <xref:System.Windows.Forms.Control.Enabled%2A> 속성을 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="662c8-129">Set its <xref:System.Windows.Forms.Control.Enabled%2A> property to `false`.</span></span>  
  
6.  <span data-ttu-id="662c8-130">둘 다에 대해 이벤트 처리기를 만들고는 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Click> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="662c8-130">Create an event handler for both of the <xref:System.Windows.Forms.Button> controls' <xref:System.Windows.Forms.Control.Click> events.</span></span> <span data-ttu-id="662c8-131">자세한 내용은 [방법: 디자이너를 사용하여 이벤트 처리기 만들기](http://msdn.microsoft.com/library/8461e9b8-14e8-406f-936e-3726732b23d2)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="662c8-131">For details, see [How to: Create Event Handlers Using the Designer](http://msdn.microsoft.com/library/8461e9b8-14e8-406f-936e-3726732b23d2).</span></span>  
  
7.  <span data-ttu-id="662c8-132">끌어서는 <xref:System.Windows.Forms.Label> 에서 제어는 **도구 상자** 폼 하 고 이름을 `resultLabel`합니다.</span><span class="sxs-lookup"><span data-stu-id="662c8-132">Drag a <xref:System.Windows.Forms.Label> control from the **Toolbox** onto the form and rename it `resultLabel`.</span></span>  
  
8.  <span data-ttu-id="662c8-133">끌어서는 <xref:System.Windows.Forms.ProgressBar> 에서 제어는 **도구 상자** 폼입니다.</span><span class="sxs-lookup"><span data-stu-id="662c8-133">Drag a <xref:System.Windows.Forms.ProgressBar> control from the **Toolbox** onto the form.</span></span>  
  
## <a name="creating-a-backgroundworker-in-your-form"></a><span data-ttu-id="662c8-134">사용자 폼에서 BackgroundWorker 만들기</span><span class="sxs-lookup"><span data-stu-id="662c8-134">Creating a BackgroundWorker in Your Form</span></span>  
 <span data-ttu-id="662c8-135">만들 수는 <xref:System.ComponentModel.BackgroundWorker> 사용 하 여 비동기 작업에 대 한는 **Windows** **Forms 디자이너**합니다.</span><span class="sxs-lookup"><span data-stu-id="662c8-135">You can create the <xref:System.ComponentModel.BackgroundWorker> for your asynchronous operation using the **Windows** **Forms Designer**.</span></span>  
  
#### <a name="to-create-a-backgroundworker-with-the-designer"></a><span data-ttu-id="662c8-136">디자이너로 BackgroundWorker를 만들려면</span><span class="sxs-lookup"><span data-stu-id="662c8-136">To create a BackgroundWorker with the Designer</span></span>  
  
-   <span data-ttu-id="662c8-137">**구성 요소** 탭은 **도구 상자**를 끌어 한 <xref:System.ComponentModel.BackgroundWorker> 폼으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="662c8-137">From the **Components** tab of the **Toolbox**, drag a <xref:System.ComponentModel.BackgroundWorker> onto the form.</span></span>  
  
## <a name="adding-asynchronous-event-handlers"></a><span data-ttu-id="662c8-138">비동기 이벤트 처리기 추가</span><span class="sxs-lookup"><span data-stu-id="662c8-138">Adding Asynchronous Event Handlers</span></span>  
 <span data-ttu-id="662c8-139">에 대 한 이벤트 처리기를 추가할 준비가 된 <xref:System.ComponentModel.BackgroundWorker> 구성 요소의 비동기 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="662c8-139">You are now ready to add event handlers for the <xref:System.ComponentModel.BackgroundWorker> component's asynchronous events.</span></span> <span data-ttu-id="662c8-140">백그라운드로 실행되는 시간이 많이 소요되는 작업(예: 피보나치 수 계산)은 이러한 이벤트 처리기 중 하나에 의해 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="662c8-140">The time-consuming operation that will run in the background, which computes Fibonacci numbers, is called by one of these event handlers.</span></span>  
  
#### <a name="to-implement-asynchronous-event-handlers"></a><span data-ttu-id="662c8-141">비동기 이벤트 처리기를 구현하려면</span><span class="sxs-lookup"><span data-stu-id="662c8-141">To implement asynchronous event handlers</span></span>  
  
1.  <span data-ttu-id="662c8-142">에 **속성** 창와는 <xref:System.ComponentModel.BackgroundWorker> 구성 요소를 선택한 상태에서 클릭는 **이벤트** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="662c8-142">In the **Properties** window, with the <xref:System.ComponentModel.BackgroundWorker> component still selected, click the **Events** button.</span></span> <span data-ttu-id="662c8-143">두 번 클릭는 <xref:System.ComponentModel.BackgroundWorker.DoWork> 및 <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> 이벤트를 이벤트 처리기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="662c8-143">Double-click the <xref:System.ComponentModel.BackgroundWorker.DoWork> and <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> events to create event handlers.</span></span> <span data-ttu-id="662c8-144">이벤트 처리기를 사용하는 방법에 대한 자세한 내용은 [방법: 디자이너를 사용하여 이벤트 처리기 만들기](http://msdn.microsoft.com/library/8461e9b8-14e8-406f-936e-3726732b23d2)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="662c8-144">For more information about how to use event handlers, see [How to: Create Event Handlers Using the Designer](http://msdn.microsoft.com/library/8461e9b8-14e8-406f-936e-3726732b23d2).</span></span>  
  
2.  <span data-ttu-id="662c8-145">사용자 폼에서 `ComputeFibonacci`라는 새 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="662c8-145">Create a new method, called `ComputeFibonacci`, in your form.</span></span> <span data-ttu-id="662c8-146">이 메서드는 실제 작업을 수행하며 백그라운드에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="662c8-146">This method does the actual work, and it will run in the background.</span></span> <span data-ttu-id="662c8-147">이 코드는 피보나치 알고리즘의 재귀적 구현을 보여 줍니다. 이는 매우 비효율적이며, 큰 숫자를 완성하는 데 기하급수적으로 긴 시간이 소요됩니다.</span><span class="sxs-lookup"><span data-stu-id="662c8-147">This code demonstrates the recursive implementation of the Fibonacci algorithm, which is notably inefficient, taking exponentially longer time to complete for larger numbers.</span></span> <span data-ttu-id="662c8-148">여기서는 응용 프로그램에서 오랜 지연을 유발할 수 있는 작업을 보여 주기 위해 설명 용도로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="662c8-148">It is used here for illustrative purposes, to show an operation that can introduce long delays in your application.</span></span>  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#10](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#10)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#10)]
     [!code-vb[System.ComponentModel.BackgroundWorker#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#10)]  
  
3.  <span data-ttu-id="662c8-149">에 <xref:System.ComponentModel.BackgroundWorker.DoWork> 이벤트 처리기 호출을 추가 `ComputeFibonacci` 메서드.</span><span class="sxs-lookup"><span data-stu-id="662c8-149">In the <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler, add a call to the `ComputeFibonacci` method.</span></span> <span data-ttu-id="662c8-150">에 대 한 첫 번째 매개 변수 `ComputeFibonacci` 에서 <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> 의 속성은 <xref:System.ComponentModel.DoWorkEventArgs>합니다.</span><span class="sxs-lookup"><span data-stu-id="662c8-150">Take the first parameter for `ComputeFibonacci` from the <xref:System.ComponentModel.DoWorkEventArgs.Argument%2A> property of the <xref:System.ComponentModel.DoWorkEventArgs>.</span></span> <span data-ttu-id="662c8-151"><xref:System.ComponentModel.BackgroundWorker> 및 <xref:System.ComponentModel.DoWorkEventArgs> 취소 및 진행률 보고에 대 한 매개 변수를 나중에 사용할 수는 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="662c8-151">The <xref:System.ComponentModel.BackgroundWorker> and <xref:System.ComponentModel.DoWorkEventArgs> parameters will be used later for progress reporting and cancellation support.</span></span> <span data-ttu-id="662c8-152">반환 값을 할당 `ComputeFibonacci` 에 <xref:System.ComponentModel.DoWorkEventArgs.Result%2A> 의 속성은 <xref:System.ComponentModel.DoWorkEventArgs>합니다.</span><span class="sxs-lookup"><span data-stu-id="662c8-152">Assign the return value from `ComputeFibonacci` to the <xref:System.ComponentModel.DoWorkEventArgs.Result%2A> property of the <xref:System.ComponentModel.DoWorkEventArgs>.</span></span> <span data-ttu-id="662c8-153">이 결과 사용할 수 있습니다는 <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="662c8-153">This result will be available to the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event handler.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="662c8-154"><xref:System.ComponentModel.BackgroundWorker.DoWork> 이벤트 처리기를 참조 하지 않습니다는 `backgroundWorker1` 인스턴스 변수를 직접이 이벤트 처리기의 특정 인스턴스에 결합는이 처럼 <xref:System.ComponentModel.BackgroundWorker>합니다.</span><span class="sxs-lookup"><span data-stu-id="662c8-154">The <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler does not reference the `backgroundWorker1` instance variable directly, as this would couple this event handler to a specific instance of <xref:System.ComponentModel.BackgroundWorker>.</span></span> <span data-ttu-id="662c8-155">대신,에 대 한 참조는 <xref:System.ComponentModel.BackgroundWorker> 이 발생 하는 이벤트에서 복구 되는 `sender` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="662c8-155">Instead, a reference to the <xref:System.ComponentModel.BackgroundWorker> that raised this event is recovered from the `sender` parameter.</span></span> <span data-ttu-id="662c8-156">둘 이상의 폼 호스팅하는 경우이 중요 <xref:System.ComponentModel.BackgroundWorker>합니다.</span><span class="sxs-lookup"><span data-stu-id="662c8-156">This is important when the form hosts more than one <xref:System.ComponentModel.BackgroundWorker>.</span></span> <span data-ttu-id="662c8-157">사용자 인터페이스 개체를 조작 하지 않아야 이기도 프로그램 <xref:System.ComponentModel.BackgroundWorker.DoWork> 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="662c8-157">It is also important not to manipulate any user-interface objects in your <xref:System.ComponentModel.BackgroundWorker.DoWork> event handler.</span></span> <span data-ttu-id="662c8-158">대신, 사용자 인터페이스를 통해 통신할는 <xref:System.ComponentModel.BackgroundWorker> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="662c8-158">Instead, communicate to the user interface through the <xref:System.ComponentModel.BackgroundWorker> events.</span></span>  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#5](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#5)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#5](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#5)]
     [!code-vb[System.ComponentModel.BackgroundWorker#5](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#5)]  
  
4.  <span data-ttu-id="662c8-159">에 `startAsyncButton` 컨트롤의 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기는 비동기 작업을 시작 하는 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="662c8-159">In the `startAsyncButton` control's <xref:System.Windows.Forms.Control.Click> event handler, add the code that starts the asynchronous operation.</span></span>  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#13](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#13)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#13](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#13)]
     [!code-vb[System.ComponentModel.BackgroundWorker#13](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#13)]  
  
5.  <span data-ttu-id="662c8-160">에 <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> 이벤트 처리기에 계산의 결과 할당는 `resultLabel` 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="662c8-160">In the <xref:System.ComponentModel.BackgroundWorker.RunWorkerCompleted> event handler, assign the result of the calculation to the `resultLabel` control.</span></span>  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#6](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#6)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#6](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#6)]
     [!code-vb[System.ComponentModel.BackgroundWorker#6](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#6)]  
  
## <a name="adding-progress-reporting-and-support-for-cancellation"></a><span data-ttu-id="662c8-161">진행률 보고 및 취소에 대한 지원 추가</span><span class="sxs-lookup"><span data-stu-id="662c8-161">Adding Progress Reporting and Support for Cancellation</span></span>  
 <span data-ttu-id="662c8-162">시간이 오래 소요되는 비동기 작업의 경우 사용자에게 진행률을 보고하고 사용자가 작업을 취소하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="662c8-162">For asynchronous operations that will take a long time, it is often desirable to report progress to the user and to allow the user to cancel the operation.</span></span> <span data-ttu-id="662c8-163"><xref:System.ComponentModel.BackgroundWorker> 프로그램 백그라운드 작업이 수행 될 때 진행률을 게시할 수 있는 이벤트 클래스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="662c8-163">The <xref:System.ComponentModel.BackgroundWorker> class provides an event that allows you to post progress as your background operation proceeds.</span></span> <span data-ttu-id="662c8-164">또한 사용 작업자 코드에 대 한 호출을 검색 하는 플래그 제공 <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> 자체를 중단 합니다.</span><span class="sxs-lookup"><span data-stu-id="662c8-164">It also provides a flag that allows your worker code to detect a call to <xref:System.ComponentModel.BackgroundWorker.CancelAsync%2A> and interrupt itself.</span></span>  
  
#### <a name="to-implement-progress-reporting"></a><span data-ttu-id="662c8-165">진행률 보고를 구현하려면</span><span class="sxs-lookup"><span data-stu-id="662c8-165">To implement progress reporting</span></span>  
  
1.  <span data-ttu-id="662c8-166">**속성** 창에서 `backgroundWorker1`을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="662c8-166">In the **Properties**, window, select `backgroundWorker1`.</span></span> <span data-ttu-id="662c8-167">설정의 <xref:System.ComponentModel.BackgroundWorker.WorkerReportsProgress%2A> 및 <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> 속성을 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="662c8-167">Set the <xref:System.ComponentModel.BackgroundWorker.WorkerReportsProgress%2A> and <xref:System.ComponentModel.BackgroundWorker.WorkerSupportsCancellation%2A> properties to `true`.</span></span>  
  
2.  <span data-ttu-id="662c8-168">`FibonacciCalculator` 폼에서 변수 두 개를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="662c8-168">Declare two variables in the `FibonacciCalculator` form.</span></span> <span data-ttu-id="662c8-169">진행률을 추적하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="662c8-169">These will be used to track progress.</span></span>  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#14](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#14)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#14](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#14)]
     [!code-vb[System.ComponentModel.BackgroundWorker#14](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#14)]  
  
3.  <span data-ttu-id="662c8-170"><xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 이벤트에 대한 이벤트 처리기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="662c8-170">Add an event handler for the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event.</span></span> <span data-ttu-id="662c8-171">에 <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> 이벤트 처리기, 업데이트는 <xref:System.Windows.Forms.ProgressBar> 와 <xref:System.ComponentModel.ProgressChangedEventArgs.ProgressPercentage%2A> 속성은 <xref:System.ComponentModel.ProgressChangedEventArgs> 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="662c8-171">In the <xref:System.ComponentModel.BackgroundWorker.ProgressChanged> event handler, update the <xref:System.Windows.Forms.ProgressBar> with the <xref:System.ComponentModel.ProgressChangedEventArgs.ProgressPercentage%2A> property of the <xref:System.ComponentModel.ProgressChangedEventArgs> parameter.</span></span>  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#7](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#7)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#7)]
     [!code-vb[System.ComponentModel.BackgroundWorker#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#7)]  
  
#### <a name="to-implement-support-for-cancellation"></a><span data-ttu-id="662c8-172">취소에 대한 지원을 구현하려면</span><span class="sxs-lookup"><span data-stu-id="662c8-172">To implement support for cancellation</span></span>  
  
1.  <span data-ttu-id="662c8-173">에 `cancelAsyncButton` 컨트롤의 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기는 비동기 작업을 취소 하는 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="662c8-173">In the `cancelAsyncButton` control's <xref:System.Windows.Forms.Control.Click> event handler, add the code that cancels the asynchronous operation.</span></span>  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#4](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#4)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#4)]
     [!code-vb[System.ComponentModel.BackgroundWorker#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#4)]  
  
2.  <span data-ttu-id="662c8-174">`ComputeFibonacci` 메서드의 다음 코드 조각은 진행률을 보고하고 취소를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="662c8-174">The following code fragments in the `ComputeFibonacci` method report progress and support cancellation.</span></span>  
  
     [!code-cpp[System.ComponentModel.BackgroundWorker#11](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#11)]
     [!code-csharp[System.ComponentModel.BackgroundWorker#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#11)]
     [!code-vb[System.ComponentModel.BackgroundWorker#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#11)]  
    [!code-cpp[System.ComponentModel.BackgroundWorker#12](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CPP/fibonacciform.cpp#12)]
    [!code-csharp[System.ComponentModel.BackgroundWorker#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/CS/fibonacciform.cs#12)]
    [!code-vb[System.ComponentModel.BackgroundWorker#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.BackgroundWorker/VB/fibonacciform.vb#12)]  
  
## <a name="checkpoint"></a><span data-ttu-id="662c8-175">검사점</span><span class="sxs-lookup"><span data-stu-id="662c8-175">Checkpoint</span></span>  
 <span data-ttu-id="662c8-176">이 시점에서 피보나치 계산기 응용 프로그램을 컴파일하여 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="662c8-176">At this point, you can compile and run the Fibonacci Calculator application.</span></span>  
  
#### <a name="to-test-your-project"></a><span data-ttu-id="662c8-177">프로젝트를 테스트하려면</span><span class="sxs-lookup"><span data-stu-id="662c8-177">To test your project</span></span>  
  
-   <span data-ttu-id="662c8-178">F5 키를 눌러 응용 프로그램을 컴파일하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="662c8-178">Press F5 to compile and run the application.</span></span>  
  
     <span data-ttu-id="662c8-179">계산 백그라운드에서 실행 되는 동안 표시 됩니다는 <xref:System.Windows.Forms.ProgressBar> 완료 될 때까지 계산의 진행 상태를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="662c8-179">While the calculation is running in the background, you will see the <xref:System.Windows.Forms.ProgressBar> displaying the progress of the calculation toward completion.</span></span> <span data-ttu-id="662c8-180">보류 중인 작업도 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="662c8-180">You can also cancel the pending operation.</span></span>  
  
     <span data-ttu-id="662c8-181">작은 숫자에 대한 계산은 매우 빠르지만 큰 수에 대한 계산은 상당한 지연이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="662c8-181">For small numbers, the calculation should be very fast, but for larger numbers, you should see a noticeable delay.</span></span> <span data-ttu-id="662c8-182">값을 30 이상 입력하면 컴퓨터 속도에 따라 몇 초의 지연이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="662c8-182">If you enter a value of 30 or greater, you should see a delay of several seconds, depending on the speed of your computer.</span></span> <span data-ttu-id="662c8-183">값이 40을 넘으면 계산을 완료하는 데 몇 분 또는 몇 시간이 소요될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="662c8-183">For values greater than 40, it may take minutes or hours to finish the calculation.</span></span> <span data-ttu-id="662c8-184">계산기가 큰 피보나치 수를 계산하는 동안 폼을 자유롭게 움직이고, 최소화 및 최대화하며, 해제할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="662c8-184">While the calculator is busy computing a large Fibonacci number, notice that you can freely move the form around, minimize, maximize, and even dismiss it.</span></span> <span data-ttu-id="662c8-185">주 UI 스레드가 계산이 완료되기를 기다리지 않기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="662c8-185">This is because the main UI thread is not waiting for the calculation to finish.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="662c8-186">다음 단계</span><span class="sxs-lookup"><span data-stu-id="662c8-186">Next Steps</span></span>  
 <span data-ttu-id="662c8-187">사용 하는 폼을 구현 하는 <xref:System.ComponentModel.BackgroundWorker> 백그라운드에서 계산을 실행 하는 구성 요소 비동기 작업에 대 한 다른 가능성을 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="662c8-187">Now that you have implemented a form that uses a <xref:System.ComponentModel.BackgroundWorker> component to execute a computation in the background, you can explore other possibilities for asynchronous operations:</span></span>  
  
-   <span data-ttu-id="662c8-188">여러 개 사용 <xref:System.ComponentModel.BackgroundWorker> 여러 동시 작업에 대 한 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="662c8-188">Use multiple <xref:System.ComponentModel.BackgroundWorker> objects for several simultaneous operations.</span></span>  
  
-   <span data-ttu-id="662c8-189">다중 스레드 응용 프로그램을 디버깅하려면 [방법: 스레드 창 사용](/visualstudio/debugger/how-to-use-the-threads-window)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="662c8-189">To debug your multithreaded application, see [How to: Use the Threads Window](/visualstudio/debugger/how-to-use-the-threads-window).</span></span>  
  
-   <span data-ttu-id="662c8-190">비동기 프로그래밍 모델을 지원하는 사용자 고유의 구성 요소를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="662c8-190">Implement your own component that supports the asynchronous programming model.</span></span> <span data-ttu-id="662c8-191">자세한 내용은 [이벤트 기반 비동기 패턴 개요](../../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="662c8-191">For more information, see [Event-based Asynchronous Pattern Overview](../../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md).</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="662c8-192">모든 종류의 다중 스레딩을 사용할 때는 매우 심각하고 복잡한 버그에 잠재적으로 노출됩니다.</span><span class="sxs-lookup"><span data-stu-id="662c8-192">When using multithreading of any sort, you potentially expose yourself to very serious and complex bugs.</span></span> <span data-ttu-id="662c8-193">다중 스레딩을 사용하는 솔루션을 구현하기 전에 [관리되는 스레딩을 구현하는 최선의 방법](../../../../docs/standard/threading/managed-threading-best-practices.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="662c8-193">Consult the [Managed Threading Best Practices](../../../../docs/standard/threading/managed-threading-best-practices.md) before implementing any solution that uses multithreading.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="662c8-194">참고 항목</span><span class="sxs-lookup"><span data-stu-id="662c8-194">See Also</span></span>  
 <xref:System.ComponentModel.BackgroundWorker>  
 [<span data-ttu-id="662c8-195">관리되는 스레딩을 구현하는 최선의 방법</span><span class="sxs-lookup"><span data-stu-id="662c8-195">Managed Threading Best Practices</span></span>](../../../../docs/standard/threading/managed-threading-best-practices.md)  
 [<span data-ttu-id="662c8-196">구성 요소에서 다중 스레딩</span><span class="sxs-lookup"><span data-stu-id="662c8-196">Multithreading in Components</span></span>](http://msdn.microsoft.com/library/2fc31e68-fb71-4544-b654-0ce720478779)  
 [<span data-ttu-id="662c8-197">빌드에 없음: Visual Basic의 다중 스레딩</span><span class="sxs-lookup"><span data-stu-id="662c8-197">NOT IN BUILD: Multithreading in Visual Basic</span></span>](http://msdn.microsoft.com/library/c731a50c-09c1-4468-9646-54c86b75d269)  
 [<span data-ttu-id="662c8-198">방법: 배경 작업을 사용하는 양식 구현</span><span class="sxs-lookup"><span data-stu-id="662c8-198">How to: Implement a Form That Uses a Background Operation</span></span>](../../../../docs/framework/winforms/controls/how-to-implement-a-form-that-uses-a-background-operation.md)  
 [<span data-ttu-id="662c8-199">연습: 백그라운드에서 작업 실행</span><span class="sxs-lookup"><span data-stu-id="662c8-199">Walkthrough: Running an Operation in the Background</span></span>](../../../../docs/framework/winforms/controls/walkthrough-running-an-operation-in-the-background.md)  
 [<span data-ttu-id="662c8-200">BackgroundWorker 구성 요소</span><span class="sxs-lookup"><span data-stu-id="662c8-200">BackgroundWorker Component</span></span>](../../../../docs/framework/winforms/controls/backgroundworker-component.md)
