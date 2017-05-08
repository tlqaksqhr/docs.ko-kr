---
title: "방법: TreeView의 성능 개선 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "TreeView 컨트롤[WPF], 성능 향상"
ms.assetid: b792c740-cf2b-4da8-8ba8-3d2e5a821874
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# 방법: TreeView의 성능 개선
<xref:System.Windows.Controls.TreeView>에 항목이 여러 개 포함되어 있으면 로드하는 데 소요되는 시간 때문에 사용자 인터페이스가 크게 지연될 수 있습니다.  <xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizing%2A?displayProperty=fullName> 연결된 속성을 `true`로 설정하면 로드 시간을 단축할 수 있습니다.  사용자가 마우스 휠을 사용하거나 스크롤 막대의 엄지 단추를 끌어 <xref:System.Windows.Controls.TreeView>를 스크롤하는 경우에도 UI 반응 속도가 느릴 수 있습니다.  <xref:System.Windows.Controls.VirtualizingStackPanel.VirtualizationMode%2A?displayProperty=fullName> 연결된 속성을 <xref:System.Windows.Controls.VirtualizationMode>으로 설정하면 사용자가 스크롤할 때의 <xref:System.Windows.Controls.TreeView> 성능을 높일 수 있습니다.  
  
## 예제  
  
## 설명  
 다음 예제에서는 <xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizing%2A?displayProperty=fullName>을 true로 설정하고 <xref:System.Windows.Controls.VirtualizingStackPanel.VirtualizationMode%2A?displayProperty=fullName>를 <xref:System.Windows.Controls.VirtualizationMode>으로 설정하여 성능을 최적화하는 <xref:System.Windows.Controls.TreeView>를 만듭니다.  
  
## 코드  
 [!code-xml[RecycleItemContainerShippets#VirtualizingTreeView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml#virtualizingtreeview)]  
  
 다음 예제에서는 이전 예제에서 사용한 데이터를 보여 줍니다.  
  
 [!code-csharp[RecycleItemContainerShippets#TreeViewData](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml.cs#treeviewdata)]
 [!code-vb[RecycleItemContainerShippets#TreeViewData](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RecycleItemContainerShippets/visualbasic/window1.xaml.vb#treeviewdata)]  
  
## 참고 항목  
 [컨트롤](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)