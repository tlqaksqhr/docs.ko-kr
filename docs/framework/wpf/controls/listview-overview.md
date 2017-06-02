---
title: "ListView 개요 | Microsoft Docs"
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
  - "컨트롤, ListView"
  - "ListView 컨트롤[WPF], ListView 컨트롤 정보"
ms.assetid: 989e12b0-260e-4570-95c6-489284003ce2
caps.latest.revision: 25
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 24
---
# ListView 개요
<xref:System.Windows.Controls.ListView> 컨트롤은 데이터 항목 집합을 여러 레이아웃이나 뷰에 표시하기 위한 인프라를 제공합니다.  예를 들어 사용자가 데이터 항목을 표에 표시하고 열을 정렬해야 할 수 있습니다.  
  
   
  
<a name="WhatisaListView"></a>   
## ListView 정의  
 <xref:System.Windows.Controls.ListView> 컨트롤은 <xref:System.Windows.Controls.ListBox>에서 파생된 <xref:System.Windows.Controls.ItemsControl>입니다.  일반적으로 이 컨트롤의 항목은 데이터 컬렉션의 멤버이며 <xref:System.Windows.Controls.ListViewItem> 개체로 표현됩니다.  <xref:System.Windows.Controls.ListViewItem>은 <xref:System.Windows.Controls.ContentControl>이며 하나의 자식 요소만 포함할 수 있습니다.  하지만 자식 요소는 모든 시각적 요소가 될 수 있습니다.  
  
