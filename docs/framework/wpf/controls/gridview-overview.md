---
title: GridView 개요
ms.date: 03/30/2017
helpviewer_keywords:
- GridView view mode [WPF]
- ListView controls [WPF], GridView view mode
- controls [WPF], ListView
ms.assetid: b2d02267-32b3-40ce-8e9f-06972d8749d9
ms.openlocfilehash: 776897d490b2748e240cf7b9a4ea21364284c4c4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="gridview-overview"></a>GridView 개요
<xref:System.Windows.Controls.GridView> 보기 모드에 대 한 보기 모드 중 하나는 <xref:System.Windows.Controls.ListView> 제어 합니다. <xref:System.Windows.Controls.GridView> 클래스와 해당 지원 클래스를 사용 하면 사용자 및 사용자가 일반적으로 대화형 열 머리글로 단추를 사용 하는 테이블에 항목 컬렉션을 볼 수 있습니다. 이 항목에서는 소개는 <xref:System.Windows.Controls.GridView> 클래스 및 해당 사용에 간략하게 설명 합니다.  
  
  
  
<a name="DefiningaListViewthatusesGridViewView"></a>   
## <a name="what-is-a-gridview-view"></a>GridView 보기란?  
 <xref:System.Windows.Controls.GridView> 보기 모드에서 데이터 필드를 열 바인딩 및 필드를 식별 하는 열 머리글을 표시 하 여 데이터 항목의 목록이 표시 됩니다. 기본 <xref:System.Windows.Controls.GridView> 스타일 열 머리글로 단추를 구현 합니다. 열 머리글에 대 한 단추를 사용 하면 중요 한 사용자 상호 작용 기능; 구현할 수 있습니다. 사용자가 정렬 하려면 열 머리글을 클릭 수는 예를 들어 <xref:System.Windows.Controls.GridView> 특정 열의 내용에 따라 데이터입니다.  
  
