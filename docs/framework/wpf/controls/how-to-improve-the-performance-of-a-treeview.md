---
title: "방법: TreeView의 성능 개선"
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
helpviewer_keywords: TreeView control [WPF], improving the performance
ms.assetid: b792c740-cf2b-4da8-8ba8-3d2e5a821874
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 209f2c5645758aba4d1e10fc36fe773faa975e6b
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-improve-the-performance-of-a-treeview"></a><span data-ttu-id="9d3ec-102">방법: TreeView의 성능 개선</span><span class="sxs-lookup"><span data-stu-id="9d3ec-102">How to: Improve the Performance of a TreeView</span></span>
<span data-ttu-id="9d3ec-103">경우는 <xref:System.Windows.Controls.TreeView> 많은 항목이 포함 된 로드 하는 데 걸리는 시간의 양 사용자 인터페이스에 크게 지연 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d3ec-103">If a <xref:System.Windows.Controls.TreeView> contains many items, the amount of time it takes to load may cause a significant delay in the user interface.</span></span> <span data-ttu-id="9d3ec-104">설정 하 여 로드 하는 시간을 향상 시킬 수 있습니다는 `VirtualizingStackPanel.IsVirtualizing` 연결 된 속성을 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="9d3ec-104">You can improve the load time by setting the `VirtualizingStackPanel.IsVirtualizing` attached property to `true`.</span></span>  <span data-ttu-id="9d3ec-105">UI도 사용자가 스크롤할 때 응답 속도가 느려질 수 있습니다는 <xref:System.Windows.Controls.TreeView> 스크롤 막대의 엄지 단추를 끌거나 마우스 휠을 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="9d3ec-105">The UI might also be slow to react when a user scrolls the <xref:System.Windows.Controls.TreeView> by using the mouse wheel or dragging the thumb of a scrollbar.</span></span> <span data-ttu-id="9d3ec-106">성능을 향상 시킬 수 있습니다는 <xref:System.Windows.Controls.TreeView> 사용자가을 설정 하 여를 스크롤할 때는 `VirtualizingStackPanel.VirtualizationMode` 연결 된 속성을 <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>합니다.</span><span class="sxs-lookup"><span data-stu-id="9d3ec-106">You can improve the performance of the <xref:System.Windows.Controls.TreeView> when the user scrolls by setting the `VirtualizingStackPanel.VirtualizationMode` attached property to <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9d3ec-107">예제</span><span class="sxs-lookup"><span data-stu-id="9d3ec-107">Example</span></span>  
  
## <a name="description"></a><span data-ttu-id="9d3ec-108">설명</span><span class="sxs-lookup"><span data-stu-id="9d3ec-108">Description</span></span>  
<span data-ttu-id="9d3ec-109">다음 예제에서는 한 <xref:System.Windows.Controls.TreeView> 로 설정 하는 `VirtualizingStackPanel.IsVirtualizing` 연결 된 속성을 true로 및 `VirtualizingStackPanel.VirtualizationMode` 연결 된 속성을 <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> 성능을 최적화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9d3ec-109">The following example creates a <xref:System.Windows.Controls.TreeView> that sets the `VirtualizingStackPanel.IsVirtualizing` attached property to true and the `VirtualizingStackPanel.VirtualizationMode` attached property to <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> to optimize its performance.</span></span>  
  
## <a name="code"></a><span data-ttu-id="9d3ec-110">코드</span><span class="sxs-lookup"><span data-stu-id="9d3ec-110">Code</span></span>  
 [!code-xaml[RecycleItemContainerShippets#VirtualizingTreeView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml#virtualizingtreeview)]  
  
 <span data-ttu-id="9d3ec-111">다음 예제에서는 사용 하 여 이전 예제에서 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9d3ec-111">The following example shows the data that the previous example uses.</span></span>  
  
 [!code-csharp[RecycleItemContainerShippets#TreeViewData](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml.cs#treeviewdata)]
 [!code-vb[RecycleItemContainerShippets#TreeViewData](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RecycleItemContainerShippets/visualbasic/window1.xaml.vb#treeviewdata)]  
  
## <a name="see-also"></a><span data-ttu-id="9d3ec-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9d3ec-112">See Also</span></span>  
 [<span data-ttu-id="9d3ec-113">컨트롤</span><span class="sxs-lookup"><span data-stu-id="9d3ec-113">Controls</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)
