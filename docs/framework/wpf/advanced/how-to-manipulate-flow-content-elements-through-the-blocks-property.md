---
title: "방법: Blocks 속성을 통한 유동 콘텐츠 요소 조작 | Microsoft Docs"
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
  - "Blocks 속성, 유동 콘텐츠 요소 조작"
  - "문서, Blocks 속성을 통한 유동 콘텐츠 요소 조작"
  - "유동 콘텐츠 요소, Blocks 속성을 통해 조작"
  - "속성, 블록, 유동 콘텐츠 요소 조작"
ms.assetid: aeda4ece-b979-4818-a093-ef938e908751
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# 방법: Blocks 속성을 통한 유동 콘텐츠 요소 조작
이 예제에서는 **Blocks** 속성을 통해 유동 콘텐츠 요소에서 수행할 수 있는 보다 일반적인 작업 중 몇 가지를 보여 줍니다.  이 속성은 <xref:System.Windows.Documents.BlockCollection>에서 항목을 추가하고 제거하는 데 사용됩니다.  **Blocks** 속성을 사용하는 유동 콘텐츠 요소에는 다음이 포함됩니다.  
  
-   <xref:System.Windows.Documents.Figure>  
  
-   <xref:System.Windows.Documents.Floater>  
  
-   <xref:System.Windows.Documents.ListItem>  
  
-   <xref:System.Windows.Documents.Section>  
  
-   <xref:System.Windows.Documents.TableCell>  
  
 이 예제에서는 <xref:System.Windows.Documents.Section>을 유동 콘텐츠 요소로 사용하지만 이러한 방법은 유동 콘텐츠 요소 컬렉션을 호스팅하는 모든 요소에도 적용할 수 있습니다.  
  
## 예제  
 다음 예제에서는 새 <xref:System.Windows.Documents.Section>을 만든 다음 **Add** 메서드를 사용하여 **Section** 콘텐츠에 새 Paragraph를 추가합니다.  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksAdd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksadd)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksAdd](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksadd)]  
  
## 예제  
 다음 예제에서는 새 <xref:System.Windows.Documents.Paragraph> 요소를 만들어 <xref:System.Windows.Documents.Section>의 시작 부분에 삽입합니다.  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksInsert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksinsert)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksInsert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksinsert)]  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Documents.Section>에 포함된 최상위 <xref:System.Windows.Documents.Block> 요소의 수를 가져옵니다.  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksCount](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblockscount)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksCount](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblockscount)]  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Documents.Section>에서 마지막 <xref:System.Windows.Documents.Block> 요소를 삭제합니다.  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksRemoveLast](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksremovelast)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksRemoveLast](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksremovelast)]  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Documents.Section>에서 모든 콘텐츠\(<xref:System.Windows.Documents.Block> 요소\)를 지웁니다.  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksClear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksclear)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksClear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksclear)]  
  
## 참고 항목  
 <xref:System.Windows.Documents.BlockCollection>   
 <xref:System.Windows.Documents.InlineCollection>   
 <xref:System.Windows.Documents.ListItemCollection>   
 [유동 문서 개요](../../../../docs/framework/wpf/advanced/flow-document-overview.md)   
 [RowGroups 속성을 통한 표의 행 그룹 조작](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)   
 [Columns 속성을 통해 표의 열 조작](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-columns-through-the-columns-property.md)   
 [RowGroups 속성을 통한 표의 행 그룹 조작](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)