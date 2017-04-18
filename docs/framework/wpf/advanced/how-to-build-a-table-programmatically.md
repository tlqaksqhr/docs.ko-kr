---
title: "방법: 프로그래밍 방식으로 표 작성 | Microsoft Docs"
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
  - "만들기, 테이블(프로그래밍 방식으로)"
  - "문서, 프로그래밍 방식으로 테이블 만들기"
  - "테이블, 프로그래밍 방식으로 만들기"
ms.assetid: e3ca88f3-6e94-4b61-82fc-42104c10b761
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 방법: 프로그래밍 방식으로 표 작성
다음 예제에서는 <xref:System.Windows.Documents.Table>을 프로그래밍 방식으로 만들고 이를 콘텐츠로 채우는 방법을 보여 줍니다.  표의 콘텐츠는 5개의 행\(<xref:System.Windows.Documents.Table.RowGroups%2A> 개체에 포함된 <xref:System.Windows.Documents.TableRow> 개체로 표시\)과 6개의 열\(<xref:System.Windows.Documents.TableColumn> 개체로 표시\)에 배분됩니다.  행은 서로 다른 표시 목적에 사용되며, 여기에는 표 전체에 대한 제목을 지정하기 위한 제목 행, 표의 데이터 열을 설명하기 위한 머리글 행 및 요약 정보가 들어 있는 바닥글 행 등이 포함됩니다.  "제목", "머리글" 및 "바닥글" 행이라는 명칭은 표로부터 비롯된 것이 아닌 단지 서로 다른 특성을 갖는 행을 나타내는 것입니다.  표 셀에는 실제 콘텐츠가 들어 있으며 여기에는 텍스트, 이미지 및 기타 거의 모든 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 요소가 포함될 수 있습니다.  
  
## 예제  
 먼저 <xref:System.Windows.Documents.Table>을 호스팅하기 위해 <xref:System.Windows.Documents.FlowDocument>가 만들어지고, 새로운 <xref:System.Windows.Documents.Table>이 만들어져서 <xref:System.Windows.Documents.FlowDocument>의 콘텐츠에 추가됩니다.  
  
 [!code-csharp[TableSnippets#_TableCreate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreate)]
 [!code-vb[TableSnippets#_TableCreate](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreate)]  
  
## 예제  
 다음은 6개의 <xref:System.Windows.Documents.TableColumn> 개체가 만들어져서 표의 <xref:System.Windows.Documents.Table.Columns%2A> 컬렉션에 추가되고 이때 서식이 일부 적용됩니다.  
  
> [!NOTE]
>  표의 <xref:System.Windows.Documents.Table.Columns%2A> 컬렉션은 0부터 시작하는 표준 색인을 사용합니다.  
  
 [!code-csharp[TableSnippets#_TableCreateColumns](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tablecreatecolumns)]
 [!code-vb[TableSnippets#_TableCreateColumns](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tablecreatecolumns)]  
  
## 예제  
 다음에는 제목 행이 만들어져서 서식이 적용된 표에 추가됩니다.  제목 행에는 표의 모든 6개의 열로 확장되는 단일 셀이 포함됩니다.  
  
 [!code-csharp[TableSnippets#_TableAddTitleRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddtitlerow)]
 [!code-vb[TableSnippets#_TableAddTitleRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddtitlerow)]  
  
## 예제  
 다음에는 머리글 행이 만들어져서 표에 추가되고 머리글 행의 셀이 만들어져서 콘텐츠가 채워집니다.  
  
 [!code-csharp[TableSnippets#_TableAddHeaderRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddheaderrow)]
 [!code-vb[TableSnippets#_TableAddHeaderRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddheaderrow)]  
  
## 예제  
 다음에는 데이터 행이 만들어져서 표에 추가되고 이 행의 셀이 만들어져서 콘텐츠가 채워집니다.  이 행을 빌드하는 것은 머리글 행을 빌드하는 것과 유사하고 서식 적용만 약간 다릅니다.  
  
 [!code-csharp[TableSnippets#_TableAddDataRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableadddatarow)]
 [!code-vb[TableSnippets#_TableAddDataRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableadddatarow)]  
  
## 예제  
 마지막으로 바닥글 행이 만들어져서 추가되고 서식이 적용됩니다.  제목 행과 마찬가지로 바닥글에는 표의 모든 6개의 열로 확장되는 단일 셀이 포함됩니다.  
  
 [!code-csharp[TableSnippets#_TableAddFooterRow](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TableSnippets/CSharp/Table.cs#_tableaddfooterrow)]
 [!code-vb[TableSnippets#_TableAddFooterRow](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TableSnippets/VisualBasic/Table.vb#_tableaddfooterrow)]  
  
## 참고 항목  
 [표 개요](../../../../docs/framework/wpf/advanced/table-overview.md)