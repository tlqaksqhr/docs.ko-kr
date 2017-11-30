---
title: "방법: Windows Forms ListView 컨트롤의 아이콘 표시"
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
helpviewer_keywords:
- ListView control [Windows Forms], displaying icons
- icons [Windows Forms], displaying for ListView controls
- lists [Windows Forms], displaying icons
- ImageList component [Windows Forms], with ListView control
- list views [Windows Forms], displaying icons
ms.assetid: 9d577542-8595-429b-99e5-078770ec9d35
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0d9a8bdc54f3f321b37bda897aac1f340f7a46aa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-icons-for-the-windows-forms-listview-control"></a><span data-ttu-id="fecd4-102">방법: Windows Forms ListView 컨트롤의 아이콘 표시</span><span class="sxs-lookup"><span data-stu-id="fecd4-102">How to: Display Icons for the Windows Forms ListView Control</span></span>
<span data-ttu-id="fecd4-103">Windows Forms <xref:System.Windows.Forms.ListView> 컨트롤 이미지 목록에서 아이콘을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fecd4-103">The Windows Forms <xref:System.Windows.Forms.ListView> control can display icons from three image lists.</span></span> <span data-ttu-id="fecd4-104">에 지정 된 이미지 목록의 이미지를 표시 하는 목록, 정보 및 SmallIcon 보기는 <xref:System.Windows.Forms.ListView.SmallImageList%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="fecd4-104">The List, Details, and SmallIcon views display images from the image list specified in the <xref:System.Windows.Forms.ListView.SmallImageList%2A> property.</span></span> <span data-ttu-id="fecd4-105">큰 아이콘 보기에 지정 된 이미지 목록의 이미지를 표시는 <xref:System.Windows.Forms.ListView.LargeImageList%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="fecd4-105">The LargeIcon view displays images from the image list specified in the <xref:System.Windows.Forms.ListView.LargeImageList%2A> property.</span></span> <span data-ttu-id="fecd4-106">목록 보기에서 설정 아이콘의 추가 집합 표시할 수도 <xref:System.Windows.Forms.ListView.StateImageList%2A> 크고 작은 아이콘과 옆에 있는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="fecd4-106">A list view can also display an additional set of icons, set in the <xref:System.Windows.Forms.ListView.StateImageList%2A> property, next to the large or small icons.</span></span> <span data-ttu-id="fecd4-107">이미지 목록에 대 한 자세한 내용은 참조 [ImageList 구성 요소](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md) 및 [하는 방법: Windows Forms ImageList 구성 요소와 이미지 추가 또는 제거](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fecd4-107">For more information about image lists, see [ImageList Component](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md) and [How to: Add or Remove Images with the Windows Forms ImageList Component](../../../../docs/framework/winforms/controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span>  
  
### <a name="to-display-images-in-a-list-view"></a><span data-ttu-id="fecd4-108">목록 보기에 이미지를 표시 하려면</span><span class="sxs-lookup"><span data-stu-id="fecd4-108">To display images in a list view</span></span>  
  
1.  <span data-ttu-id="fecd4-109">적절 한 속성을 설정-<xref:System.Windows.Forms.ListView.SmallImageList%2A>, <xref:System.Windows.Forms.ListView.LargeImageList%2A>, 또는 <xref:System.Windows.Forms.ListView.StateImageList%2A>— 기존 <xref:System.Windows.Forms.ImageList> 사용 하려는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="fecd4-109">Set the appropriate property—<xref:System.Windows.Forms.ListView.SmallImageList%2A>, <xref:System.Windows.Forms.ListView.LargeImageList%2A>, or <xref:System.Windows.Forms.ListView.StateImageList%2A>—to the existing <xref:System.Windows.Forms.ImageList> component you wish to use.</span></span>  
  
     <span data-ttu-id="fecd4-110">속성 창에 디자이너에서 나 코드에서 이러한 속성을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fecd4-110">These properties can be set in the designer with the Properties window, or in code.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#41)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#41)]  
  
2.  <span data-ttu-id="fecd4-111">설정의 <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> 또는 <xref:System.Windows.Forms.ListViewItem.StateImageIndex%2A> 아이콘이 연결된 되어 있는 각 목록 항목에 대 한 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="fecd4-111">Set the <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> or <xref:System.Windows.Forms.ListViewItem.StateImageIndex%2A> property for each list item that has an associated icon.</span></span>  
  
     <span data-ttu-id="fecd4-112">또는 코드에서 이러한 속성을 설정할 수 있습니다는 **ListViewItem 컬렉션 편집기**합니다.</span><span class="sxs-lookup"><span data-stu-id="fecd4-112">These properties can be set in code, or within the **ListViewItem Collection Editor**.</span></span> <span data-ttu-id="fecd4-113">열려는 **ListViewItem 컬렉션 편집기**, 줄임표 단추를 클릭 (![VisualStudioEllipsesButton 스크린 샷](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton"))는 옆에있는<xref:System.Windows.Forms.ListView.Items%2A>속성에는 **속성** 창.</span><span class="sxs-lookup"><span data-stu-id="fecd4-113">To open the **ListViewItem Collection Editor**, click the ellipsis button (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) next to the <xref:System.Windows.Forms.ListView.Items%2A> property on the **Properties** window.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#42](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#42)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#42](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#42)]  
  
## <a name="see-also"></a><span data-ttu-id="fecd4-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fecd4-114">See Also</span></span>  
 [<span data-ttu-id="fecd4-115">ListView 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="fecd4-115">ListView Control Overview</span></span>](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)  
 [<span data-ttu-id="fecd4-116">방법: Windows Forms ListView 컨트롤을 사용하여 항목 추가 및 제거</span><span class="sxs-lookup"><span data-stu-id="fecd4-116">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)  
 [<span data-ttu-id="fecd4-117">방법: Windows Forms ListView 컨트롤에 열 추가</span><span class="sxs-lookup"><span data-stu-id="fecd4-117">How to: Add Columns to the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)  
 [<span data-ttu-id="fecd4-118">방법: TreeView 또는 ListView 컨트롤에 사용자 지정 정보 추가(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="fecd4-118">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)  
 [<span data-ttu-id="fecd4-119">ImageList 구성 요소</span><span class="sxs-lookup"><span data-stu-id="fecd4-119">ImageList Component</span></span>](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)
