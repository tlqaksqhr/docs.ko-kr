---
title: "GridView 개요 | Microsoft Docs"
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
  - "GridView 보기 모드"
  - "ListView 컨트롤, GridView 보기 모드"
ms.assetid: b2d02267-32b3-40ce-8e9f-06972d8749d9
caps.latest.revision: 26
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 25
---
# GridView 개요
<xref:System.Windows.Controls.GridView> 보기 모드는 <xref:System.Windows.Controls.ListView> 컨트롤의 보기 모드 중 하나입니다.  <xref:System.Windows.Controls.GridView> 클래스 및 지원 클래스를 사용하면 대개 단추를 대화형 열 머리글로 사용하는 표 형식으로 항목 컬렉션을 볼 수 있습니다.  이 항목에서는 <xref:System.Windows.Controls.GridView> 클래스를 소개하고 클래스 사용 방법을 간략하게 설명합니다.  
  
   
  
<a name="DefiningaListViewthatusesGridViewView"></a>   
## GridView 뷰 정의  
 <xref:System.Windows.Controls.GridView> 보기 모드에서는 데이터 필드를 열에 바인딩하고 필드를 식별하는 열 머리글을 표시하여 데이터 항목의 목록을 보여 줍니다.  기본 <xref:System.Windows.Controls.GridView> 스타일을 사용하면 열 머리글이 단추로 구현됩니다.  단추를 열 머리글로 사용하면 중요한 사용자 상호 작용 기능을 구현할 수 있습니다. 예를 들면 사용자가 열 머리글을 클릭하여 특정 열의 콘텐츠를 기준으로 <xref:System.Windows.Controls.GridView> 데이터를 정렬할 수 있습니다.  
  
