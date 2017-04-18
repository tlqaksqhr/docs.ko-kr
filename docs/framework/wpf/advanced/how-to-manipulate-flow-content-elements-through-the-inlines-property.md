---
title: "방법: Inlines 속성을 통한 유동 콘텐츠 요소 조작 | Microsoft Docs"
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
  - "문서, Inlines 속성을 통한 유동 콘텐츠 요소 조작"
  - "유동 콘텐츠 요소, Inlines 속성을 통해 조작"
  - "Inlines 속성, 유동 콘텐츠 요소 조작"
  - "속성, Inlines, 유동 콘텐츠 요소 조작"
ms.assetid: 510780d2-3da1-4360-8763-7054bda22ea3
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# 방법: Inlines 속성을 통한 유동 콘텐츠 요소 조작
다음 예제에서는 **Inlines** 속성을 통해 인라인 유동 콘텐츠 요소 및 이러한 요소의 컨테이너\(예: <xref:System.Windows.Controls.TextBlock>\)에서 수행할 수 있는 보다 일반적인 작업 중 몇 가지를 보여 줍니다.  이 속성은 <xref:System.Windows.Documents.InlineCollection>에서 항목을 추가하고 제거하는 데 사용됩니다.  **Inlines** 속성을 사용하는 유동 콘텐츠 요소에는 다음이 포함됩니다.  
  
-   <xref:System.Windows.Documents.Bold>  
  
-   <xref:System.Windows.Documents.Hyperlink>  
  
-   <xref:System.Windows.Documents.Italic>  
  
-   <xref:System.Windows.Documents.Paragraph>  
  
-   <xref:System.Windows.Documents.Span>  
  
-   <xref:System.Windows.Documents.Underline>  
  
 이 예제에서는 <xref:System.Windows.Documents.Span>을 유동 콘텐츠 요소로 사용하지만 이러한 방법은 <xref:System.Windows.Documents.InlineCollection> 컬렉션을 호스팅하는 모든 요소나 컨트롤에도 적용할 수 있습니다.  
  
## 예제  
 다음 예제에서는 새 <xref:System.Windows.Documents.Span> 개체를 만든 다음 **Add** 메서드를 사용하여 두 텍스트 런\(Text Run\)을 <xref:System.Windows.Documents.Span>의 콘텐츠 자식으로 추가합니다.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesAdd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesadd)]
 [!code-vb[SpanSnippets#_SpanInlinesAdd](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesadd)]  
  
## 예제  
 다음 예제에서는 새 <xref:System.Windows.Documents.Run> 요소를 만들어 <xref:System.Windows.Documents.Span>의 시작 부분에 삽입합니다.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesInsert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesinsert)]
 [!code-vb[SpanSnippets#_SpanInlinesInsert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesinsert)]  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Documents.Span>에 포함된 최상위 <xref:System.Windows.Documents.Inline> 요소의 수를 가져옵니다.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesCount](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinescount)]
 [!code-vb[SpanSnippets#_SpanInlinesCount](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinescount)]  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Documents.Span>에서 마지막 <xref:System.Windows.Documents.Inline> 요소를 삭제합니다.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesRemoveLast](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesremovelast)]
 [!code-vb[SpanSnippets#_SpanInlinesRemoveLast](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesremovelast)]  
  
## 예제  
 다음 예제에서는 <xref:System.Windows.Documents.Span>에서 모든 콘텐츠\(<xref:System.Windows.Documents.Inline> 요소\)를 지웁니다.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesClear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesclear)]
 [!code-vb[SpanSnippets#_SpanInlinesClear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesclear)]  
  
## 참고 항목  
 <xref:System.Windows.Documents.BlockCollection>   
 <xref:System.Windows.Documents.InlineCollection>   
 <xref:System.Windows.Documents.ListItemCollection>   
 [유동 문서 개요](../../../../docs/framework/wpf/advanced/flow-document-overview.md)   
 [Blocks 속성을 통한 FlowDocument 조작](../../../../docs/framework/wpf/advanced/how-to-manipulate-a-flowdocument-through-the-blocks-property.md)   
 [Columns 속성을 통해 표의 열 조작](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-columns-through-the-columns-property.md)   
 [RowGroups 속성을 통한 표의 행 그룹 조작](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)