<a name="DefiningaListViewView"></a>   
## ListView의 뷰 모드 정의  
 <xref:System.Windows.Controls.ListView> 컨트롤의 콘텐츠에 대한 뷰 모드를 지정하려면 <xref:System.Windows.Controls.ListView.View%2A> 속성을 설정합니다.  [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에서 제공하는 뷰 모드 중 하나는 <xref:System.Windows.Controls.GridView>로 이 모드에서는 열을 사용자 지정할 수 있는 표에 데이터 항목 컬렉션을 표시합니다.  
  
 다음 예제에서는 직원 정보를 표시하는 <xref:System.Windows.Controls.ListView> 컨트롤의 <xref:System.Windows.Controls.GridView>를 정의하는 방법을 보여 줍니다.  
  
 [!code-xml[ListViewCode#ListViewEmployee](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 다음 그림에서는 이전 예제의 데이터가 어떻게 표시되는지 보여 줍니다.  
  
 ![GridView 출력이 있는 ListView](../../../../docs/framework/wpf/controls/media/listviewgridview.png "ListViewGridView")  
  
 <xref:System.Windows.Controls.ViewBase> 클래스에서 상속되는 클래스를 정의하여 사용자 지정 뷰 모드를 만들 수 있습니다.  사용자 지정 뷰를 만드는 데 필요한 인프라는 <xref:System.Windows.Controls.ViewBase> 클래스에서 제공합니다.  사용자 지정 뷰를 만드는 방법에 대한 자세한 내용은 [ListView의 사용자 지정 뷰 모드 만들기](../../../../docs/framework/wpf/controls/how-to-create-a-custom-view-mode-for-a-listview.md)를 참조하십시오.  
  
<a name="BindingDatatoaListView"></a>   
## ListView에 데이터 바인딩  
 <xref:System.Windows.Controls.ItemsControl.Items%2A> 및 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 속성을 사용하여 <xref:System.Windows.Controls.ListView> 컨트롤에 대한 항목을 지정합니다.  다음 예제에서는 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> 속성을 `EmployeeInfoDataSource`라는 데이터 컬렉션으로 설정합니다.  
  
 [!code-xml[ListViewCode#ItemsSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#itemssource)]  
  
 <xref:System.Windows.Controls.GridView>에서 <xref:System.Windows.Controls.GridViewColumn> 개체는 지정된 데이터 필드에 바인딩됩니다.  다음 예제에서는 <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> 속성에 대해 <xref:System.Windows.Data.Binding>을 지정하여 <xref:System.Windows.Controls.GridViewColumn> 개체를 데이터 필드에 바인딩합니다.  
  
 [!code-csharp[ListViewCode#GridViewColumnProperties](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml.cs#gridviewcolumnproperties)]
 [!code-vb[ListViewCode#GridViewColumnProperties](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCode/visualbasic/window1.xaml.vb#gridviewcolumnproperties)]
 [!code-xml[ListViewCode#GridViewColumnProperties](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#gridviewcolumnproperties)]  
  
 열의 셀에 스타일을 지정하기 위해 <xref:System.Windows.DataTemplate>을 정의하는 과정에서 <xref:System.Windows.Data.Binding>을 지정할 수도 있습니다.  다음 예제에서는 <xref:System.Windows.ResourceKey>로 식별되는 <xref:System.Windows.DataTemplate>에서 <xref:System.Windows.Controls.GridViewColumn>에 대한 <xref:System.Windows.Data.Binding>을 설정합니다.  이 예제에서는 <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A>을 정의하지 않습니다. 정의하는 경우 <xref:System.Windows.DataTemplate>으로 지정된 바인딩이 재정의되기 때문입니다.  
  
 [!code-xml[ListViewTemplate#GridViewCellTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcelltemplate)]  
  
 [!code-xml[ListViewTemplate#CellTemplateProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#celltemplateproperty)]  
  
<a name="StylingaListView"></a>   
## GridView를 구현하는 ListView에 스타일 지정  
 <xref:System.Windows.Controls.ListView> 컨트롤에는 표시되는 데이터 항목을 나타내는 <xref:System.Windows.Controls.ListViewItem> 개체가 포함됩니다.  다음 속성을 사용하여 데이터 항목의 콘텐츠와 스타일을 정의할 수 있습니다.  
  
-   <xref:System.Windows.Controls.ListView> 컨트롤에서는 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>, <xref:System.Windows.Controls.ItemsControl.ItemTemplateSelector%2A> 및 <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> 속성을 사용합니다.  
  
-   <xref:System.Windows.Controls.ListViewItem> 컨트롤에서는 <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> 및 <xref:System.Windows.Controls.ContentControl.ContentTemplateSelector%2A> 속성을 사용합니다.  
  
 <xref:System.Windows.Controls.GridView>에서 셀 사이의 정렬 문제가 발생하지 않도록 <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>을 사용하여 속성을 설정하거나 <xref:System.Windows.Controls.ListView>의 항목 너비에 영향을 주는 콘텐츠를 추가하지 마십시오.  예를 들어 <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>에서 <xref:System.Windows.FrameworkElement.Margin%2A> 속성을 설정하면 정렬 문제가 발생할 수 있습니다.  <xref:System.Windows.Controls.GridView>에 있는 항목 너비에 영향을 주는 콘텐츠를 정의하거나 속성을 지정하려면 <xref:System.Windows.Controls.GridView> 클래스 속성 및 <xref:System.Windows.Controls.GridViewColumn> 등의 관련 클래스 속성을 사용하십시오.  
  
 <xref:System.Windows.Controls.GridView> 및 지원 클래스를 사용하는 방법에 대한 자세한 내용은 [GridView 개요](../../../../docs/framework/wpf/controls/gridview-overview.md)를 참조하십시오.  
  
 <xref:System.Windows.Controls.ListView> 컨트롤에 대한 <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>을 정의하고 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>도 정의하는 경우에는 스타일에 <xref:System.Windows.Controls.ContentPresenter>를 포함해야 <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A>이 제대로 작동합니다.  
  
 <xref:System.Windows.Controls.GridView>를 사용하여 표시되는 <xref:System.Windows.Controls.ListView> 콘텐츠에 <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> 및 <xref:System.Windows.Controls.Control.VerticalContentAlignment%2A> 속성을 사용하지 마십시오.  <xref:System.Windows.Controls.GridView>의 열 콘텐츠 정렬을 지정하려면 <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A>을 정의하십시오.  
  
<a name="UsingtheSameViewMoreThanOnce"></a>   
## 같은 뷰 모드 공유  
 두 개의 <xref:System.Windows.Controls.ListView> 컨트롤이 동시에 같은 뷰 모드를 공유할 수 없습니다.  둘 이상의 <xref:System.Windows.Controls.ListView> 컨트롤에 같은 뷰 모드를 사용하려고 하면 예외가 발생합니다.  
  
 둘 이상의 <xref:System.Windows.Controls.ListView>가 동시에 사용할 수 있는 뷰 모드를 지정하려면 템플릿이나 스타일을 사용하십시오.  뷰를 <xref:System.Windows.FrameworkElement.Resources%2A>로 정의하는 방법에 대한 예제를 보려면 [ListView with Multiple Views 샘플](http://go.microsoft.com/fwlink/?LinkID=160013)을 참조하십시오.  
  
<a name="CreatingaCustomView"></a>   
## 사용자 지정 뷰 모드 만들기  
 <xref:System.Windows.Controls.GridView>와 같은 사용자 지정 뷰는 <xref:System.Windows.Controls.ListViewItem> 개체로 표현되는 데이터 항목을 표시하기 위한 도구를 제공하는 <xref:System.Windows.Controls.ViewBase> 추상 클래스에서 파생됩니다.  
  
 사용자 지정 뷰 모드의 예제를 보려면 [ListView with Multiple Views 샘플](http://go.microsoft.com/fwlink/?LinkID=160013)을 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Controls.GridView>   
 <xref:System.Windows.Controls.ListView>   
 <xref:System.Windows.Controls.ListViewItem>   
 <xref:System.Windows.Data.Binding>   
 [GridView 개요](../../../../docs/framework/wpf/controls/gridview-overview.md)   
 [방법 항목](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)   
 [컨트롤](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)