---
title: "연습: 디자인 타임에 Windows Forms에서 WPF 콘텐츠 정렬"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WPF user control [Windows Forms], hosting in a layout panel
- WPF content [Windows Forms], arranging at design time
- Windows Forms, arranging WPF content at design time
- WPF content [Windows Forms], hosting in Windows Forms
- Windows Forms, anchoring and docking WPF content
- interoperability [WPF]
ms.assetid: 5efb1c53-1484-43d6-aa8a-f4861b99bb8a
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9ae86989489ec4c50a4234eeb4a0950a71e53b0a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-arranging-wpf-content-on-windows-forms-at-design-time"></a><span data-ttu-id="5ea55-102">연습: 디자인 타임에 Windows Forms에서 WPF 콘텐츠 정렬</span><span class="sxs-lookup"><span data-stu-id="5ea55-102">Walkthrough: Arranging WPF Content on Windows Forms at Design Time</span></span>
<span data-ttu-id="5ea55-103">이 연습에서는 기준 위치 지정 및 맞춤선과 같은 Windows Forms 레이아웃 기능을 사용하여 WPF(Windows Presentation Foundation) 컨트롤을 정렬하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5ea55-103">This walkthrough shows you how to use the Windows Forms layout features, such as anchoring and snaplines, to arrange Windows Presentation Foundation (WPF) controls.</span></span>  
  
 <span data-ttu-id="5ea55-104">이 연습에서는 다음 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="5ea55-104">In this walkthrough, you perform the following tasks:</span></span>  
  
-   <span data-ttu-id="5ea55-105">프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5ea55-105">Create the project.</span></span>  
  
-   <span data-ttu-id="5ea55-106">WPF 컨트롤을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5ea55-106">Create the WPF control.</span></span>  
  
-   <span data-ttu-id="5ea55-107">레이아웃 패널에서 WPF 컨트롤을 호스트합니다.</span><span class="sxs-lookup"><span data-stu-id="5ea55-107">Host WPF controls in a layout panel.</span></span>  
  
-   <span data-ttu-id="5ea55-108">맞춤선을 사용하여 WPF 컨트롤을 맞춥니다.</span><span class="sxs-lookup"><span data-stu-id="5ea55-108">Use snaplines to align WPF controls.</span></span>  
  
-   <span data-ttu-id="5ea55-109">WPF 컨트롤을 고정 및 도킹합니다.</span><span class="sxs-lookup"><span data-stu-id="5ea55-109">Anchor and dock WPF controls.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5ea55-110">표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ea55-110">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="5ea55-111">설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5ea55-111">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="5ea55-112">자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5ea55-112">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5ea55-113">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="5ea55-113">Prerequisites</span></span>  
 <span data-ttu-id="5ea55-114">이 연습을 완료하려면 다음 구성 요소가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5ea55-114">You need the following components to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vs_dev11_long](../../../../includes/vs-dev11-long-md.md)]<span data-ttu-id="5ea55-115">.</span><span class="sxs-lookup"><span data-stu-id="5ea55-115">.</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="5ea55-116">프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="5ea55-116">Creating the Project</span></span>  
 <span data-ttu-id="5ea55-117">첫 번째 단계에서는 Windows Forms 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5ea55-117">The first step is to create the Windows Forms project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5ea55-118">WPF 콘텐츠를 호스트하는 경우 C# 및 Visual Basic 프로젝트만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ea55-118">When hosting WPF content, only C# and Visual Basic projects are supported.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="5ea55-119">프로젝트를 만들려면</span><span class="sxs-lookup"><span data-stu-id="5ea55-119">To create the project</span></span>  
  
-   <span data-ttu-id="5ea55-120">Visual Basic 또는 Visual C# 라는 새 Windows Forms 응용 프로그램 프로젝트 만들기 `ArrangeElementHost`합니다.</span><span class="sxs-lookup"><span data-stu-id="5ea55-120">Create a new Windows Forms Application project in Visual Basic or Visual C# named `ArrangeElementHost`.</span></span>  
  
## <a name="creating-the-wpf-control"></a><span data-ttu-id="5ea55-121">WPF 컨트롤 만들기</span><span class="sxs-lookup"><span data-stu-id="5ea55-121">Creating the WPF Control</span></span>  
 <span data-ttu-id="5ea55-122">프로젝트에 WPF 컨트롤을 추가한 후 폼에 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ea55-122">After you add a WPF control to the project, you can arrange it on the form.</span></span>  
  
