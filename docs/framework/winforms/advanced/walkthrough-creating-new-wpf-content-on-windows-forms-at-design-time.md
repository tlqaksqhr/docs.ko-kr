---
title: "연습: 디자인 타임에 Windows Forms에서 새 WPF 콘텐츠 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- interoperability [Windows Forms], WPF and Windows Forms
- WPF content [Windows Forms], hosting in Windows Forms
- hosting WPF content in Windows Forms
- ElementHost control
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: 2e92d8e8-f0e4-4df7-9f07-2acf35cd798c
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cc357b8ad1ff450c699878dfffe1fbb6e2440f49
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time"></a><span data-ttu-id="61f8a-102">연습: 디자인 타임에 Windows Forms에서 새 WPF 콘텐츠 만들기</span><span class="sxs-lookup"><span data-stu-id="61f8a-102">Walkthrough: Creating New WPF Content on Windows Forms at Design Time</span></span>
<span data-ttu-id="61f8a-103">이 항목에서는 Windows Forms 기반 응용 프로그램에서 사용할 WPF(Windows Presentation Foundation) 컨트롤을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="61f8a-103">This topic shows you how to create a Windows Presentation Foundation (WPF) control for use in your Windows Forms-based applications.</span></span>  
  
 <span data-ttu-id="61f8a-104">이 연습에서는 다음 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="61f8a-104">In this walkthrough, you perform the following tasks:</span></span>  
  
-   <span data-ttu-id="61f8a-105">프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="61f8a-105">Create the project.</span></span>  
  
-   <span data-ttu-id="61f8a-106">새 WPF 컨트롤을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="61f8a-106">Create a new WPF control.</span></span>  
  
-   <span data-ttu-id="61f8a-107">새 WPF 컨트롤을 Windows Form에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="61f8a-107">Add the new WPF control to a Windows Form.</span></span> <span data-ttu-id="61f8a-108">WPF 컨트롤이 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤에서 호스트됩니다.</span><span class="sxs-lookup"><span data-stu-id="61f8a-108">The WPF control is hosted in an <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="61f8a-109">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61f8a-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="61f8a-110">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="61f8a-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="61f8a-111">자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="61f8a-111">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="61f8a-112">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="61f8a-112">Prerequisites</span></span>  
 <span data-ttu-id="61f8a-113">이 연습을 완료하려면 다음 구성 요소가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="61f8a-113">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)]<span data-ttu-id="61f8a-114">.</span><span class="sxs-lookup"><span data-stu-id="61f8a-114">.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="61f8a-115">프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="61f8a-115">Creating the Project</span></span>  
 <span data-ttu-id="61f8a-116">첫 번째 단계에서는 Windows Forms 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="61f8a-116">The first step is to create the Windows Forms project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="61f8a-117">WPF 콘텐츠를 호스트하는 경우 C# 및 Visual Basic 프로젝트만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="61f8a-117">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="61f8a-118">프로젝트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="61f8a-118">To create the project</span></span>  
  
-   <span data-ttu-id="61f8a-119">Visual Basic 또는 Visual C# 라는 새 Windows Forms 응용 프로그램 프로젝트 만들기 `HostingWpf`합니다.</span><span class="sxs-lookup"><span data-stu-id="61f8a-119">Create a new Windows Forms Application project in Visual Basic or Visual C# named `HostingWpf`.</span></span>  
  
