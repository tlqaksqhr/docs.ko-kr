---
title: "연습: 첫 응용 프로그램 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- creating a touch-sensitive application [WPF]
- touchscreen applications [WPF], creating
- touch-sensitive applications [WPF], creating
- creating a touchscreen application [WPF]
ms.assetid: d69e602e-9a25-4e24-950b-e89eaa2a906b
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 502fb9ae0c488f5f3e438a3ae0a7087538183f1b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-creating-your-first-touch-application"></a><span data-ttu-id="60f79-102">연습: 첫 응용 프로그램 만들기</span><span class="sxs-lookup"><span data-stu-id="60f79-102">Walkthrough: Creating Your First Touch Application</span></span>
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="60f79-103">터치에 응답 하도록 응용 프로그램이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60f79-103"> enables applications to respond to touch.</span></span> <span data-ttu-id="60f79-104">예를 들어 하나를 사용 하 여 응용 프로그램 상호 작용할 수 있습니다 또는 터치 지원 장치 등이 연습에서는 사용자가을 이동할 수 있도록 응용 프로그램을 만듭니다 터치 스크린에 손가락 크기 조정 또는 터치를 사용 하 여 단일 개체를 회전 합니다.</span><span class="sxs-lookup"><span data-stu-id="60f79-104">For example, you can interact with an application by using one or more fingers on a touch-sensitive device, such as a touchscreen This walkthrough creates an application that enables the user to move, resize, or rotate a single object by using touch.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="60f79-105">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="60f79-105">Prerequisites</span></span>  
 <span data-ttu-id="60f79-106">이 연습을 완료하려면 다음 구성 요소가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="60f79-106">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_dev10_ext](../../../../includes/vs-dev10-ext-md.md)]<span data-ttu-id="60f79-107">.</span><span class="sxs-lookup"><span data-stu-id="60f79-107">.</span></span>  
  
-   <span data-ttu-id="60f79-108">Windows 7</span><span class="sxs-lookup"><span data-stu-id="60f79-108">Windows 7.</span></span>  
  
