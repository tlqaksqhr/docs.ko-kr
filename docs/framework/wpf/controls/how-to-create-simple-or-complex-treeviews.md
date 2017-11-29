---
title: "방법: 간단하거나 복잡한 TreeView 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- TreeView control [WPF], creating
- Control class [WPF], TreeView [WPF], creating
ms.assetid: 1defbb78-b8e7-4c0e-b650-576453ac828d
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5e09f0f39d0c9a40a0e91299d308921917067166
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-simple-or-complex-treeviews"></a>방법: 간단하거나 복잡한 TreeView 만들기
이 예제에는 간단 하거나 복잡 한를 만드는 방법을 보여 줍니다 <xref:System.Windows.Controls.TreeView> 컨트롤입니다.  
  
 A <xref:System.Windows.Controls.TreeView> 계층 구조로 구성 됩니다 <xref:System.Windows.Controls.TreeViewItem> 컨트롤을 포함할 수 있는 간단한 텍스트 문자열와 더 복잡 한 콘텐츠를 같은 <xref:System.Windows.Controls.Button> 컨트롤 또는 <xref:System.Windows.Controls.StackPanel> 포함 된 내용이 있습니다. 명시적으로 정의할 수는 <xref:System.Windows.Controls.TreeView> 콘텐츠 또는 데이터 원본에서 콘텐츠를 제공할 수 있습니다. 이 항목에서는 이러한 개념의 예를 제공 합니다.  
  
## <a name="example"></a>예제  
 <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> 속성은 <xref:System.Windows.Controls.TreeViewItem> 콘텐츠를 포함 하는 <xref:System.Windows.Controls.TreeView> 해당 항목에 대해 표시 됩니다. A <xref:System.Windows.Controls.TreeViewItem> 수도 <xref:System.Windows.Controls.TreeViewItem> 자식 요소와 컨트롤 사용 하 여 이러한 하위 요소를 정의할 수는 <xref:System.Windows.Controls.ItemsControl.Items%2A> 속성입니다.  
  
 다음 예제에서는 명시적으로 정의 하는 방법을 보여 줍니다. <xref:System.Windows.Controls.TreeViewItem> 설정 하 여 콘텐츠는 <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> 속성을 텍스트 문자열입니다.  
  
 [!code-xaml[TreeViewSimple#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#1)]  
  
 다음 예제에서는의 자식 요소를 정의 하는 방법을 보여는 <xref:System.Windows.Controls.TreeViewItem> 정의 하 여 <xref:System.Windows.Controls.ItemsControl.Items%2A> 있는 <xref:System.Windows.Controls.Button> 컨트롤입니다.  
  
 [!code-xaml[TreeViewSimple#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#3)]  
  
 만드는 방법을 보여 주는 다음 예제는 <xref:System.Windows.Controls.TreeView> 위치는 <xref:System.Windows.Data.XmlDataProvider> 제공 <xref:System.Windows.Controls.TreeViewItem> 콘텐츠 및 <xref:System.Windows.HierarchicalDataTemplate> 콘텐츠의 모양을 정의 합니다.  
  
 [!code-xaml[TreeViewSimple#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#6)]  
  
 [!code-xaml[TreeViewSimple#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#7)]  
  
 [!code-xaml[TreeViewSimple#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#5)]  
  
 만드는 방법을 보여 주는 다음 예제는 <xref:System.Windows.Controls.TreeView> 여기서는 <xref:System.Windows.Controls.TreeViewItem> 넣는 <xref:System.Windows.Controls.DockPanel> 내용을 포함 하는 컨트롤입니다.  
  
 [!code-xaml[TreeViewSimple#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#9)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Controls.TreeView>  
 <xref:System.Windows.Controls.TreeViewItem>  
 [TreeView 개요](../../../../docs/framework/wpf/controls/treeview-overview.md)  
 [방법 항목](../../../../docs/framework/wpf/controls/treeview-how-to-topics.md)
