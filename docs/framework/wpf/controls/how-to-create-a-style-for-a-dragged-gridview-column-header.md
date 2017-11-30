---
title: "방법: 끌어 온 GridView 열 머리글의 스타일 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: ListView controls [WPF], styling
ms.assetid: 0b999645-0313-4b33-80b9-19ece08b5459
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 503683de875b8853e219139800eef2a5417a1574
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-style-for-a-dragged-gridview-column-header"></a><span data-ttu-id="2fc16-102">방법: 끌어 온 GridView 열 머리글의 스타일 만들기</span><span class="sxs-lookup"><span data-stu-id="2fc16-102">How to: Create a Style for a Dragged GridView Column Header</span></span>
<span data-ttu-id="2fc16-103">끌어 온의 모양을 변경 하는 방법을 보여 주는이 예제 <xref:System.Windows.Controls.GridViewColumnHeader> 사용자 열 위치를 변경 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="2fc16-103">This example shows how to change the appearance of a dragged <xref:System.Windows.Controls.GridViewColumnHeader> when the user changes the position of a column.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2fc16-104">예제</span><span class="sxs-lookup"><span data-stu-id="2fc16-104">Example</span></span>  
 <span data-ttu-id="2fc16-105">열 머리글의 다른 위치로 끌어 올 때는 <xref:System.Windows.Controls.ListView> 사용 하 여 <xref:System.Windows.Controls.GridView> 보기 모드에 대 한 열을 새 위치로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fc16-105">When you drag a column header to another location in a <xref:System.Windows.Controls.ListView> that uses <xref:System.Windows.Controls.GridView> for its view mode, the column moves to the new position.</span></span> <span data-ttu-id="2fc16-106">열 머리글을 끄는 동안 부동 머리글의 복사본이 원래 머리글 외에도 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="2fc16-106">While you are dragging the column header, a floating copy of the header appears in addition to the original header.</span></span> <span data-ttu-id="2fc16-107">열 머리글에는 <xref:System.Windows.Controls.GridView> 로 표시 됩니다는 <xref:System.Windows.Controls.GridViewColumnHeader> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="2fc16-107">A column header in a <xref:System.Windows.Controls.GridView> is represented by a <xref:System.Windows.Controls.GridViewColumnHeader> object.</span></span>  
  
 <span data-ttu-id="2fc16-108">부동 및 원래 머리글의 모양을 사용자 지정 하려면 설정할 수 있습니다 <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> 수정 하는 <xref:System.Windows.Controls.GridViewColumnHeader> <xref:System.Windows.Style>합니다.</span><span class="sxs-lookup"><span data-stu-id="2fc16-108">To customize the appearance of both the floating and original headers, you can set <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> to modify the <xref:System.Windows.Controls.GridViewColumnHeader> <xref:System.Windows.Style>.</span></span> <span data-ttu-id="2fc16-109">이러한 <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> 때 적용 되는 <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> 속성 값은 `true` 및 <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> 속성 값은 <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>합니다.</span><span class="sxs-lookup"><span data-stu-id="2fc16-109">These <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> are applied when the <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> property value is `true` and the <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> property value is <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>.</span></span>  
  
 <span data-ttu-id="2fc16-110">사용자가 마우스 단추를 누를 한 누르고 위에 마우스를 일시 중지할 경우는 <xref:System.Windows.Controls.GridViewColumnHeader>, <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> 속성 값이 변경 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="2fc16-110">When the user presses the mouse button and holds it down while the mouse pauses on the <xref:System.Windows.Controls.GridViewColumnHeader>, the <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> property value changes to `true`.</span></span> <span data-ttu-id="2fc16-111">마찬가지로, 사용자 끌기 작업 시작는 <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> 속성 변경 <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>합니다.</span><span class="sxs-lookup"><span data-stu-id="2fc16-111">Likewise, when the user begins the drag operation, the <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> property changes to <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>.</span></span>  
  
 <span data-ttu-id="2fc16-112">다음 예제에서는 설정 하는 방법을 보여 줍니다. <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> 변경 하는 <xref:System.Windows.Controls.Control.Foreground%2A> 및 <xref:System.Windows.Controls.Control.Background%2A> 사용자가을 새 위치로 열을 끌 때 원래와 부동 머리글의 색입니다.</span><span class="sxs-lookup"><span data-stu-id="2fc16-112">The following example shows how to set <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> to change the <xref:System.Windows.Controls.Control.Foreground%2A> and <xref:System.Windows.Controls.Control.Background%2A> colors of the original and floating headers when the user drags a column to a new position.</span></span>  
  
 [!code-xaml[ListViewHeaderRoleStyle#GVCHControlTemplateStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#gvchcontroltemplatestart)]  
[!code-xaml[ListViewHeaderRoleStyle#ControlTemplateTriggersStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#controltemplatetriggersstart)]  
[!code-xaml[ListViewHeaderRoleStyle#IsPressed](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#ispressed)]  
[!code-xaml[ListViewHeaderRoleStyle#Floating](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#floating)]  
[!code-xaml[ListViewHeaderRoleStyle#ControlTemplateTriggersEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#controltemplatetriggersend)]  
[!code-xaml[ListViewHeaderRoleStyle#GVCHControlTemplateEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#gvchcontroltemplateend)]  
  
## <a name="see-also"></a><span data-ttu-id="2fc16-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2fc16-113">See Also</span></span>  
 <xref:System.Windows.Controls.GridViewColumnHeader>  
 <xref:System.Windows.Controls.GridViewColumnHeaderRole>  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [<span data-ttu-id="2fc16-114">방법 항목</span><span class="sxs-lookup"><span data-stu-id="2fc16-114">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [<span data-ttu-id="2fc16-115">ListView 개요</span><span class="sxs-lookup"><span data-stu-id="2fc16-115">ListView Overview</span></span>](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [<span data-ttu-id="2fc16-116">GridView 개요</span><span class="sxs-lookup"><span data-stu-id="2fc16-116">GridView Overview</span></span>](../../../../docs/framework/wpf/controls/gridview-overview.md)
