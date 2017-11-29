---
title: "연습: WPF에서 Windows Forms 컨트롤 정렬"
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
- hybrid applications [WPF interoperability]
- arranging controls [WPF]
ms.assetid: a1db8049-15c7-45d6-ae3d-36a6735cb848
caps.latest.revision: "31"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f78da83657c4c1bd913f67c9e612264cc5dbdf99
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-arranging-windows-forms-controls-in-wpf"></a><span data-ttu-id="58bc3-102">연습: WPF에서 Windows Forms 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="58bc3-102">Walkthrough: Arranging Windows Forms Controls in WPF</span></span>
<span data-ttu-id="58bc3-103">이 연습에서는 사용 하는 방법을 보여 줍니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 레이아웃을 정렬 하는 기능 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 하이브리드 응용 프로그램의 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-103">This walkthrough shows you how to use [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout features to arrange [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls in a hybrid application.</span></span>  
  
 <span data-ttu-id="58bc3-104">이 연습에서 설명하는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-104">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="58bc3-105">프로젝트 만들기.</span><span class="sxs-lookup"><span data-stu-id="58bc3-105">Creating the project.</span></span>  
  
-   <span data-ttu-id="58bc3-106">기본 레이아웃 설정 사용</span><span class="sxs-lookup"><span data-stu-id="58bc3-106">Using default layout settings.</span></span>  
  
-   <span data-ttu-id="58bc3-107">콘텐츠에 맞게 크기 조정</span><span class="sxs-lookup"><span data-stu-id="58bc3-107">Sizing to content.</span></span>  
  
-   <span data-ttu-id="58bc3-108">절대 위치 사용</span><span class="sxs-lookup"><span data-stu-id="58bc3-108">Using absolute positioning.</span></span>  
  
-   <span data-ttu-id="58bc3-109">명시적으로 크기 지정</span><span class="sxs-lookup"><span data-stu-id="58bc3-109">Specifying size explicitly.</span></span>  
  
-   <span data-ttu-id="58bc3-110">레이아웃 속성 설정</span><span class="sxs-lookup"><span data-stu-id="58bc3-110">Setting layout properties.</span></span>  
  
-   <span data-ttu-id="58bc3-111">z 순서 제한 사항 이해</span><span class="sxs-lookup"><span data-stu-id="58bc3-111">Understanding z-order limitations.</span></span>  
  
-   <span data-ttu-id="58bc3-112">도킹</span><span class="sxs-lookup"><span data-stu-id="58bc3-112">Docking.</span></span>  
  
-   <span data-ttu-id="58bc3-113">표시 유형 설정</span><span class="sxs-lookup"><span data-stu-id="58bc3-113">Setting visibility.</span></span>  
  
-   <span data-ttu-id="58bc3-114">늘어나지 않는 컨트롤 호스트</span><span class="sxs-lookup"><span data-stu-id="58bc3-114">Hosting a control that does not stretch.</span></span>  
  
-   <span data-ttu-id="58bc3-115">배율 조정</span><span class="sxs-lookup"><span data-stu-id="58bc3-115">Scaling.</span></span>  
  
-   <span data-ttu-id="58bc3-116">회전</span><span class="sxs-lookup"><span data-stu-id="58bc3-116">Rotating.</span></span>  
  
-   <span data-ttu-id="58bc3-117">안쪽 여백 및 여백 설정</span><span class="sxs-lookup"><span data-stu-id="58bc3-117">Setting padding and margins.</span></span>  
  
