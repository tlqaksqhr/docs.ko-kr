---
title: "방법: Blocks 속성을 통한 유동 콘텐츠 요소 조작"
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
- documents [WPF], manipulating flow content elements through Blocks property
- flow content elements [WPF], manipulating through Blocks property
- properties [WPF], Blocks [WPF], manipulating flow content elements
- Blocks property [WPF], manipulating flow content elements
ms.assetid: aeda4ece-b979-4818-a093-ef938e908751
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f246b7ab5eae52b745849daf2bedadb7431d7d34
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-manipulate-flow-content-elements-through-the-blocks-property"></a>방법: Blocks 속성을 통한 유동 콘텐츠 요소 조작
이러한 예제를 보여 주는 통해 유동 콘텐츠 요소에서 수행할 수 있는 일반적인 작업 중 몇 가지는 **블록** 속성입니다. 항목 추가 및 제거 하려면이 속성은 사용 <xref:System.Windows.Documents.BlockCollection>합니다. 유동 콘텐츠 요소는 **블록** 속성에 포함 합니다.  
  
-   <xref:System.Windows.Documents.Figure>  
  
-   <xref:System.Windows.Documents.Floater>  
  
-   <xref:System.Windows.Documents.ListItem>  
  
-   <xref:System.Windows.Documents.Section>  
  
-   <xref:System.Windows.Documents.TableCell>  
  
 이러한 예제를 사용 하는 문제가 발생 <xref:System.Windows.Documents.Section> 유동 콘텐츠 요소 없지만 이러한 기술은 유동 콘텐츠 요소 컬렉션을 호스트 하는 모든 요소에 적용 가능 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 새 <xref:System.Windows.Documents.Section> 다음 사용 하 여는 **추가** 새 단락을 추가 하는 메서드는 **섹션** 내용입니다.  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksAdd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksadd)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksAdd](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksadd)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 새 <xref:System.Windows.Documents.Paragraph> 요소를 맨 앞에 삽입 하는 <xref:System.Windows.Documents.Section>합니다.  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksInsert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksinsert)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksInsert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksinsert)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 최상위의 수를 가져옵니다 <xref:System.Windows.Documents.Block> 에 포함 된 요소는 <xref:System.Windows.Documents.Section>합니다.  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksCount](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblockscount)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksCount](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblockscount)]  
  
## <a name="example"></a>예제  
 다음 예에서는 삭제 마지막 <xref:System.Windows.Documents.Block> 요소에는 <xref:System.Windows.Documents.Section>합니다.  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksRemoveLast](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksremovelast)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksRemoveLast](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksremovelast)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 모든 내용을 지웁니다 (<xref:System.Windows.Documents.Block> 요소)에서 고 <xref:System.Windows.Documents.Section>합니다.  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksClear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksclear)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksClear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksclear)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Documents.BlockCollection>  
 <xref:System.Windows.Documents.InlineCollection>  
 <xref:System.Windows.Documents.ListItemCollection>  
 [유동 문서 개요](../../../../docs/framework/wpf/advanced/flow-document-overview.md)  
 [RowGroups 속성을 통한 테이블의 행 그룹 조작](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)  
 [Columns 속성을 통해 테이블의 열 조작](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-columns-through-the-columns-property.md)  
 [RowGroups 속성을 통한 테이블의 행 그룹 조작](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
