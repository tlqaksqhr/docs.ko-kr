---
title: "방법: 깊이를 확인할 수 없는 데이터에 TreeView 바인딩"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: TreeView control [WPF], binding to data of indeterminate depth
ms.assetid: daddcd74-1b0f-4ffd-baeb-ec934c5e0f53
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: be21ecb75420b6499e5b95d5f4d93a5f079f9646
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-bind-a-treeview-to-data-that-has-an-indeterminable-depth"></a>방법: 깊이를 확인할 수 없는 데이터에 TreeView 바인딩
바인딩할 하는 경우가 있을 수 있습니다는 <xref:System.Windows.Controls.TreeView> 깊이가 알 수 없는 데이터 원본에 있습니다.  이 데이터를 재귀 폴더가 포함 폴더, 파일 시스템 또는 회사의 조직 구조와 같이 기본적 직원 부하 직원으로 다른 직원 들이 있는 경우에 발생할 수 있습니다.  
  
 데이터 원본에는 계층적 개체 모델이 있어야 합니다. 예를 들어 한 `Employee` 클래스 직원의 직속 부하 직원 개체의 컬렉션을 포함 될 수 있습니다. 계층적 방식으로 데이터를 표시 하는 데이터의 계층적 표현을 빌드해야 합니다.  
  
 설정 하는 경우는 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A?displayProperty=nameWithType> 속성 및 경우에는 <xref:System.Windows.Controls.ItemsControl> 생성는 <xref:System.Windows.Controls.ItemsControl> 각 자식 항목 다음의 자식에 대 한 <xref:System.Windows.Controls.ItemsControl> 동일한 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> 부모로 합니다. 예를 들어, 설정 하는 경우는 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> 데이터 바인딩된 속성 <xref:System.Windows.Controls.TreeView>, 각 <xref:System.Windows.Controls.TreeViewItem> 생성된 되는 <xref:System.Windows.DataTemplate> 에 할당 된는 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> 의 속성은 <xref:System.Windows.Controls.TreeView>합니다.  
  
 <xref:System.Windows.HierarchicalDataTemplate> 지정할 수 있습니다는 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 에 대 한는 <xref:System.Windows.Controls.TreeViewItem>, 또는 모든 <xref:System.Windows.Controls.HeaderedItemsControl>, 데이터 서식 파일에 있습니다. 설정 하는 경우는 <xref:System.Windows.HierarchicalDataTemplate.ItemsSource%2A?displayProperty=nameWithType> 속성 값을 때 사용 되는 <xref:System.Windows.HierarchicalDataTemplate> 적용 됩니다. 사용 하 여는 <xref:System.Windows.HierarchicalDataTemplate>를 재귀적으로 설정할 수 있습니다는 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 각 <xref:System.Windows.Controls.TreeViewItem> 에 <xref:System.Windows.Controls.TreeView>합니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 바인딩하는 방법을 <xref:System.Windows.Controls.TreeView> 계층적 데이터 및 사용에는 <xref:System.Windows.HierarchicalDataTemplate> 지정 하는 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 각각에 대해 <xref:System.Windows.Controls.TreeViewItem>합니다.  <xref:System.Windows.Controls.TreeView> 회사의 직원을 나타내는 XML 데이터에 바인딩합니다.  각 `Employee` 다른 요소를 포함할 수 `Employee` 를 부하 직원을 나타내는 요소입니다. 데이터가 재귀적으로 적용 되어는 <xref:System.Windows.HierarchicalDataTemplate> 각 수준에 적용할 수 있습니다.  
  
 [!code-xaml[TreeViewWithUnknownDepth#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewWithUnknownDepth/CS/Window1.xaml#1)]  
  
## <a name="see-also"></a>참고 항목  
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [데이터 템플릿 개요](../../../../docs/framework/wpf/data/data-templating-overview.md)