> [!NOTE]
>  되는 단추 컨트롤 <xref:System.Windows.Controls.GridView> 열 머리글로 사용에서 파생 된 <xref:System.Windows.Controls.Primitives.ButtonBase>합니다.  
  
 다음 그림에서는 한 <xref:System.Windows.Controls.GridView> 뷰 <xref:System.Windows.Controls.ListView> 콘텐츠입니다.  
  
 **ListView 콘텐츠의 GridView 보기**  
  
 ![스타일 지정된 ListView](../../../../docs/framework/wpf/controls/media/styledlistview.PNG "StyledListView")  
  
 <xref:System.Windows.Controls.GridView> 열은로 나타납니다 <xref:System.Windows.Controls.GridViewColumn> 개체 수의 콘텐츠를 자동으로 크기를 조정 합니다. 필요에 따라 있습니다 명시적으로 설정할 수는 <xref:System.Windows.Controls.GridViewColumn> 특정 너비입니다. 열 헤더 사이에 위치 조정 막대를 끌어와 열의 크기를 조정할 수 있습니다. 있습니다 수 동적으로 추가, 제거, 바꾸기 및이 기능에 내장 되어 있으므로 열 순서 바꾸기 <xref:System.Windows.Controls.GridView>합니다. 그러나 <xref:System.Windows.Controls.GridView> 표시 하는 데이터를 직접 업데이트할 수 없습니다.  
  
 다음 예제에서는 정의 하는 방법을 보여 줍니다.는 <xref:System.Windows.Controls.GridView> 직원 데이터를 표시 하는 합니다. 이 예제에서는 <xref:System.Windows.Controls.ListView> 정의 `EmployeeInfoDataSource` 로 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>합니다. 속성 정의 <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> 바인딩할 <xref:System.Windows.Controls.GridViewColumn> 콘텐츠를 `EmployeeInfoDataSource` 데이터 범주입니다.  
  
 [!code-xaml[ListViewCode#ListViewEmployee](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCode/CSharp/Window1.xaml#listviewemployee)]  
  
 다음 그림은 이전 예에서 만든 테이블을 보여줍니다.  
  
 **ItemsSource의 데이터를 표시하는 GridView**  
  
 ![GridView 출력이 있는 ListView](../../../../docs/framework/wpf/controls/media/listviewgridview.JPG "ListViewGridView")  
  
<a name="GridViewLayoutandStyle"></a>   
## <a name="gridview-layout-and-style"></a>GridView 레이아웃 및 스타일  
 열 셀과 열 머리글을 한 <xref:System.Windows.Controls.GridViewColumn> 너비가 동일 합니다. 기본적으로 각 열은 콘텐츠에 맞게 너비의 크기를 조정합니다. 선택적으로 열을 고정 너비로 설정할 수 있습니다.  
  
 관련 데이터 콘텐츠가 가로 행에 표시됩니다. 예를 들어, 이전 그림에서 각 직원의 성, 이름 및 ID 번호가 가로 행에 표시되므로 집합으로 표시됩니다.  
  
<a name="DefiningandStylingColumnsinaGridView"></a>   
### <a name="defining-and-styling-columns-in-a-gridview"></a>GridView에서 열 정의 및 스타일 지정  
 에 표시할 데이터 필드를 정의 하는 경우는 <xref:System.Windows.Controls.GridViewColumn>를 사용 하 여는 <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A>, <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A>, 또는 <xref:System.Windows.Controls.GridViewColumn.CellTemplateSelector%2A> 속성입니다. <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> 속성 템플릿 속성 중 하나 보다 우선 합니다.  
  
 열에 콘텐츠의 맞춤을 지정 하는 <xref:System.Windows.Controls.GridView>, 정의 <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A>합니다. 사용 하지 않는 <xref:System.Windows.Controls.Control.HorizontalContentAlignment%2A> 및 <xref:System.Windows.Controls.Control.VerticalContentAlignment%2A> 에 대 한 속성 <xref:System.Windows.Controls.ListView> 를 사용 하 여 표시 되는 콘텐츠는 <xref:System.Windows.Controls.GridView>합니다.  
  
 열 머리글에 대 한 템플릿 및 스타일 속성을 지정 하려면 사용 된 <xref:System.Windows.Controls.GridView>, <xref:System.Windows.Controls.GridViewColumn>, 및 <xref:System.Windows.Controls.GridViewColumnHeader> 클래스입니다. 자세한 내용은 [GridView 열 헤더 스타일 및 템플릿 개요](../../../../docs/framework/wpf/controls/gridview-column-header-styles-and-templates-overview.md)를 참조하세요.  
  
<a name="AddingVisualElementstoaGridViewView"></a>   
### <a name="adding-visual-elements-to-a-gridview"></a>GridView에 시각적 요소 추가  
 같은 시각적 요소를 추가 하려면 <xref:System.Windows.Controls.CheckBox> 및 <xref:System.Windows.Controls.Button> 컨트롤과 <xref:System.Windows.Controls.GridView> 보기 모드 템플릿 또는 스타일을 사용 합니다.  
  
 데이터 항목으로 시각적 요소를 명시적으로 정의 하는 경우에 한 번만 나타날 수 있습니다는 <xref:System.Windows.Controls.GridView>합니다. 요소에는 부모가 하나뿐일 수 있기 때문에 이 제한사항이 존재하고, 시각적 트리에 한 번만 표시될 수 있습니다.  
  
<a name="StylingRowsinaGridViewView"></a>   
### <a name="styling-rows-in-a-gridview"></a>GridView의 행 스타일 지정  
 사용 하 여는 <xref:System.Windows.Controls.GridViewRowPresenter> 및 <xref:System.Windows.Controls.GridViewHeaderRowPresenter> 서식을 지정 하 고의 행을 표시 하는 클래스는 <xref:System.Windows.Controls.GridView>합니다. 에 있는 행의 스타일에는 방법의 예는 <xref:System.Windows.Controls.GridView> 보기 모드를 참조 하십시오 [에 스타일을 행 ListView를 구현 하는 GridView](../../../../docs/framework/wpf/controls/how-to-style-a-row-in-a-listview-that-implements-a-gridview.md)합니다.  
  
<a name="AlignmentIssuesWhenUsingItemContainerStyle"></a>   
### <a name="alignment-issues-when-you-use-itemcontainerstyle"></a>ItemContainerStyle을 사용할 때 맞춤 문제  
 열 머리글 및 셀 간의 맞춤 문제를 방지 하려면 또는 설정 하지 마십시오 속성에 있는 항목의 너비에 영향을 주는 서식 파일을 지정 된 <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>합니다. 예를 들어, 설정 하지 않으면는 <xref:System.Windows.FrameworkElement.Margin%2A> 속성 지정 하거나는 <xref:System.Windows.Controls.ControlTemplate> 를 추가 하는 <xref:System.Windows.Controls.CheckBox> 에 <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> 에 정의 되어 있는 <xref:System.Windows.Controls.ListView> 컨트롤입니다. 대신, 속성 및 열 너비를 정의 하는 클래스에 직접 영향을 주는 서식 파일을 지정 된 <xref:System.Windows.Controls.GridView> 보기 모드입니다.  
  
 예를 들어, 추가 하는 <xref:System.Windows.Controls.CheckBox> 행에 <xref:System.Windows.Controls.GridView> 모드 보기, 추가 <xref:System.Windows.Controls.CheckBox> 에 <xref:System.Windows.DataTemplate>로 설정한는 <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> 속성 <xref:System.Windows.DataTemplate>합니다.  
  
<a name="InteractingwithaGridViewControl"></a>   
## <a name="user-interactions-with-a-gridview"></a>GridView와의 사용자 상호 작용  
 사용 하는 경우는 <xref:System.Windows.Controls.GridView> 응용 프로그램에서 사용자와 상호 작용 하 고 수정할 수의 서식을 <xref:System.Windows.Controls.GridView>합니다. 예를 들어, 열을 다시 정렬하고, 열의 크기를 조정하며, 테이블에서 항목을 선택하고, 콘텐츠를 스크롤할 수 있습니다. 사용자가 열 헤더 단추를 클릭하면 응답하는 이벤트 처리기도 정의할 수 있습니다. 이벤트 처리기에 표시 되는 데이터를 정렬 하는 등 작업을 수행할 수는 <xref:System.Windows.Controls.GridView> 열 내용에 따라 합니다.  
  
 다음 목록에는 기능을 사용 하 여에서 자세히 설명 <xref:System.Windows.Controls.GridView> 사용자 상호 작용에:  
  
-   **끌어서 놓기 메서드를 사용하여 열을 다시 정렬.**  
  
     사용자의 열 순서를 변경할 수는 <xref:System.Windows.Controls.GridView> 을 끌어서 열 머리글 위에 있는 동안 마우스 왼쪽된 단추를 누르면 다음 해당 열을 새 위치로 합니다. 사용자가 열 헤더를 끌어오는 동안 헤더의 부동 버전과 함께 열을 삽입할 위치를 표시하는 검은 실선이 표시됩니다.  
  
     헤더의 부동 버전에 대 한 기본 스타일을 수정 하려는 경우 지정는 <xref:System.Windows.Controls.ControlTemplate> 에 대 한는 <xref:System.Windows.Controls.GridViewColumnHeader> 즉 입력 때 트리거되는 <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> 속성이로 설정 된 <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating>합니다. 자세한 내용은 [끌어 온 GridView 열 헤더의 스타일 만들기](../../../../docs/framework/wpf/controls/how-to-create-a-style-for-a-dragged-gridview-column-header.md)를 참조하세요.  
  
-   **콘텐츠에 맞게 열의 크기 조정.**  
  
     콘텐츠에 맞게 열의 크기를 조정하려면 열 헤더의 오른쪽에 있는 위치 조정 막대를 두 번 클릭할 수 있습니다.  
  
    > [!NOTE]
    >  설정할 수 있습니다는 <xref:System.Windows.Controls.GridViewColumn.Width%2A> 속성을 `Double.NaN` 동일한 효과 얻을 합니다.  
  
-   **행 항목 선택.**  
  
     사용자가 하나 이상의 항목을 선택할 수는 <xref:System.Windows.Controls.GridView>합니다.  
  
     변경 하려는 경우는 <xref:System.Windows.Style> 선택된 항목의 참조 [스타일 ListView에서 선택한 항목을 사용 하 여 트리거](../../../../docs/framework/wpf/controls/how-to-use-triggers-to-style-selected-items-in-a-listview.md)합니다.  
  
-   **처음에 화면에 표시되지 않는 콘텐츠를 보려면 스크롤.**  
  
     하는 경우의 크기는 <xref:System.Windows.Controls.GridView> 은 하지 작아서 표시할 수 있는 모든 항목, 사용자가 가로로 스크롤될 수 또는 세로 스크롤 막대를 사용 하 여 통해 제공 되는 한 <xref:System.Windows.Controls.ScrollViewer> 컨트롤입니다. A <xref:System.Windows.Controls.Primitives.ScrollBar> 모든 내용이 특정 방향으로 표시 될 경우 숨겨집니다. 열 표제는 세로 스크롤 막대로는 스크롤되지 않지만 가로로는 스크롤됩니다.  
  
-   **열 표제 단추를 클릭하여 열과 상호 작용.**  
  
     열 헤더 단추를 클릭하면, 정렬 알고리즘을 제공한 경우 열에 표시되는 데이터를 정렬할 수 있습니다.  
  
     처리할 수는 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 정렬 알고리즘 등과 같은 기능을 제공 하기 위해 열 머리글이 단추에 대 한 이벤트입니다. 처리 하는 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 에 이벤트 처리기를 설정 하는 하나의 열 머리글에 대 한 이벤트는 <xref:System.Windows.Controls.GridViewColumnHeader>합니다. 처리 하는 이벤트 처리기를 설정 하는 <xref:System.Windows.Controls.Primitives.ButtonBase.Click> 에 처리기를 설정 하는 모든 열 머리글에 대 한 이벤트는 <xref:System.Windows.Controls.ListView> 제어 합니다.  
  
<a name="Obtaining_Other_Custom_Views"></a>   
## <a name="obtaining-other-custom-views"></a>다른 사용자 지정 보기 가져오기  
 <xref:System.Windows.Controls.GridView> 에서 파생 된 클래스는 <xref:System.Windows.Controls.ViewBase> 추상 클래스은 대 한 가능한 보기 모드 중 하나는 <xref:System.Windows.Controls.ListView> 클래스입니다. 다른 사용자 지정 보기를 만들 수 있습니다 <xref:System.Windows.Controls.ListView> 에서 파생 된 <xref:System.Windows.Controls.ViewBase> 클래스입니다. 사용자 지정 보기 모드의 예는 [ListView의 사용자 지정 뷰 모드 만들기](../../../../docs/framework/wpf/controls/how-to-create-a-custom-view-mode-for-a-listview.md)를 참조하세요.  
  
<a name="GridViewSupportingClasses"></a>   
## <a name="gridview-supporting-classes"></a>GridView 지원 클래스  
 다음 클래스는 <xref:System.Windows.Controls.GridView> 보기 모드입니다.  
  
-   <xref:System.Windows.Controls.GridViewColumn>  
  
-   <xref:System.Windows.Controls.GridViewColumnHeader>  
  
-   <xref:System.Windows.Controls.GridViewRowPresenter>  
  
-   <xref:System.Windows.Controls.GridViewHeaderRowPresenter>  
  
-   <xref:System.Windows.Controls.GridViewColumnCollection>  
  
-   <xref:System.Windows.Controls.GridViewColumnHeaderRole>  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.ListViewItem>  
 <xref:System.Windows.Controls.GridViewColumn>  
 <xref:System.Windows.Controls.GridViewColumnHeader>  
 <xref:System.Windows.Controls.GridViewRowPresenter>  
 <xref:System.Windows.Controls.GridViewHeaderRowPresenter>  
 <xref:System.Windows.Controls.ViewBase>  
 [ListView 개요](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [헤더를 클릭하면 GridView 열 정렬](../../../../docs/framework/wpf/controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md)  
 [방법 항목](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)