-   <span data-ttu-id="60f79-109">터치식 등을 지 원하는 Windows Touch 터치 스크린 입력을 허용 하는 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="60f79-109">A device that accepts touch input, such as a touchscreen, that supports Windows Touch.</span></span>  
  
 <span data-ttu-id="60f79-110">또한 응용 프로그램을 만들 하는 방법에 대 한 기본적인 이해 있어야 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]를 구독 하 고 이벤트를 처리 하는 방법에 특히 합니다.</span><span class="sxs-lookup"><span data-stu-id="60f79-110">Additionally, you should have a basic understanding of how to create an application in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], especially how to subscribe to and handle an event.</span></span> <span data-ttu-id="60f79-111">자세한 내용은 참조 [연습: 내 첫 WPF 데스크톱 응용 프로그램](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="60f79-111">For more information, see [Walkthrough: My first WPF desktop application](../../../../docs/framework/wpf/getting-started/walkthrough-my-first-wpf-desktop-application.md).</span></span>  
  
## <a name="creating-the-application"></a><span data-ttu-id="60f79-112">응용 프로그램 작성</span><span class="sxs-lookup"><span data-stu-id="60f79-112">Creating the Application</span></span>  
  
#### <a name="to-create-the-application"></a><span data-ttu-id="60f79-113">응용 프로그램을 만들려면</span><span class="sxs-lookup"><span data-stu-id="60f79-113">To create the application</span></span>  
  
1.  <span data-ttu-id="60f79-114">Visual Basic 또는 Visual C#에서 `BasicManipulation`이라는 새 WPF 응용 프로그램 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="60f79-114">Create a new WPF Application project in Visual Basic or Visual C# named `BasicManipulation`.</span></span> <span data-ttu-id="60f79-115">자세한 내용은 [방법: 새 WPF 응용 프로그램 프로젝트 만들기](http://msdn.microsoft.com/en-us/1f6aea7a-33e1-4d3f-8555-1daa42e95d82)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="60f79-115">For more information, see [How to: Create a New WPF Application Project](http://msdn.microsoft.com/en-us/1f6aea7a-33e1-4d3f-8555-1daa42e95d82).</span></span>  
  
2.  <span data-ttu-id="60f79-116">MainWindow.xaml의 내용을 다음 XAML로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="60f79-116">Replace the contents of MainWindow.xaml with the following XAML.</span></span>  
  
     <span data-ttu-id="60f79-117">이 태그는 빨강을 포함 하는 간단한 응용 프로그램을 만듭니다 <xref:System.Windows.Shapes.Rectangle> 에 <xref:System.Windows.Controls.Canvas>합니다.</span><span class="sxs-lookup"><span data-stu-id="60f79-117">This markup creates a simple application that contains a red <xref:System.Windows.Shapes.Rectangle> on a <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="60f79-118"><xref:System.Windows.UIElement.IsManipulationEnabled%2A> 의 속성은 <xref:System.Windows.Shapes.Rectangle> 조작 이벤트를 받을 있도록 true로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="60f79-118">The <xref:System.Windows.UIElement.IsManipulationEnabled%2A> property of the <xref:System.Windows.Shapes.Rectangle> is set to true so that it will receive manipulation events.</span></span> <span data-ttu-id="60f79-119">응용 프로그램 구독 하는 <xref:System.Windows.UIElement.ManipulationStarting>, <xref:System.Windows.UIElement.ManipulationDelta>, 및 <xref:System.Windows.UIElement.ManipulationInertiaStarting> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="60f79-119">The application subscribes to the <xref:System.Windows.UIElement.ManipulationStarting>, <xref:System.Windows.UIElement.ManipulationDelta>, and <xref:System.Windows.UIElement.ManipulationInertiaStarting> events.</span></span> <span data-ttu-id="60f79-120">이 이벤트는 논리를 포함할는 <xref:System.Windows.Shapes.Rectangle> 경우는 사용자가 조작할 합니다.</span><span class="sxs-lookup"><span data-stu-id="60f79-120">These events contain the logic to move the <xref:System.Windows.Shapes.Rectangle> when the user manipulates it.</span></span>  
  
     [!code-xaml[BasicManipulation#UI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml#ui)]  
  
3.  <span data-ttu-id="60f79-121">Visual Basic에서 MainWindow.xaml의 첫 번째 줄을 사용 하는 경우 대체 `x:Class="BasicManipulation.MainWindow"` 와 `x:Class="MainWindow"`합니다.</span><span class="sxs-lookup"><span data-stu-id="60f79-121">If you are using Visual Basic, in the first line of MainWindow.xaml, replace `x:Class="BasicManipulation.MainWindow"` with `x:Class="MainWindow"`.</span></span>  
  
4.  <span data-ttu-id="60f79-122">에 `MainWindow` 클래스, 다음 추가 <xref:System.Windows.UIElement.ManipulationStarting> 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="60f79-122">In the `MainWindow` class, add the following <xref:System.Windows.UIElement.ManipulationStarting> event handler.</span></span>  
  
     <span data-ttu-id="60f79-123"><xref:System.Windows.UIElement.ManipulationStarting> 이벤트가 발생할 때 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 터치 검색 입력 개체를 조작 하기 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="60f79-123">The <xref:System.Windows.UIElement.ManipulationStarting> event occurs when [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] detects that touch input begins to manipulate an object.</span></span> <span data-ttu-id="60f79-124">코드는 조작의 위치에 상대적이 되도록 지정 된 <xref:System.Windows.Window> 설정 하 여는 <xref:System.Windows.Input.ManipulationStartingEventArgs.ManipulationContainer%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="60f79-124">The code specifies that the position of the manipulation should be relative to the <xref:System.Windows.Window> by setting the <xref:System.Windows.Input.ManipulationStartingEventArgs.ManipulationContainer%2A> property.</span></span>  
  
     [!code-csharp[BasicManipulation#ManipulationStarting](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml.cs#manipulationstarting)]
     [!code-vb[BasicManipulation#ManipulationStarting](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicmanipulation/visualbasic/mainwindow.xaml.vb#manipulationstarting)]  
  
5.  <span data-ttu-id="60f79-125">에 `MainWindow` 클래스, 다음 추가 <xref:System.Windows.Input.ManipulationDelta> 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="60f79-125">In the `MainWindow` class, add the following <xref:System.Windows.Input.ManipulationDelta> event handler.</span></span>  
  
     <span data-ttu-id="60f79-126"><xref:System.Windows.Input.ManipulationDelta> 터치 입력 위치를 변경 하 고 조작 하는 동안 여러 번 발생할 수 있는 이벤트가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="60f79-126">The <xref:System.Windows.Input.ManipulationDelta> event occurs when the touch input changes position and can occur multiple times during a manipulation.</span></span> <span data-ttu-id="60f79-127">이벤트를 손가락 발생 한 후에 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60f79-127">The event can also occur after a finger is raised.</span></span> <span data-ttu-id="60f79-128">예를 들어 사용자가 화면에서 손가락을 끌 경우는 <xref:System.Windows.Input.ManipulationDelta> 이벤트 손가락 이동으로 여러 번 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="60f79-128">For example, if the user drags a finger across a screen, the <xref:System.Windows.Input.ManipulationDelta> event occurs multiple times as the finger moves.</span></span> <span data-ttu-id="60f79-129">사용자의 화면에서 손가락을 발생 시킬 때는 <xref:System.Windows.Input.ManipulationDelta> 관성을 시뮬레이션 하 이벤트가 계속 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="60f79-129">When the user raises a finger from the screen, the <xref:System.Windows.Input.ManipulationDelta> event keeps occurring to simulate inertia.</span></span>  
  
     <span data-ttu-id="60f79-130">코드 적용는 <xref:System.Windows.Input.ManipulationDeltaEventArgs.DeltaManipulation%2A> 에 <xref:System.Windows.UIElement.RenderTransform%2A> 의 <xref:System.Windows.Shapes.Rectangle> 터치를 이동할 때 이동 하려면 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="60f79-130">The code applies the <xref:System.Windows.Input.ManipulationDeltaEventArgs.DeltaManipulation%2A> to the <xref:System.Windows.UIElement.RenderTransform%2A> of the <xref:System.Windows.Shapes.Rectangle> to move it as the user moves the touch input.</span></span> <span data-ttu-id="60f79-131">또한 확인 여부는 <xref:System.Windows.Shapes.Rectangle> 의 경계를 벗어납니다는 <xref:System.Windows.Window> 관성 하는 동안 이벤트가 발생할 때.</span><span class="sxs-lookup"><span data-stu-id="60f79-131">It also checks whether the <xref:System.Windows.Shapes.Rectangle> is outside the bounds of the <xref:System.Windows.Window> when the event occurs during inertia.</span></span> <span data-ttu-id="60f79-132">응용 프로그램 호출에서 <xref:System.Windows.Input.ManipulationDeltaEventArgs.Complete%2A?displayProperty=nameWithType> 조작 발생 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="60f79-132">If so, the application calls the <xref:System.Windows.Input.ManipulationDeltaEventArgs.Complete%2A?displayProperty=nameWithType> method to end the manipulation.</span></span>  
  
     [!code-csharp[BasicManipulation#ManipulationDelta](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml.cs#manipulationdelta)]
     [!code-vb[BasicManipulation#ManipulationDelta](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicmanipulation/visualbasic/mainwindow.xaml.vb#manipulationdelta)]  
  
6.  <span data-ttu-id="60f79-133">에 `MainWindow` 클래스, 다음 추가 <xref:System.Windows.UIElement.ManipulationInertiaStarting> 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="60f79-133">In the `MainWindow` class, add the following <xref:System.Windows.UIElement.ManipulationInertiaStarting> event handler.</span></span>  
  
     <span data-ttu-id="60f79-134"><xref:System.Windows.UIElement.ManipulationInertiaStarting> 사용자 화면에서 손가락을 모두 발생 하면 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="60f79-134">The <xref:System.Windows.UIElement.ManipulationInertiaStarting> event occurs when the user raises all fingers from the screen.</span></span> <span data-ttu-id="60f79-135">코드에는 초기 속도 이동, 확장 및 사각형의 회전에 대 한 선언을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="60f79-135">The code sets the initial velocity and deceleration for the movement, expansion, and rotation of the rectangle.</span></span>  
  
     [!code-csharp[BasicManipulation#ManipulationInertiaStarting](../../../../samples/snippets/csharp/VS_Snippets_Wpf/basicmanipulation/csharp/mainwindow.xaml.cs#manipulationinertiastarting)]
     [!code-vb[BasicManipulation#ManipulationInertiaStarting](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/basicmanipulation/visualbasic/mainwindow.xaml.vb#manipulationinertiastarting)]  
  
7.  <span data-ttu-id="60f79-136">프로젝트를 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="60f79-136">Build and run the project.</span></span>  
  
     <span data-ttu-id="60f79-137">창에 나타나는 빨간색 사각형이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="60f79-137">You should see a red square appear in the window.</span></span>  
  
## <a name="testing-the-application"></a><span data-ttu-id="60f79-138">응용 프로그램 테스트</span><span class="sxs-lookup"><span data-stu-id="60f79-138">Testing the Application</span></span>  
 <span data-ttu-id="60f79-139">응용 프로그램을 테스트 하려면 다음 조작을 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="60f79-139">To test the application, try the following manipulations.</span></span> <span data-ttu-id="60f79-140">Note 동시에 다음 중 하나 이상 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60f79-140">Note that you can do more than one of the following at the same time.</span></span>  
  
-   <span data-ttu-id="60f79-141">이동 하는 <xref:System.Windows.Shapes.Rectangle>, 위에 손가락을 놓고는 <xref:System.Windows.Shapes.Rectangle> 화면에서 손가락을 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="60f79-141">To move the <xref:System.Windows.Shapes.Rectangle>, put a finger on the <xref:System.Windows.Shapes.Rectangle> and move the finger across the screen.</span></span>  
  
-   <span data-ttu-id="60f79-142">크기를 조정 하려면는 <xref:System.Windows.Shapes.Rectangle>에 두 손가락을 배치는 <xref:System.Windows.Shapes.Rectangle> 가까워지거나 함께 또는 서로 다른에서 멀리 손가락을 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="60f79-142">To resize the <xref:System.Windows.Shapes.Rectangle>, put two fingers on the <xref:System.Windows.Shapes.Rectangle> and move the fingers closer together or farther apart from each other.</span></span>  
  
-   <span data-ttu-id="60f79-143">회전 하려면는 <xref:System.Windows.Shapes.Rectangle>에 두 손가락을 배치는 <xref:System.Windows.Shapes.Rectangle> 서로 손가락의 회전 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60f79-143">To rotate the <xref:System.Windows.Shapes.Rectangle>, put two fingers on the <xref:System.Windows.Shapes.Rectangle> and rotate the fingers around each other.</span></span>  
  
 <span data-ttu-id="60f79-144">관성 시킬 신속 하 게 발생 화면에서 손가락 이전 조작을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="60f79-144">To cause inertia, quickly raise your fingers from the screen as you perform the previous manipulations.</span></span> <span data-ttu-id="60f79-145"><xref:System.Windows.Shapes.Rectangle> 이동, 크기 조정 또는 회전 중지 하기 전에 몇 초 동안 계속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="60f79-145">The <xref:System.Windows.Shapes.Rectangle> will continue to move, resize, or rotate for a few seconds before it stops.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60f79-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="60f79-146">See Also</span></span>  
 <xref:System.Windows.UIElement.ManipulationStarting?displayProperty=nameWithType>  
 <xref:System.Windows.UIElement.ManipulationDelta?displayProperty=nameWithType>  
 <xref:System.Windows.UIElement.ManipulationInertiaStarting?displayProperty=nameWithType>
