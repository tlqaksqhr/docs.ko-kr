---
title: "방법: TreeView에서 TreeViewItem 찾기 | Microsoft Docs"
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
  - "TreeView 컨트롤[WPF], TreeViewItem 찾기"
  - "TreeViewItem[WPF], 찾기"
ms.assetid: 72ecd40c-3939-4e01-b617-5e9daa6074d9
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# 방법: TreeView에서 TreeViewItem 찾기
<xref:System.Windows.Controls.TreeView> 컨트롤에서는 계층적 데이터를 표시하는 편리한 방법을 제공합니다.  <xref:System.Windows.Controls.TreeView>가 데이터 소스에 바인딩되어 있으면 <xref:System.Windows.Controls.TreeView.SelectedItem%2A> 속성에서 선택된 데이터 개체를 빠르게 검색할 수 있는 편리한 방법을 제공합니다.  일반적으로 기본 데이터 개체를 사용하는 것이 가장 좋지만, 데이터의 포함하는 <xref:System.Windows.Controls.TreeViewItem>을 프로그래밍 방식으로 조작해야 하는 경우도 있습니다.  예를 들어 프로그래밍 방식으로 <xref:System.Windows.Controls.TreeViewItem>을 확장하거나 <xref:System.Windows.Controls.TreeView>에서 다른 항목을 선택해야 할 수 있습니다.  
  
 특정 데이터 개체를 포함하는 <xref:System.Windows.Controls.TreeViewItem>을 찾으려면 <xref:System.Windows.Controls.TreeView>의 각 수준을 트래버스해야 합니다.  성능을 향상시키기 위해 <xref:System.Windows.Controls.TreeView>의 항목을 가상화할 수도 있습니다.  또한 항목을 가상화할 경우 데이터 개체가 포함되는지 여부를 확인하도록 <xref:System.Windows.Controls.TreeViewItem>을 구현해야 합니다.  
  
## 예제  
  
## 설명  
 다음 예제에서는 <xref:System.Windows.Controls.TreeView>에서 특정 개체를 검색하고 이 개체의 포함하는 <xref:System.Windows.Controls.TreeViewItem>을 반환합니다.  이 예제에서는 각 <xref:System.Windows.Controls.TreeViewItem>이 자식 항목을 검색할 수 있도록 인스턴스화되었는지 확인합니다.  또한 이 예제는 <xref:System.Windows.Controls.TreeView>에서 가상화된 항목을 사용하지 않는 경우에도 작동합니다.  
  
> [!NOTE]
>  다음 예제는 기본 데이터 모델에 관계없이 모든 <xref:System.Windows.Controls.TreeView>에 대해 작동하며, 개체를 찾을 때까지 모든 <xref:System.Windows.Controls.TreeViewItem>을 검색합니다.  성능을 향상시키는 또 다른 방법은 데이터 모델에서 지정된 개체를 검색하고, 데이터 계층 내에서 개체 위치를 추적한 다음, <xref:System.Windows.Controls.TreeView>에서 해당하는 <xref:System.Windows.Controls.TreeViewItem>을 찾는 것입니다.  그러나 이 성능 향상 방법을 사용하려면 데이터 모델에 대한 지식이 필요하며 지정된 모든 <xref:System.Windows.Controls.TreeView>에 사용할 수 있도록 이 방법을 일반화할 수는 없습니다.  
  
## 코드  
 [!code-csharp[TreeViewFindTVI#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml.cs#1)]
 [!code-vb[TreeViewFindTVI#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TreeViewFindTVI/VisualBasic/MainWindow.xaml.vb#1)]  
  
 앞의 코드는 `BringIntoView`라는 메서드를 노출하는 사용자 지정 <xref:System.Windows.Controls.VirtualizingStackPanel>을 기반으로 합니다.  다음 코드에서는 사용자 지정 <xref:System.Windows.Controls.VirtualizingStackPanel>을 정의합니다.  
  
 [!code-csharp[TreeViewFindTVI#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml.cs#2)]
 [!code-vb[TreeViewFindTVI#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TreeViewFindTVI/VisualBasic/MainWindow.xaml.vb#2)]  
  
 다음 XAML에서는 사용자 지정 <xref:System.Windows.Controls.VirtualizingStackPanel>을 사용하는 <xref:System.Windows.Controls.TreeView>를 만드는 방법을 보여 줍니다.  
  
 [!code-xml[TreeViewFindTVI#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml#3)]  
  
## 참고 항목  
 [TreeView의 성능 개선](../../../../docs/framework/wpf/controls/how-to-improve-the-performance-of-a-treeview.md)