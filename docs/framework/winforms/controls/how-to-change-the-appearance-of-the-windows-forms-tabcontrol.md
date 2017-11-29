---
title: "방법: Windows Forms TabControl의 모양 변경"
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
- icons [Windows Forms], displaying on tabs
- TabControl control [Windows Forms], changing page appearance
- tabs [Windows Forms], controlling appearance
- buttons [Windows Forms], displaying tabs as
ms.assetid: 7c6cc443-ed62-4d26-b94d-b8913b44f773
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b244930f0837d3b1d548e0f7a8c77dd80e1ce039
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-tabcontrol"></a><span data-ttu-id="fb75a-102">방법: Windows Forms TabControl의 모양 변경</span><span class="sxs-lookup"><span data-stu-id="fb75a-102">How to: Change the Appearance of the Windows Forms TabControl</span></span>
<span data-ttu-id="fb75a-103">속성을 사용 하 여 Windows Forms에서 탭의 모양을 변경할 수는 <xref:System.Windows.Forms.TabControl> 및 <xref:System.Windows.Forms.TabPage> 컨트롤의 개별 탭을 구성 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="fb75a-103">You can change the appearance of tabs in Windows Forms by using properties of the <xref:System.Windows.Forms.TabControl> and the <xref:System.Windows.Forms.TabPage> objects that make up the individual tabs on the control.</span></span> <span data-ttu-id="fb75a-104">이러한 속성을 설정 하 여 탭에 이미지를 표시, 표시 하거나 수 있습니다 가로 대신 세로로 탭, 여러 행의 탭이 표시 하 고 사용 하도록 설정 탭을 프로그래밍 방식으로 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb75a-104">By setting these properties, you can display images on tabs, display tabs vertically instead of horizontally, display multiple rows of tabs, and enable or disable tabs programmatically.</span></span>  
  
### <a name="to-display-an-icon-on-the-label-part-of-a-tab"></a><span data-ttu-id="fb75a-105">탭의 레이블 부분에 아이콘을 표시 하려면</span><span class="sxs-lookup"><span data-stu-id="fb75a-105">To display an icon on the label part of a tab</span></span>  
  
1.  <span data-ttu-id="fb75a-106">추가 <xref:System.Windows.Forms.ImageList> 컨트롤을 폼입니다.</span><span class="sxs-lookup"><span data-stu-id="fb75a-106">Add an <xref:System.Windows.Forms.ImageList> control to the form.</span></span>  
  
