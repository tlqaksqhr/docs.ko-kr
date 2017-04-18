---
title: "방법: SelectedValue, SelectedValuePath 및 SelectedItem 사용 | Microsoft Docs"
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
  - "Control 클래스, SelectedItem 속성"
  - "Control 클래스, SelectedValue 속성"
  - "Control 클래스, SelectedValuePath 속성"
  - "Control 클래스, TreeView 속성"
  - "SelectedValue, SelectedItem 속성"
  - "SelectedValue, SelectedValuePath 속성"
  - "TreeView 컨트롤, SelectedItem 속성"
  - "TreeView 컨트롤, SelectedValue 속성"
  - "TreeView 컨트롤, SelectedValuePath 속성"
ms.assetid: 2fc92ad4-f02c-4f89-bbe9-d4978a7af0db
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# 방법: SelectedValue, SelectedValuePath 및 SelectedItem 사용
이 예제에서는 <xref:System.Windows.Controls.TreeView.SelectedValue%2A> 및 <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> 속성을 사용하여 <xref:System.Windows.Controls.TreeView>의 <xref:System.Windows.Controls.TreeView.SelectedItem%2A>에 대한 값을 지정하는 방법을 보여 줍니다.  
  
## 예제  
 <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> 속성은 <xref:System.Windows.Controls.TreeView>의 <xref:System.Windows.Controls.TreeView.SelectedItem%2A>에 대해 <xref:System.Windows.Controls.TreeView.SelectedValue%2A>를 지정하는 방법을 제공합니다.  <xref:System.Windows.Controls.TreeView.SelectedItem%2A>은 <xref:System.Windows.Controls.ItemsControl.Items%2A> 컬렉션의 개체를 나타내며 <xref:System.Windows.Controls.TreeView>는 선택한 항목의 단일 속성에 대한 값을 표시합니다.  <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> 속성은 <xref:System.Windows.Controls.TreeView.SelectedValue%2A> 속성의 값을 확인하는 데 사용되는 속성에 대한 경로를 지정합니다.  이 항목의 예제에서는 이 개념을 설명합니다.  
  
 다음 예제에서는 직원 정보가 포함된 <xref:System.Windows.Data.XmlDataProvider>를 보여 줍니다.  
  
 [!code-xml[TreeViewSelectedValue#XMLDataProvider](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#xmldataprovider)]  
  
 다음 예제에서는 `Employee`의 `EmployeeName` 및 `EmployeeWorkDay`를 표시하는 <xref:System.Windows.HierarchicalDataTemplate>을 정의합니다.  <xref:System.Windows.HierarchicalDataTemplate>은 `EmployeeNumber`를 템플릿의 일부로 지정하지 않습니다.  
  
 [!code-xml[TreeViewSelectedValue#HierarchicalDataTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#hierarchicaldatatemplate)]  
  
 다음 예제에서는 이전에 정의된 <xref:System.Windows.HierarchicalDataTemplate>을 사용하고 <xref:System.Windows.Controls.TreeView.SelectedValue%2A> 속성을 `EmployeeNumber`로 설정하는 <xref:System.Windows.Controls.TreeView>를 보여 줍니다.  <xref:System.Windows.Controls.TreeView>에서 `EmployeeName`을 선택하면 선택한 `EmployeeName`에 해당하는 `EmployeeInfo` 데이터 항목을 <xref:System.Windows.Controls.TreeView.SelectedItem%2A> 속성에서 반환합니다.  그러나 이 <xref:System.Windows.Controls.TreeView>의 <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A>가 `EmployeeNumber`로 설정되어 있기 때문에 <xref:System.Windows.Controls.TreeView.SelectedValue%2A>가 `EmployeeNumber`로 설정됩니다.  
  
 [!code-xml[TreeViewSelectedValue#SelectedValuePath](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#selectedvaluepath)]  
  
## 참고 항목  
 <xref:System.Windows.Controls.TreeView>   
 <xref:System.Windows.Controls.TreeViewItem>   
 [TreeView 개요](../../../../docs/framework/wpf/controls/treeview-overview.md)   
 [방법 항목](../../../../docs/framework/wpf/controls/treeview-how-to-topics.md)