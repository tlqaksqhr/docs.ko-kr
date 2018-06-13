---
title: '방법: Blocks 속성을 통한 FlowDocument 조작'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 'documents [WPF], manipulating FlowDocuments through Blocks property [WPF], , '
- ', '
ms.assetid: cbb7291e-3f1b-433e-9e16-f4d93ced14e8
ms.openlocfilehash: 0190a5c0e343d625f9aa9e896a581dd54bf822dd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33544065"
---
# <a name="how-to-manipulate-a-flowdocument-through-the-blocks-property"></a>방법: Blocks 속성을 통한 FlowDocument 조작
이러한 예제에서 수행할 수 있는 일반적인 작업 몇 가지를 보여는 <xref:System.Windows.Documents.FlowDocument> 통해는 <xref:System.Windows.Documents.FlowDocument.Blocks%2A> 속성입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 새 <xref:System.Windows.Documents.FlowDocument> 한 다음 새 추가 <xref:System.Windows.Documents.Paragraph> 요소는 <xref:System.Windows.Documents.FlowDocument>합니다.  
  
 [!code-csharp[FlowDocumentSnippets#_FlowDocumentBlocksAdd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_flowdocumentblocksadd)]
 [!code-vb[FlowDocumentSnippets#_FlowDocumentBlocksAdd](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_flowdocumentblocksadd)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 새 <xref:System.Windows.Documents.Paragraph> 요소를 맨 앞에 삽입 하는 <xref:System.Windows.Documents.FlowDocument>합니다.  
  
 [!code-csharp[FlowDocumentSnippets#_FlowDocumentBlocksInsert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_flowdocumentblocksinsert)]
 [!code-vb[FlowDocumentSnippets#_FlowDocumentBlocksInsert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_flowdocumentblocksinsert)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 최상위의 수를 가져옵니다 <xref:System.Windows.Documents.Block> 에 포함 된 요소는 <xref:System.Windows.Documents.FlowDocument>합니다.  
  
 [!code-csharp[FlowDocumentSnippets#_FlowDocumentBlocksCount](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_flowdocumentblockscount)]
 [!code-vb[FlowDocumentSnippets#_FlowDocumentBlocksCount](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_flowdocumentblockscount)]  
  
## <a name="example"></a>예제  
 다음 예에서는 삭제 마지막 <xref:System.Windows.Documents.Block> 요소에는 <xref:System.Windows.Documents.FlowDocument>합니다.  
  
 [!code-csharp[FlowDocumentSnippets#_FlowDocumentBlocksRemoveLast](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_flowdocumentblocksremovelast)]
 [!code-vb[FlowDocumentSnippets#_FlowDocumentBlocksRemoveLast](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_flowdocumentblocksremovelast)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 모든 내용을 지웁니다 (<xref:System.Windows.Documents.Block> 요소)에서 고 <xref:System.Windows.Documents.FlowDocument>합니다.  
  
 [!code-csharp[FlowDocumentSnippets#_FlowDocumentBlocksClear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_flowdocumentblocksclear)]
 [!code-vb[FlowDocumentSnippets#_FlowDocumentBlocksClear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_flowdocumentblocksclear)]  
  
## <a name="see-also"></a>참고 항목  
 [RowGroups 속성을 통한 테이블의 행 그룹 조작](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)  
 [Columns 속성을 통해 테이블의 열 조작](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-columns-through-the-columns-property.md)  
 [RowGroups 속성을 통한 테이블의 행 그룹 조작](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