#### <a name="to-create-wpf-controls"></a><span data-ttu-id="5ea55-123">WPF 컨트롤을 만들려면</span><span class="sxs-lookup"><span data-stu-id="5ea55-123">To create WPF controls</span></span>  
  
1.  <span data-ttu-id="5ea55-124">프로젝트에 새 WPF <xref:System.Windows.Controls.UserControl>을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="5ea55-124">Add a new WPF <xref:System.Windows.Controls.UserControl> to the project.</span></span> <span data-ttu-id="5ea55-125">컨트롤 형식의 기본 이름인 `UserControl1.xaml`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5ea55-125">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="5ea55-126">자세한 내용은 참조 [연습: 새 WPF 콘텐츠 만들기 디자인 타임에 Windows Forms](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5ea55-126">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](../../../../docs/framework/winforms/advanced/walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>  
  
2.  <span data-ttu-id="5ea55-127">디자인 뷰에서 `UserControl1`이 선택되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5ea55-127">In Design view, make sure that `UserControl1` is selected.</span></span> <span data-ttu-id="5ea55-128">자세한 내용은 참조 [하는 방법: 선택 하 고 디자인 화면에서 요소 이동](http://msdn.microsoft.com/en-us/54cb70b6-b35b-46e4-a0cc-65189399c474)합니다.</span><span class="sxs-lookup"><span data-stu-id="5ea55-128">For more information, see [How to: Select and Move Elements on the Design Surface](http://msdn.microsoft.com/en-us/54cb70b6-b35b-46e4-a0cc-65189399c474).</span></span>  
  
3.  <span data-ttu-id="5ea55-129">에 **속성** 창의 설정의 값은 <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A> 속성을 `200`합니다.</span><span class="sxs-lookup"><span data-stu-id="5ea55-129">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties to `200`.</span></span>  
  
4.  <span data-ttu-id="5ea55-130"><xref:System.Windows.Controls.Control.Background%2A> 속성 값을 `Blue`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5ea55-130">Set the value of the <xref:System.Windows.Controls.Control.Background%2A> property to `Blue`.</span></span>  
  
5.  <span data-ttu-id="5ea55-131">프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="5ea55-131">Build the project.</span></span>  
  
## <a name="hosting-wpf-controls-in-a-layout-panel"></a><span data-ttu-id="5ea55-132">레이아웃 패널에서 WPF 컨트롤 호스트</span><span class="sxs-lookup"><span data-stu-id="5ea55-132">Hosting WPF Controls in a Layout Panel</span></span>  
 <span data-ttu-id="5ea55-133">다른 Windows Forms 컨트롤을 사용하는 것과 동일한 방식으로 레이아웃 패널에서 WPF 컨트롤을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ea55-133">You can use WPF controls in layout panels in the same way you use other Windows Forms controls.</span></span>  
  
#### <a name="to-host-wpf-controls-in-a-layout-panel"></a><span data-ttu-id="5ea55-134">레이아웃 패널에서 WPF 컨트롤을 호스트하려면</span><span class="sxs-lookup"><span data-stu-id="5ea55-134">To host WPF controls in a layout panel</span></span>  
  
1.  <span data-ttu-id="5ea55-135">Windows Forms 디자이너에서 `Form1`을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5ea55-135">Open `Form1` in the Windows Forms Designer.</span></span>  
  
2.  <span data-ttu-id="5ea55-136">에 **도구 상자**를 끌어 한 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 폼으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ea55-136">In the **Toolbox**, drag a <xref:System.Windows.Forms.TableLayoutPanel> control onto the form.</span></span>  
  
3.  <span data-ttu-id="5ea55-137">에 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤의 스마트 태그 패널에서 선택 **마지막 행 제거**합니다.</span><span class="sxs-lookup"><span data-stu-id="5ea55-137">On the <xref:System.Windows.Forms.TableLayoutPanel> control's smart tag panel, select **Remove Last Row**.</span></span>  
  
4.  <span data-ttu-id="5ea55-138"><xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 더 큰 너비와 높이로 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="5ea55-138">Resize the <xref:System.Windows.Forms.TableLayoutPanel> control to a larger width and height.</span></span>  
  
5.  <span data-ttu-id="5ea55-139">에 **도구 상자**를 두 번 클릭 `UserControl1` 의 인스턴스를 만드는 `UserControl1` 의 첫 번째 셀에는 <xref:System.Windows.Forms.TableLayoutPanel> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ea55-139">In the **Toolbox**, double-click `UserControl1` to create an instance of `UserControl1` in the first cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
     <span data-ttu-id="5ea55-140">`UserControl1` 인스턴스가 `elementHost1`이라는 새 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤에서 호스트됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ea55-140">The instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>  
  
6.  <span data-ttu-id="5ea55-141">에 **도구 상자**를 두 번 클릭 `UserControl1` 의 두 번째 셀에 다른 인스턴스를 만들 수는 <xref:System.Windows.Forms.TableLayoutPanel> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ea55-141">In the **Toolbox**, double-click `UserControl1` to create another instance in the second cell of the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
7.  <span data-ttu-id="5ea55-142">에 **문서 개요** 창에서 `tableLayoutPanel1`합니다.</span><span class="sxs-lookup"><span data-stu-id="5ea55-142">In the **Document Outline** window, select `tableLayoutPanel1`.</span></span> <span data-ttu-id="5ea55-143">자세한 내용은 참조 [문서 개요 창](http://msdn.microsoft.com/en-us/9054f2bc-f6f8-4242-9fe0-be71089b12f8)합니다.</span><span class="sxs-lookup"><span data-stu-id="5ea55-143">For more information, see [Document Outline Window](http://msdn.microsoft.com/en-us/9054f2bc-f6f8-4242-9fe0-be71089b12f8).</span></span>  
  
8.  <span data-ttu-id="5ea55-144">에 **속성** 창의 설정의 값은 <xref:System.Windows.Forms.Control.Padding%2A> 속성을 `10, 10, 10, 10`합니다.</span><span class="sxs-lookup"><span data-stu-id="5ea55-144">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Control.Padding%2A> property to `10, 10, 10, 10`.</span></span>  
  
     <span data-ttu-id="5ea55-145">두 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤 모두 새 레이아웃에 맞게 크기가 조정됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ea55-145">Both <xref:System.Windows.Forms.Integration.ElementHost> controls are resized to fit into the new layout.</span></span>  
  
## <a name="using-snaplines-to-align-wpf-controls"></a><span data-ttu-id="5ea55-146">맞춤선을 사용하여 WPF 컨트롤 맞춤</span><span class="sxs-lookup"><span data-stu-id="5ea55-146">Using Snaplines to Align WPF Controls</span></span>  
 <span data-ttu-id="5ea55-147">맞춤선을 사용하여 폼에서 컨트롤을 쉽게 맞출 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ea55-147">Snaplines enable easy alignment of controls on a form.</span></span> <span data-ttu-id="5ea55-148">맞춤선을 사용하여 WPF 컨트롤도 맞출 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ea55-148">You can use snaplines to align your WPF controls as well.</span></span> <span data-ttu-id="5ea55-149">자세한 내용은 참조 [연습: 맞춤선 Windows Forms에서 사용 하 여 컨트롤 정렬](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5ea55-149">For more information, see [Walkthrough: Arranging Controls on Windows Forms Using Snaplines](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md).</span></span>  
  
#### <a name="to-use-snaplines-to-align-wpf-controls"></a><span data-ttu-id="5ea55-150">맞춤선을 사용하여 WPF 컨트롤을 맞추려면</span><span class="sxs-lookup"><span data-stu-id="5ea55-150">To use snaplines to align WPF controls</span></span>  
  
1.  <span data-ttu-id="5ea55-151">**도구 상자**의 인스턴스를 끌어 `UserControl1` 폼 아래 공간에 배치 하 고는 <xref:System.Windows.Forms.TableLayoutPanel> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ea55-151">From the **Toolbox**, drag an instance of `UserControl1` onto the form and place it in the space beneath the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
     <span data-ttu-id="5ea55-152">`UserControl1` 인스턴스가 `elementHost3`이라는 새 <xref:System.Windows.Forms.Integration.ElementHost> 컨트롤에서 호스트됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ea55-152">The instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost3`.</span></span>  
  
2.  <span data-ttu-id="5ea55-153">맞춤선을 사용하여 `elementHost3`의 왼쪽 가장자리를 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤의 왼쪽 가장자리에 맞춥니다.</span><span class="sxs-lookup"><span data-stu-id="5ea55-153">Using snaplines, align the left edge of `elementHost3` with the left edge of <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
3.  <span data-ttu-id="5ea55-154">맞춤선을 사용하여 `elementHost3`의 크기를 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤과 동일한 너비로 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="5ea55-154">Using snaplines, size `elementHost3` to the same width as the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
4.  <span data-ttu-id="5ea55-155">가운데 맞춤선이 컨트롤 사이에 나타날 때까지 `elementHost3`을 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤 쪽으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5ea55-155">Move `elementHost3` toward the <xref:System.Windows.Forms.TableLayoutPanel> control until a center snapline appears between the controls.</span></span>  
  
5.  <span data-ttu-id="5ea55-156">에 **속성** 여백 속성의 값을 설정 하는 창 `20, 20, 20, 20`합니다.</span><span class="sxs-lookup"><span data-stu-id="5ea55-156">In the **Properties** window, set the value of the Margin property to `20, 20, 20, 20`.</span></span>  
  
6.  <span data-ttu-id="5ea55-157">가운데 맞춤선이 다시 나타날 때까지 `elementHost3`을 <xref:System.Windows.Forms.TableLayoutPanel> 컨트롤에서 멀리 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5ea55-157">Move the `elementHost3` away from the <xref:System.Windows.Forms.TableLayoutPanel> control until the center snapline appears again.</span></span> <span data-ttu-id="5ea55-158">이제 가운데 맞춤선이 여백 20을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5ea55-158">The center snapline now indicates a margin of 20.</span></span>  
  
7.  <span data-ttu-id="5ea55-159">왼쪽 가장자리가 `elementHost1`의 왼쪽 가장자리와 맞춰질 때까지 `elementHost3`을 오른쪽으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="5ea55-159">Move `elementHost3` to the right, until its left edge aligns with the left edge of `elementHost1`.</span></span>  
  
8.  <span data-ttu-id="5ea55-160">오른쪽 가장자리가 `elementHost2`의 오른쪽 가장자리와 맞춰질 때까지 `elementHost3`의 너비를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="5ea55-160">Change the width of `elementHost3` until its right edge aligns with the right edge of `elementHost2`.</span></span>  
  
## <a name="anchoring-and-docking-wpf-controls"></a><span data-ttu-id="5ea55-161">WPF 컨트롤 고정 및 도킹</span><span class="sxs-lookup"><span data-stu-id="5ea55-161">Anchoring and Docking WPF Controls</span></span>  
 <span data-ttu-id="5ea55-162">폼에 호스트된 WPF 컨트롤은 다른 Windows Forms 컨트롤과 동일한 고정 및 도킹 동작을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="5ea55-162">A WPF control hosted on a form has the same anchoring and docking behavior as other Windows Forms controls.</span></span>  
  
#### <a name="to-anchor-and-dock-wpf-controls"></a><span data-ttu-id="5ea55-163">WPF 컨트롤을 고정 및 도킹하려면</span><span class="sxs-lookup"><span data-stu-id="5ea55-163">To anchor and dock WPF controls</span></span>  
  
1.  <span data-ttu-id="5ea55-164">`elementHost1`를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5ea55-164">Select `elementHost1`.</span></span>  
  
2.  <span data-ttu-id="5ea55-165">에 **속성** 창에서 설정 된 <xref:System.Windows.Forms.Control.Anchor%2A> 속성을 **위쪽, 아래쪽, 왼쪽, 오른쪽**합니다.</span><span class="sxs-lookup"><span data-stu-id="5ea55-165">In the **Properties** window, set the <xref:System.Windows.Forms.Control.Anchor%2A> property to **Top, Bottom, Left, Right**.</span></span>  
  
3.  <span data-ttu-id="5ea55-166"><xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 더 큰 크기로 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="5ea55-166">Resize the <xref:System.Windows.Forms.TableLayoutPanel> control to a larger size.</span></span>  
  
     <span data-ttu-id="5ea55-167">`elementHost1` 컨트롤의 크기가 조정되어 셀을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="5ea55-167">The `elementHost1` control resizes to fill the cell.</span></span>  
  
4.  <span data-ttu-id="5ea55-168">`elementHost2`를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5ea55-168">Select `elementHost2`.</span></span>  
  
5.  <span data-ttu-id="5ea55-169">에 **속성** 창의 설정의 값은 <xref:System.Windows.Forms.Control.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle.Fill>합니다.</span><span class="sxs-lookup"><span data-stu-id="5ea55-169">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>  
  
     <span data-ttu-id="5ea55-170">`elementHost2` 컨트롤의 크기가 조정되어 셀을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="5ea55-170">The `elementHost2` control resizes to fill the cell.</span></span>  
  
6.  <span data-ttu-id="5ea55-171"><xref:System.Windows.Forms.TableLayoutPanel> 컨트롤을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5ea55-171">Select the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>  
  
7.  <span data-ttu-id="5ea55-172"><xref:System.Windows.Forms.Control.Dock%2A> 속성의 값을 <xref:System.Windows.Forms.DockStyle.Top>로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5ea55-172">Set the value of its <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Top>.</span></span>  
  
8.  <span data-ttu-id="5ea55-173">`elementHost3`를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5ea55-173">Select `elementHost3`.</span></span>  
  
9. <span data-ttu-id="5ea55-174"><xref:System.Windows.Forms.Control.Dock%2A> 속성의 값을 <xref:System.Windows.Forms.DockStyle.Fill>로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5ea55-174">Set the value of its <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>  
  
     <span data-ttu-id="5ea55-175">`elementHost3` 컨트롤의 크기가 조정되어 폼의 나머지 공간을 채웁니다.</span><span class="sxs-lookup"><span data-stu-id="5ea55-175">The `elementHost3` control resizes to fill the remaining space on the form.</span></span>  
  
10. <span data-ttu-id="5ea55-176">폼의 크기를 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="5ea55-176">Resize the form.</span></span>  
  
     <span data-ttu-id="5ea55-177"><xref:System.Windows.Forms.Integration.ElementHost> 컨트롤 3개의 크기가 모두 적절하게 조정됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ea55-177">All three <xref:System.Windows.Forms.Integration.ElementHost> controls resize appropriately.</span></span>  
  
     <span data-ttu-id="5ea55-178">자세한 내용은 참조 [하는 방법: 앵커 및 TableLayoutPanel 컨트롤의 자식 컨트롤을 도킹](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5ea55-178">For more information, see [How to: Anchor and Dock Child Controls in a TableLayoutPanel Control](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ea55-179">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5ea55-179">See Also</span></span>  
 <xref:System.Windows.Forms.Integration.ElementHost>  
 <xref:System.Windows.Forms.Integration.WindowsFormsHost>  
 [<span data-ttu-id="5ea55-180">방법: TableLayoutPanel 컨트롤의 자식 컨트롤 고정 및 도킹</span><span class="sxs-lookup"><span data-stu-id="5ea55-180">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)  
 [<span data-ttu-id="5ea55-181">방법: 디자인 타임에 컨트롤을 양식의 가장자리에 맞춤</span><span class="sxs-lookup"><span data-stu-id="5ea55-181">How to: Align a Control to the Edges of Forms at Design Time</span></span>](../../../../docs/framework/winforms/controls/how-to-align-a-control-to-the-edges-of-forms-at-design-time.md)  
 [<span data-ttu-id="5ea55-182">연습: Windows Forms에서 맞춤선을 사용하여 컨트롤 정렬</span><span class="sxs-lookup"><span data-stu-id="5ea55-182">Walkthrough: Arranging Controls on Windows Forms Using Snaplines</span></span>](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)  
 [<span data-ttu-id="5ea55-183">마이그레이션 및 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="5ea55-183">Migration and Interoperability</span></span>](../../../../docs/framework/wpf/advanced/migration-and-interoperability.md)  
 [<span data-ttu-id="5ea55-184">WPF 컨트롤 사용</span><span class="sxs-lookup"><span data-stu-id="5ea55-184">Using WPF Controls</span></span>](../../../../docs/framework/winforms/advanced/using-wpf-controls.md)  
 [<span data-ttu-id="5ea55-185">WPF 디자이너</span><span class="sxs-lookup"><span data-stu-id="5ea55-185">WPF Designer</span></span>](http://msdn.microsoft.com/en-us/c6c65214-8411-4e16-b254-163ed4099c26)
