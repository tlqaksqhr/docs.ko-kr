---
title: TreeView 개요
ms.date: 03/30/2017
helpviewer_keywords:
- expanding node [WPF]
- TreeView control [WPF], about TreeView control
- Control class [WPF], TreeView
ms.assetid: 62212512-5a5c-4864-949e-b6a6a3a52c02
ms.openlocfilehash: f8c49013bc34671ec590f0bd9f84a0f2cf3f9aaf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33557786"
---
# <a name="treeview-overview"></a>TreeView 개요
<xref:System.Windows.Controls.TreeView> 컨트롤은 축소 가능한 노드를 사용 하 여 계층 구조에서 정보를 표시 하는 방법을 제공 합니다. 이 항목에서는 소개는 <xref:System.Windows.Controls.TreeView> 및 <xref:System.Windows.Controls.TreeViewItem> 컨트롤과 목록과 해당 사용법은 간단한 예제를 제공 합니다.  
  
  
<a name="Simple_TreeView_Control"></a>   
## <a name="what-is-a-treeview"></a>TreeView란?  
 <xref:System.Windows.Controls.TreeView> 이 <xref:System.Windows.Controls.ItemsControl> 를 사용 하 여 항목을 중첩 하 <xref:System.Windows.Controls.TreeViewItem> 컨트롤입니다. 다음 예제에서는 <xref:System.Windows.Controls.TreeView>합니다.  
  
 [!code-xaml[TreeViewSnips#EmbeddedTVIs](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSnips/CSharp/Window1.xaml#embeddedtvis)]  
  
<a name="Creating_a_TreeView"></a>   
## <a name="creating-a-treeview"></a>TreeView 만들기  
 <xref:System.Windows.Controls.TreeView> 계층을 포함 하는 컨트롤 <xref:System.Windows.Controls.TreeViewItem> 컨트롤입니다. A <xref:System.Windows.Controls.TreeViewItem> 컨트롤은 한 <xref:System.Windows.Controls.HeaderedItemsControl> 올려진는 <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> 및 <xref:System.Windows.Controls.ItemsControl.Items%2A> 컬렉션입니다.  
  
 정의 하는 경우는 <xref:System.Windows.Controls.TreeView> 를 사용 하 여 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]를 명시적으로 정의할 수는 <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> 의 콘텐츠는 <xref:System.Windows.Controls.TreeViewItem> 컨트롤 및 해당 컬렉션을 구성 하는 항목입니다. 위의 그림에서는 이 메서드를 보여 줍니다.  
  
 지정할 수 있습니다는 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 으로 데이터 원본 한 다음 지정는 <xref:System.Windows.Controls.HeaderedItemsControl.HeaderTemplate%2A> 및 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> 정의 하는 <xref:System.Windows.Controls.TreeViewItem> 콘텐츠입니다.  
  
 레이아웃을 정의 하는 <xref:System.Windows.Controls.TreeViewItem> 컨트롤을 사용할 수도 있습니다 <xref:System.Windows.HierarchicalDataTemplate> 개체입니다. 자세한 내용 및 예제는 [SelectedValue, SelectedValuePath 및 SelectedItem 사용](../../../../docs/framework/wpf/controls/how-to-use-selectedvalue-selectedvaluepath-and-selecteditem.md)을 참조하세요.  
  
 항목이 없는 경우는 <xref:System.Windows.Controls.TreeViewItem> 컨트롤을 자동으로 묶어야 하 여 한 <xref:System.Windows.Controls.TreeViewItem> 시점을 제어할는 <xref:System.Windows.Controls.TreeView> 컨트롤이 표시 됩니다.  
  
<a name="Expanding_and_Collapsing_a_TreeViewItem"></a>   
## <a name="expanding-and-collapsing-a-treeviewitem"></a>TreeViewItem 확장 및 축소  
 사용자 확장 되는 <xref:System.Windows.Controls.TreeViewItem>, <xref:System.Windows.Controls.TreeViewItem.IsExpanded%2A> 속성이 `true`합니다. 또한 확장 하거나 축소할 수는 <xref:System.Windows.Controls.TreeViewItem> 설정 하 여 직접 사용자 개입 없이 <xref:System.Windows.Controls.TreeViewItem.IsExpanded%2A> 속성을 `true` (확장) 또는 `false` (축소) 합니다. 이 속성이 변경 될 때는 <xref:System.Windows.Controls.TreeViewItem.Expanded> 또는 <xref:System.Windows.Controls.TreeViewItem.Collapsed> 이벤트가 발생 합니다.  
  
 때는 <xref:System.Windows.FrameworkElement.BringIntoView%2A> 메서드가 호출 되는 <xref:System.Windows.Controls.TreeViewItem> 컨트롤은 <xref:System.Windows.Controls.TreeViewItem> 와 해당 부모 <xref:System.Windows.Controls.TreeViewItem> 컨트롤을 확장 합니다. 경우는 <xref:System.Windows.Controls.TreeViewItem> 보이지 않거나 부분적으로 표시 되는 <xref:System.Windows.Controls.TreeView> 표시 하려면 스크롤합니다.  
  
<a name="TreeViewItem_Selection"></a>   
## <a name="treeviewitem-selection"></a>TreeViewItem 선택  
 사용자가 클릭할 때는 <xref:System.Windows.Controls.TreeViewItem> 컨트롤을 선택 합니다는 <xref:System.Windows.Controls.TreeViewItem.Selected> 이벤트 발생 및 해당 <xref:System.Windows.Controls.TreeViewItem.IsSelected%2A> 속성이로 설정 된 `true`합니다. <xref:System.Windows.Controls.TreeViewItem> 도 됩니다는 <xref:System.Windows.Controls.TreeView.SelectedItem%2A> 의 <xref:System.Windows.Controls.TreeView> 제어 합니다. 반대로, 선택 영역에서 변경 될 때는 <xref:System.Windows.Controls.TreeViewItem> 컨트롤을 해당 <xref:System.Windows.Controls.TreeViewItem.Unselected> 이벤트 발생 및 해당 <xref:System.Windows.Controls.TreeViewItem.IsSelected%2A> 속성이 `false`합니다.  
  
 <xref:System.Windows.Controls.TreeView.SelectedItem%2A> 속성에는 <xref:System.Windows.Controls.TreeView> 컨트롤은 읽기 전용 속성 이며 명시적으로 설정할 수 없습니다 따라서 합니다. <xref:System.Windows.Controls.TreeView.SelectedItem%2A> 사용자가 클릭할 경우 속성은 설정는 <xref:System.Windows.Controls.TreeViewItem> 컨트롤 또는 때는 <xref:System.Windows.Controls.TreeViewItem.IsSelected%2A> 속성이로 설정 되어 `true` 에 <xref:System.Windows.Controls.TreeViewItem> 제어 합니다.  
  
 사용 하 여는 <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> 속성을 통해 지정 된 <xref:System.Windows.Controls.TreeView.SelectedValue%2A> 의 <xref:System.Windows.Controls.TreeView.SelectedItem%2A>합니다. 자세한 내용은 [SelectedValue, SelectedValuePath 및 SelectedItem 사용](../../../../docs/framework/wpf/controls/how-to-use-selectedvalue-selectedvaluepath-and-selecteditem.md)을 참조하세요.  
  
 이벤트 처리기를 등록할 수 있습니다는 <xref:System.Windows.Controls.TreeView.SelectedItemChanged> 선택 된 시기를 결정 하기 위해 이벤트 <xref:System.Windows.Controls.TreeViewItem> 변경 합니다. <xref:System.Windows.RoutedPropertyChangedEventArgs%601> 처리기 이벤트를 지정 하는 제공 되는 <xref:System.Windows.RoutedPropertyChangedEventArgs%601.OldValue%2A>, 이전 선택 되 및 <xref:System.Windows.RoutedPropertyChangedEventArgs%601.NewValue%2A>, 현재 선택 영역을 변수인 합니다. 응용 프로그램 또는 사용자가 이전 또는 현재에 선택한 항목이 없는 경우 두 값은 `null`이 될 수 있습니다.  
  
<a name="TreeView_Style"></a>   
## <a name="treeview-style"></a>TreeView 스타일  
 에 대 한 기본 스타일은 <xref:System.Windows.Controls.TreeView> 컨트롤 안에 배치는 <xref:System.Windows.Controls.StackPanel> 포함 된 개체는 <xref:System.Windows.Controls.ScrollViewer> 제어 합니다. 설정 하는 경우는 <xref:System.Windows.FrameworkElement.Width%2A> 및 <xref:System.Windows.FrameworkElement.Height%2A> 속성에 대 한는 <xref:System.Windows.Controls.TreeView>, 이러한 값 크기를 사용 하는 <xref:System.Windows.Controls.StackPanel> 표시 하는 개체는 <xref:System.Windows.Controls.TreeView>합니다. 표시할 수 있는 콘텐츠 표시 영역 보다 큰 경우는 <xref:System.Windows.Controls.ScrollViewer> 사용자를 통해 스크롤할 수 있도록 자동으로 표시 됩니다는 <xref:System.Windows.Controls.TreeView> 콘텐츠입니다.  
  
 모양을 사용자 지정 하는 <xref:System.Windows.Controls.TreeViewItem> 제어, 설정는 <xref:System.Windows.FrameworkElement.Style%2A> 을 사용자 지정 속성 <xref:System.Windows.Style>합니다.  
  
 설정 하는 방법을 보여 주는 다음 예제는 <xref:System.Windows.Controls.Control.Foreground%2A> 및 <xref:System.Windows.Controls.Control.FontSize%2A> 속성 값을 한 <xref:System.Windows.Controls.TreeViewItem> 제어를 사용 하 여는 <xref:System.Windows.FrameworkElement.Style%2A>합니다.  
  
 [!code-xaml[TreeViewSimple#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#8)]  
  
<a name="Adding_Images_and_oOther_Content_to_TreeView_Items"></a>   
## <a name="adding-images-and-other-content-to-treeview-items"></a>TreeView 항목에 이미지 및 기타 콘텐츠 추가  
 에 둘 이상의 개체를 포함할 수는 <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> 의 콘텐츠는 <xref:System.Windows.Controls.TreeViewItem>합니다. 여러 개체에 포함 하려면 <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> 콘텐츠와 같은 레이아웃 컨트롤, 내부 개체를 포함 합니다는 <xref:System.Windows.Controls.Panel> 또는 <xref:System.Windows.Controls.StackPanel>합니다.  
  
 다음 예제에서는 정의 하는 방법을 보여 줍니다.는 <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> 의 <xref:System.Windows.Controls.TreeViewItem> 로 <xref:System.Windows.Controls.CheckBox> 및 <xref:System.Windows.Controls.TextBlock> 포함 된에 <xref:System.Windows.Controls.DockPanel> 제어 합니다.  
  
 [!code-xaml[TreeViewSnips#TVIHeader](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSnips/CSharp/Window1.xaml#tviheader)]  
  
 다음 예제에서는 정의 하는 방법을 보여 줍니다.는 <xref:System.Windows.DataTemplate> 를 포함 하는 <xref:System.Windows.Controls.Image> 및 <xref:System.Windows.Controls.TextBlock> 내부에 <xref:System.Windows.Controls.DockPanel> 제어 합니다. 사용할 수는 <xref:System.Windows.DataTemplate> 설정 하는 <xref:System.Windows.Controls.HeaderedItemsControl.HeaderTemplate%2A> 또는 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> 에 대 한는 <xref:System.Windows.Controls.TreeViewItem>합니다.  
  
 [!code-xaml[TreeViewDataBinding#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewDataBinding/CSharp/Window1.xaml#6)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Controls.TreeView>  
 <xref:System.Windows.Controls.TreeViewItem>  
 [방법 항목](../../../../docs/framework/wpf/controls/treeview-how-to-topics.md)  
 [WPF 콘텐츠 모델](../../../../docs/framework/wpf/controls/wpf-content-model.md)
