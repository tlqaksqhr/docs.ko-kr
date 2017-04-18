---
title: "방법: GridView를 구현하는 ListView 행의 스타일 지정 | Microsoft Docs"
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
  - "GridView 컨트롤을 행 스타일 지정"
  - "GridView를 구현하는 ListView의 행 스타일 지정"
  - "ListView 컨트롤을 Gridview가 있는 행 스타일 지정"
ms.assetid: 2e406ba2-70a0-4e62-841f-0934859de76e
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# 방법: GridView를 구현하는 ListView 행의 스타일 지정
행 스타일을 지정 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Controls.ListView> 구현 하는 컨트롤을 <xref:System.Windows.Controls.GridView><xref:System.Windows.Controls.ListView.View%2A> 모드입니다.  
  
## <a name="example"></a>예제  
 행 스타일을 지정할 수 있습니다는 <xref:System.Windows.Controls.ListView> 설정 하 여 컨트롤은 <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> 에 <xref:System.Windows.Controls.ListView> 제어 합니다. 로 표현 되는 해당 항목에 대 한 스타일 설정 <xref:System.Windows.Controls.ListViewItem> 개체입니다. <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> 참조는 <xref:System.Windows.Controls.ControlTemplate> 행 내용을 표시 하는 데 사용 되는 개체입니다.  
  
 다음 예제에서 추출 되는 전체 샘플에 저장 된 음악 정보 컬렉션을 표시 한 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 데이터베이스입니다. 데이터베이스에 각 노래 등급 필드가 있고이 필드의 값은 노래 정보 행을 표시 하는 방법을 지정 합니다.  
  
 다음 예제에서는 정의 하는 방법을 보여 줍니다. <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> 에 대 한는 <xref:System.Windows.Controls.ListViewItem> 음악 컬렉션에서 노래를 나타내는 개체입니다. <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> 참조 <xref:System.Windows.Controls.ControlTemplate> 노래 정보 행을 표시 하는 방법을 지정 하는 개체입니다.  
  
 [!code-xml[ListViewItemStyleSnippet#ItemContainerStyle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#itemcontainerstyle)]  
  
 다음 예제에서는 한 <xref:System.Windows.Controls.ControlTemplate> 텍스트 문자열을 추가 하는 `"Strongly Recommended"` 행에 있습니다. 이 서식 파일에서 참조 되는 <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> song의 등급에 5 (5)의 값을 표시 합니다. <xref:System.Windows.Controls.ControlTemplate> 포함 한 <xref:System.Windows.Controls.GridViewRowPresenter> 에 정의 된 대로 열에 있는 행의 내용을 배치 하는 개체는 <xref:System.Windows.Controls.GridView> 보기 모드입니다.  
  
 [!code-xml[ListViewItemStyleSnippet#ControlTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#controltemplate)]  
  
 다음 예제에서는 <xref:System.Windows.Controls.GridView>합니다.  
  
 [!code-xml[ListViewItemStyleSnippet#GridView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#gridview)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Controls.ListView>   
 <xref:System.Windows.Controls.GridView>   
 [방법 도움말 항목](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)   
 [ListView 개요](../../../../docs/framework/wpf/controls/listview-overview.md)   
 [스타일 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md)