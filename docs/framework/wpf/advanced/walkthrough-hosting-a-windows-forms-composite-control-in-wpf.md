---
title: "연습: WPF에서 Windows Forms 복합 컨트롤 호스팅"
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
- hosting Windows Forms control in WPF [WPF]
- composite controls [WPF], hosting in WPF
ms.assetid: 96fcd78d-1c77-4206-8928-3a0579476ef4
caps.latest.revision: "33"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a9f9a63d9fced326d20013b1f306d1fe0b7721dd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-hosting-a-windows-forms-composite-control-in-wpf"></a><span data-ttu-id="9bbda-102">연습: WPF에서 Windows Forms 복합 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="9bbda-102">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]<span data-ttu-id="9bbda-103">에서는 응용 프로그램을 만들기 위한 다양한 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-103"> provides a rich environment for creating applications.</span></span> <span data-ttu-id="9bbda-104">그러나에 있는 경우 상당한 투자 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 코드는 것이 보다 효율적으로 이라도 다시 사용을 코드의 일부 프로그램 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램이 처음부터 다시 작성 하기 보다는 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-104">However, when you have a substantial investment in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] code, it can be more effective to reuse at least some of that code in your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application rather than to rewrite it from scratch.</span></span> <span data-ttu-id="9bbda-105">가장 일반적인 시나리오는 기존 경우 [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-105">The most common scenario is when you have existing [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] controls.</span></span> <span data-ttu-id="9bbda-106">경우에 따라 이러한 컨트롤에 대한 소스 코드에 액세스하지 못할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-106">In some cases, you might not even have access to the source code for these controls.</span></span> [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="9bbda-107">이러한 컨트롤을 호스팅하기 위한 간단한 프로시저를 제공는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-107"> provides a straightforward procedure for hosting such controls in a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="9bbda-108">사용할 수는 예를 들어 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 대부분의에서 특수화 된 호스팅하면서 프로그래밍에 대 한 <xref:System.Windows.Forms.DataGridView> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-108">For example, you can use [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] for most of your programming while hosting your specialized <xref:System.Windows.Forms.DataGridView> controls.</span></span>  
  
 <span data-ttu-id="9bbda-109">이 연습 단계를 안내 응용 프로그램을 호스팅하는 [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] 합성 컨트롤에서 데이터 입력을 수행 하는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-109">This walkthrough steps you through an application that hosts a [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] composite control to perform data entry in a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="9bbda-110">복합 컨트롤은 DLL로 패키지됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-110">The composite control is packaged in a DLL.</span></span> <span data-ttu-id="9bbda-111">이 일반적인 절차는 더 복잡한 응용 프로그램 및 컨트롤로 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-111">This general procedure can be extended to more complex applications and controls.</span></span> <span data-ttu-id="9bbda-112">이 연습에서 모양과 기능을 거의 동일한 [연습: Windows Forms에서 WPF 합성 컨트롤 호스팅](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-112">This walkthrough is designed to be nearly identical in appearance and functionality to [Walkthrough: Hosting a WPF Composite Control in Windows Forms](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md).</span></span> <span data-ttu-id="9bbda-113">주요 차이점은 호스팅 시나리오가 반대라는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-113">The primary difference is that the hosting scenario is reversed.</span></span>  
  
 <span data-ttu-id="9bbda-114">이 연습은 두 개의 섹션으로 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-114">The walkthrough is divided into two sections.</span></span> <span data-ttu-id="9bbda-115">첫 번째 섹션 구현에 간략하게 설명 된 [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] 합성 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-115">The first section briefly describes the implementation of the [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] composite control.</span></span> <span data-ttu-id="9bbda-116">두 번째 섹션에서 복합 컨트롤을 호스트 하는 방법을 자세히 설명 된 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램의 컨트롤에서 이벤트를 수신 및 컨트롤의 속성 중 일부에 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-116">The second section discusses in detail how to host the composite control in a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application, receive events from the control, and access some of the control's properties.</span></span>  
  
 <span data-ttu-id="9bbda-117">이 연습에서 설명하는 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-117">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="9bbda-118">Windows Forms 복합 컨트롤 구현</span><span class="sxs-lookup"><span data-stu-id="9bbda-118">Implementing the Windows Forms composite control.</span></span>  
  
