---
title: "방법: 깊이를 확인할 수 없는 데이터에 TreeView 바인딩 | Microsoft Docs"
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
  - "TreeView 컨트롤[WPF], 깊이를 확인할 수 없는 데이터에 바인딩"
ms.assetid: daddcd74-1b0f-4ffd-baeb-ec934c5e0f53
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# 방법: 깊이를 확인할 수 없는 데이터에 TreeView 바인딩
깊이를 알 수 없는 데이터 소스에 <xref:System.Windows.Controls.TreeView>를 바인딩해야 할 경우가 있습니다.  폴더에 폴더가 포함되는 파일 시스템이나 직원이 다른 직원을 직속 부하로 두는 회사의 조직 구조와 같이 데이터의 성격이 재귀적인 경우를 예로 들 수 있습니다.  
  
 이러한 데이터 소스에는 계층적 개체 모델이 있어야 합니다.  예를 들어 `Employee` 클래스에는 한 직원의 직속 부하인 Employee 개체의 컬렉션이 포함될 수 있습니다.  데이터가 계층적 방식이 아닌 다른 방식으로 표현되는 경우 데이터에 대한 계층적 표현을 만들어야 합니다.  
  
 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A?displayProperty=fullName> 속성을 설정하고 <xref:System.Windows.Controls.ItemsControl>이 각 자식 항목에 대해 <xref:System.Windows.Controls.ItemsControl>을 생성하는 경우 자식 <xref:System.Windows.Controls.ItemsControl>은 동일한 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>을 부모로 사용합니다.  예를 들어 데이터 바인딩 <xref:System.Windows.Controls.TreeView>에 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> 속성을 설정하면, 생성되는 각 <xref:System.Windows.Controls.TreeViewItem>이 <xref:System.Windows.Controls.TreeView>의 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> 속성에 할당된 <xref:System.Windows.DataTemplate>을 사용합니다.  
  
 <xref:System.Windows.HierarchicalDataTemplate>을 사용하면 <xref:System.Windows.Controls.TreeViewItem>에 대해 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>를 지정하거나 데이터 템플릿에 임의의 <xref:System.Windows.Controls.HeaderedItemsControl>을 지정할 수 있습니다.  <xref:System.Windows.HierarchicalDataTemplate.ItemsSource%2A?displayProperty=fullName> 속성을 설정하면 <xref:System.Windows.HierarchicalDataTemplate>이 적용될 때 해당 값이 사용됩니다.  <xref:System.Windows.HierarchicalDataTemplate>을 사용하면 <xref:System.Windows.Controls.TreeView>의 각 <xref:System.Windows.Controls.TreeViewItem>에 대해 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>를 재귀적으로 설정할 수 있습니다.  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Controls.TreeView>를 계층적 데이터에 바인딩한 다음 <xref:System.Windows.HierarchicalDataTemplate>을 사용하여 각 <xref:System.Windows.Controls.TreeViewItem>에 대한 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>를 지정하는 방법을 보여 줍니다.  <xref:System.Windows.Controls.TreeView>는 회사의 직원을 나타내는 XML 데이터에 바인딩됩니다.  각 `Employee` 요소는 해당 부하 직원을 나타내는 다른 `Employee` 요소를 포함할 수 있습니다.  데이터가 재귀적이므로 <xref:System.Windows.HierarchicalDataTemplate>을 각 수준에 적용할 수 있습니다.  
  
 [!code-xml[TreeViewWithUnknownDepth#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewWithUnknownDepth/CS/Window1.xaml#1)]  
  
## 참고 항목  
 [데이터 바인딩 개요](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [데이터 템플릿 개요](../../../../docs/framework/wpf/data/data-templating-overview.md)