2.  <span data-ttu-id="fb75a-107">이미지 목록에 이미지를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb75a-107">Add images to the image list.</span></span>  
  
     <span data-ttu-id="fb75a-108">이미지 목록에 대 한 자세한 내용은 참조 [ImageList 구성 요소](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md) 및 [하는 방법: Windows Forms ImageList 구성 요소와 이미지 추가 또는 제거](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fb75a-108">For more information about image lists, see [ImageList Component](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md) and [How to: Add or Remove Images with the Windows Forms ImageList Component](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span>  
  
3.  <span data-ttu-id="fb75a-109">설정의 <xref:System.Windows.Forms.TabControl.ImageList%2A> 속성의는 <xref:System.Windows.Forms.TabControl> 에 <xref:System.Windows.Forms.ImageList> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb75a-109">Set the <xref:System.Windows.Forms.TabControl.ImageList%2A> property of the <xref:System.Windows.Forms.TabControl> to the <xref:System.Windows.Forms.ImageList> control.</span></span>  
  
4.  <span data-ttu-id="fb75a-110">설정의 <xref:System.Windows.Forms.TabPage.ImageIndex%2A> 속성의는 <xref:System.Windows.Forms.TabPage> 목록에서 적절 한 이미지의 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="fb75a-110">Set the <xref:System.Windows.Forms.TabPage.ImageIndex%2A> property of the <xref:System.Windows.Forms.TabPage> to the index of an appropriate image in the list.</span></span>  
  
### <a name="to-create-multiple-rows-of-tabs"></a><span data-ttu-id="fb75a-111">여러 행의 탭을 만들려면</span><span class="sxs-lookup"><span data-stu-id="fb75a-111">To create multiple rows of tabs</span></span>  
  
1.  <span data-ttu-id="fb75a-112">탭 페이지 수를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb75a-112">Add the number of tab pages you want.</span></span>  
  
2.  <span data-ttu-id="fb75a-113">설정의 <xref:System.Windows.Forms.TabControl.Multiline%2A> 의 속성은 <xref:System.Windows.Forms.TabControl> 를 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="fb75a-113">Set the <xref:System.Windows.Forms.TabControl.Multiline%2A> property of the <xref:System.Windows.Forms.TabControl> to `true`.</span></span>  
  
3.  <span data-ttu-id="fb75a-114">설정 탭 여러 행에 표시 되지 않습니다는 <xref:System.Windows.Forms.Control.Width%2A> 의 속성에서 <xref:System.Windows.Forms.TabControl> 모든 탭 보다 좁은 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="fb75a-114">If the tabs do not already appear in multiple rows, set the <xref:System.Windows.Forms.Control.Width%2A> property of the <xref:System.Windows.Forms.TabControl> to be narrower than all the tabs.</span></span>  
  
### <a name="to-arrange-tabs-on-the-side-of-the-control"></a><span data-ttu-id="fb75a-115">탭 컨트롤의 측면을 정렬 하려면</span><span class="sxs-lookup"><span data-stu-id="fb75a-115">To arrange tabs on the side of the control</span></span>  
  
-   <span data-ttu-id="fb75a-116">설정의 <xref:System.Windows.Forms.TabControl.Alignment%2A> 의 속성은 <xref:System.Windows.Forms.TabControl> 를 <xref:System.Windows.Forms.TabAlignment.Left> 또는 <xref:System.Windows.Forms.TabAlignment.Right>합니다.</span><span class="sxs-lookup"><span data-stu-id="fb75a-116">Set the <xref:System.Windows.Forms.TabControl.Alignment%2A> property of the <xref:System.Windows.Forms.TabControl> to <xref:System.Windows.Forms.TabAlignment.Left> or <xref:System.Windows.Forms.TabAlignment.Right>.</span></span>  
  
### <a name="to-programmatically-enable-or-disable-all-controls-on-a-tab"></a><span data-ttu-id="fb75a-117">탭에 있는 모든 컨트롤을 사용 하지 않도록 설정 하거나 프로그래밍 방식으로 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="fb75a-117">To programmatically enable or disable all controls on a tab</span></span>  
  
1.  <span data-ttu-id="fb75a-118">설정의 <xref:System.Windows.Forms.TabPage.Enabled%2A> 의 속성은 <xref:System.Windows.Forms.TabPage> 를 `true` 또는 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="fb75a-118">Set the <xref:System.Windows.Forms.TabPage.Enabled%2A> property of the <xref:System.Windows.Forms.TabPage> to `true` or `false`.</span></span>  
  
    ```vb  
    TabPage1.Enabled = False  
    ```  
  
    ```csharp  
    tabPage1.Enabled = false;  
    ```  
  
    ```cpp  
    tabPage1->Enabled = false;  
    ```  
  
### <a name="to-display-tabs-as-buttons"></a><span data-ttu-id="fb75a-119">탭을 단추로 표시 하려면</span><span class="sxs-lookup"><span data-stu-id="fb75a-119">To display tabs as buttons</span></span>  
  
-   <span data-ttu-id="fb75a-120">설정의 <xref:System.Windows.Forms.TabControl.Appearance%2A> 의 속성은 <xref:System.Windows.Forms.TabControl> 를 <xref:System.Windows.Forms.TabAppearance.Buttons> 또는 <xref:System.Windows.Forms.TabAppearance.FlatButtons>합니다.</span><span class="sxs-lookup"><span data-stu-id="fb75a-120">Set the <xref:System.Windows.Forms.TabControl.Appearance%2A> property of the <xref:System.Windows.Forms.TabControl> to <xref:System.Windows.Forms.TabAppearance.Buttons> or <xref:System.Windows.Forms.TabAppearance.FlatButtons>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb75a-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fb75a-121">See Also</span></span>  
 [<span data-ttu-id="fb75a-122">TabControl 컨트롤</span><span class="sxs-lookup"><span data-stu-id="fb75a-122">TabControl Control</span></span>](../../../../docs/framework/winforms/controls/tabcontrol-control-windows-forms.md)  
 [<span data-ttu-id="fb75a-123">TabControl 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="fb75a-123">TabControl Control Overview</span></span>](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)  
 [<span data-ttu-id="fb75a-124">방법: 탭 페이지에 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="fb75a-124">How to: Add a Control to a Tab Page</span></span>](../../../../docs/framework/winforms/controls/how-to-add-a-control-to-a-tab-page.md)  
 [<span data-ttu-id="fb75a-125">방법: 탭 페이지 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="fb75a-125">How to: Disable Tab Pages</span></span>](../../../../docs/framework/winforms/controls/how-to-disable-tab-pages.md)  
 [<span data-ttu-id="fb75a-126">방법: Windows Forms TabControl을 사용하여 탭 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="fb75a-126">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
