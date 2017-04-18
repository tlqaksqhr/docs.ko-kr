---
title: "방법: Blocks 속성을 통한 FlowDocument 조작 | Microsoft Docs"
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
  - "Blocks 속성, FlowDocuments 조작"
  - "문서, Blocks 속성을 통한 FlowDocuments 조작"
  - "FlowDocuments, Blocks 속성을 통해 조작"
  - "속성, 블록, FlowDocuments 조작"
ms.assetid: cbb7291e-3f1b-433e-9e16-f4d93ced14e8
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# 방법: Blocks 속성을 통한 FlowDocument 조작
이 예제에서는 <xref:System.Windows.Documents.FlowDocument.Blocks%2A> 속성을 통해 <xref:System.Windows.Documents.FlowDocument>에서 수행할 수 있는 보다 일반적인 작업 중 몇 가지를 보여 줍니다.  
  
## 예제  
 다음 예제에서는 새 <xref:System.Windows.Documents.FlowDocument>를 만든 다음 새 <xref:System.Windows.Documents.Paragraph> 요소를 <xref:System.Windows.Documents.FlowDocument>에 추가합니다.  
  
 [!code-csharp[FlowDocumentSnippets#_FlowDocumentBlocksAdd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_flowdocumentblocksadd)]
 [!code-vb[FlowDocumentSnippets#_FlowDocumentBlocksAdd](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_flowdocumentblocksadd)]  
  
## 예제  
 다음 예제에서는 새 <xref:System.Windows.Documents.Paragraph> 요소를 만들어 <xref:System.Windows.Documents.FlowDocument>의 시작 부분에 삽입합니다.  
  
 [!code-csharp[FlowDocumentSnippets#_FlowDocumentBlocksInsert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_flowdocumentblocksinsert)]
 [!code-vb[FlowDocumentSnippets#_FlowDocumentBlocksInsert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_flowdocumentblocksinsert)]  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Documents.FlowDocument>에 포함된 최상위 <xref:System.Windows.Documents.Block> 요소의 수를 가져옵니다.  
  
 [!code-csharp[FlowDocumentSnippets#_FlowDocumentBlocksCount](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_flowdocumentblockscount)]
 [!code-vb[FlowDocumentSnippets#_FlowDocumentBlocksCount](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_flowdocumentblockscount)]  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Documents.FlowDocument>에서 마지막 <xref:System.Windows.Documents.Block> 요소를 삭제합니다.  
  
 [!code-csharp[FlowDocumentSnippets#_FlowDocumentBlocksRemoveLast](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_flowdocumentblocksremovelast)]
 [!code-vb[FlowDocumentSnippets#_FlowDocumentBlocksRemoveLast](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_flowdocumentblocksremovelast)]  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Documents.FlowDocument>에서 모든 콘텐츠\(<xref:System.Windows.Documents.Block> 요소\)를 지웁니다.  
  
 [!code-csharp[FlowDocumentSnippets#_FlowDocumentBlocksClear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_flowdocumentblocksclear)]
 [!code-vb[FlowDocumentSnippets#_FlowDocumentBlocksClear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_flowdocumentblocksclear)]  
  
## 참고 항목  
 [RowGroups 속성을 통한 표의 행 그룹 조작](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)   
 [Columns 속성을 통해 표의 열 조작](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-columns-through-the-columns-property.md)   
 [RowGroups 속성을 통한 표의 행 그룹 조작](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)