-   <span data-ttu-id="9bbda-119">WPF 호스트 응용 프로그램 구현</span><span class="sxs-lookup"><span data-stu-id="9bbda-119">Implementing the WPF host application.</span></span>  
  
 <span data-ttu-id="9bbda-120">이 연습에서 설명 하는 작업의 전체 코드 목록을 보려면 [WPF 샘플에서 Windows Forms 합성 컨트롤 호스팅](http://go.microsoft.com/fwlink/?LinkID=159999)합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-120">For a complete code listing of the tasks illustrated in this walkthrough, see [Hosting a Windows Forms Composite Control in WPF Sample](http://go.microsoft.com/fwlink/?LinkID=159999).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9bbda-121">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="9bbda-121">Prerequisites</span></span>  
 <span data-ttu-id="9bbda-122">이 연습을 완료하려면 다음 구성 요소가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-122">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)]<span data-ttu-id="9bbda-123">.</span><span class="sxs-lookup"><span data-stu-id="9bbda-123">.</span></span>  
  
## <a name="implementing-the-windows-forms-composite-control"></a><span data-ttu-id="9bbda-124">Windows Forms 복합 컨트롤 구현</span><span class="sxs-lookup"><span data-stu-id="9bbda-124">Implementing the Windows Forms Composite Control</span></span>  
 <span data-ttu-id="9bbda-125">[!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] 이 예제에서 사용 하는 복합 컨트롤은 간단한 데이터 입력 폼입니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-125">The [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] composite control used in this example is a simple data-entry form.</span></span> <span data-ttu-id="9bbda-126">이 폼에서는 사용자의 이름 및 주소를 사용한 다음 사용자 지정 이벤트를 사용하여 해당 정보를 호스트에 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-126">This form takes the user's name and address and then uses a custom event to return that information to the host.</span></span> <span data-ttu-id="9bbda-127">다음 그림에서는 렌더링된 컨트롤을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-127">The following illustration shows the rendered control.</span></span>  
  
 <span data-ttu-id="9bbda-128">![단순 Windows Forms 컨트롤](../../../../docs/framework/wpf/advanced/media/wfcontrol.gif "WFControl")</span><span class="sxs-lookup"><span data-stu-id="9bbda-128">![Simple Windows Forms control](../../../../docs/framework/wpf/advanced/media/wfcontrol.gif "WFControl")</span></span>  
<span data-ttu-id="9bbda-129">Windows Forms 복합 컨트롤</span><span class="sxs-lookup"><span data-stu-id="9bbda-129">Windows Forms composite control</span></span>  
  
### <a name="creating-the-project"></a><span data-ttu-id="9bbda-130">프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="9bbda-130">Creating the Project</span></span>  
 <span data-ttu-id="9bbda-131">프로젝트를 시작하려면</span><span class="sxs-lookup"><span data-stu-id="9bbda-131">To start the project:</span></span>  
  
1.  <span data-ttu-id="9bbda-132">시작 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], 열 및는 **새 프로젝트** 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="9bbda-132">Launch [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], and open the **New Project** dialog box.</span></span>  
  
2.  <span data-ttu-id="9bbda-133">창의 범주에서 선택 된 **Windows Forms 컨트롤 라이브러리** 템플릿.</span><span class="sxs-lookup"><span data-stu-id="9bbda-133">In the Window category, select the **Windows Forms Control Library** template.</span></span>  
  
3.  <span data-ttu-id="9bbda-134">새 프로젝트의 이름을 `MyControls`합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-134">Name the new project `MyControls`.</span></span>  
  
4.  <span data-ttu-id="9bbda-135">위치에 대 한 최상위 폴더를 편리 하 게 명명 된 같은 지정한 `WpfHostingWindowsFormsControl`합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-135">For the location, specify a conveniently named top-level folder, such as `WpfHostingWindowsFormsControl`.</span></span> <span data-ttu-id="9bbda-136">나중에 이 폴더에 호스트 응용 프로그램을 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-136">Later, you will put the host application in this folder.</span></span>  
  
5.  <span data-ttu-id="9bbda-137">클릭 **확인** 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-137">Click **OK** to create the project.</span></span> <span data-ttu-id="9bbda-138">라는 단일 컨트롤을 포함 하는 기본 프로젝트 `UserControl1`합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-138">The default project contains a single control named `UserControl1`.</span></span>  
  
6.  <span data-ttu-id="9bbda-139">솔루션 탐색기에서 이름을 바꿀 `UserControl1` 를 `MyControl1`합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-139">In Solution Explorer, rename `UserControl1` to `MyControl1`.</span></span>  
  
 <span data-ttu-id="9bbda-140">프로젝트에는 다음과 같은 시스템 DLL에 대한 참조가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-140">Your project should have references to the following system DLLs.</span></span> <span data-ttu-id="9bbda-141">이러한 DLL이 기본적으로 포함되지 않은 경우 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-141">If any of these DLLs are not included by default, add them to the project.</span></span>  
  
-   <span data-ttu-id="9bbda-142">시스템</span><span class="sxs-lookup"><span data-stu-id="9bbda-142">System</span></span>  
  
-   <span data-ttu-id="9bbda-143">System.Data</span><span class="sxs-lookup"><span data-stu-id="9bbda-143">System.Data</span></span>  
  
-   <span data-ttu-id="9bbda-144">System.Drawing</span><span class="sxs-lookup"><span data-stu-id="9bbda-144">System.Drawing</span></span>  
  
