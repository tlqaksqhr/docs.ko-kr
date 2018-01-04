---
title: "방법: GridView를 구현하는 ListView의 항목 그룹화"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ListView controls [WPF], grouping items with GridViews
- grouping items in ListViews implementing GridViews [WPF]
- GridView controls [WPF], grouping items
ms.assetid: eebef25b-ddc6-424e-a66d-ea228d1bf33d
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8a97a6c85036a6daf4e8c908186953f9a75f952a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-group-items-in-a-listview-that-implements-a-gridview"></a><span data-ttu-id="1dab5-102">방법: GridView를 구현하는 ListView의 항목 그룹화</span><span class="sxs-lookup"><span data-stu-id="1dab5-102">How to: Group Items in a ListView That Implements a GridView</span></span>
<span data-ttu-id="1dab5-103">에 있는 항목의 그룹을 표시 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.GridView> 의 보기 모드는 <xref:System.Windows.Controls.ListView> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="1dab5-103">This example shows how to display groups of items in the <xref:System.Windows.Controls.GridView> view mode of a <xref:System.Windows.Controls.ListView> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1dab5-104">예</span><span class="sxs-lookup"><span data-stu-id="1dab5-104">Example</span></span>  
 <span data-ttu-id="1dab5-105">에 있는 항목의 그룹을 표시 하려면는 <xref:System.Windows.Controls.ListView>, 정의 <xref:System.Windows.Data.CollectionViewSource>합니다.</span><span class="sxs-lookup"><span data-stu-id="1dab5-105">To display groups of items in a <xref:System.Windows.Controls.ListView>, define a <xref:System.Windows.Data.CollectionViewSource>.</span></span> <span data-ttu-id="1dab5-106">다음 예제에서는 한 <xref:System.Windows.Data.CollectionViewSource> 의 값에 따라 데이터 항목을 그룹화 하는 `Catalog` 데이터 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="1dab5-106">The following example shows a <xref:System.Windows.Data.CollectionViewSource> that groups data items according to the value of the `Catalog` data field.</span></span>  
  
 [!code-xaml[GridViewWithGroups#GroupingCollectionViewSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#groupingcollectionviewsource)]  
  
 <span data-ttu-id="1dab5-107">다음 예에서는 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 에 대 한는 <xref:System.Windows.Controls.ListView> 에 <xref:System.Windows.Data.CollectionViewSource> 앞의 예제에서 정의 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="1dab5-107">The following example sets the <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> for the <xref:System.Windows.Controls.ListView> to the <xref:System.Windows.Data.CollectionViewSource> that the previous example defines.</span></span> <span data-ttu-id="1dab5-108">이 예제에서는 또한 정의 <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> 구현 하는 <xref:System.Windows.Controls.Expander> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="1dab5-108">The example also defines a <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> that implements an <xref:System.Windows.Controls.Expander> control.</span></span>  
  
 [!code-xaml[GridViewWithGroups#ListViewGroups](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#listviewgroups)]  
[!code-xaml[GridViewWithGroups#ListViewEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#listviewend)]  
  
## <a name="see-also"></a><span data-ttu-id="1dab5-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1dab5-109">See Also</span></span>  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [<span data-ttu-id="1dab5-110">방법 항목</span><span class="sxs-lookup"><span data-stu-id="1dab5-110">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [<span data-ttu-id="1dab5-111">ListView 개요</span><span class="sxs-lookup"><span data-stu-id="1dab5-111">ListView Overview</span></span>](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [<span data-ttu-id="1dab5-112">GridView 개요</span><span class="sxs-lookup"><span data-stu-id="1dab5-112">GridView Overview</span></span>](../../../../docs/framework/wpf/controls/gridview-overview.md)