-   <span data-ttu-id="58bc3-118">동적 레이아웃 컨테이너 사용</span><span class="sxs-lookup"><span data-stu-id="58bc3-118">Using dynamic layout containers.</span></span>  
  
 <span data-ttu-id="58bc3-119">이 연습에서 설명 하는 작업의 전체 코드 목록을 보려면 [WPF 샘플에서 Windows Forms 컨트롤 정렬](http://go.microsoft.com/fwlink/?LinkID=159971)합니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-119">For a complete code listing of the tasks illustrated in this walkthrough, see [Arranging Windows Forms Controls in WPF Sample](http://go.microsoft.com/fwlink/?LinkID=159971).</span></span>  
  
 <span data-ttu-id="58bc3-120">작업을 완료 하는 경우 이해 것 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 레이아웃 기능에서 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-기반 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-120">When you are finished, you will have an understanding of [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] layout features in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based applications.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="58bc3-121">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="58bc3-121">Prerequisites</span></span>  
 <span data-ttu-id="58bc3-122">이 연습을 완료하려면 다음 구성 요소가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-122">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)]<span data-ttu-id="58bc3-123">.</span><span class="sxs-lookup"><span data-stu-id="58bc3-123">.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="58bc3-124">프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="58bc3-124">Creating the Project</span></span>  
  
#### <a name="to-create-and-set-up-the-project"></a><span data-ttu-id="58bc3-125">프로젝트를 만들고 설정하려면</span><span class="sxs-lookup"><span data-stu-id="58bc3-125">To create and set up the project</span></span>  
  
1.  <span data-ttu-id="58bc3-126">이라는 WPF 응용 프로그램 프로젝트 만들기 `WpfLayoutHostingWf`합니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-126">Create a WPF Application project named `WpfLayoutHostingWf`.</span></span>  
  
2.  <span data-ttu-id="58bc3-127">솔루션 탐색기에서 다음 어셈블리에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-127">In Solution Explorer, add references to the following assemblies.</span></span>  
  
    -   <span data-ttu-id="58bc3-128">WindowsFormsIntegration</span><span class="sxs-lookup"><span data-stu-id="58bc3-128">WindowsFormsIntegration</span></span>  
  
    -   <span data-ttu-id="58bc3-129">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="58bc3-129">System.Windows.Forms</span></span>  
  
    -   <span data-ttu-id="58bc3-130">System.Drawing</span><span class="sxs-lookup"><span data-stu-id="58bc3-130">System.Drawing</span></span>  
  
3.  <span data-ttu-id="58bc3-131">MainWindow.xaml을 두 번 클릭하여 XAML 보기에서 엽니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-131">Double-click MainWindow.xaml to open it in XAML view.</span></span>  
  
4.  <span data-ttu-id="58bc3-132">에 <xref:System.Windows.Window> 요소를 다음 추가 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 네임 스페이스 매핑을 합니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-132">In the <xref:System.Windows.Window> element, add the following [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] namespace mapping.</span></span>  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5.  <span data-ttu-id="58bc3-133">에 <xref:System.Windows.Controls.Grid> 요소 집합에서 <xref:System.Windows.Controls.Grid.ShowGridLines%2A> 속성을 `true` 5 개의 행과 열을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-133">In the <xref:System.Windows.Controls.Grid> element set the <xref:System.Windows.Controls.Grid.ShowGridLines%2A> property to `true` and define five rows and three columns.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#2)]  
  
## <a name="using-default-layout-settings"></a><span data-ttu-id="58bc3-134">기본 레이아웃 설정 사용</span><span class="sxs-lookup"><span data-stu-id="58bc3-134">Using Default Layout Settings</span></span>  
 <span data-ttu-id="58bc3-135">기본적으로는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 호스팅된에 대 한 레이아웃을 처리 하는 요소 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-135">By default, the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element handles the layout for the hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control.</span></span>  
  
#### <a name="to-use-default-layout-settings"></a><span data-ttu-id="58bc3-136">기본 레이아웃 설정을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="58bc3-136">To use default layout settings</span></span>  
  
1.  <span data-ttu-id="58bc3-137">다음 XAML을 복사는 <xref:System.Windows.Controls.Grid> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-137">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#3)]  
  
2.  <span data-ttu-id="58bc3-138">F5 키를 눌러 응용 프로그램을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-138">Press F5 to build and run the application.</span></span> <span data-ttu-id="58bc3-139">[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] <xref:System.Windows.Forms.Button?displayProperty=nameWithType> 컨트롤이에 표시 되는 <xref:System.Windows.Controls.Canvas>합니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-139">The [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<xref:System.Windows.Forms.Button?displayProperty=nameWithType> control appears in the <xref:System.Windows.Controls.Canvas>.</span></span> <span data-ttu-id="58bc3-140">호스팅된 컨트롤이 해당 내용에 따라 크기가 및 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소 호스팅된 컨트롤에 맞게 크기가 조정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-140">The hosted control is sized based on its content, and the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is sized to accommodate the hosted control.</span></span>  
  
## <a name="sizing-to-content"></a><span data-ttu-id="58bc3-141">콘텐츠에 맞게 크기 조정</span><span class="sxs-lookup"><span data-stu-id="58bc3-141">Sizing to Content</span></span>  
 <span data-ttu-id="58bc3-142"><xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소 호스팅된 컨트롤의 내용을 제대로 표시의 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-142">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element ensures that the hosted control is sized to display its content properly.</span></span>  
  
#### <a name="to-size-to-content"></a><span data-ttu-id="58bc3-143">콘텐츠 크기를 조정하려면</span><span class="sxs-lookup"><span data-stu-id="58bc3-143">To size to content</span></span>  
  
1.  <span data-ttu-id="58bc3-144">다음 XAML을 복사는 <xref:System.Windows.Controls.Grid> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-144">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#4)]  
  
2.  <span data-ttu-id="58bc3-145">F5 키를 눌러 응용 프로그램을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-145">Press F5 to build and run the application.</span></span> <span data-ttu-id="58bc3-146">긴 텍스트 문자열과 글꼴 크기를 올바르게 표시 하려면 두 개의 새 단추 컨트롤의 크기가 및 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소는 호스트 된 컨트롤에 맞게 크기가 조정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-146">The two new button controls are sized to display the longer text string and larger font size properly, and the <xref:System.Windows.Forms.Integration.WindowsFormsHost> elements are resized to accommodate the hosted controls.</span></span>  
  
## <a name="using-absolute-positioning"></a><span data-ttu-id="58bc3-147">절대 위치 사용</span><span class="sxs-lookup"><span data-stu-id="58bc3-147">Using Absolute Positioning</span></span>  
 <span data-ttu-id="58bc3-148">절대 위치를 배치 하는 데 사용할 수는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 사용자 인터페이스 (UI)에 있는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-148">You can use absolute positioning to place the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element anywhere in the user interface (UI).</span></span>  
  
#### <a name="to-use-absolute-positioning"></a><span data-ttu-id="58bc3-149">절대 위치를 사용하려면</span><span class="sxs-lookup"><span data-stu-id="58bc3-149">To use absolute positioning</span></span>  
  
1.  <span data-ttu-id="58bc3-150">다음 XAML을 복사는 <xref:System.Windows.Controls.Grid> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-150">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#5)]  
  
2.  <span data-ttu-id="58bc3-151">F5 키를 눌러 응용 프로그램을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-151">Press F5 to build and run the application.</span></span> <span data-ttu-id="58bc3-152"><xref:System.Windows.Forms.Integration.WindowsFormsHost> 표 형태 셀의 위쪽에서 20 픽셀, 왼쪽에서 20 픽셀 요소가 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-152">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is placed 20 pixels from the top side of the grid cell and 20 pixels from the left.</span></span>  
  
## <a name="specifying-size-explicitly"></a><span data-ttu-id="58bc3-153">명시적으로 크기 지정</span><span class="sxs-lookup"><span data-stu-id="58bc3-153">Specifying Size Explicitly</span></span>  
 <span data-ttu-id="58bc3-154">크기를 지정할 수는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 사용 하 여 요소는 <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-154">You can specify the size of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element using the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties.</span></span>  
  
#### <a name="to-specify-size-explicitly"></a><span data-ttu-id="58bc3-155">명시적으로 크기를 지정하려면</span><span class="sxs-lookup"><span data-stu-id="58bc3-155">To specify size explicitly</span></span>  
  
1.  <span data-ttu-id="58bc3-156">다음 XAML을 복사는 <xref:System.Windows.Controls.Grid> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-156">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#6)]  
  
2.  <span data-ttu-id="58bc3-157">F5 키를 눌러 응용 프로그램을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-157">Press F5 to build and run the application.</span></span> <span data-ttu-id="58bc3-158"><xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소가 기본 레이아웃 설정 보다 작은 70 픽셀 너비 50 픽셀의 크기를 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-158">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is set to a size of 50 pixels wide by 70 pixels high, which is smaller than the default layout settings.</span></span> <span data-ttu-id="58bc3-159">콘텐츠는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤을 그에 따라 다시 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-159">The content of the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is rearranged accordingly.</span></span>  
  
## <a name="setting-layout-properties"></a><span data-ttu-id="58bc3-160">레이아웃 속성 설정</span><span class="sxs-lookup"><span data-stu-id="58bc3-160">Setting Layout Properties</span></span>  
 <span data-ttu-id="58bc3-161">속성을 사용 하 여 호스팅된 컨트롤에 레이아웃 관련 속성을 항상 설정 된 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-161">Always set layout-related properties on the hosted control by using the properties of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="58bc3-162">호스트된 컨트롤에서 직접 레이아웃 속성을 설정하면 의도하지 않은 결과가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-162">Setting layout properties directly on the hosted control will yield unintended results.</span></span>  
  
 <span data-ttu-id="58bc3-163">호스팅된 컨트롤에 대해 레이아웃 관련 속성을 설정 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-163">Setting layout-related properties on the hosted control in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] has no effect.</span></span>  
  
#### <a name="to-see-the-effects-of-setting-properties-on-the-hosted-control"></a><span data-ttu-id="58bc3-164">호스트된 컨트롤에서 속성 설정의 결과를 확인하려면</span><span class="sxs-lookup"><span data-stu-id="58bc3-164">To see the effects of setting properties on the hosted control</span></span>  
  
1.  <span data-ttu-id="58bc3-165">다음 XAML을 복사는 <xref:System.Windows.Controls.Grid> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-165">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#7)]  
  
2.  <span data-ttu-id="58bc3-166">솔루션 탐색기에서 MainWindow.xaml.</span><span class="sxs-lookup"><span data-stu-id="58bc3-166">In Solution Explorer, double-click MainWindow.xaml.</span></span> <span data-ttu-id="58bc3-167">vb 또는 MainWindow.xaml.cs를 두 번 클릭하여 코드 편집기에서 엽니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-167">vb or MainWindow.xaml.cs to open it in the Code Editor.</span></span>  
  
3.  <span data-ttu-id="58bc3-168">다음 코드를 복사는 `MainWindow` 클래스 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-168">Copy the following code into the `MainWindow` class definition.</span></span>  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#101)]
     [!code-vb[WpfLayoutHostingWfWithXaml#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#101)]  
  
4.  <span data-ttu-id="58bc3-169">F5 키를 눌러 응용 프로그램을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-169">Press F5 to build and run the application.</span></span>  
  
5.  <span data-ttu-id="58bc3-170">클릭는 **Click me** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-170">Click the **Click me** button.</span></span> <span data-ttu-id="58bc3-171">`button1_Click` 이벤트 처리기 설정은 <xref:System.Windows.Forms.Control.Top%2A> 및 <xref:System.Windows.Forms.Control.Left%2A> 호스팅된 컨트롤의 속성에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-171">The `button1_Click` event handler sets the <xref:System.Windows.Forms.Control.Top%2A> and <xref:System.Windows.Forms.Control.Left%2A> properties on the hosted control.</span></span> <span data-ttu-id="58bc3-172">이 인해 내 재배치 호스팅된 컨트롤에서 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-172">This causes the hosted control to be repositioned within the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="58bc3-173">호스트는 동일한 화면 영역을 유지하지만 호스트된 컨트롤은 잘립니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-173">The host maintains the same screen area, but the hosted control is clipped.</span></span> <span data-ttu-id="58bc3-174">호스팅된 컨트롤을 채우는 항상 대신는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-174">Instead, the hosted control should always fill the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span>  
  
## <a name="understanding-z-order-limitations"></a><span data-ttu-id="58bc3-175">Z 순서 제한 사항 이해</span><span class="sxs-lookup"><span data-stu-id="58bc3-175">Understanding Z-Order Limitations</span></span>  
 <span data-ttu-id="58bc3-176">기본적으로 표시 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소는 항상의 맨 위에 그려집니다 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 요소 z-순서에 따라 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-176">By default, visible <xref:System.Windows.Forms.Integration.WindowsFormsHost> elements are always drawn on top of other [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elements, and they are unaffected by z-order.</span></span> <span data-ttu-id="58bc3-177">Z 순서 지정을 활성화 하려면 설정는 <xref:System.Windows.Interop.HwndHost.IsRedirected%2A> 의 속성은 <xref:System.Windows.Forms.Integration.WindowsFormsHost> true로 및 <xref:System.Windows.Interop.HwndHost.CompositionMode%2A> 속성을 <xref:System.Windows.Interop.CompositionMode.Full> 또는 <xref:System.Windows.Interop.CompositionMode.OutputOnly>합니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-177">To enable z-ordering, set the <xref:System.Windows.Interop.HwndHost.IsRedirected%2A> property of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> to true and the <xref:System.Windows.Interop.HwndHost.CompositionMode%2A> property to <xref:System.Windows.Interop.CompositionMode.Full> or <xref:System.Windows.Interop.CompositionMode.OutputOnly>.</span></span>  
  
#### <a name="to-see-the-default-z-order-behavior"></a><span data-ttu-id="58bc3-178">기본 z 순서 동작을 확인하려면</span><span class="sxs-lookup"><span data-stu-id="58bc3-178">To see the default z-order behavior</span></span>  
  
1.  <span data-ttu-id="58bc3-179">다음 XAML을 복사는 <xref:System.Windows.Controls.Grid> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-179">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#8)]  
  
2.  <span data-ttu-id="58bc3-180">F5 키를 눌러 응용 프로그램을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-180">Press F5 to build and run the application.</span></span> <span data-ttu-id="58bc3-181"><xref:System.Windows.Forms.Integration.WindowsFormsHost> label 요소 위에 그려집니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-181">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is painted over the label element.</span></span>  
  
#### <a name="to-see-the-z-order-behavior-when-isredirected-is-true"></a><span data-ttu-id="58bc3-182">IsRedirected가 true일 때 z 순서 동작을 확인하려면</span><span class="sxs-lookup"><span data-stu-id="58bc3-182">To see the z-order behavior when IsRedirected is true</span></span>  
  
1.  <span data-ttu-id="58bc3-183">다음 XAML 개씩을 z 순서를 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-183">Replace the previous z-order example with the following XAML.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#8b](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml#8b)]  
  
     <span data-ttu-id="58bc3-184">F5 키를 눌러 응용 프로그램을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-184">Press F5 to build and run the application.</span></span> <span data-ttu-id="58bc3-185">Label 요소 위에 그려집니다는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-185">The label element is painted over the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span>  
  
## <a name="docking"></a><span data-ttu-id="58bc3-186">도킹</span><span class="sxs-lookup"><span data-stu-id="58bc3-186">Docking</span></span>  
 <span data-ttu-id="58bc3-187"><xref:System.Windows.Forms.Integration.WindowsFormsHost>요소는 지원 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 도킹 합니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-187"><xref:System.Windows.Forms.Integration.WindowsFormsHost> element supports [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] docking.</span></span> <span data-ttu-id="58bc3-188">설정의 <xref:System.Windows.Controls.DockPanel.Dock%2A> 연결 된 속성에서 호스팅된 컨트롤에 도킹을 <xref:System.Windows.Controls.DockPanel> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-188">Set the <xref:System.Windows.Controls.DockPanel.Dock%2A> attached property to dock the hosted control in a <xref:System.Windows.Controls.DockPanel> element.</span></span>  
  
#### <a name="to-dock-a-hosted-control"></a><span data-ttu-id="58bc3-189">호스트된 컨트롤을 도킹하려면</span><span class="sxs-lookup"><span data-stu-id="58bc3-189">To dock a hosted control</span></span>  
  
1.  <span data-ttu-id="58bc3-190">다음 XAML을 복사는 <xref:System.Windows.Controls.Grid> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-190">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#9)]  
  
2.  <span data-ttu-id="58bc3-191">F5 키를 눌러 응용 프로그램을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-191">Press F5 to build and run the application.</span></span> <span data-ttu-id="58bc3-192"><xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소 오른쪽에 도킹 된 <xref:System.Windows.Controls.DockPanel> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-192">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is docked to the right side of the <xref:System.Windows.Controls.DockPanel> element.</span></span>  
  
## <a name="setting-visibility"></a><span data-ttu-id="58bc3-193">표시 유형 설정</span><span class="sxs-lookup"><span data-stu-id="58bc3-193">Setting Visibility</span></span>  
 <span data-ttu-id="58bc3-194">만들 수 있습니다 프로그램 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 보이지 않는 제어 하거나 설정 하 여 축소할 수는 <xref:System.Windows.UIElement.Visibility%2A> 속성에는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-194">You can make your [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control invisible or collapse it by setting the <xref:System.Windows.UIElement.Visibility%2A> property on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span> <span data-ttu-id="58bc3-195">컨트롤이 보이지 않으면 표시되지는 않지만 레이아웃 공간은 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-195">When a control is invisible, it is not displayed, but it occupies layout space.</span></span> <span data-ttu-id="58bc3-196">컨트롤이 축소되면 표시되지 않고 레이아웃 공간도 자치하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-196">When a control is collapsed, it is not displayed, nor does it occupy layout space.</span></span>  
  
#### <a name="to-set-the-visibility-of-a-hosted-control"></a><span data-ttu-id="58bc3-197">호스트된 컨트롤의 표시 유형을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="58bc3-197">To set the visibility of a hosted control</span></span>  
  
1.  <span data-ttu-id="58bc3-198">다음 XAML을 복사는 <xref:System.Windows.Controls.Grid> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-198">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#10)]  
  
2.  <span data-ttu-id="58bc3-199">MainWindow.xaml.vb 또는 MainWindow.xaml.cs에서 다음 코드를 클래스 정의에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-199">In MainWindow.xaml.vb or MainWindow.xaml.cs, copy the following code into the class definition.</span></span>  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#102)]
     [!code-vb[WpfLayoutHostingWfWithXaml#102](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#102)]  
  
3.  <span data-ttu-id="58bc3-200">F5 키를 눌러 응용 프로그램을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-200">Press F5 to build and run the application.</span></span>  
  
4.  <span data-ttu-id="58bc3-201">클릭는 **보이지 않도록 하려면 클릭** 단추를 눌러는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 보이지 않는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-201">Click the **Click to make invisible** button to make the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element invisible.</span></span>  
  
5.  <span data-ttu-id="58bc3-202">클릭는 **축소 하려면 클릭** 단추를 숨기는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 레이아웃에서 요소 완전히 합니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-202">Click the **Click to collapse** button to hide the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element from the layout entirely.</span></span> <span data-ttu-id="58bc3-203">경우는 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤 축소 되는 경우 요소는 해당 공간을 차지 하도록 다시 정렬 됩니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-203">When the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] control is collapsed, the surrounding elements are rearranged to occupy its space.</span></span>  
  
## <a name="hosting-a-control-that-does-not-stretch"></a><span data-ttu-id="58bc3-204">늘어나지 않는 컨트롤 호스트</span><span class="sxs-lookup"><span data-stu-id="58bc3-204">Hosting a Control That Does Not Stretch</span></span>  
 <span data-ttu-id="58bc3-205">일부 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤 크기가 고정 되어 있으며 레이아웃의 사용 가능한 공간을 채우기 위해 늘여 지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-205">Some [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls have a fixed size and do not stretch to fill available space in the layout.</span></span> <span data-ttu-id="58bc3-206">예를 들어는 <xref:System.Windows.Forms.MonthCalendar> 컨트롤 고정 된 공간에 월을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-206">For example, the <xref:System.Windows.Forms.MonthCalendar> control displays a month in a fixed space.</span></span>  
  
#### <a name="to-host-a-control-that-does-not-stretch"></a><span data-ttu-id="58bc3-207">늘어나지 않는 컨트롤을 호스트하려면</span><span class="sxs-lookup"><span data-stu-id="58bc3-207">To host a control that does not stretch</span></span>  
  
1.  <span data-ttu-id="58bc3-208">다음 XAML을 복사는 <xref:System.Windows.Controls.Grid> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-208">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#11)]  
  
2.  <span data-ttu-id="58bc3-209">F5 키를 눌러 응용 프로그램을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-209">Press F5 to build and run the application.</span></span> <span data-ttu-id="58bc3-210"><xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소 가운데에 그리드 행에 있지만 사용 가능한 공간을 채우기 위해 늘어나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-210">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element is centered in the grid row, but it is not stretched to fill the available space.</span></span> <span data-ttu-id="58bc3-211">호스팅된 하 여 표시 되는 월을 두 개 이상의 창 충분히 클 경우 표시 될 수 있습니다 <xref:System.Windows.Forms.MonthCalendar> 컨트롤 이지만 이러한 행에 가운데 맞춤 됩니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-211">If the window is large enough, you may see two or more months displayed by the hosted <xref:System.Windows.Forms.MonthCalendar> control, but these are centered in the row.</span></span> <span data-ttu-id="58bc3-212">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 레이아웃 엔진의 크기를 사용 가능한 공간을 채울 수 있는 요소에 중점을 합니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-212">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout engine centers elements that cannot be sized to fill the available space.</span></span>  
  
## <a name="scaling"></a><span data-ttu-id="58bc3-213">배율 조정</span><span class="sxs-lookup"><span data-stu-id="58bc3-213">Scaling</span></span>  
 <span data-ttu-id="58bc3-214">와 달리 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 요소, 대부분 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤은 지속적으로 확장 가능 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-214">Unlike [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elements, most [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls are not continuously scalable.</span></span> <span data-ttu-id="58bc3-215">기본적으로는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소 가능한 경우 호스팅된 컨트롤의 크기를 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-215">By default, the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element scales its hosted control when possible.</span></span>  <span data-ttu-id="58bc3-216">완전 한 확장을 사용 하려면 설정는 <xref:System.Windows.Interop.HwndHost.IsRedirected%2A> 의 속성은 <xref:System.Windows.Forms.Integration.WindowsFormsHost> true로 및 <xref:System.Windows.Interop.HwndHost.CompositionMode%2A> 속성을 <xref:System.Windows.Interop.CompositionMode.Full> 또는 <xref:System.Windows.Interop.CompositionMode.OutputOnly>합니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-216">To enable full-fledged scaling, set the <xref:System.Windows.Interop.HwndHost.IsRedirected%2A> property of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> to true and the <xref:System.Windows.Interop.HwndHost.CompositionMode%2A> property to <xref:System.Windows.Interop.CompositionMode.Full> or <xref:System.Windows.Interop.CompositionMode.OutputOnly>.</span></span>  
  
#### <a name="to-scale-a-hosted-control-by-using-the-default-behavior"></a><span data-ttu-id="58bc3-217">기본 동작을 사용하여 호스트된 컨트롤의 배율을 조정하려면</span><span class="sxs-lookup"><span data-stu-id="58bc3-217">To scale a hosted control by using the default behavior</span></span>  
  
1.  <span data-ttu-id="58bc3-218">다음 XAML을 복사는 <xref:System.Windows.Controls.Grid> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-218">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#12)]  
  
2.  <span data-ttu-id="58bc3-219">F5 키를 눌러 응용 프로그램을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-219">Press F5 to build and run the application.</span></span> <span data-ttu-id="58bc3-220">호스트된 컨트롤과 해당 주변 요소가 0.5의 비율로 배율 조정됩니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-220">The hosted control and its surrounding elements are scaled by a factor of 0.5.</span></span> <span data-ttu-id="58bc3-221">그러나 호스트된 컨트롤의 글꼴은 배율 조정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-221">However, the hosted control's font is not scaled.</span></span>  
  
#### <a name="to-scale-a-hosted-control-by-setting-isredirected-to-true"></a><span data-ttu-id="58bc3-222">IsRedirected를 true로 설정하여 호스트된 컨트롤의 배율을 조정하려면</span><span class="sxs-lookup"><span data-stu-id="58bc3-222">To scale a hosted control by setting IsRedirected to true</span></span>  
  
1.  <span data-ttu-id="58bc3-223">위의 배율 조정 예제를 다음 XAML로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-223">Replace the previous scaling example with the following XAML.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#12b](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml#12b)]  
  
2.  <span data-ttu-id="58bc3-224">F5 키를 눌러 응용 프로그램을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-224">Press F5 to build and run the application.</span></span> <span data-ttu-id="58bc3-225">호스트된 컨트롤, 주변 요소 및 호스트된 컨트롤의 글꼴이 0.5의 비율로 배율 조정됩니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-225">The hosted control, its surrounding elements, and the hosted control's font are scaled by a factor of 0.5.</span></span>  
  
## <a name="rotating"></a><span data-ttu-id="58bc3-226">회전</span><span class="sxs-lookup"><span data-stu-id="58bc3-226">Rotating</span></span>  
 <span data-ttu-id="58bc3-227">와 달리 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 요소 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤 회전을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-227">Unlike [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elements, [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls do not support rotation.</span></span> <span data-ttu-id="58bc3-228">기본적으로는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 다른 요소를 회전 하지 않습니다 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 회전 변환을 적용 하는 경우 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-228">By default, the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element does not rotate with other [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elements when a rotation transformation is applied.</span></span> <span data-ttu-id="58bc3-229">180도 발생 이외의 회전 값에서 <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-229">Any rotation value other than 180 degrees raises the <xref:System.Windows.Forms.Integration.WindowsFormsHost.LayoutError> event.</span></span>  <span data-ttu-id="58bc3-230">다른 각도로 회전을 사용 하려면 설정는 <xref:System.Windows.Interop.HwndHost.IsRedirected%2A> 의 속성은 <xref:System.Windows.Forms.Integration.WindowsFormsHost> true로 및 <xref:System.Windows.Interop.HwndHost.CompositionMode%2A> 속성을 <xref:System.Windows.Interop.CompositionMode.Full> 또는 <xref:System.Windows.Interop.CompositionMode.OutputOnly>합니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-230">To enable rotating to any angle, set the <xref:System.Windows.Interop.HwndHost.IsRedirected%2A> property of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> to true and the <xref:System.Windows.Interop.HwndHost.CompositionMode%2A> property to <xref:System.Windows.Interop.CompositionMode.Full> or <xref:System.Windows.Interop.CompositionMode.OutputOnly>.</span></span>  
  
#### <a name="to-see-the-effect-of-rotation-in-a-hybrid-application"></a><span data-ttu-id="58bc3-231">혼합 응용 프로그램에서 회전의 결과를 확인하려면</span><span class="sxs-lookup"><span data-stu-id="58bc3-231">To see the effect of rotation in a hybrid application</span></span>  
  
1.  <span data-ttu-id="58bc3-232">다음 XAML을 복사는 <xref:System.Windows.Controls.Grid> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-232">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#13)]  
  
2.  <span data-ttu-id="58bc3-233">F5 키를 눌러 응용 프로그램을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-233">Press F5 to build and run the application.</span></span> <span data-ttu-id="58bc3-234">호스트된 컨트롤은 회전되지 않지만 주변 요소는 180도 각도로 회전됩니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-234">The hosted control is not rotated, but its surrounding elements are rotated by an angle of 180 degrees.</span></span> <span data-ttu-id="58bc3-235">요소를 표시하려면 창의 크기를 조정해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-235">You may have to resize the window to see the elements.</span></span>  
  
#### <a name="to-see-the-effect-of-rotation-in-a-hybrid-application-when-isredirected-is-true"></a><span data-ttu-id="58bc3-236">IsRedirected가 true인 경우 혼합 응용 프로그램에서 회전의 결과를 확인하려면</span><span class="sxs-lookup"><span data-stu-id="58bc3-236">To see the effect of rotation in a hybrid application when IsRedirected is true</span></span>  
  
1.  <span data-ttu-id="58bc3-237">위의 회전 예제를 다음 XAML로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-237">Replace the previous rotation example with the following XAML.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#13b](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml#13b)]  
  
2.  <span data-ttu-id="58bc3-238">F5 키를 눌러 응용 프로그램을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-238">Press F5 to build and run the application.</span></span> <span data-ttu-id="58bc3-239">호스트된 컨트롤이 회전됩니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-239">The hosted control is rotated.</span></span>  <span data-ttu-id="58bc3-240"><xref:System.Windows.Media.RotateTransform.Angle%2A> 속성 값으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-240">Note that the <xref:System.Windows.Media.RotateTransform.Angle%2A> property can be set to any value.</span></span> <span data-ttu-id="58bc3-241">요소를 표시하려면 창의 크기를 조정해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-241">You may have to resize the window to see the elements.</span></span>  
  
## <a name="setting-padding-and-margins"></a><span data-ttu-id="58bc3-242">안쪽 여백 및 여백 설정</span><span class="sxs-lookup"><span data-stu-id="58bc3-242">Setting Padding and Margins</span></span>  
 <span data-ttu-id="58bc3-243">안쪽 여백 및 안쪽 여백을 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 레이아웃은 안쪽 여백 및 여백을 유사 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-243">Padding and margins in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layout are similar to padding and margins in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span> <span data-ttu-id="58bc3-244">설정 하기만 <xref:System.Windows.Controls.Control.Padding%2A> 및 <xref:System.Windows.FrameworkElement.Margin%2A> 속성에는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-244">Simply set the <xref:System.Windows.Controls.Control.Padding%2A> and <xref:System.Windows.FrameworkElement.Margin%2A> properties on the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element.</span></span>  
  
#### <a name="to-set-padding-and-margins-for-a-hosted-control"></a><span data-ttu-id="58bc3-245">호스트된 컨트롤에 대해 안쪽 여백 및 여백을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="58bc3-245">To set padding and margins for a hosted control</span></span>  
  
1.  <span data-ttu-id="58bc3-246">다음 XAML을 복사는 <xref:System.Windows.Controls.Grid> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-246">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#14)]  
    [!code-xaml[WpfLayoutHostingWfWithXaml#15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#15)]  
  
2.  <span data-ttu-id="58bc3-247">F5 키를 눌러 응용 프로그램을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-247">Press F5 to build and run the application.</span></span> <span data-ttu-id="58bc3-248">안쪽 여백 및 여백 설정이 적용 될 호스팅된 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 컨트롤에 적용 될 것 같은 방식으로 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-248">The padding and margin settings are applied to the hosted [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls in the same way they would be applied in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span>  
  
## <a name="using-dynamic-layout-containers"></a><span data-ttu-id="58bc3-249">동적 레이아웃 컨테이너 사용</span><span class="sxs-lookup"><span data-stu-id="58bc3-249">Using Dynamic Layout Containers</span></span>  
 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]<span data-ttu-id="58bc3-250">두 개의 동적 레이아웃 컨테이너를 제공 <xref:System.Windows.Forms.FlowLayoutPanel> 및 <xref:System.Windows.Forms.TableLayoutPanel>합니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-250"> provides two dynamic layout containers, <xref:System.Windows.Forms.FlowLayoutPanel> and <xref:System.Windows.Forms.TableLayoutPanel>.</span></span> <span data-ttu-id="58bc3-251">이러한 컨테이너에 사용할 수도 있습니다 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 레이아웃 합니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-251">You can also use these containers in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] layouts.</span></span>  
  
#### <a name="to-use-a-dynamic-layout-container"></a><span data-ttu-id="58bc3-252">동적 레이아웃 컨테이너를 사용하려면</span><span class="sxs-lookup"><span data-stu-id="58bc3-252">To use a dynamic layout container</span></span>  
  
1.  <span data-ttu-id="58bc3-253">다음 XAML을 복사는 <xref:System.Windows.Controls.Grid> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-253">Copy the following XAML into the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
     [!code-xaml[WpfLayoutHostingWfWithXaml#16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml#16)]  
  
2.  <span data-ttu-id="58bc3-254">MainWindow.xaml.vb 또는 MainWindow.xaml.cs에서 다음 코드를 클래스 정의에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-254">In MainWindow.xaml.vb or MainWindow.xaml.cs copy the following code into the class definition.</span></span>  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#103](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#103)]
     [!code-vb[WpfLayoutHostingWfWithXaml#103](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#103)]  
  
3.  <span data-ttu-id="58bc3-255">에 대 한 호출 추가 `InitializeFlowLayoutPanel` 생성자에서 메서드.</span><span class="sxs-lookup"><span data-stu-id="58bc3-255">Add a call to the `InitializeFlowLayoutPanel` method in the constructor.</span></span>  
  
     [!code-csharp[WpfLayoutHostingWfWithXaml#104](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/CSharp/Window1.xaml.cs#104)]
     [!code-vb[WpfLayoutHostingWfWithXaml#104](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfLayoutHostingWfWithXaml/VisualBasic/Window1.xaml.vb#104)]  
  
4.  <span data-ttu-id="58bc3-256">F5 키를 눌러 응용 프로그램을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-256">Press F5 to build and run the application.</span></span> <span data-ttu-id="58bc3-257"><xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소 입력의 <xref:System.Windows.Controls.DockPanel>, 및 <xref:System.Windows.Forms.FlowLayoutPanel> 해당 자식 컨트롤을 기본에서 정렬 <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>합니다.</span><span class="sxs-lookup"><span data-stu-id="58bc3-257">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element fills the <xref:System.Windows.Controls.DockPanel>, and <xref:System.Windows.Forms.FlowLayoutPanel> arranges its child controls in the default <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58bc3-258">참고 항목</span><span class="sxs-lookup"><span data-stu-id="58bc3-258">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="58bc3-259">WPF 디자이너</span><span class="sxs-lookup"><span data-stu-id="58bc3-259">WPF Designer</span></span>](http://msdn.microsoft.com/en-us/c6c65214-8411-4e16-b254-163ed4099c26)  
 [<span data-ttu-id="58bc3-260">WindowsFormsHost 요소에 대한 레이아웃 고려 사항</span><span class="sxs-lookup"><span data-stu-id="58bc3-260">Layout Considerations for the WindowsFormsHost Element</span></span>](../../../../docs/framework/wpf/advanced/layout-considerations-for-the-windowsformshost-element.md)  
 [<span data-ttu-id="58bc3-261">WPF 샘플에서 정렬 Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="58bc3-261">Arranging Windows Forms Controls in WPF Sample</span></span>](http://go.microsoft.com/fwlink/?LinkID=159971)  
 [<span data-ttu-id="58bc3-262">연습: WPF에서 Windows Forms 복합 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="58bc3-262">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)  
 [<span data-ttu-id="58bc3-263">연습: Windows Forms에서 WPF 복합 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="58bc3-263">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
