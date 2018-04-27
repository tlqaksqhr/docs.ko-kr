---
title: '연습: WPF에서 ActiveX 컨트롤 호스팅'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ActiveX controls [WPF interoperability]
- hosting ActiveX controls [WPF]
ms.assetid: 1931d292-0dd1-434f-963c-dcda7638d75a
caps.latest.revision: 30
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fc4f577da04fb8ed15bae3c0497b35803a46f08f
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2018
---
# <a name="walkthrough-hosting-an-activex-control-in-wpf"></a><span data-ttu-id="d6c71-102">연습: WPF에서 ActiveX 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="d6c71-102">Walkthrough: Hosting an ActiveX Control in WPF</span></span>
<span data-ttu-id="d6c71-103">향상 된 상호 작용할 수 있도록 브라우저를 사용할 수 있습니다 [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] 의 제어 프로그램 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-기반 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="d6c71-103">To enable improved interaction with browsers, you can use [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] controls in your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based application.</span></span> <span data-ttu-id="d6c71-104">이 연습에서는 호스팅하는 방법을 보여 줍니다.는 [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] 의 컨트롤로 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 페이지.</span><span class="sxs-lookup"><span data-stu-id="d6c71-104">This walkthrough demonstrates how you can host the [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)] as a control on a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] page.</span></span>  
  
 <span data-ttu-id="d6c71-105">이 연습에서 설명하는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d6c71-105">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="d6c71-106">프로젝트 만들기.</span><span class="sxs-lookup"><span data-stu-id="d6c71-106">Creating the project.</span></span>  
  
-   <span data-ttu-id="d6c71-107">ActiveX 컨트롤을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d6c71-107">Creating the ActiveX control.</span></span>  
  
-   <span data-ttu-id="d6c71-108">WPF 페이지에서 ActiveX 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="d6c71-108">Hosting the ActiveX control on a WPF Page.</span></span>  
  
 <span data-ttu-id="d6c71-109">사용 하는 방법을 이해 하 게이 연습을 완료 하는 경우 [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] 의 제어 프로그램 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-기반 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="d6c71-109">When you have completed this walkthrough, you will understand how to use [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] controls in your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-based application.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d6c71-110">전제 조건</span><span class="sxs-lookup"><span data-stu-id="d6c71-110">Prerequisites</span></span>  
 <span data-ttu-id="d6c71-111">이 연습을 완료하려면 다음 구성 요소가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="d6c71-111">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[TLA#tla_wmp](../../../../includes/tlasharptla-wmp-md.md)]<span data-ttu-id="d6c71-112"> Visual Studio가 설치 된 컴퓨터에 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6c71-112"> installed on the computer where Visual Studio is installed.</span></span>  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)]<span data-ttu-id="d6c71-113">.</span><span class="sxs-lookup"><span data-stu-id="d6c71-113">.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="d6c71-114">프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="d6c71-114">Creating the Project</span></span>  
  
#### <a name="to-create-and-set-up-the-project"></a><span data-ttu-id="d6c71-115">프로젝트를 만들고 설정하려면</span><span class="sxs-lookup"><span data-stu-id="d6c71-115">To create and set up the project</span></span>  
  
1.  <span data-ttu-id="d6c71-116">이라는 WPF 응용 프로그램 프로젝트 만들기 `HostingAxInWpf`합니다.</span><span class="sxs-lookup"><span data-stu-id="d6c71-116">Create a WPF Application project named `HostingAxInWpf`.</span></span>  
  
2.  <span data-ttu-id="d6c71-117">Windows Forms 컨트롤 라이브러리 프로젝트를 솔루션에 추가 하 고 프로젝트 이름을 `WmpAxLib`합니다.</span><span class="sxs-lookup"><span data-stu-id="d6c71-117">Add a Windows Forms Control Library project to the solution, and name the project `WmpAxLib`.</span></span>  
  
3.  <span data-ttu-id="d6c71-118">WmpAxLib 프로젝트에서 wmp.dll 라고 하는 Windows Media Player 어셈블리에 대 한 참조를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6c71-118">In the WmpAxLib project, add a reference to the Windows Media Player assembly, which is named wmp.dll.</span></span>  
  
4.  <span data-ttu-id="d6c71-119">열기는 **도구 상자**합니다.</span><span class="sxs-lookup"><span data-stu-id="d6c71-119">Open the **Toolbox**.</span></span>  
  
5.  <span data-ttu-id="d6c71-120">마우스 오른쪽 단추로 클릭는 **도구 상자**, 클릭 하 고 **항목 선택**합니다.</span><span class="sxs-lookup"><span data-stu-id="d6c71-120">Right-click in the **Toolbox**, and then click **Choose Items**.</span></span>  
  
6.  <span data-ttu-id="d6c71-121">클릭는 **COM 구성 요소** 탭을는 **Windows Media Player** 컨트롤을 선택한 다음 클릭 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="d6c71-121">Click the **COM Components** tab, select the **Windows Media Player** control, and then click **OK**.</span></span>  
  
     <span data-ttu-id="d6c71-122">에 Windows Media Player 컨트롤이 추가 되 고 **도구 상자**합니다.</span><span class="sxs-lookup"><span data-stu-id="d6c71-122">The Windows Media Player control is added to the **Toolbox**.</span></span>  
  
7.  <span data-ttu-id="d6c71-123">솔루션 탐색기에서 마우스 오른쪽 단추로 클릭는 **UserControl1** 파일을 선택한 다음 클릭 **이름 바꾸기**합니다.</span><span class="sxs-lookup"><span data-stu-id="d6c71-123">In Solution Explorer, right-click the **UserControl1** file, and then click **Rename**.</span></span>  
  
8.  <span data-ttu-id="d6c71-124">이름을 변경한 `WmpAxControl.vb` 또는 `WmpAxControl.cs`언어에 따라, 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6c71-124">Change the name to `WmpAxControl.vb` or `WmpAxControl.cs`, depending on the language.</span></span>  
  
9. <span data-ttu-id="d6c71-125">모든 참조는 메시지가 클릭 **예**합니다.</span><span class="sxs-lookup"><span data-stu-id="d6c71-125">If you are prompted to rename all references, click **Yes**.</span></span>  
  
## <a name="creating-the-activex-control"></a><span data-ttu-id="d6c71-126">ActiveX 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="d6c71-126">Creating the ActiveX Control</span></span>  
 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]<span data-ttu-id="d6c71-127"> 자동으로 생성 한 <xref:System.Windows.Forms.AxHost> 에 대 한 래퍼 클래스는 [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] 컨트롤 디자인 화면에 추가 된 경우를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6c71-127"> automatically generates an <xref:System.Windows.Forms.AxHost> wrapper class for a [!INCLUDE[TLA#tla_actx](../../../../includes/tlasharptla-actx-md.md)] control when the control is added to a design surface.</span></span> <span data-ttu-id="d6c71-128">다음 절차는 AxInterop.WMPLib.dll 이라는 관리 되는 어셈블리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d6c71-128">The following procedure creates a managed assembly named AxInterop.WMPLib.dll.</span></span>  
  
