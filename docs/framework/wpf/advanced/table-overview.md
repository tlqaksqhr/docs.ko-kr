---
title: "표 개요 | Microsoft Docs"
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
  - "문서, 테이블"
  - "유동 콘텐츠 요소[WPF], 표"
  - "테이블"
ms.assetid: 5e1105f4-8fc4-473a-ba55-88c8e71386e6
caps.latest.revision: 21
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# 표 개요
<xref:System.Windows.Documents.Table>은 유동 문서 콘텐츠의 모눈 기반 표현을 지원하는 블록 수준 요소입니다.  이 요소의 유연성은 매우 유용하지만 이러한 유연성으로 인해 이를 이해하고 올바르게 사용하는 것이 매우 복잡해지기도 합니다.  
  
 이 항목에는 다음 단원이 포함되어 있습니다.  
  
-   [표 기본 사항](#table_basics)  
  
-   [표와 모눈의 차이점](#table_vs_Grid)  
  
-   [표 기본 구조](#basic_table_structure)  
  
-   [표 포함 관계](#table_containment)  
  
-   [행 그룹화](#row_groupings)  
  
-   [배경 렌더링 우선 순위](#rednering_precedence)  
  
-   [행 또는 열 확장](#spanning_rows_or_columns)  
  
-   [코드를 사용하여 테이블 빌드](#building_a_table_with_code)  
  
-   [관련 항목](#see_also)  
  
<a name="table_basics"></a>   
## 표 기본 사항  
  
<a name="table_vs_Grid"></a>   
### 표와 모눈의 차이점  
 <xref:System.Windows.Documents.Table> 및 <xref:System.Windows.Controls.Grid>는 공통된 기능을 공유하지만 각각 적합한 시나리오는 서로 다릅니다.  <xref:System.Windows.Documents.Table>은 유동 콘텐츠 내에서 사용되도록 설계된 것입니다. 유동 콘텐츠에 대한 자세한 내용은 [유동 문서 개요](../../../../docs/framework/wpf/advanced/flow-document-overview.md)를 참조하십시오.  모눈은 기본적으로는 유동 콘텐츠 외부 어디에서든 사용할 수 있으나 폼 내부에서 사용하기에 가장 적합합니다.  <xref:System.Windows.Documents.FlowDocument> 내부에서 <xref:System.Windows.Documents.Table>은 페이지 매김, 열 흐름 변경 및 콘텐츠 선택과 같은 유동 콘텐츠 동작을 지원하지만 <xref:System.Windows.Controls.Grid>는 지원하지 않습니다.  한편 <xref:System.Windows.Controls.Grid>는 <xref:System.Windows.Controls.Grid>가 행 및 열 인덱스를 기반으로 요소를 추가하는 반면 <xref:System.Windows.Documents.Table>은 그렇지 않다는 등의 여러 가지 이유에서 <xref:System.Windows.Documents.FlowDocument> 외부에서 사용하기에 가장 적합합니다.  <xref:System.Windows.Controls.Grid> 요소를 사용하면 자식 콘텐츠를 계층화할 수 있으므로 단일 "셀" 내에 둘 이상의 요소가 존재할 수 있습니다. <xref:System.Windows.Documents.Table>은 계층화를 지원하지 않습니다.  <xref:System.Windows.Controls.Grid>의 자식 요소는 해당 "셀" 경계 영역을 기준으로 절대 위치에 배치될 수 있습니다.  <xref:System.Windows.Documents.Table>은 이 기능을 지원하지 않습니다.  마지막으로 <xref:System.Windows.Controls.Grid>는 <xref:System.Windows.Documents.Table>에 비해 리소스를 더 적게 필요로 하므로 성능을 향상시키려면 <xref:System.Windows.Controls.Grid> 사용을 고려해 보십시오.  
  
<a name="basic_table_structure"></a>   
### 표 기본 구조  
 <xref:System.Windows.Documents.Table>은 열\(<xref:System.Windows.Documents.TableColumn> 요소로 표현\)과 행\(<xref:System.Windows.Documents.TableRow> 요소로 표현\)으로 구성되는 모눈 기반 표시를 제공합니다.  <xref:System.Windows.Documents.TableColumn> 요소는 콘텐츠를 호스팅하지 않고 단지 열의 열과 특성을 정의하기만 합니다.  <xref:System.Windows.Documents.TableRow> 요소는 <xref:System.Windows.Documents.TableRowGroup> 요소 내에서 호스팅되어야 하며 표 행의 그룹화를 정의합니다.  표가 표시할 실제 콘테츠가 들어 있는 <xref:System.Windows.Documents.TableCell> 요소는 <xref:System.Windows.Documents.TableRow> 요소 내에서 호스팅되어야 합니다.  <xref:System.Windows.Documents.TableCell>에는 <xref:System.Windows.Documents.Block>에서 파생된 요소만 포함될 수 있습니다.  <xref:System.Windows.Documents.TableCell>에 사용할 수 있는 유효한 자식 요소는 다음과 같습니다.  
  
-   <xref:System.Windows.Documents.BlockUIContainer>  
  
-   <xref:System.Windows.Documents.List>  
  
-   <xref:System.Windows.Documents.Paragraph>  
  
-   <xref:System.Windows.Documents.Section>  
  
-   <xref:System.Windows.Documents.Table>  
  
> [!NOTE]
>  <xref:System.Windows.Documents.TableCell> 요소는 텍스트 콘텐츠를 직접 호스팅하지 않을 수도 있습니다.  <xref:System.Windows.Documents.TableCell>과 같은 유동 콘텐츠 요소에 대한 포함 규칙과 관련된 자세한 내용은 [유동 문서 개요](../../../../docs/framework/wpf/advanced/flow-document-overview.md)를 참조하십시오.  
  
> [!NOTE]
>  <xref:System.Windows.Documents.Table>은 <xref:System.Windows.Controls.Grid> 요소와 비슷하지만 보다 많은 기능을 제공하기 때문에 리소스 오버헤드가 더 높습니다.  
  
 다음 예제에서는 [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)]을 사용하여 간단한 2 x 3 표를 정의합니다.  
  
 [!code-xml[TableSnippets2#_Table_BasicLayout](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_basiclayout)]  
  
 다음 그림에서는 이 예제가 렌더링되는 방법을 보여 줍니다.  
  
 ![스크린 샷: 기본 표 렌더링](../../../../docs/framework/wpf/advanced/media/basictablerrender.png "BasicTablerRender")  
  
<a name="table_containment"></a>   
### 표 포함 관계  
 <xref:System.Windows.Documents.Table>은 <xref:System.Windows.Documents.Block> 요소에서 파생되며 <xref:System.Windows.Documents.Block> 수준 요소에 대한 일반적인 규칙을 따릅니다.  <xref:System.Windows.Documents.Table> 요소는 다음과 같은 요소에 포함될 수 있습니다.  
  
-   <xref:System.Windows.Documents.FlowDocument>  
  
-   <xref:System.Windows.Documents.TableCell>  
  
-   <xref:System.Windows.Controls.ListBoxItem>  
  
-   <xref:System.Windows.Controls.ListViewItem>  
  
-   <xref:System.Windows.Documents.Section>  
  
-   <xref:System.Windows.Documents.Floater>  
  
-   <xref:System.Windows.Documents.Figure>  
  
<a name="row_groupings"></a>   
### 행 그룹화  
 <xref:System.Windows.Documents.TableRowGroup> 요소는 표 안에서 행을 임의로 그룹화할 수 있는 방법을 제공하며, 표의 모든 행은 행 그룹에 속해야 합니다.  행 그룹 내의 행은 대개 공통된 의미를 가지며 그룹으로 스타일을 지정할 수 있습니다.  행 그룹은 일반적으로 제목, 머리글 및 바닥글 행과 같은 특정 용도의 행을 표에 포함된 기본 콘텐츠와 구분하기 위해 사용합니다.  
  
 다음 예제에서는 [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)]을 사용하여 스타일이 지정된 머리글과 바닥글 행이 있는 표를 정의합니다.  
  
 [!code-xml[TableSnippets2#_Table_RowGroups](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_rowgroups)]  
  
 다음 그림에서는 이 예제가 렌더링되는 방법을 보여 줍니다.  
  
 ![스크린 샷: 표 행 그룹](../../../../docs/framework/wpf/advanced/media/table-rowgroups.png "Table\_RowGroups")  
  
<a name="renderning_precedence"></a>   
### 배경 렌더링 우선 순위  
 표 요소는 다음과 같은 순서\(오름차순의 [z\-순서](GTMT)\)로 렌더링됩니다.  이 순서는 변경할 수 없습니다.  예를 들어 이렇게 설정된 순서를 재정의하는 데 사용할 수 있는 이들 요소에 대한 "Z\-순서" 속성은 없습니다.  
  
1.  <xref:System.Windows.Documents.Table>  
  
2.  <xref:System.Windows.Documents.TableColumn>  
  
3.  <xref:System.Windows.Documents.TableRowGroup>  
  
4.  <xref:System.Windows.Documents.TableRow>  
  
5.  <xref:System.Windows.Documents.TableCell>  
  
 다음 예제에서는 표 안에서 이들 요소 각각에 대한 배경색을 정의합니다.  
  
 [!code-xml[TableSnippets2#_Table_ZOrder](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_zorder)]  
  
 다음 그림에서는 이 예제가 렌더링되는 방식을 보여 줍니다\(배경색만 표시\).  
  
 ![스크린 샷: 표 z 순서](../../../../docs/framework/wpf/advanced/media/table-zorder.png "Table\_ZOrder")  
  
<a name="spanning_rows_or_columns"></a>   
### 행 또는 열 확장  
 표의 셀은 <xref:System.Windows.Documents.TableCell.RowSpan%2A> 또는 <xref:System.Windows.Documents.TableCell.ColumnSpan%2A> 속성을 사용하여 각각 여러 개의 행 또는 열로 확장하도록 구성할 수 있습니다.  
  
 다음 예제에서는 하나의 셀을 세 개의 열로 확장합니다.  
  
 [!code-xml[TableSnippets2#_Table_ColumnSpan](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets2/CSharp/Window1.xaml#_table_columnspan)]  
  
 다음 그림에서는 이 예제가 렌더링되는 방법을 보여 줍니다.  
  
 ![스크린 샷: 세 열에 걸친 셀](../../../../docs/framework/wpf/advanced/media/table-columnspan.png "Table\_ColumnSpan")  
  
<a name="building_a_table_with_code"></a>   
## 코드를 사용하여 테이블 빌드  
 다음 예제에서는 <xref:System.Windows.Documents.Table>을 프로그래밍 방식으로 만들고 이를 콘텐츠로 채우는 방법을 보여 줍니다.  표의 콘텐츠는 5개의 행\(<xref:System.Windows.Documents.Table.RowGroups%2A> 개체에 포함된 <xref:System.Windows.Documents.TableRow> 개체로 표시\)과 6개의 열\(<xref:System.Windows.Documents.TableColumn> 개체로 표시\)에 배분됩니다.  행은 서로 다른 표시 목적에 사용되며, 여기에는 표 전체에 대한 제목을 지정하기 위한 제목 행, 표의 데이터 열을 설명하기 위한 머리글 행 및 요약 정보가 들어 있는 바닥글 행 등이 포함됩니다.  "제목", "머리글" 및 "바닥글" 행이라는 명칭은 표로부터 비롯된 것이 아닌 단지 서로 다른 특성을 갖는 행을 나타내는 것입니다.  표 셀에는 실제 콘텐츠가 들어 있으며 여기에는 텍스트, 이미지 및 기타 거의 모든 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 요소가 포함될 수 있습니다.  
  
 먼저 <xref:System.Windows.Documents.Table>을 호스팅하기 위해 <xref:System.Windows.Documents.FlowDocument>가 만들어지고, 새로운 <xref:System.Windows.Documents.Table>이 만들어져서 <xref:System.Windows.Documents.FlowDocument>의 콘텐츠에 추가됩니다.  
  
 [!code-csharp[TableSnippets#_TableCreate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreate)]
 [!code-vb[TableSnippets#_TableCreate](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreate)]  
  
 다음은 6개의 <xref:System.Windows.Documents.TableColumn> 개체가 만들어져서 표의 <xref:System.Windows.Documents.Table.Columns%2A> 컬렉션에 추가되고 이때 서식이 일부 적용됩니다.  
  
> [!NOTE]
>  표의 <xref:System.Windows.Documents.Table.Columns%2A> 컬렉션은 0부터 시작하는 표준 색인을 사용합니다.  
  
 [!code-csharp[TableSnippets#_TableCreateColumns](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreatecolumns)]
 [!code-vb[TableSnippets#_TableCreateColumns](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreatecolumns)]  
  
 다음에는 제목 행이 만들어져서 서식이 적용된 표에 추가됩니다.  제목 행에는 표의 모든 6개의 열로 확장되는 단일 셀이 포함됩니다.  
  
 [!code-csharp[TableSnippets#_TableAddTitleRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddtitlerow)]
 [!code-vb[TableSnippets#_TableAddTitleRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddtitlerow)]  
  
 다음에는 머리글 행이 만들어져서 표에 추가되고 머리글 행의 셀이 만들어져서 콘텐츠가 채워집니다.  
  
 [!code-csharp[TableSnippets#_TableAddHeaderRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddheaderrow)]
 [!code-vb[TableSnippets#_TableAddHeaderRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddheaderrow)]  
  
 다음에는 데이터 행이 만들어져서 표에 추가되고 이 행의 셀이 만들어져서 콘텐츠가 채워집니다.  이 행을 빌드하는 것은 머리글 행을 빌드하는 것과 유사하고 서식 적용만 약간 다릅니다.  
  
 [!code-csharp[TableSnippets#_TableAddDataRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableadddatarow)]
 [!code-vb[TableSnippets#_TableAddDataRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableadddatarow)]  
  
 마지막으로 바닥글 행이 만들어져서 추가되고 서식이 적용됩니다.  제목 행과 마찬가지로 바닥글에는 표의 모든 6개의 열로 확장되는 단일 셀이 포함됩니다.  
  
 [!code-csharp[TableSnippets#_TableAddFooterRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddfooterrow)]
 [!code-vb[TableSnippets#_TableAddFooterRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddfooterrow)]  
  
## 참고 항목  
 [유동 문서 개요](../../../../docs/framework/wpf/advanced/flow-document-overview.md)   
 [XAML로 표 정의](../../../../docs/framework/wpf/advanced/how-to-define-a-table-with-xaml.md)   
 [WPF의 문서](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)   
 [유동 콘텐츠 요소 사용](../../../../docs/framework/wpf/advanced/how-to-use-flow-content-elements.md)