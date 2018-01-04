---
title: "방법: Inlines 속성을 통한 유동 콘텐츠 요소 조작"
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
- flow content elements [WPF], manipulating through Inlines property
- documents [WPF], manipulating flow Content elements through Inlines property
- Inlines property [WPF], manipulating flow Content elements
- properties [WPF], Inlines [WPF], manipulating flow Content elements
ms.assetid: 510780d2-3da1-4360-8763-7054bda22ea3
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c5d90756ee200ba091f2f9e15e9e7d5632984ba9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-manipulate-flow-content-elements-through-the-inlines-property"></a>방법: Inlines 속성을 통한 유동 콘텐츠 요소 조작
이 예에서는 인라인 유동 콘텐츠 요소에서 수행할 수 있는 보다 일반적인 작업 중 일부를 보여 줍니다 (및 이러한 요소는 컨테이너와 같은 <xref:System.Windows.Controls.TextBlock>)를 통해는 **인라인** 속성입니다. 항목 추가 및 제거 하려면이 속성은 사용 <xref:System.Windows.Documents.InlineCollection>합니다. 유동 콘텐츠 요소는 **인라인** 속성에 포함 합니다.  
  
-   <xref:System.Windows.Documents.Bold>  
  
-   <xref:System.Windows.Documents.Hyperlink>  
  
-   <xref:System.Windows.Documents.Italic>  
  
-   <xref:System.Windows.Documents.Paragraph>  
  
-   <xref:System.Windows.Documents.Span>  
  
-   <xref:System.Windows.Documents.Underline>  
  
 이러한 예제를 사용 하는 문제가 발생 <xref:System.Windows.Documents.Span> 유동 콘텐츠 요소 하지만 이러한 방법은에 적용할 수 있는 모든 요소 또는 컨트롤을 호스트 하는 <xref:System.Windows.Documents.InlineCollection> 컬렉션입니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 새 <xref:System.Windows.Documents.Span> 개체, 한 다음 사용 하는 **추가** 두 텍스트를 추가 하는 방법을의 콘텐츠 자식으로 실행 되는 <xref:System.Windows.Documents.Span>합니다.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesAdd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesadd)]
 [!code-vb[SpanSnippets#_SpanInlinesAdd](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesadd)]  
  
## <a name="example"></a>예  
 다음 예제에서는 새 <xref:System.Windows.Documents.Run> 요소를 맨 앞에 삽입 하는 <xref:System.Windows.Documents.Span>합니다.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesInsert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesinsert)]
 [!code-vb[SpanSnippets#_SpanInlinesInsert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesinsert)]  
  
## <a name="example"></a>예  
 다음 예제에서는 최상위의 수를 가져옵니다 <xref:System.Windows.Documents.Inline> 에 포함 된 요소는 <xref:System.Windows.Documents.Span>합니다.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesCount](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinescount)]
 [!code-vb[SpanSnippets#_SpanInlinesCount](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinescount)]  
  
## <a name="example"></a>예  
 다음 예에서는 삭제 마지막 <xref:System.Windows.Documents.Inline> 요소에는 <xref:System.Windows.Documents.Span>합니다.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesRemoveLast](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesremovelast)]
 [!code-vb[SpanSnippets#_SpanInlinesRemoveLast](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesremovelast)]  
  
## <a name="example"></a>예  
 다음 예제에서는 모든 내용을 지웁니다 (<xref:System.Windows.Documents.Inline> 요소)에서 고 <xref:System.Windows.Documents.Span>합니다.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesClear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesclear)]
 [!code-vb[SpanSnippets#_SpanInlinesClear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesclear)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Documents.BlockCollection>  
 <xref:System.Windows.Documents.InlineCollection>  
 <xref:System.Windows.Documents.ListItemCollection>  
 [유동 문서 개요](../../../../docs/framework/wpf/advanced/flow-document-overview.md)  
 [Blocks 속성을 통한 FlowDocument 조작](../../../../docs/framework/wpf/advanced/how-to-manipulate-a-flowdocument-through-the-blocks-property.md)  
 [Columns 속성을 통해 테이블의 열 조작](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-columns-through-the-columns-property.md)  
 [RowGroups 속성을 통한 테이블의 행 그룹 조작](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