-   <span data-ttu-id="9bbda-145">System.Windows.Forms</span><span class="sxs-lookup"><span data-stu-id="9bbda-145">System.Windows.Forms</span></span>  
  
-   <span data-ttu-id="9bbda-146">System.Xml</span><span class="sxs-lookup"><span data-stu-id="9bbda-146">System.Xml</span></span>  
  
### <a name="adding-controls-to-the-form"></a><span data-ttu-id="9bbda-147">폼에 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="9bbda-147">Adding Controls to the Form</span></span>  
 <span data-ttu-id="9bbda-148">폼에 컨트롤을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="9bbda-148">To add controls to the form:</span></span>  
  
-   <span data-ttu-id="9bbda-149">열기 `MyControl1` 디자이너에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-149">Open `MyControl1` in the designer.</span></span>  
  
 <span data-ttu-id="9bbda-150">다섯 개의 <xref:System.Windows.Forms.Label> 컨트롤과 해당 <xref:System.Windows.Forms.TextBox> 컨트롤, 크기 및 폼에 앞의 그림에 있는 것 처럼 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-150">Add five <xref:System.Windows.Forms.Label> controls and their corresponding <xref:System.Windows.Forms.TextBox> controls, sized and arranged as they are in the preceding illustration, on the form.</span></span> <span data-ttu-id="9bbda-151">예제에서는 <xref:System.Windows.Forms.TextBox> 컨트롤에 이름이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-151">In the example, the <xref:System.Windows.Forms.TextBox> controls are named:</span></span>  
  
-   `txtName`  
  
-   `txtAddress`  
  
-   `txtCity`  
  
-   `txtState`  
  
-   `txtZip`  
  
 <span data-ttu-id="9bbda-152">두 개의 추가 <xref:System.Windows.Forms.Button> 레이블이 표시 컨트롤 **확인** 및 **취소**합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-152">Add two <xref:System.Windows.Forms.Button> controls labeled **OK** and **Cancel**.</span></span> <span data-ttu-id="9bbda-153">예제에서는 단추 이름이 `btnOK` 및 `btnCancel`각각.</span><span class="sxs-lookup"><span data-stu-id="9bbda-153">In the example, the button names are `btnOK` and `btnCancel`, respectively.</span></span>  
  