## <a name="creating-a-new-wpf-control"></a><span data-ttu-id="61f8a-120">새 WPF 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="61f8a-120">Creating a New WPF Control</span></span>  
 <span data-ttu-id="61f8a-121">새 WPF 컨트롤을 만들고 프로젝트에 추가하는 작업은 다른 항목을 프로젝트에 추가하는 것만큼 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="61f8a-121">Creating a new WPF control and adding it to your project is as easy as adding any other item to your project.</span></span> <span data-ttu-id="61f8a-122">Windows Forms 디자이너는 특정 종류의 명명 된 컨트롤을 사용할 *합성 컨트롤*, 또는 *사용자 정의 컨트롤*합니다.</span><span class="sxs-lookup"><span data-stu-id="61f8a-122">The Windows Forms Designer works with a particular kind of control named *composite control*, or *user control*.</span></span> <span data-ttu-id="61f8a-123">WPF 사용자 정의 컨트롤에 대한 자세한 내용은 <xref:System.Windows.Controls.UserControl>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="61f8a-123">For more information about WPF user controls, see <xref:System.Windows.Controls.UserControl>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="61f8a-124">WPF용 <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> 형식은 Windows Forms에서 제공하는 <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>이라는 사용자 정의 컨트롤 형식과 별개입니다.</span><span class="sxs-lookup"><span data-stu-id="61f8a-124">The <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> type for WPF is distinct from the user control type provided by Windows Forms, which is also named <xref:System.Windows.Forms.UserControl?displayProperty=nameWithType>.</span></span>  
  
#### <a name="to-create-a-new-wpf-control"></a><span data-ttu-id="61f8a-125">새 WPF 컨트롤을 만들려면</span><span class="sxs-lookup"><span data-stu-id="61f8a-125">To create a new WPF control</span></span>  
  
1.  <span data-ttu-id="61f8a-126">**솔루션 탐색기**, 새 추가 **WPF 사용자 정의 컨트롤 라이브러리** 프로젝트를 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="61f8a-126">In **Solution Explorer**, add a new **WPF User Control Library** project to the solution.</span></span> <span data-ttu-id="61f8a-127">컨트롤 라이브러리의 기본 이름인 `WpfControlLibrary1`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="61f8a-127">Use the default name for the control library, `WpfControlLibrary1`.</span></span> <span data-ttu-id="61f8a-128">기본 컨트롤 이름은 `UserControl1.xaml`입니다.</span><span class="sxs-lookup"><span data-stu-id="61f8a-128">The default control name is `UserControl1.xaml`.</span></span>  
  
     <span data-ttu-id="61f8a-129">새 컨트롤을 추가하면 다음과 같은 효과가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61f8a-129">Adding the new control has the following effects.</span></span>  
  
    -   <span data-ttu-id="61f8a-130">UserControl1.xaml 파일이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="61f8a-130">File UserControl1.xaml is added.</span></span>  
  
    -   <span data-ttu-id="61f8a-131">UserControl1.xaml.cs 또는 UserControl1.xaml.vb 파일이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="61f8a-131">Either file UserControl1.xaml.cs or UserControl1.xaml.vb is added.</span></span> <span data-ttu-id="61f8a-132">이 파일에는 이벤트 처리기 및 기타 구현에 대한 코드 숨김이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="61f8a-132">This file contains the code-behind for event handlers and other implementation.</span></span>  
  
    -   <span data-ttu-id="61f8a-133">WPF 어셈블리에 대한 참조가 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="61f8a-133">References to WPF assemblies are added.</span></span>  
  
    -   <span data-ttu-id="61f8a-134">UserControl1.xaml 파일이 [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)]에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="61f8a-134">File UserControl1.xaml opens in the [!INCLUDE[wpfdesigner_current_long](../../../../includes/wpfdesigner-current-long-md.md)].</span></span>  
  