> [!NOTE]
>  <xref:System.Windows.Controls.GridView>에서 열 머리글로 사용되는 단추 컨트롤은 <xref:System.Windows.Controls.Primitives.ButtonBase>에서 파생됩니다.  
  
 다음 그림에서는 <xref:System.Windows.Controls.ListView> 콘텐츠의 <xref:System.Windows.Controls.GridView> 뷰를 보여 줍니다.  
  
 **ListView 콘텐츠의 GridView 뷰**  
  
 ![스타일 지정된 ListView](../../../../docs/framework/wpf/controls/media/styledlistview.png "StyledListView")  
  
 <xref:System.Windows.Controls.GridView> 열은 콘텐츠에 따라 크기가 자동으로 조정되는 <xref:System.Windows.Controls.GridViewColumn> 개체로 표현됩니다.  필요한 경우 <xref:System.Windows.Controls.GridViewColumn>을 특정 너비로 명시적으로 설정할 수 있습니다.  열 머리글 사이의 그리퍼를 끌어 열 크기를 조정할 수 있으며,  <xref:System.Windows.Controls.GridView>에 기본적으로 포함된 기능을 사용하여 열을 동적으로 추가, 제거, 대체 및 다시 정렬할 수 있습니다.  그러나 <xref:System.Windows.Controls.GridView>에서는 표시되는 데이터를 직접 업데이트할 수 없습니다.  
  
 다음 예제에서는 직원 데이터를 표시하는 <xref:System.Windows.Controls.GridView>를 정의하는 방법을 보여 줍니다.  이 예제에서 <xref:System.Windows.Controls.ListView>는 `EmployeeInfoDataSource`를 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>로 정의합니다.  <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A>의 속성 정의에서는 <xref:System.Windows.Controls.GridViewColumn>의 콘텐츠를 `EmployeeInfoDataSource` 데이터 범주에 바인딩합니다.  
  
 [!code-xml[ListViewCode#ListViewEmployee](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 다음 그림에서는 이전 예제에서 만든 표를 보여 줍니다.  
  
 **ItemsSource에서 가져온 데이터를 표시하는 GridView**  
  
 ![GridView 출력이 있는 ListView](../../../../docs/framework/wpf/controls/media/listviewgridview.png "ListViewGridView")  
  
<a name="GridViewLayoutandStyle"></a>   
## GridView 레이아웃과 스타일  
 <xref:System.Windows.Controls.GridViewColumn>에서 열의 셀과 머리글은 너비가 동일합니다.  기본적으로 각 열의 너비는 콘텐츠에 맞게 자동으로 조정되지만  필요한 경우 열을 고정 너비로 설정할 수 있습니다.  
  
 관련된 데이터 콘텐츠는 가로 행에 표시됩니다.  예를 들어 위의 그림에서 각 직원의 성, 이름 및 ID 번호는 가로 행에 표시되기 때문에 하나의 집합으로 표시됩니다.  
  
<a name="DefiningandStylingColumnsinaGridView"></a>   
### GridView에서 열 정의 및 스타일 지정  
 <xref:System.Windows.Controls.GridViewColumn>에 표시할 데이터 필드를 정의할 때는 <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A>, <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> 또는 <xref:System.Windows.Controls.GridViewColumn.CellTemplateSelector%2A> 속성을 사용합니다.  <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> 속성은 다른 두 가지 템플릿 속성보다 우선 적용됩니다.  
  
 <xref:System.Windows.Controls.GridView>의 열 콘텐츠 정렬을 지정하려면 <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A>을 정의하십시오.  <xref:System.Windows.Controls.GridView>를 사용하여 표시되는 <xref:System.Windows.Controls.ListView> 콘텐츠에 <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> 및 <xref:System.Windows.Controls.Control.VerticalContentAlignment%2A> 속성을 사용하지 마십시오.  
  
 열 머리글의 템플릿과 스타일 속성은 <xref:System.Windows.Controls.GridView>, <xref:System.Windows.Controls.GridViewColumn> 및 <xref:System.Windows.Controls.GridViewColumnHeader> 클래스를 사용하여 지정합니다.  자세한 내용은 [GridView 열 머리글 스타일 및 템플릿 개요](../../../../docs/framework/wpf/controls/gridview-column-header-styles-and-templates-overview.md)를 참조하십시오.  
  
<a name="AddingVisualElementstoaGridViewView"></a>   
### GridView에 시각적 요소 추가  
 <xref:System.Windows.Controls.CheckBox> 및 <xref:System.Windows.Controls.Button> 컨트롤과 같은 시각적 요소를 <xref:System.Windows.Controls.GridView> 보기 모드에 추가하려면 템플릿이나 스타일을 사용합니다.  
  
 시각적 요소를 데이터 항목으로 명시적으로 정의하면 해당 시각적 요소를 <xref:System.Windows.Controls.GridView>에 한 번만 표시할 수 있습니다.  요소는 부모를 하나만 가질 수 있습니다. 따라서 [시각적 트리](GTMT)에 한 번만 표시될 수 있으므로 이와 같은 제한이 적용됩니다.  
  
<a name="StylingRowsinaGridViewView"></a>   
### GridView의 행에 스타일 지정  
 <xref:System.Windows.Controls.GridViewRowPresenter> 및 <xref:System.Windows.Controls.GridViewHeaderRowPresenter> 클래스를 사용하여 <xref:System.Windows.Controls.GridView> 행의 서식을 지정하고 이러한 행을 표시할 수 있습니다.  <xref:System.Windows.Controls.GridView> 보기 모드에서 행의 스타일을 지정하는 방법에 대한 예제를 보려면 [GridView를 구현하는 ListView 행의 스타일 지정](../../../../docs/framework/wpf/controls/how-to-style-a-row-in-a-listview-that-implements-a-gridview.md)을 참조하십시오.  
  
<a name="AlignmentIssuesWhenUsingItemContainerStyle"></a>   
### ItemContainerStyle을 사용할 때의 맞춤 문제  
 열 머리글과 셀 사이의 맞춤 문제를 방지하려면 <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>에 항목의 너비에 영향을 주는 템플릿을 지정하거나 속성을 설정하지 마십시오.  예를 들어 <xref:System.Windows.Controls.ListView> 컨트롤에 정의되어 있는 <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>에 <xref:System.Windows.Controls.CheckBox>를 추가하는 <xref:System.Windows.Controls.ControlTemplate>이나 <xref:System.Windows.FrameworkElement.Margin%2A> 속성을 설정하면 안 됩니다.  대신 열 너비에 영향을 주는 속성과 템플릿은 <xref:System.Windows.Controls.GridView> 보기 모드를 정의하는 클래스에 직접 지정해야 합니다.  
  
 예를 들어 <xref:System.Windows.Controls.GridView> 보기 모드의 행에 <xref:System.Windows.Controls.CheckBox>를 추가하려면 <xref:System.Windows.Controls.CheckBox>를 <xref:System.Windows.DataTemplate>에 추가한 다음 <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> 속성을 이 <xref:System.Windows.DataTemplate>으로 설정합니다.  
  
<a name="InteractingwithaGridViewControl"></a>   
## GridView와의 사용자 상호 작용  
 응용 프로그램에 <xref:System.Windows.Controls.GridView>를 사용하면 사용자가 <xref:System.Windows.Controls.GridView>와 상호 작용하고 해당 서식을 수정할 수 있습니다.  예를 들어 사용자는 열을 다시 정렬하거나 열의 크기를 조정하고, 표에서 항목을 선택하고 콘텐츠를 스크롤할 수 있습니다.  사용자가 열 머리글 단추를 클릭할 때 응답하는 이벤트 처리기를 정의할 수도 있습니다.  이벤트 처리기를 사용하면 열의 콘텐츠를 기준으로 <xref:System.Windows.Controls.GridView>에 표시된 데이터를 정렬하는 등의 작업을 수행할 수 있습니다.  
  
 다음 목록에서는 <xref:System.Windows.Controls.GridView>를 사용하여 구현할 수 있는 사용자 상호 작용 기능을 더 자세하게 설명합니다.  
  
-   **끌어서 놓기 방법으로 열 다시 정렬**  
  
     특정 열 머리글 위에서 마우스 왼쪽 단추를 누른 채 해당 열을 새 위치로 끌어다 놓는 방법으로 <xref:System.Windows.Controls.GridView>의 열을 다시 정렬할 수 있습니다.  열 머리글을 끄는 동안에는 머리글의 부동 버전 및 열을 삽입할 위치를 나타내는 검정색 실선이 함께 표시됩니다.  
  
     머리글 부동 버전의 기본 스타일을 수정하려면 <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> 속성이 <xref:System.Windows.Controls.GridViewColumnHeaderRole>일 때 트리거되는 <xref:System.Windows.Controls.GridViewColumnHeader> 형식에 대해 <xref:System.Windows.Controls.ControlTemplate>을 지정하십시오.  자세한 내용은 [끌어 온 GridView 열 머리글의 스타일 만들기](../../../../docs/framework/wpf/controls/how-to-create-a-style-for-a-dragged-gridview-column-header.md)를 참조하십시오.  
  
-   **콘텐츠에 맞게 열 크기 조정**  
  
     열 머리글 오른쪽에 있는 그리퍼를 두 번 클릭하면 콘텐츠에 맞게 열 크기를 조정할 수 있습니다.  
  
    > [!NOTE]
    >  <xref:System.Windows.Controls.GridViewColumn.Width%2A> 속성을 `Double.NaN`으로 설정하여 동일한 효과를 얻을 수도 있습니다.  
  
-   **행 항목 선택**  
  
     <xref:System.Windows.Controls.GridView>에서 항목을 하나 이상 선택할 수 있습니다.  
  
     선택 항목의 <xref:System.Windows.Style>을 변경하려면 [ListView에서 트리거를 사용하여 선택한 항목의 스타일 지정](../../../../docs/framework/wpf/controls/how-to-use-triggers-to-style-selected-items-in-a-listview.md)을 참조하십시오.  
  
-   **스크롤하여 화면에 기본적으로 보이지 않는 콘텐츠 보기**  
  
     <xref:System.Windows.Controls.GridView>가 작아서 모든 항목을 한 번에 표시할 수 없는 경우 <xref:System.Windows.Controls.ScrollViewer> 컨트롤을 통해 제공되는 스크롤 막대를 사용하여 가로 또는 세로로 스크롤할 수 있습니다.  콘텐츠가 화면에 모두 표시되는 방향의 <xref:System.Windows.Controls.Primitives.ScrollBar>는 숨겨집니다.  열 머리글은 세로 스크롤 막대로는 스크롤할 수 없고 가로로만 스크롤할 수 있습니다.  
  
-   **열 머리글 단추를 클릭하여 열과 상호 작용**  
  
     정렬 알고리즘을 제공하면 사용자가 열 머리글 단추를 클릭하여 열에 표시되는 데이터를 정렬할 수 있습니다.  
  
     열 머리글 단추의 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트를 처리하여 정렬 알고리즘과 같은 기능을 제공할 수 있습니다.  단일 열 머리글의 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트를 처리하려면 <xref:System.Windows.Controls.GridViewColumnHeader>에 이벤트 처리기를 설정하고,  모든 열 머리글의 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 이벤트를 처리하는 이벤트 처리기를 설정하려면 <xref:System.Windows.Controls.ListView> 컨트롤에 이벤트 처리기를 설정합니다.  
  
<a name="Obtaining_Other_Custom_Views"></a>   
## 다른 사용자 지정 뷰 가져오기  
 <xref:System.Windows.Controls.ViewBase> 추상 클래스에서 파생되는 <xref:System.Windows.Controls.GridView> 클래스는 <xref:System.Windows.Controls.ListView> 클래스에 사용할 수 있는 여러 가지 보기 모드 중 하나에 불과합니다.  <xref:System.Windows.Controls.ViewBase> 클래스에서 클래스를 파생시켜 <xref:System.Windows.Controls.ListView>에 대한 다른 사용자 지정 뷰를 만들 수 있습니다.  사용자 지정 보기 모드의 예제를 보려면 [ListView의 사용자 지정 뷰 모드 만들기](../../../../docs/framework/wpf/controls/how-to-create-a-custom-view-mode-for-a-listview.md)를 참조하십시오.  
  
<a name="GridViewSupportingClasses"></a>   
## GridView 지원 클래스  
 <xref:System.Windows.Controls.GridView> 보기 모드를 지원하는 클래스는 다음과 같습니다.  
  
-   <xref:System.Windows.Controls.GridViewColumn>  
  
-   <xref:System.Windows.Controls.GridViewColumnHeader>  
  
-   <xref:System.Windows.Controls.GridViewRowPresenter>  
  
-   <xref:System.Windows.Controls.GridViewHeaderRowPresenter>  
  
-   <xref:System.Windows.Controls.GridViewColumnCollection>  
  
-   <xref:System.Windows.Controls.GridViewColumnHeaderRole>  
  
## 참고 항목  
 <xref:System.Windows.Controls.ListView>   
 <xref:System.Windows.Controls.ListViewItem>   
 <xref:System.Windows.Controls.GridViewColumn>   
 <xref:System.Windows.Controls.GridViewColumnHeader>   
 <xref:System.Windows.Controls.GridViewRowPresenter>   
 <xref:System.Windows.Controls.GridViewHeaderRowPresenter>   
 <xref:System.Windows.Controls.ViewBase>   
 [ListView 개요](../../../../docs/framework/wpf/controls/listview-overview.md)   
 [머리글을 클릭할 때 GridView 열 정렬](../../../../docs/framework/wpf/controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md)   
 [방법 항목](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)