### <a name="implementing-the-supporting-code"></a><span data-ttu-id="9bbda-154">지원 코드 구현</span><span class="sxs-lookup"><span data-stu-id="9bbda-154">Implementing the Supporting Code</span></span>  
 <span data-ttu-id="9bbda-155">코드 보기에서 폼을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-155">Open the form in code view.</span></span> <span data-ttu-id="9bbda-156">컨트롤 사용자 지정을 발생 시켜 해당 호스트에 수집 된 데이터를 반환 `OnButtonClick` 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-156">The control returns the collected data to its host by raising the custom `OnButtonClick` event.</span></span> <span data-ttu-id="9bbda-157">데이터는 이벤트 인수 개체에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-157">The data is contained in the event argument object.</span></span> <span data-ttu-id="9bbda-158">다음 코드에서는 이벤트 및 대리자 선언을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-158">The following code shows the event and delegate declaration.</span></span>  
  
 <span data-ttu-id="9bbda-159">`MyControl1` 클래스에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-159">Add the following code to the `MyControl1` class.</span></span>  
  
 [!code-csharp[WpfHostingWindowsFormsControl#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#2)]
 [!code-vb[WpfHostingWindowsFormsControl#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#2)]  
  
 <span data-ttu-id="9bbda-160">`MyControlEventArgs` 클래스는 호스트에 반환 될 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-160">The `MyControlEventArgs` class contains the information to be returned to the host.</span></span>  
  
 <span data-ttu-id="9bbda-161">다음 클래스를 폼에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-161">Add the following class to the form.</span></span>  
  
 [!code-csharp[WpfHostingWindowsFormsControl#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#3)]
 [!code-vb[WpfHostingWindowsFormsControl#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#3)]  
  
 <span data-ttu-id="9bbda-162">사용자가 클릭할 때는 **확인** 또는 **취소** 단추를는 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기 만들기는 `MyControlEventArgs` 데이터를 포함 하는 개체를 발생 시킵니다는 `OnButtonClick` 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-162">When the user clicks the **OK** or **Cancel** button, the <xref:System.Windows.Forms.Control.Click> event handlers create a `MyControlEventArgs` object that contains the data and raises the `OnButtonClick` event.</span></span> <span data-ttu-id="9bbda-163">두 명의 처리기 간의 유일한 차이점은 이벤트 인수 `IsOK` 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-163">The only difference between the two handlers is the event argument's `IsOK` property.</span></span> <span data-ttu-id="9bbda-164">이 속성을 통해 호스트는 클릭한 단추를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-164">This property enables the host to determine which button was clicked.</span></span> <span data-ttu-id="9bbda-165">로 설정 된 `true` 에 대 한는 **확인** 단추 및 `false` 에 대 한는 **취소** 단추입니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-165">It is set to `true` for the **OK** button, and `false` for the **Cancel** button.</span></span> <span data-ttu-id="9bbda-166">다음 코드에서는 두 개의 단추 처리기를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-166">The following code shows the two button handlers.</span></span>  
  
 <span data-ttu-id="9bbda-167">`MyControl1` 클래스에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-167">Add the following code to the `MyControl1` class.</span></span>  
  
 [!code-csharp[WpfHostingWindowsFormsControl#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/MyControls/MyControl1.cs#4)]
 [!code-vb[WpfHostingWindowsFormsControl#4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/MyControls/MyControl1.vb#4)]  
  
### <a name="giving-the-assembly-a-strong-name-and-building-the-assembly"></a><span data-ttu-id="9bbda-168">어셈블리에 강력한 이름을 지정하고 어셈블리 빌드</span><span class="sxs-lookup"><span data-stu-id="9bbda-168">Giving the Assembly a Strong Name and Building the Assembly</span></span>  
 <span data-ttu-id="9bbda-169">이 어셈블리를 참조할 수는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램에서는, 강력한 이름이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-169">For this assembly to be referenced by a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application, it must have a strong name.</span></span> <span data-ttu-id="9bbda-170">강력한 이름을 만들려면 Sn.exe와 키 파일을 만들고 프로젝트에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-170">To create a strong name, create a key file with Sn.exe and add it to your project.</span></span>  
  
1.  <span data-ttu-id="9bbda-171">[!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] 명령 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-171">Open a [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)] command prompt.</span></span> <span data-ttu-id="9bbda-172">이렇게 하려면 클릭는 **시작** 메뉴를 선택한 후 **모든 프로그램/Microsoft Visual Studio 2010/Visual Studio 도구/Visual Studio 명령 프롬프트**합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-172">To do so, click the **Start** menu, and then select **All Programs/Microsoft Visual Studio 2010/Visual Studio Tools/Visual Studio Command Prompt**.</span></span> <span data-ttu-id="9bbda-173">그러면 사용자 지정된 환경 변수가 있는 콘솔 창이 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-173">This launches a console window with customized environment variables.</span></span>  
  
2.  <span data-ttu-id="9bbda-174">명령 프롬프트에서 사용 하 여는 `cd` 명령 프로젝트 폴더로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-174">At the command prompt, use the `cd` command to go to your project folder.</span></span>  
  
3.  <span data-ttu-id="9bbda-175">다음 명령을 실행하여 MyControls.snk라는 키 파일을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-175">Generate a key file named MyControls.snk by running the following command.</span></span>  
  
    ```  
    Sn.exe -k MyControls.snk  
    ```  
  
4.  <span data-ttu-id="9bbda-176">프로젝트에서 키 파일을 포함 하려면 솔루션 탐색기에서 프로젝트 이름을 마우스 오른쪽 단추로 클릭 하 고 클릭 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-176">To include the key file in your project, right-click the project name in Solution Explorer and then click **Properties**.</span></span> <span data-ttu-id="9bbda-177">프로젝트 디자이너에서 클릭는 **서명** 탭을는 **어셈블리에 서명** 확인란을 선택 하 고 다음 키 파일을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-177">In the Project Designer, click the **Signing** tab, select the **Sign the assembly** check box and then browse to your key file.</span></span>  
  
5.  <span data-ttu-id="9bbda-178">솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-178">Build the solution.</span></span> <span data-ttu-id="9bbda-179">빌드하면 MyControls.dll이라는 DLL이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-179">The build will produce a DLL named MyControls.dll.</span></span>  
  
## <a name="implementing-the-wpf-host-application"></a><span data-ttu-id="9bbda-180">WPF 호스트 응용 프로그램 구현</span><span class="sxs-lookup"><span data-stu-id="9bbda-180">Implementing the WPF Host Application</span></span>  
 <span data-ttu-id="9bbda-181">[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 사용 하 여 응용 프로그램 호스트는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 컨트롤을 호스트 `MyControl1`합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-181">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] host application uses the <xref:System.Windows.Forms.Integration.WindowsFormsHost> control to host `MyControl1`.</span></span> <span data-ttu-id="9bbda-182">응용 프로그램 핸들이 `OnButtonClick` 컨트롤에서 데이터를 받을 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-182">The application handles the `OnButtonClick` event to receive the data from the control.</span></span> <span data-ttu-id="9bbda-183">옵션 단추에서 컨트롤의 속성 중 일부를 변경할 수 있도록 하는 컬렉션에는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-183">It also has a collection of option buttons that enable you to change some of the control's properties from the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="9bbda-184">다음 그림에서는 완료된 응용 프로그램을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-184">The following illustration shows the finished application.</span></span>  
  
 <span data-ttu-id="9bbda-185">![WPF 페이지에 포함 된 컨트롤](../../../../docs/framework/wpf/advanced/media/avalonhost.gif "AvalonHost")</span><span class="sxs-lookup"><span data-stu-id="9bbda-185">![A control embedded in a WPF page](../../../../docs/framework/wpf/advanced/media/avalonhost.gif "AvalonHost")</span></span>  
<span data-ttu-id="9bbda-186">WPF 응용 프로그램에 포함된 컨트롤을 보여 주는 전체 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="9bbda-186">The complete application, showing the control embedded in the WPF application</span></span>  
  
### <a name="creating-the-project"></a><span data-ttu-id="9bbda-187">프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="9bbda-187">Creating the Project</span></span>  
 <span data-ttu-id="9bbda-188">프로젝트를 시작하려면</span><span class="sxs-lookup"><span data-stu-id="9bbda-188">To start the project:</span></span>  
  
1.  <span data-ttu-id="9bbda-189">열기 [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)]를 선택 하 고 **새 프로젝트**합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-189">Open [!INCLUDE[TLA2#tla_visualstu](../../../../includes/tla2sharptla-visualstu-md.md)], and select **New Project**.</span></span>  
  
2.  <span data-ttu-id="9bbda-190">창의 범주에서 선택 된 **WPF 응용 프로그램** 템플릿.</span><span class="sxs-lookup"><span data-stu-id="9bbda-190">In the Window category, select the **WPF Application** template.</span></span>
  
3.  <span data-ttu-id="9bbda-191">새 프로젝트의 이름을 `WpfHost`합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-191">Name the new project `WpfHost`.</span></span>  
  
4.  <span data-ttu-id="9bbda-192">위치에는 MyControls 프로젝트를 포함하는 동일한 최상위 폴더를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-192">For the location, specify the same top-level folder that contains the MyControls project.</span></span>  
  
5.  <span data-ttu-id="9bbda-193">클릭 **확인** 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-193">Click **OK** to create the project.</span></span>  
  
 <span data-ttu-id="9bbda-194">포함 된 DLL에 대 한 참조를 추가 해야 `MyControl1` 및 기타 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-194">You also need to add references to the DLL that contains `MyControl1` and other assemblies.</span></span>  
  
1.  <span data-ttu-id="9bbda-195">솔루션 탐색기에서 프로젝트 이름을 마우스 오른쪽 단추로 클릭 하 고 선택 **참조 추가**합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-195">Right-click the project name in Solution Explorer and select **Add Reference**.</span></span>  
  
2.  <span data-ttu-id="9bbda-196">클릭는 **찾아보기** 탭을 MyControls.dll 포함 된 폴더로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-196">Click the **Browse** tab, and browse to the folder that contains MyControls.dll.</span></span> <span data-ttu-id="9bbda-197">이 연습에서 이 폴더는 MyControls\bin\Debug입니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-197">For this walkthrough, this folder is MyControls\bin\Debug.</span></span>  
  
3.  <span data-ttu-id="9bbda-198">MyControls.dll를 선택한 다음 클릭 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-198">Select MyControls.dll, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="9bbda-199">WindowsFormsIntegration.dll 라는 WindowsFormsIntegration 어셈블리에 대 한 참조를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-199">Add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>  
  
### <a name="implementing-the-basic-layout"></a><span data-ttu-id="9bbda-200">기본 레이아웃 구현</span><span class="sxs-lookup"><span data-stu-id="9bbda-200">Implementing the Basic Layout</span></span>  
 <span data-ttu-id="9bbda-201">[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 호스트의 응용 프로그램에서 MainWindow.xaml에서 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-201">The [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] of the host application is implemented in MainWindow.xaml.</span></span> <span data-ttu-id="9bbda-202">이 파일에 포함 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 레이아웃을 정의 하 고 호스트 하는 태그는 [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-202">This file contains [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] markup that defines the layout, and hosts the [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] control.</span></span> <span data-ttu-id="9bbda-203">응용 프로그램은 세 가지 영역으로 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-203">The application is divided into three regions:</span></span>  
  
-   <span data-ttu-id="9bbda-204">**컨트롤 속성** 패널의 옵션 단추 호스팅된 컨트롤의 다양 한 속성을 수정 하는 데 사용할 수 있는 컬렉션을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-204">The **Control Properties** panel, which contains a collection of option buttons that you can use to modify various properties of the hosted control.</span></span>  
  
-   <span data-ttu-id="9bbda-205">**데이터를 컨트롤에서에서** 몇 가지 들어 있는 패널 <xref:System.Windows.Controls.TextBlock> 호스팅된 컨트롤에서 데이터를 표시 하는 요소를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-205">The **Data from Control** panel, which contains several <xref:System.Windows.Controls.TextBlock> elements that display the data returned from the hosted control.</span></span>  
  
-   <span data-ttu-id="9bbda-206">호스트된 컨트롤 자체.</span><span class="sxs-lookup"><span data-stu-id="9bbda-206">The hosted control itself.</span></span>  
  
 <span data-ttu-id="9bbda-207">기본 레이아웃은 다음과 같은 XAML로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-207">The basic layout is shown in the following XAML.</span></span> <span data-ttu-id="9bbda-208">태그는 호스트에 `MyControl1` 이 예제에서 생략 되지만 나중에 설명 하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-208">The markup that is needed to host `MyControl1` is omitted from this example, but will be discussed later.</span></span>  
  
 <span data-ttu-id="9bbda-209">MainWindow.xaml의 XAML을 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-209">Replace the XAML in MainWindow.xaml with the following.</span></span> <span data-ttu-id="9bbda-210">Visual Basic을 사용 하는 경우 클래스를 변경 `x:Class="MainWindow"`합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-210">If you are using Visual Basic, change the class to `x:Class="MainWindow"`.</span></span>  
  
 [!code-xaml[WpfHostingWindowsFormsControl#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#100)]  
  
 <span data-ttu-id="9bbda-211">첫 번째 <xref:System.Windows.Controls.StackPanel> 요소 집합이 여러 개 포함 <xref:System.Windows.Controls.RadioButton> 호스팅된 컨트롤의 다양 한 기본 속성을 수정할 수 있도록 하는 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-211">The first <xref:System.Windows.Controls.StackPanel> element contains several sets of <xref:System.Windows.Controls.RadioButton> controls that enable you to modify various default properties of the hosted control.</span></span> <span data-ttu-id="9bbda-212">이 뒤에 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소를 호스팅하고 `MyControl1`합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-212">That is followed by a <xref:System.Windows.Forms.Integration.WindowsFormsHost> element, which hosts `MyControl1`.</span></span> <span data-ttu-id="9bbda-213">최종 <xref:System.Windows.Controls.StackPanel> 몇 가지 요소 들어 <xref:System.Windows.Controls.TextBlock> 호스팅된 컨트롤에서 반환 되는 데이터를 표시 하는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-213">The final <xref:System.Windows.Controls.StackPanel> element contains several <xref:System.Windows.Controls.TextBlock> elements that display the data that is returned by the hosted control.</span></span> <span data-ttu-id="9bbda-214">요소를 정렬 및 <xref:System.Windows.Controls.DockPanel.Dock%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A> 특성 설정을 간격이 나 왜곡 없이으로 구성 된 창에 호스트 된 컨트롤을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-214">The ordering of the elements and the <xref:System.Windows.Controls.DockPanel.Dock%2A> and <xref:System.Windows.FrameworkElement.Height%2A> attribute settings embed the hosted control into the window with no gaps or distortion.</span></span>  
  
#### <a name="hosting-the-control"></a><span data-ttu-id="9bbda-215">컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="9bbda-215">Hosting the Control</span></span>  
 <span data-ttu-id="9bbda-216">필요한 요소를 중점적으로 편집한 다음 버전에서는 이전 XAML의 호스트에 `MyControl1`합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-216">The following edited version of the previous XAML focuses on the elements that are needed to host `MyControl1`.</span></span>  
  
 [!code-xaml[WpfHostingWindowsFormsControl#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#101)]  
[!code-xaml[WpfHostingWindowsFormsControl#102](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml#102)]  
  
 <span data-ttu-id="9bbda-217">`xmlns` 네임 스페이스 매핑 특성에 대 한 참조를 만듭니다.는 `MyControls` 호스팅된 컨트롤이 있는 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-217">The `xmlns` namespace mapping attribute creates a reference to the `MyControls` namespace that contains the hosted control.</span></span> <span data-ttu-id="9bbda-218">이 매핑을 사용 하 여 나타내기 위해 `MyControl1` 에 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 으로 `<mcl:MyControl1>`합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-218">This mapping enables you to represent `MyControl1` in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] as `<mcl:MyControl1>`.</span></span>  
  
 <span data-ttu-id="9bbda-219">XAML의 두 요소가 호스팅을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-219">Two elements in the XAML handle the hosting:</span></span>  
  
-   <span data-ttu-id="9bbda-220">`WindowsFormsHost`나타냅니다는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 호스트를 사용 하면 요소는 [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] 컨트롤에 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-220">`WindowsFormsHost` represents the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element that enables you to host a [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] control in a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] application.</span></span>  
  
-   <span data-ttu-id="9bbda-221">`mcl:MyControl1`를 나타내는 `MyControl1`에 추가 되는 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소의 자식 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-221">`mcl:MyControl1`, which represents `MyControl1`, is added to the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's child collection.</span></span> <span data-ttu-id="9bbda-222">결과적으로,이 [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] 컨트롤이의 일부로 렌더링 되는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 창, 응용 프로그램에서 제어와 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-222">As a result, this [!INCLUDE[TLA2#tla_winforms](../../../../includes/tla2sharptla-winforms-md.md)] control is rendered as part of the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] window, and you can communicate with the control from the application.</span></span>  
  
### <a name="implementing-the-code-behind-file"></a><span data-ttu-id="9bbda-223">코드 숨김 파일 구현</span><span class="sxs-lookup"><span data-stu-id="9bbda-223">Implementing the Code-Behind File</span></span>  
 <span data-ttu-id="9bbda-224">기능을 구현 하는 절차적 코드를 포함 하는 코드 숨김 파일의 MainWindow.xaml.vb 또는 MainWindow.xaml.cs는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 이전 섹션에서 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-224">The code-behind file, MainWindow.xaml.vb or MainWindow.xaml.cs, contains the procedural code that implements the functionality of the [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] discussed in the preceding section.</span></span> <span data-ttu-id="9bbda-225">기본 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-225">The primary tasks are:</span></span>  
  
-   <span data-ttu-id="9bbda-226">이벤트 처리기를 연결 `MyControl1`의 `OnButtonClick` 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-226">Attaching an event handler to `MyControl1`'s `OnButtonClick` event.</span></span>  
  
-   <span data-ttu-id="9bbda-227">다양 한 속성을 수정 `MyControl1`옵션 단추 모음을 설정 하는 방법에 따라 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-227">Modifying various properties of `MyControl1`, based on how the collection of option buttons are set.</span></span>  
  
-   <span data-ttu-id="9bbda-228">컨트롤에서 수집한 데이터 표시.</span><span class="sxs-lookup"><span data-stu-id="9bbda-228">Displaying the data collected by the control.</span></span>  
  
#### <a name="initializing-the-application"></a><span data-ttu-id="9bbda-229">응용 프로그램 초기화</span><span class="sxs-lookup"><span data-stu-id="9bbda-229">Initializing the Application</span></span>  
 <span data-ttu-id="9bbda-230">초기화 코드 창에 대 한 이벤트 처리기에 포함 된 <xref:System.Windows.FrameworkElement.Loaded> 이벤트를 컨트롤의 이벤트 처리기를 연결 하 고 `OnButtonClick` 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-230">The initialization code is contained in an event handler for the window's <xref:System.Windows.FrameworkElement.Loaded> event and attaches an event handler to the control's `OnButtonClick` event.</span></span>  
  
 <span data-ttu-id="9bbda-231">MainWindow.xaml.vb 또는 MainWindow.xaml.cs에서 다음 코드를 추가 `MainWindow` 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-231">In MainWindow.xaml.vb or MainWindow.xaml.cs, add the following code to the `MainWindow` class.</span></span>  
  
 [!code-csharp[WpfHostingWindowsFormsControl#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#11)]
 [!code-vb[WpfHostingWindowsFormsControl#11](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#11)]  
  
 <span data-ttu-id="9bbda-232">때문에 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 이전에 추가한 설명 `MyControl1` 에 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 캐스팅할 수 요소의 자식 요소 컬렉션의 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소의 <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A> 에 대 한 참조를 얻으려고 `MyControl1`합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-232">Because the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] discussed previously added `MyControl1` to the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's child element collection, you can cast the <xref:System.Windows.Forms.Integration.WindowsFormsHost> element's <xref:System.Windows.Forms.Integration.WindowsFormsHost.Child%2A> to get the reference to `MyControl1`.</span></span> <span data-ttu-id="9bbda-233">이벤트 처리기를 연결 하려면 해당 참조를 사용 다음 `OnButtonClick`합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-233">You can then use that reference to attach an event handler to `OnButtonClick`.</span></span>  
  
 <span data-ttu-id="9bbda-234">컨트롤 자체에 대 한 참조를 제공할 뿐 아니라 <xref:System.Windows.Forms.Integration.WindowsFormsHost> 다양 한 응용 프로그램에서 조작할 수 있는 컨트롤의 속성을 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-234">In addition to providing a reference to the control itself, <xref:System.Windows.Forms.Integration.WindowsFormsHost> exposes a number of the control's properties, which you can manipulate from the application.</span></span> <span data-ttu-id="9bbda-235">초기화 코드는 나중에 응용 프로그램에서 사용할 수 있도록 private 전역 변수에 해당 값을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-235">The initialization code assigns those values to private global variables for later use in the application.</span></span>  
  
 <span data-ttu-id="9bbda-236">형식에 쉽게 액세스할 수 있도록는 `MyControls` DLL의 경우 다음 추가 `Imports` 또는 `using` 문을 파일의 맨 위에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-236">So that you can easily access the types in the `MyControls` DLL, add the following `Imports` or `using` statement to the top of the file.</span></span>  
  
```vb  
Imports MyControls  
```  
  
```csharp  
using MyControls;  
```  
  
#### <a name="handling-the-onbuttonclick-event"></a><span data-ttu-id="9bbda-237">OnButtonClick 이벤트 처리</span><span class="sxs-lookup"><span data-stu-id="9bbda-237">Handling the OnButtonClick Event</span></span>  
 <span data-ttu-id="9bbda-238">`MyControl1`발생는 `OnButtonClick` 이벤트 사용자가 컨트롤의 단추 중 하나를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-238">`MyControl1` raises the `OnButtonClick` event when the user clicks either of the control's buttons.</span></span>  
  
 <span data-ttu-id="9bbda-239">`MainWindow` 클래스에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-239">Add the following code to the `MainWindow` class.</span></span>  
  
 [!code-csharp[WpfHostingWindowsFormsControl#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#12)]
 [!code-vb[WpfHostingWindowsFormsControl#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#12)]  
  
 <span data-ttu-id="9bbda-240">텍스트 상자에 데이터 압축은 `MyControlEventArgs` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-240">The data in the text boxes is packed into the `MyControlEventArgs` object.</span></span> <span data-ttu-id="9bbda-241">사용자가 클릭할 경우의 **확인** 단추 이벤트 처리기 데이터를 추출 하 고 아래쪽 패널에 표시 `MyControl1`합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-241">If the user clicks the **OK** button, the event handler extracts the data and displays it in the panel below `MyControl1`.</span></span>  
  
#### <a name="modifying-the-controls-properties"></a><span data-ttu-id="9bbda-242">컨트롤의 속성 수정</span><span class="sxs-lookup"><span data-stu-id="9bbda-242">Modifying the Control’s Properties</span></span>  
 <span data-ttu-id="9bbda-243"><xref:System.Windows.Forms.Integration.WindowsFormsHost> 요소 몇 가지 호스팅된 컨트롤의 기본 속성을 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-243">The <xref:System.Windows.Forms.Integration.WindowsFormsHost> element exposes several of the hosted control's default properties.</span></span> <span data-ttu-id="9bbda-244">결과적으로 응용 프로그램의 스타일과 더 가깝게 일치하도록 컨트롤의 모양을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-244">As a result, you can change the appearance of the control to match the style of your application more closely.</span></span> <span data-ttu-id="9bbda-245">왼쪽 패널의 옵션 단추 집합을 사용하여 사용자는 여러 가지 색 및 글꼴 속성을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-245">The sets of option buttons in the left panel enable the user to modify several color and font properties.</span></span> <span data-ttu-id="9bbda-246">단추의 각 집합에 대 한 처리기는 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트를 사용자의 옵션 단추 선택 항목을 검색 하 고 컨트롤에 해당 속성을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-246">Each set of buttons has a handler for the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event, which detects the user's option button selections and changes the corresponding property on the control.</span></span>  
  
 <span data-ttu-id="9bbda-247">`MainWindow` 클래스에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-247">Add the following code to the `MainWindow` class.</span></span>  
  
 [!code-csharp[WpfHostingWindowsFormsControl#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/CSharp/WpfHost/Page1.xaml.cs#13)]
 [!code-vb[WpfHostingWindowsFormsControl#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WpfHostingWindowsFormsControl/VisualBasic/WpfHost/Page1.xaml.vb#13)]  
  
 <span data-ttu-id="9bbda-248">응용 프로그램을 빌드 및 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-248">Build and run the application.</span></span> <span data-ttu-id="9bbda-249">합성 Windows Forms 컨트롤의 텍스트를 추가 하 고 클릭 **확인**합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-249">Add some text in the Windows Forms composite control and then click **OK**.</span></span> <span data-ttu-id="9bbda-250">텍스트가 레이블에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-250">The text appears in the labels.</span></span> <span data-ttu-id="9bbda-251">컨트롤에 대한 효과를 확인하려면 다른 라디오 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9bbda-251">Click the different radio buttons to see the effect on the control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bbda-252">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9bbda-252">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="9bbda-253">WPF 디자이너</span><span class="sxs-lookup"><span data-stu-id="9bbda-253">WPF Designer</span></span>](http://msdn.microsoft.com/en-us/c6c65214-8411-4e16-b254-163ed4099c26)  
 [<span data-ttu-id="9bbda-254">연습: WPF에서 Windows Forms 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="9bbda-254">Walkthrough: Hosting a Windows Forms Control in WPF</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-windows-forms-control-in-wpf.md)  
 [<span data-ttu-id="9bbda-255">연습: Windows Forms에서 WPF 복합 컨트롤 호스팅</span><span class="sxs-lookup"><span data-stu-id="9bbda-255">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
