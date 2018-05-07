---
title: '방법: GridView를 구현하는 ListView 행의 스타일 지정'
ms.date: 03/30/2017
helpviewer_keywords:
- GridView controls [WPF], styling rows
- styling rows in ListViews implementing GridViews [WPF]
- ListView controls [WPF], styling rows with GridViews
ms.assetid: 2e406ba2-70a0-4e62-841f-0934859de76e
ms.openlocfilehash: 313ead6de45f2a137775adb0ad9aad8bd061c066
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-style-a-row-in-a-listview-that-implements-a-gridview"></a>방법: GridView를 구현하는 ListView 행의 스타일 지정
행 스타일을 지정 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.ListView> 구현 하는 컨트롤을 <xref:System.Windows.Controls.GridView> <xref:System.Windows.Controls.ListView.View%2A> 모드입니다.  
  
## <a name="example"></a>예제  
 행 스타일을 지정할 수 있습니다는 <xref:System.Windows.Controls.ListView> 설정 하 여 컨트롤은 <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> 에 <xref:System.Windows.Controls.ListView> 제어 합니다. 로 표현 되는 해당 항목에 대 한 스타일을 설정 <xref:System.Windows.Controls.ListViewItem> 개체입니다. <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> 참조는 <xref:System.Windows.Controls.ControlTemplate> 행 내용을 표시 하는 데 사용 되는 개체입니다.  
  
 다음 예제가 포함되어 있는 원래의 전체 샘플에서는 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 데이터베이스에 저장된 곡 모음집 정보를 표시합니다. 데이터베이스의 각 곡에는 순위 필드가 있으며 이 필드의 값은 곡 정보 행의 표시 방법을 지정합니다.  
  
 다음 예제에서는 정의 하는 방법을 보여 줍니다. <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> 에 대 한는 <xref:System.Windows.Controls.ListViewItem> 노래 컬렉션에서 노래를 나타내는 개체입니다. <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> 참조 <xref:System.Windows.Controls.ControlTemplate> 노래 정보 행을 표시 하는 방법을 지정 하는 개체입니다.  
  
 [!code-xaml[ListViewItemStyleSnippet#ItemContainerStyle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#itemcontainerstyle)]  
  
 다음 예제에서는 한 <xref:System.Windows.Controls.ControlTemplate> 텍스트 문자열을 추가 하는 `"Strongly Recommended"` 행에 있습니다. 이 서식 파일에서 참조 되는 <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> 노래의 등급에 5 (5)의 값을 표시 합니다. <xref:System.Windows.Controls.ControlTemplate> 포함 한 <xref:System.Windows.Controls.GridViewRowPresenter> 개체에 정의 된 대로 열에 있는 행의 내용을 배치 하는 <xref:System.Windows.Controls.GridView> 보기 모드입니다.  
  
 [!code-xaml[ListViewItemStyleSnippet#ControlTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#controltemplate)]  
  
 다음 예제에서는 정의 <xref:System.Windows.Controls.GridView>합니다.  
  
 [!code-xaml[ListViewItemStyleSnippet#GridView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#gridview)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [방법 항목](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [ListView 개요](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [스타일 지정 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md)
