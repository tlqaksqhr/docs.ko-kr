---
title: "방법: 간단하거나 복잡한 TreeView 만들기 | Microsoft Docs"
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
  - "Control 클래스, TreeView, 만들기"
  - "TreeView 컨트롤, 만들기"
ms.assetid: 1defbb78-b8e7-4c0e-b650-576453ac828d
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# 방법: 간단하거나 복잡한 TreeView 만들기
이 예제에서는 간단하거나 복잡한 <xref:System.Windows.Controls.TreeView> 컨트롤을 만드는 방법을 보여 줍니다.  
  
 <xref:System.Windows.Controls.TreeView>는 간단한 텍스트 문자열과, 포함된 내용이 있는 <xref:System.Windows.Controls.StackPanel> 컨트롤 또는 <xref:System.Windows.Controls.Button> 컨트롤 등의 보다 복잡한 내용을 포함할 수 있는 <xref:System.Windows.Controls.TreeViewItem> 컨트롤의 계층으로 구성됩니다.  <xref:System.Windows.Controls.TreeView>의 내용을 명시적으로 정의할 수도 있고 데이터 소스에서 내용을 제공하도록 설정할 수도 있습니다.  이 항목에서는 예제를 통해 이러한 개념에 대해 설명합니다.  
  
## 예제  
 <xref:System.Windows.Controls.TreeViewItem>의 <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> 속성에는 <xref:System.Windows.Controls.TreeView>가 해당 항목에 대해 표시하는 내용이 포함됩니다.  또한 <xref:System.Windows.Controls.TreeViewItem>은 <xref:System.Windows.Controls.TreeViewItem> 컨트롤을 자식 요소로 포함할 수 있으며 이러한 자식 요소는 <xref:System.Windows.Controls.ItemsControl.Items%2A> 속성을 사용하여 정의할 수 있습니다.  
  
 다음 예제에서는 <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> 속성을 텍스트 문자열로 설정하여 <xref:System.Windows.Controls.TreeViewItem>의 내용을 명시적으로 정의하는 방법을 보여 줍니다.  
  
 [!code-xml[TreeViewSimple#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#1)]  
  
 다음 예제에서는 <xref:System.Windows.Controls.Button> 컨트롤로 <xref:System.Windows.Controls.ItemsControl.Items%2A>를 정의하여 <xref:System.Windows.Controls.TreeViewItem>의 자식 요소를 정의하는 방법을 보여 줍니다.  
  
 [!code-xml[TreeViewSimple#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#3)]  
  
 다음 예제에서는 <xref:System.Windows.Data.XmlDataProvider>로 <xref:System.Windows.Controls.TreeViewItem> 내용을 지정하고 <xref:System.Windows.HierarchicalDataTemplate>으로 내용의 모양을 정의하여 <xref:System.Windows.Controls.TreeView>를 만드는 방법을 보여 줍니다.  
  
 [!code-xml[TreeViewSimple#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#6)]  
  
 [!code-xml[TreeViewSimple#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#7)]  
  
 [!code-xml[TreeViewSimple#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#5)]  
  
 다음 예제에서는 포함된 내용이 있는 <xref:System.Windows.Controls.DockPanel> 컨트롤을 <xref:System.Windows.Controls.TreeViewItem> 내용에 포함하여 <xref:System.Windows.Controls.TreeView>를 만드는 방법을 보여 줍니다.  
  
 [!code-xml[TreeViewSimple#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#9)]  
  
## 참고 항목  
 <xref:System.Windows.Controls.TreeView>   
 <xref:System.Windows.Controls.TreeViewItem>   
 [TreeView 개요](../../../../docs/framework/wpf/controls/treeview-overview.md)   
 [방법 항목](../../../../docs/framework/wpf/controls/treeview-how-to-topics.md)