2.  <span data-ttu-id="61f8a-135">디자인 뷰에서 `UserControl1`이 선택되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="61f8a-135">In Design view, make sure that `UserControl1` is selected.</span></span> <span data-ttu-id="61f8a-136">자세한 내용은 참조 [하는 방법: 선택 하 고 디자인 화면에서 요소 이동](http://msdn.microsoft.com/library/54cb70b6-b35b-46e4-a0cc-65189399c474)합니다.</span><span class="sxs-lookup"><span data-stu-id="61f8a-136">For more information, see [How to: Select and Move Elements on the Design Surface](http://msdn.microsoft.com/library/54cb70b6-b35b-46e4-a0cc-65189399c474).</span></span>  
  
3.  <span data-ttu-id="61f8a-137">에 **속성** 창의 설정의 값은 <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A> 속성을 `200`합니다.</span><span class="sxs-lookup"><span data-stu-id="61f8a-137">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to `200`.</span></span>  
  
4.  <span data-ttu-id="61f8a-138">**도구 상자**를 끌어 한 <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> 컨트롤을 디자인 화면으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="61f8a-138">From the **Toolbox**, drag a <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control onto the design surface.</span></span>  
  
5.  <span data-ttu-id="61f8a-139">에 **속성** 창의 설정의 값은 <xref:System.Windows.Controls.TextBox.Text%2A> 속성을 **호스팅된 콘텐츠**합니다.</span><span class="sxs-lookup"><span data-stu-id="61f8a-139">In the **Properties** window, set the value of the <xref:System.Windows.Controls.TextBox.Text%2A> property to **Hosted Content**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="61f8a-140">일반적으로 더 복잡한 WPF 콘텐츠를 호스트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61f8a-140">In general, you should host more sophisticated WPF content.</span></span> <span data-ttu-id="61f8a-141"><xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> 컨트롤은 여기서 설명 목적으로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="61f8a-141">The <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> control is used here for illustrative purposes only.</span></span>  
  
6.  <span data-ttu-id="61f8a-142">프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="61f8a-142">Build the project.</span></span>  
  
## <a name="adding-a-wpf-control-to-a-windows-form"></a><span data-ttu-id="61f8a-143">Windows Form에 WPF 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="61f8a-143">Adding a WPF Control to a Windows Form</span></span>  
 <span data-ttu-id="61f8a-144">폼에서 새 WPF 컨트롤을 사용할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="61f8a-144">Your new WPF control is ready for use on the form.</span></span> <span data-ttu-id="61f8a-145">Windows Forms는 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤을 사용하여 WPF 콘텐츠를 호스트합니다.</span><span class="sxs-lookup"><span data-stu-id="61f8a-145">Windows Forms uses the <xref:System.Windows.Forms.Integration.ElementHost> control to host WPF content</span></span>  
  
#### <a name="to-add-a-wpf-control-to-a-windows-form"></a><span data-ttu-id="61f8a-146">Windows Form에 WPF 컨트롤을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="61f8a-146">To add a WPF control to a Windows Form</span></span>  
  
1.  <span data-ttu-id="61f8a-147">Windows Forms 디자이너에서 `Form1`을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="61f8a-147">Open `Form1` in the Windows Forms Designer.</span></span>  
  
2.  <span data-ttu-id="61f8a-148">에 **도구 상자**, 레이블이 있는 탭을 찾을 **WPFUserControlLibrary WPF 사용자 정의 컨트롤**합니다.</span><span class="sxs-lookup"><span data-stu-id="61f8a-148">In the **Toolbox**, find the tab labeled **WPFUserControlLibrary WPF User Controls**.</span></span>  
  
3.  <span data-ttu-id="61f8a-149">`UserControl1` 인스턴스를 폼으로 끕니다.</span><span class="sxs-lookup"><span data-stu-id="61f8a-149">Drag an instance of `UserControl1` onto the form.</span></span>  
  
    -   <span data-ttu-id="61f8a-150">WPF 컨트롤을 호스트할 폼에 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤이 자동으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="61f8a-150">An <xref:System.Windows.Forms.Integration.ElementHost> control is created automatically on the form to host the WPF control.</span></span>  
  
    -   <span data-ttu-id="61f8a-151"><xref:System.Windows.Forms.Integration.ElementHost> 컨트롤의 이름은 `elementHost1` 및는 **속성** 창 나타나면 해당 <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> 속성이로 설정 되어 **UserControl1**합니다.</span><span class="sxs-lookup"><span data-stu-id="61f8a-151">The <xref:System.Windows.Forms.Integration.ElementHost> control is named `elementHost1` and in the **Properties** window, you can see its <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> property is set to **UserControl1**.</span></span>  
  
    -   <span data-ttu-id="61f8a-152">WPF 어셈블리에 대한 참조가 프로젝트에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="61f8a-152">References to WPF assemblies are added to the project.</span></span>  
  
    -   <span data-ttu-id="61f8a-153">`elementHost1` 컨트롤에는 사용 가능한 호스팅 옵션을 표시하는 스마트 태그 패널이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61f8a-153">The `elementHost1` control has a smart tag panel that shows the available hosting options.</span></span>  
  
4.  <span data-ttu-id="61f8a-154">에 **ElementHost 작업** 스마트 태그 패널 **부모 컨테이너에서 도킹**합니다.</span><span class="sxs-lookup"><span data-stu-id="61f8a-154">In the **ElementHost Tasks** smart tag panel, select **Dock in parent container**.</span></span>  
  
5.  <span data-ttu-id="61f8a-155">F5 키를 눌러 응용 프로그램을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="61f8a-155">Press F5 to build and run the application.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="61f8a-156">다음 단계</span><span class="sxs-lookup"><span data-stu-id="61f8a-156">Next Steps</span></span>  
 <span data-ttu-id="61f8a-157">Windows Forms와 WPF는 서로 다른 기술이지만 긴밀하게 상호 운용하도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="61f8a-157">Windows Forms and WPF are different technologies, but they are designed to interoperate closely.</span></span> <span data-ttu-id="61f8a-158">응용 프로그램에서 다양한 모양과 동작을 제공하려면 다음을 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="61f8a-158">To provide richer appearance and behavior in your applications, try the following.</span></span>  
  
-   <span data-ttu-id="61f8a-159">WPF 페이지에서 Windows Forms 컨트롤을 호스트합니다.</span><span class="sxs-lookup"><span data-stu-id="61f8a-159">Host a Windows Forms control in a WPF page.</span></span> <span data-ttu-id="61f8a-160">자세한 내용은 참조 [연습: WPF의 Windows Forms 컨트롤 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="61f8a-160">For more information, see [Walkthrough: Hosting a Windows Forms Control in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md).</span></span>  
  
-   <span data-ttu-id="61f8a-161">WPF 콘텐츠에 Windows Forms 시각적 스타일을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="61f8a-161">Apply Windows Forms visual styles to your WPF content.</span></span> <span data-ttu-id="61f8a-162">자세한 내용은 [방법: 혼합 응용 프로그램에서 비주얼 스타일 사용](../../../../docs/framework/wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="61f8a-162">For more information, see [How to: Enable Visual Styles in a Hybrid Application](../../../../docs/framework/wpf/advanced/how-to-enable-visual-styles-in-a-hybrid-application.md).</span></span>  
  
-   <span data-ttu-id="61f8a-163">WPF 콘텐츠의 스타일을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="61f8a-163">Change the style of your WPF content.</span></span> <span data-ttu-id="61f8a-164">자세한 내용은 참조 [연습: WPF 콘텐츠 스타일 지정](../../../../docs/framework/winforms/advanced/walkthrough-styling-wpf-content.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="61f8a-164">For more information, see [Walkthrough: Styling WPF Content](../../../../docs/framework/winforms/advanced/walkthrough-styling-wpf-content.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61f8a-165">참고 항목</span><span class="sxs-lookup"><span data-stu-id="61f8a-165">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="61f8a-166">마이그레이션 및 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="61f8a-166">Migration and Interoperability</span></span>](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 [<span data-ttu-id="61f8a-167">WPF 컨트롤 사용</span><span class="sxs-lookup"><span data-stu-id="61f8a-167">Using WPF Controls</span></span>](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
 [<span data-ttu-id="61f8a-168">WPF 디자이너</span><span class="sxs-lookup"><span data-stu-id="61f8a-168">WPF Designer</span></span>](http://msdn.microsoft.com/library/c6c65214-8411-4e16-b254-163ed4099c26)
