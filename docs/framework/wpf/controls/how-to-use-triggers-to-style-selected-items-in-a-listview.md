---
title: "방법: ListView에서 트리거를 사용하여 선택한 항목의 스타일 지정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: ListView controls [WPF], styling
ms.assetid: 1e2bdce0-afe8-4507-9b18-f33de43de25a
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e86c7f875376a4ab28eec7cd032a165745445441
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-triggers-to-style-selected-items-in-a-listview"></a><span data-ttu-id="8527b-102">방법: ListView에서 트리거를 사용하여 선택한 항목의 스타일 지정</span><span class="sxs-lookup"><span data-stu-id="8527b-102">How to: Use Triggers to Style Selected Items in a ListView</span></span>
<span data-ttu-id="8527b-103">정의 하는 방법을 보여 주는이 예제 <xref:System.Windows.Style.Triggers%2A> 에 대 한는 <xref:System.Windows.Controls.ListViewItem> 제어 되도록 때의 속성 값을는 <xref:System.Windows.Controls.ListViewItem> 변경은 <xref:System.Windows.Style> 의 <xref:System.Windows.Controls.ListViewItem> 변경 내용에 대 한 응답에서입니다.</span><span class="sxs-lookup"><span data-stu-id="8527b-103">This example shows how to define <xref:System.Windows.Style.Triggers%2A> for a <xref:System.Windows.Controls.ListViewItem> control so that when a property value of a <xref:System.Windows.Controls.ListViewItem> changes, the <xref:System.Windows.Style> of the <xref:System.Windows.Controls.ListViewItem> changes in response.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8527b-104">예제</span><span class="sxs-lookup"><span data-stu-id="8527b-104">Example</span></span>  
 <span data-ttu-id="8527b-105">원하는 경우는 <xref:System.Windows.Style> 의 <xref:System.Windows.Controls.ListViewItem> 속성 변경에 대 한 응답을 변경 하려면 정의 <xref:System.Windows.Style.Triggers%2A> 에 대 한는 <xref:System.Windows.Style> 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="8527b-105">If you want the <xref:System.Windows.Style> of a <xref:System.Windows.Controls.ListViewItem> to change in response to property changes, define <xref:System.Windows.Style.Triggers%2A> for the <xref:System.Windows.Style> change.</span></span>  
  
 <span data-ttu-id="8527b-106">다음 예제에서는 정의 <xref:System.Windows.Trigger> 로 설정 하는 <xref:System.Windows.Controls.Control.Foreground%2A> 속성을 <xref:System.Windows.Media.Brushes.Blue%2A> , 코드 변경 내용에서 <xref:System.Windows.FrameworkElement.Cursor%2A> 표시 하는 <xref:System.Windows.Input.CursorType.Hand> 때는 <xref:System.Windows.UIElement.IsMouseOver%2A> 속성 변경 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="8527b-106">The following example defines a <xref:System.Windows.Trigger> that sets the <xref:System.Windows.Controls.Control.Foreground%2A> property to <xref:System.Windows.Media.Brushes.Blue%2A> and changes the <xref:System.Windows.FrameworkElement.Cursor%2A> to display a <xref:System.Windows.Input.CursorType.Hand> when the <xref:System.Windows.UIElement.IsMouseOver%2A> property changes to `true`.</span></span>  
  
 [!code-xaml[ListViewChkBox#ListViewItemTriggersStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersstart)]  
[!code-xaml[ListViewChkBox#Trigger](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#trigger)]  
[!code-xaml[ListViewChkBox#ListViewItemTriggersEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersend)]  
  
 <span data-ttu-id="8527b-107">다음 예제에서는 정의 <xref:System.Windows.MultiTrigger> 로 설정 하는 <xref:System.Windows.Controls.Control.Foreground%2A> 속성은 <xref:System.Windows.Controls.ListViewItem> 를 <xref:System.Windows.Media.Brushes.Yellow%2A> 때는 <xref:System.Windows.Controls.ListViewItem> 선택한 항목은 키보드 포커스를 가진 합니다.</span><span class="sxs-lookup"><span data-stu-id="8527b-107">The following example defines a <xref:System.Windows.MultiTrigger> that sets the <xref:System.Windows.Controls.Control.Foreground%2A> property of a <xref:System.Windows.Controls.ListViewItem> to <xref:System.Windows.Media.Brushes.Yellow%2A> when the <xref:System.Windows.Controls.ListViewItem> is the selected item and has keyboard focus.</span></span>  
  
 [!code-xaml[ListViewChkBox#ListViewItemTriggersStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersstart)]  
[!code-xaml[ListViewChkBox#MultiTrigger](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#multitrigger)]  
[!code-xaml[ListViewChkBox#ListViewItemTriggersEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersend)]  
  
## <a name="see-also"></a><span data-ttu-id="8527b-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8527b-108">See Also</span></span>  
 <xref:System.Windows.Controls.Control>  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [<span data-ttu-id="8527b-109">방법 항목</span><span class="sxs-lookup"><span data-stu-id="8527b-109">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [<span data-ttu-id="8527b-110">ListView 개요</span><span class="sxs-lookup"><span data-stu-id="8527b-110">ListView Overview</span></span>](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [<span data-ttu-id="8527b-111">GridView 개요</span><span class="sxs-lookup"><span data-stu-id="8527b-111">GridView Overview</span></span>](../../../../docs/framework/wpf/controls/gridview-overview.md)
