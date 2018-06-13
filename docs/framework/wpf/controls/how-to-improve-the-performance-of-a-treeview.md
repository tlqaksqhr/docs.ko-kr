---
title: '방법: TreeView의 성능 개선'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TreeView control [WPF], improving the performance
ms.assetid: b792c740-cf2b-4da8-8ba8-3d2e5a821874
ms.openlocfilehash: 75f17c770af89f08fedfd3c8193a916901fe6f79
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33552755"
---
# <a name="how-to-improve-the-performance-of-a-treeview"></a>방법: TreeView의 성능 개선
경우는 <xref:System.Windows.Controls.TreeView> 많은 항목이 포함 된 로드 하는 데 걸리는 시간의 양 사용자 인터페이스에 크게 지연 될 수 있습니다. 설정 하 여 로드 하는 시간을 향상 시킬 수 있습니다는 `VirtualizingStackPanel.IsVirtualizing` 연결 된 속성을 `true`합니다.  UI도 사용자가 스크롤할 때 응답 속도가 느려질 수 있습니다는 <xref:System.Windows.Controls.TreeView> 스크롤 막대의 엄지 단추를 끌거나 마우스 휠을 사용 하 여 합니다. 성능을 향상 시킬 수 있습니다는 <xref:System.Windows.Controls.TreeView> 사용자가을 설정 하 여를 스크롤할 때는 `VirtualizingStackPanel.VirtualizationMode` 연결 된 속성을 <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>합니다.  
  
## <a name="example"></a>예제  
  
## <a name="description"></a>설명  
다음 예제에서는 한 <xref:System.Windows.Controls.TreeView> 로 설정 하는 `VirtualizingStackPanel.IsVirtualizing` 연결 된 속성을 true로 및 `VirtualizingStackPanel.VirtualizationMode` 연결 된 속성을 <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> 성능을 최적화할 수 있습니다.  
  
## <a name="code"></a>코드  
 [!code-xaml[RecycleItemContainerShippets#VirtualizingTreeView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml#virtualizingtreeview)]  
  
 다음 예제에서는 사용 하 여 이전 예제에서 데이터를 보여 줍니다.  
  
 [!code-csharp[RecycleItemContainerShippets#TreeViewData](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml.cs#treeviewdata)]
 [!code-vb[RecycleItemContainerShippets#TreeViewData](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RecycleItemContainerShippets/visualbasic/window1.xaml.vb#treeviewdata)]  
  
## <a name="see-also"></a>참고 항목  
 [컨트롤](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)