#### <a name="to-create-the-activex-control"></a><span data-ttu-id="d6c71-129">ActiveX 컨트롤을 만들려면</span><span class="sxs-lookup"><span data-stu-id="d6c71-129">To create the ActiveX control</span></span>  
  
1.  <span data-ttu-id="d6c71-130">Windows Forms 디자이너에서 WmpAxControl.vb 또는 WmpAxControl.cs를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d6c71-130">Open WmpAxControl.vb or WmpAxControl.cs in the Windows Forms Designer.</span></span>  
  
2.  <span data-ttu-id="d6c71-131">**도구 상자**, Windows Media Player 컨트롤 디자인 화면을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6c71-131">From the **Toolbox**, add the Windows Media Player control to the design surface.</span></span>  
  
3.  <span data-ttu-id="d6c71-132">속성 창에서 Windows Media Player 컨트롤의 값을 설정 <xref:System.Windows.Forms.Control.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle.Fill>합니다.</span><span class="sxs-lookup"><span data-stu-id="d6c71-132">In the Properties window, set the value of the Windows Media Player control's <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>  
  
4.  <span data-ttu-id="d6c71-133">WmpAxLib 컨트롤 라이브러리 프로젝트를 빌드하십시오.</span><span class="sxs-lookup"><span data-stu-id="d6c71-133">Build the WmpAxLib control library project.</span></span>  
  
## <a name="hosting-the-activex-control-on-a-wpf-page"></a><span data-ttu-id="d6c71-134">WPF 페이지에서 ActiveX 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="d6c71-134">Hosting the ActiveX Control on a WPF Page</span></span>  
  
