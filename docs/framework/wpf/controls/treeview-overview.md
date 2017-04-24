---
title: "TreeView 개요 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Control 클래스, TreeView"
  - "노드 확장"
  - "TreeView 컨트롤, TreeView 컨트롤 정보"
ms.assetid: 62212512-5a5c-4864-949e-b6a6a3a52c02
caps.latest.revision: 33
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 32
---
# TreeView 개요
<xref:System.Windows.Controls.TreeView> 컨트롤은 축소 가능한 노드를 사용하여 계층 구조로 정보를 표시할 수 있는 방법을 제공합니다.  이 항목에서는 <xref:System.Windows.Controls.TreeView> 및 <xref:System.Windows.Controls.TreeViewItem> 컨트롤에 대해 소개하고 컨트롤 사용 방법을 보여 주는 간단한 예제를 제공합니다.  
  
   
  
<a name="Simple_TreeView_Control"></a>   
## TreeView 정의  
 <xref:System.Windows.Controls.TreeView>는 <xref:System.Windows.Controls.TreeViewItem> 컨트롤을 사용하여 항목을 중첩하는 <xref:System.Windows.Controls.ItemsControl>입니다.  다음 예제에서는 <xref:System.Windows.Controls.TreeView>를 만듭니다.  
  
 [!code-xml[TreeViewSnips#EmbeddedTVIs](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSnips/CSharp/Window1.xaml#embeddedtvis)]  
  
<a name="Creating_a_TreeView"></a>   
## TreeView 만들기  
 <xref:System.Windows.Controls.TreeView> 컨트롤에는 <xref:System.Windows.Controls.TreeViewItem> 컨트롤 계층이 포함됩니다.  <xref:System.Windows.Controls.TreeViewItem> 컨트롤은 <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A>와 <xref:System.Windows.Controls.ItemsControl.Items%2A> 컬렉션이 있는 <xref:System.Windows.Controls.HeaderedItemsControl>입니다.  
  
 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]을 사용하여 <xref:System.Windows.Controls.TreeView>를 정의하는 경우 <xref:System.Windows.Controls.TreeViewItem> 컨트롤의 <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> 내용과 해당 컬렉션을 구성하는 항목을 명시적으로 정의할 수 있습니다.  앞의 그림은 이 작업을 수행하는 방법을 보여 줍니다.  
  
 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>를 데이터 소스로 지정한 다음 <xref:System.Windows.Controls.HeaderedItemsControl.HeaderTemplate%2A>과 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>을 지정하여 <xref:System.Windows.Controls.TreeViewItem>의 내용을 정의할 수도 있습니다.  
  
 <xref:System.Windows.HierarchicalDataTemplate> 개체를 사용하여 <xref:System.Windows.Controls.TreeViewItem> 컨트롤의 레이아웃을 정의할 수도 있습니다.  자세한 내용과 예제는 [SelectedValue, SelectedValuePath 및 SelectedItem 사용](../../../../docs/framework/wpf/controls/how-to-use-selectedvalue-selectedvaluepath-and-selecteditem.md)을 참조하십시오.  
  
 항목이 <xref:System.Windows.Controls.TreeViewItem> 컨트롤이 아닌 경우에도 <xref:System.Windows.Controls.TreeView> 컨트롤이 표시될 때 자동으로 <xref:System.Windows.Controls.TreeViewItem> 컨트롤 안에 포함됩니다.  
  
<a name="Expanding_and_Collapsing_a_TreeViewItem"></a>   
## TreeViewItem 확장 및 축소  
 사용자가 <xref:System.Windows.Controls.TreeViewItem>을 확장하면 <xref:System.Windows.Controls.TreeViewItem.IsExpanded%2A> 속성이 `true`로 설정됩니다.  사용자가 직접 확장하거나 축소하지 않아도 <xref:System.Windows.Controls.TreeViewItem.IsExpanded%2A> 속성을 `true`\(확장\) 또는 `false`\(축소\)로 설정하여 <xref:System.Windows.Controls.TreeViewItem>을 확장하거나 축소할 수 있습니다.  이 속성이 변경되면 <xref:System.Windows.Controls.TreeViewItem.Expanded> 또는 <xref:System.Windows.Controls.TreeViewItem.Collapsed> 이벤트가 발생합니다.  
  
 <xref:System.Windows.Controls.TreeViewItem> 컨트롤에 대해 <xref:System.Windows.FrameworkElement.BringIntoView%2A> 메서드가 호출되면 <xref:System.Windows.Controls.TreeViewItem>과 해당 부모 <xref:System.Windows.Controls.TreeViewItem> 컨트롤이 확장됩니다.  <xref:System.Windows.Controls.TreeViewItem>이 표시되지 않거나 일부만 표시되는 경우 이를 표시할 수 있도록 <xref:System.Windows.Controls.TreeView>가 스크롤됩니다.  
  
<a name="TreeViewItem_Selection"></a>   
## TreeViewItem 선택  
 사용자가 <xref:System.Windows.Controls.TreeViewItem> 컨트롤을 클릭하여 선택하면 <xref:System.Windows.Controls.TreeViewItem.Selected> 이벤트가 발생하고 컨트롤의 <xref:System.Windows.Controls.TreeViewItem.IsSelected%2A> 속성이 `true`로 설정됩니다.  <xref:System.Windows.Controls.TreeViewItem>도 <xref:System.Windows.Controls.TreeView> 컨트롤의 <xref:System.Windows.Controls.TreeView.SelectedItem%2A>이 됩니다.  이와는 반대로 <xref:System.Windows.Controls.TreeViewItem> 컨트롤에서 다른 컨트롤로 선택이 변경되면 <xref:System.Windows.Controls.TreeViewItem.Unselected> 이벤트가 발생하고 컨트롤의 <xref:System.Windows.Controls.TreeViewItem.IsSelected%2A> 속성이 `false`로 설정됩니다.  
  
 <xref:System.Windows.Controls.TreeView> 컨트롤의 <xref:System.Windows.Controls.TreeView.SelectedItem%2A> 속성은 읽기 전용 속성이므로 명시적으로 설정할 수 없습니다.  사용자가 <xref:System.Windows.Controls.TreeViewItem> 컨트롤을 클릭하거나 <xref:System.Windows.Controls.TreeViewItem> 컨트롤의 <xref:System.Windows.Controls.TreeViewItem.IsSelected%2A> 속성이 `true`로 설정되어 있는 경우 <xref:System.Windows.Controls.TreeView.SelectedItem%2A> 속성이 설정됩니다.  
  
 <xref:System.Windows.Controls.TreeView.SelectedItem%2A>의 <xref:System.Windows.Controls.TreeView.SelectedValue%2A>를 지정하려면 <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> 속성을 사용합니다.  자세한 내용은 [SelectedValue, SelectedValuePath 및 SelectedItem 사용](../../../../docs/framework/wpf/controls/how-to-use-selectedvalue-selectedvaluepath-and-selecteditem.md)을 참조하십시오.  
  
 <xref:System.Windows.Controls.TreeView.SelectedItemChanged> 이벤트에서 이벤트 처리기를 등록하면 선택된 <xref:System.Windows.Controls.TreeViewItem>의 변경 여부를 파악할 수 있습니다.  이벤트 처리기에 제공된 <xref:System.Windows.RoutedPropertyChangedEventArgs%601>가 이전 선택에 해당하는 <xref:System.Windows.RoutedPropertyChangedEventArgs%601.OldValue%2A>와 현재 선택에 해당하는 <xref:System.Windows.RoutedPropertyChangedEventArgs%601.NewValue%2A>를 지정합니다.  응용 프로그램이나 사용자가 이전에 선택한 내용 또는 현재 선택한 내용이 없는 경우 두 값 중 하나가 `null`이 될 수 있습니다.  
  
<a name="TreeView_Style"></a>   
## TreeView 스타일  
 <xref:System.Windows.Controls.TreeView> 컨트롤의 기본 스타일은 <xref:System.Windows.Controls.ScrollViewer> 컨트롤이 있는 <xref:System.Windows.Controls.StackPanel> 개체 내에 컨트롤을 배치하는 것입니다.  <xref:System.Windows.Controls.TreeView>에 <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A> 속성을 설정한 경우 이 값에 따라 <xref:System.Windows.Controls.TreeView>가 표시되는 <xref:System.Windows.Controls.StackPanel> 개체의 크기가 결정됩니다.  표시할 내용이 표시 영역보다 큰 경우에는 사용자가 <xref:System.Windows.Controls.TreeView>의 내용을 스크롤할 수 있도록 <xref:System.Windows.Controls.ScrollViewer>가 자동으로 표시됩니다.  
  
 <xref:System.Windows.Controls.TreeViewItem> 컨트롤의 모양을 사용자 지정하려면 <xref:System.Windows.FrameworkElement.Style%2A> 속성을 사용자 지정 <xref:System.Windows.Style>로 설정합니다.  
  
 다음 예제에서는 <xref:System.Windows.FrameworkElement.Style%2A>을 사용하여 <xref:System.Windows.Controls.TreeViewItem> 컨트롤의 <xref:System.Windows.Controls.Control.Foreground%2A> 및 <xref:System.Windows.Controls.Control.FontSize%2A> 속성 값을 설정하는 방법을 보여 줍니다.  
  
 [!code-xml[TreeViewSimple#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#8)]  
  
<a name="Adding_Images_and_oOther_Content_to_TreeView_Items"></a>   
## TreeView 항목에 이미지 및 다른 내용 추가  
 <xref:System.Windows.Controls.TreeViewItem>의 <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A>에 두 개 이상의 개체를 포함할 수 있습니다.  <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> 내용에 여러 개의 개체를 포함하려면 <xref:System.Windows.Controls.Panel> 또는 <xref:System.Windows.Controls.StackPanel>과 같은 레이아웃 컨트롤 내에 개체를 포함합니다.  
  
 다음 예제에서는 <xref:System.Windows.Controls.TreeViewItem>의 <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A>를 <xref:System.Windows.Controls.DockPanel> 컨트롤에 포함된 <xref:System.Windows.Controls.CheckBox> 및 <xref:System.Windows.Controls.TextBlock>으로 정의하는 방법을 보여 줍니다.  
  
 [!code-xml[TreeViewSnips#TVIHeader](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSnips/CSharp/Window1.xaml#tviheader)]  
  
 다음 예제에서는 <xref:System.Windows.Controls.Image> 및 <xref:System.Windows.Controls.TextBlock>이 <xref:System.Windows.Controls.DockPanel> 컨트롤에 포함된 <xref:System.Windows.DataTemplate>을 정의하는 방법을 보여 줍니다.  <xref:System.Windows.Controls.TreeViewItem>의 <xref:System.Windows.Controls.HeaderedItemsControl.HeaderTemplate%2A> 또는 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>을 설정하는 데 <xref:System.Windows.DataTemplate>을 사용할 수 있습니다.  
  
 [!code-xml[TreeViewDataBinding#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewDataBinding/CSharp/Window1.xaml#6)]  
  
## 참고 항목  
 <xref:System.Windows.Controls.TreeView>   
 <xref:System.Windows.Controls.TreeViewItem>   
 [방법 항목](../../../../docs/framework/wpf/controls/treeview-how-to-topics.md)   
 [WPF 콘텐츠 모델](../../../../docs/framework/wpf/controls/wpf-content-model.md)