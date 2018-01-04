---
title: "테이블 개요"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- flow content elements [WPF], Table
- documents [WPF], tables
- tables [WPF]
ms.assetid: 5e1105f4-8fc4-473a-ba55-88c8e71386e6
caps.latest.revision: "21"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 922faa06456a1aa86ffd0c805ab33577280ccf4f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="table-overview"></a>테이블 개요
<xref:System.Windows.Documents.Table>유동 문서 콘텐츠 그리드 기반 프레젠테이션을 지 원하는 블록 수준 요소가입니다. 이 요소의 유연성 덕분에 이 요소는 매우 유용하지만 이해하고 제대로 사용하기가 더 복잡합니다.  
  
 이 항목에는 다음과 같은 섹션이 포함되어 있습니다.  
  
-   [테이블 기본 사항](#table_basics)  
  
-   [Table은 Grid와 어떻게 다를까요?](#table_vs_Grid)  
  
-   [기본 테이블 구조](#basic_table_structure)  
  
-   [테이블 포함](#table_containment)  
  
-   [행 그룹](#row_groupings)  
  
-   [백그라운드 렌더링 우선 순위](#rendering_precedence)  
  
-   [행 및 열 확장](#spanning_rows_or_columns)  
  
-   [코드로 테이블 빌드](#building_a_table_with_code)  
  
-   [관련 항목] 
  
<a name="table_basics"></a>   
## <a name="table-basics"></a>테이블 기본 사항  
  
<a name="table_vs_Grid"></a>   
### <a name="how-is-table-different-then-grid"></a>Table은 Grid와 어떻게 다를까요?  
 <xref:System.Windows.Documents.Table>및 <xref:System.Windows.Controls.Grid> 공통 된 기능을 공유 하지만 각는 다양 한 시나리오에 가장 적합 합니다. A <xref:System.Windows.Documents.Table> 유동 콘텐츠 내에서 사용 하도록 설계 되었습니다 (참조 [흐름 문서 개요](../../../../docs/framework/wpf/advanced/flow-document-overview.md) 유동 콘텐츠에 대 한 자세한 내용은). 그리드는 폼 내부에서 사용하는 것이 적합합니다(기본적으로 유동 콘텐츠 외부의 모든 위치). 내에서 한 <xref:System.Windows.Documents.FlowDocument>, <xref:System.Windows.Documents.Table> 지원 유동 콘텐츠 동작 하는 동안 콘텐츠 선택, 페이지 매김 및 열 흐름 변경 등는 <xref:System.Windows.Controls.Grid> 는 그렇지 않습니다. A <xref:System.Windows.Controls.Grid> 반면에 외부에 <xref:System.Windows.Documents.FlowDocument> 비롯 한 여러 가지 이유로 <xref:System.Windows.Controls.Grid> 행 및 열 인덱스에 따라 요소를 추가 <xref:System.Windows.Documents.Table> 는 그렇지 않습니다. <xref:System.Windows.Controls.Grid> 자식 콘텐츠를 단일 "셀"에 존재 하는 요소가 둘 이상 허용 층으로 요소를 사용 하면 <xref:System.Windows.Documents.Table>레이어 링을 지원 하지 않습니다. 자식 요소는 <xref:System.Windows.Controls.Grid> 절대 해당 "셀" 경계 영역을 기준으로 배치 될 수 있습니다. <xref:System.Windows.Documents.Table>이 기능을 지원 하지 않습니다. 마지막으로, 한 <xref:System.Windows.Controls.Grid> 적은 리소스가 필요 없으면 <xref:System.Windows.Documents.Table> 하므로 사용 하 여 것이 좋습니다는 <xref:System.Windows.Controls.Grid> 성능 향상을 위해 합니다.  
  
<a name="basic_table_structure"></a>   
### <a name="basic-table-structure"></a>기본 테이블 구조  
 <xref:System.Windows.Documents.Table>열으로 구성 된 그리드 기반 프레젠테이션을 제공 (나타내는 <xref:System.Windows.Documents.TableColumn> 요소)와 행 (나타내는 <xref:System.Windows.Documents.TableRow> 요소). <xref:System.Windows.Documents.TableColumn>요소 콘텐츠를 호스트 하지 마세요. 단순히 열과 열의 특성을 정의합니다. <xref:System.Windows.Documents.TableRow>요소에서 호스트 되어야 합니다는 <xref:System.Windows.Documents.TableRowGroup> 테이블에 대 한 행의 그룹화를 정의 하는 요소입니다. <xref:System.Windows.Documents.TableCell>테이블에 의해 표시 되는 실제 콘텐츠를 포함 하는 요소에서 호스트 되어야 합니다는 <xref:System.Windows.Documents.TableRow> 요소입니다. <xref:System.Windows.Documents.TableCell>파생 된 요소를 하나만 있습니다 <xref:System.Windows.Documents.Block>합니다.  에 대 한 올바른 자식 요소는 <xref:System.Windows.Documents.TableCell> 포함 합니다.  
  
-   <xref:System.Windows.Documents.BlockUIContainer>  
  
-   <xref:System.Windows.Documents.List>  
  
-   <xref:System.Windows.Documents.Paragraph>  
  
-   <xref:System.Windows.Documents.Section>  
  
-   <xref:System.Windows.Documents.Table>  
  
> [!NOTE]
>  <xref:System.Windows.Documents.TableCell>요소 직접 텍스트 콘텐츠를 호스팅하지 않을 수도 있습니다. 콘텐츠 요소와 같은 흐름에 대 한 포함 규칙에 대 한 자세한 내용은 <xref:System.Windows.Documents.TableCell>, 참조 [흐름 문서 개요](../../../../docs/framework/wpf/advanced/flow-document-overview.md)합니다.  
  
> [!NOTE]
>  <xref:System.Windows.Documents.Table>비슷합니다는 <xref:System.Windows.Controls.Grid> 요소 하지만 더 많은 기능이 있으며, 따라서 큰 리소스 오버 헤드가 필요 합니다.  
  
 다음 예제에서는 간단한 2 x 3 테이블에 [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)]합니다.  
  
 [!code-xaml[TableSnippets2#_Table_BasicLayout](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_basiclayout)]  
  
 다음 그림은 이 예제에서 렌더링하는 방법을 보여줍니다.  
  
 ![스크린샷: 기본 테이블 렌더링](../../../../docs/framework/wpf/advanced/media/basictablerrender.png "BasicTablerRender")  
  
<a name="table_containment"></a>   
### <a name="table-containment"></a>테이블 포함  
 <xref:System.Windows.Documents.Table>파생 되는 <xref:System.Windows.Documents.Block> 요소에 대 한 일반적인 규칙을 준수 <xref:System.Windows.Documents.Block> 수준 요소입니다.  A <xref:System.Windows.Documents.Table> 요소 중 다음과 같은 요소가 포함 될 수 있습니다.  
  
-   <xref:System.Windows.Documents.FlowDocument>  
  
-   <xref:System.Windows.Documents.TableCell>  
  
-   <xref:System.Windows.Controls.ListBoxItem>  
  
-   <xref:System.Windows.Controls.ListViewItem>  
  
-   <xref:System.Windows.Documents.Section>  
  
-   <xref:System.Windows.Documents.Floater>  
  
-   <xref:System.Windows.Documents.Figure>  
  
<a name="row_groupings"></a>   
### <a name="row-groupings"></a>행 그룹  
 <xref:System.Windows.Documents.TableRowGroup> 요소는 테이블 내에서 행을 임의로 그룹화 하는 방법을 제공 합니다; 테이블의 모든 행은 행 그룹에 속해야 합니다.  행 그룹 내의 행은 보통 공통 의도를 공유하고 그룹으로 스타일을 지정할 수 있습니다.  행 그룹은 공통적으로 제목, 헤더 및 바닥글 행과 같은 특수 용도 행을 테이블에 포함된 기본 콘텐츠에서 구분하는 데 사용됩니다.  
  
 다음 예제에서는 [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] 스타일의 머리글 및 바닥글 행이 있는 테이블을 정의할 수 있습니다.  
  
 [!code-xaml[TableSnippets2#_Table_RowGroups](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_rowgroups)]  
  
 다음 그림은 이 예제에서 렌더링하는 방법을 보여줍니다.  
  
 ![스크린샷: 테이블 행 그룹](../../../../docs/framework/wpf/advanced/media/table-rowgroups.png "Table_RowGroups")  
  
<a name="rendering_precedence"></a>   
### <a name="background-rendering-precedence"></a>백그라운드 렌더링 우선 순위  
 테이블 요소는 다음 순서로 렌더링됩니다(최저부터 최고까지 z 순서). 이 순서는 변경할 수 없습니다. 예를 들어 설정된 순서를 재정의하는 데 사용할 수 있는 다음 요소에 대한 "Z 순서" 속성은 없습니다.  
  
1.  <xref:System.Windows.Documents.Table>  
  
2.  <xref:System.Windows.Documents.TableColumn>  
  
3.  <xref:System.Windows.Documents.TableRowGroup>  
  
4.  <xref:System.Windows.Documents.TableRow>  
  
5.  <xref:System.Windows.Documents.TableCell>  
  
 테이블에서 이러한 각 요소의 배경색을 정의하는 다음 예제를 살펴보겠습니다.  
  
 [!code-xaml[TableSnippets2#_Table_ZOrder](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_zorder)]  
  
 다음 그림은 이 예제가 렌더링되는 방법을 보여 줍니다(배경색만 표시).  
  
 ![스크린샷: 테이블 z 순서](../../../../docs/framework/wpf/advanced/media/table-zorder.png "Table_ZOrder")  
  
<a name="spanning_rows_or_columns"></a>   
### <a name="spanning-rows-or-columns"></a>행 및 열 확장  
 사용 하 여 여러 행 이나 열에 걸쳐 표 셀을 구성할 수 있습니다는 <xref:System.Windows.Documents.TableCell.RowSpan%2A> 또는 <xref:System.Windows.Documents.TableCell.ColumnSpan%2A> 특성에 각각 있습니다.  
  
 셀이 세 개의 열에 걸쳐 있는 다음 예제를 살펴보겠습니다.  
  
 [!code-xaml[TableSnippets2#_Table_ColumnSpan](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_columnspan)]  
  
 다음 그림은 이 예제에서 렌더링하는 방법을 보여줍니다.  
  
 ![스크린샷: 세 열에 걸친 셀](../../../../docs/framework/wpf/advanced/media/table-columnspan.png "Table_ColumnSpan")  
  
<a name="building_a_table_with_code"></a>   
## <a name="building-a-table-with-code"></a>코드로 테이블 빌드  
 다음 예제에서는 프로그래밍 방식으로 만드는 방법을 보여는 <xref:System.Windows.Documents.Table> 콘텐츠를 채웁니다. 테이블의 내용이 5 개의 행에 할당 됩니다 (나타내는 <xref:System.Windows.Documents.TableRow> 에 포함 된 개체는 <xref:System.Windows.Documents.Table.RowGroups%2A> 개체)와 6 개의 열 (나타내는 <xref:System.Windows.Documents.TableColumn> 개체). 행은 전체 테이블의 제목을 지정하는 제목 행, 테이블의 데이터 열을 설명하는 헤더 행 및 요약 정보가 포함된 바닥글 행 등의 여러 다른 프레젠테이션 용도로 사용됩니다.  “제목”, “헤더” 및 “바닥글” 행의 개념은 테이블에 고유한 것이 아니며, 여러 다른 특성이 있는 행일 뿐입니다. 테이블 셀에 텍스트, 이미지 또는 기타 거의 모든 구성 될 수 있습니다는 실제 콘텐츠를 포함할 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 요소입니다.  
  
 첫째, 한 <xref:System.Windows.Documents.FlowDocument> 만들어집니다 호스트에는 <xref:System.Windows.Documents.Table>, 및 새 <xref:System.Windows.Documents.Table> 만들어지고의 내용에 추가 <xref:System.Windows.Documents.FlowDocument>합니다.  
  
 [!code-csharp[TableSnippets#_TableCreate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreate)]
 [!code-vb[TableSnippets#_TableCreate](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreate)]  
  
 다음은 6 개의 <xref:System.Windows.Documents.TableColumn> 개체 생성 되 고 테이블의 추가 <xref:System.Windows.Documents.Table.Columns%2A> 서식이 적용 된 컬렉션입니다.  
  
> [!NOTE]
>  테이블의 <xref:System.Windows.Documents.Table.Columns%2A> 컬렉션 표준 인덱스를 사용 합니다.  
  
 [!code-csharp[TableSnippets#_TableCreateColumns](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreatecolumns)]
 [!code-vb[TableSnippets#_TableCreateColumns](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreatecolumns)]  
  
 다음으로 제목 행을 만들어 서식이 적용된 테이블에 추가합니다.  제목 행은 테이블의 6개 열에 모두 걸친 단일 셀을 포함하게 됩니다.  
  
 [!code-csharp[TableSnippets#_TableAddTitleRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddtitlerow)]
 [!code-vb[TableSnippets#_TableAddTitleRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddtitlerow)]  
  
 다음으로 헤더 행을 만들어 테이블에 추가하고, 헤더 행의 셀을 만들어 콘텐츠로 채웁니다.  
  
 [!code-csharp[TableSnippets#_TableAddHeaderRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddheaderrow)]
 [!code-vb[TableSnippets#_TableAddHeaderRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddheaderrow)]  
  
 다음으로 데이터 행을 만들어 테이블에 추가하고, 이 행의 셀을 만들어 콘텐츠로 채웁니다.  이 행을 작성하는 것은 헤더 행을 작성하는 것과 비슷합니다. 단, 약간 다른 서식이 지정됩니다.  
  
 [!code-csharp[TableSnippets#_TableAddDataRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableadddatarow)]
 [!code-vb[TableSnippets#_TableAddDataRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableadddatarow)]  
  
 마지막으로 바닥글 행을 만들어 추가하고 서식을 지정합니다.  제목 행과 마찬가지로 바닥글에는 테이블의 6개 열에 모두 걸친 단일 셀이 포함됩니다.  
  
 [!code-csharp[TableSnippets#_TableAddFooterRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddfooterrow)]
 [!code-vb[TableSnippets#_TableAddFooterRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddfooterrow)]  
  
## <a name="see-also"></a>참고 항목  
 [유동 문서 개요](../../../../docs/framework/wpf/advanced/flow-document-overview.md)  
 [XAML로 테이블 정의](../../../../docs/framework/wpf/advanced/how-to-define-a-table-with-xaml.md)  
 [WPF의 문서](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [유동 콘텐츠 요소 사용](../../../../docs/framework/wpf/advanced/how-to-use-flow-content-elements.md)