#### <a name="to-host-the-activex-control"></a><span data-ttu-id="d6c71-135">ActiveX 컨트롤을 호스트 하려면</span><span class="sxs-lookup"><span data-stu-id="d6c71-135">To host the ActiveX control</span></span>  
  
1.  <span data-ttu-id="d6c71-136">HostingAxInWpf 프로젝트에서 생성 된에 대 한 참조를 추가 [!INCLUDE[TLA2#tla_actx](../../../../includes/tla2sharptla-actx-md.md)] 상호 운용성 어셈블리.</span><span class="sxs-lookup"><span data-stu-id="d6c71-136">In the HostingAxInWpf project, add a reference to the generated [!INCLUDE[TLA2#tla_actx](../../../../includes/tla2sharptla-actx-md.md)] interoperability assembly.</span></span>  
  
     <span data-ttu-id="d6c71-137">이 어셈블리 AxInterop.WMPLib.dll은, Windows Media Player 컨트롤을 가져올 때 WmpAxLib 프로젝트의 디버그 폴더에 추가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d6c71-137">This assembly is named AxInterop.WMPLib.dll and was added to the Debug folder of the WmpAxLib project when you imported the Windows Media Player control.</span></span>  
  
2.  <span data-ttu-id="d6c71-138">WindowsFormsIntegration.dll 라는 WindowsFormsIntegration 어셈블리에 대 한 참조를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6c71-138">Add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>  
  
3.  <span data-ttu-id="d6c71-139">에 대 한 참조 추가 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] System.Windows.Forms.dll 이름으로 지정 된 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="d6c71-139">Add a reference to the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] assembly, which is named System.Windows.Forms.dll.</span></span>  
  
4.  <span data-ttu-id="d6c71-140">WPF Designer의 MainWindow.xaml을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d6c71-140">Open MainWindow.xaml in the WPF Designer.</span></span>  
  
5.  <span data-ttu-id="d6c71-141">이름에서 <xref:System.Windows.Controls.Grid> 요소 `grid1`합니다.</span><span class="sxs-lookup"><span data-stu-id="d6c71-141">Name the <xref:System.Windows.Controls.Grid> element `grid1`.</span></span>  
  
     [!code-xaml[HostingAxInWpf#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingAxInWpf/CSharp/HostingAxInWpf/window1.xaml#1)]  
  
6.  <span data-ttu-id="d6c71-142">디자인 보기 또는 XAML 보기에서 선택 된 <xref:System.Windows.Window> 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d6c71-142">In Design view or XAML view, select the <xref:System.Windows.Window> element.</span></span>  
  
7.  <span data-ttu-id="d6c71-143">속성 창에서 클릭 된 **이벤트** 탭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6c71-143">In the Properties window, click the **Events** tab.</span></span>  
  
8.  <span data-ttu-id="d6c71-144">두 번 클릭 하 여 <xref:System.Windows.FrameworkElement.Loaded> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="d6c71-144">Double-click the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>  
  
9. <span data-ttu-id="d6c71-145">다음 코드를 처리 하는 <xref:System.Windows.FrameworkElement.Loaded> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="d6c71-145">Insert the following code to handle the <xref:System.Windows.FrameworkElement.Loaded> event.</span></span>  
  
     <span data-ttu-id="d6c71-146">이 코드의 인스턴스를 만듭니다.는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 제어 하 고 인스턴스를 추가 `AxWindowsMediaPlayer` 을 자식으로 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6c71-146">This code creates an instance of the <xref:System.Windows.Forms.Integration.WindowsFormsHost> control and adds an instance of the `AxWindowsMediaPlayer` control as its child.</span></span>  
  
     [!code-csharp[HostingAxInWpf#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HostingAxInWpf/CSharp/HostingAxInWpf/window1.xaml.cs#11)]
     [!code-vb[HostingAxInWpf#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HostingAxInWpf/VisualBasic/HostingAxInWpf/window1.xaml.vb#11)]  
  
10. <span data-ttu-id="d6c71-147">F5 키를 눌러 응용 프로그램을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d6c71-147">Press F5 to build and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6c71-148">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d6c71-148">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="d6c71-149">WPF 디자이너</span><span class="sxs-lookup"><span data-stu-id="d6c71-149">WPF Designer</span></span>](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)  
 [<span data-ttu-id="d6c71-150">연습: WPF에서 Windows Forms 복합 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="d6c71-150">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)  
 [<span data-ttu-id="d6c71-151">연습: Windows Forms에서 WPF 복합 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="d6c71-151">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
