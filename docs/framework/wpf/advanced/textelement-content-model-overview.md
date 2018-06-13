---
title: TextElement 콘텐츠 모델 개요
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- documents [WPF], flow documents
- TextElement content model [WPF]
- flow content elements [WPF], TextElement content model
ms.assetid: d0a7791c-b090-438c-812f-b9d009d83ee9
ms.openlocfilehash: 4a50e8a10563fdc5e16ee2e2a46389e13b51e447
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33548859"
---
# <a name="textelement-content-model-overview"></a>TextElement 콘텐츠 모델 개요
에 대 한 지원 되는 콘텐츠를 설명 하는이 콘텐츠 모델 개요는 <xref:System.Windows.Documents.TextElement>합니다. <xref:System.Windows.Documents.Paragraph> 클래스는 유형의 <xref:System.Windows.Documents.TextElement>합니다. 콘텐츠 모델은 어떤 개체/요소가 다른 개체/요소에 포함될 수 있는지를 설명합니다. 이 개요에서 파생 된 개체에 사용 되는 콘텐츠 모델을 요약 <xref:System.Windows.Documents.TextElement>합니다. 자세한 내용은 참조 [문서 개요 흐름](../../../../docs/framework/wpf/advanced/flow-document-overview.md)합니다.  
  
  
<a name="text_element_classes"></a>   
## <a name="content-model-diagram"></a>콘텐츠 모델 다이어그램  
 다음 다이어그램에서 파생 된 클래스에 대 한 콘텐츠 모델을 요약 <xref:System.Windows.Documents.TextElement> 뿐만 아니라 다른 비- `TextElement` 클래스가이 모델에 적합 합니다.  
  
 ![다이어그램: 유동 콘텐츠 포함 스키마](../../../../docs/framework/wpf/advanced/media/flow-content-schema.png "Flow_Content_Schema")  
  
 위의 다이어그램에서 볼 수 있듯이 요소에 대해 허용 되는 자식이 반드시 의해 결정 되지 않습니다는 클래스에서 파생 된 여부는 <xref:System.Windows.Documents.Block> 클래스 또는 <xref:System.Windows.Documents.Inline> 클래스입니다. 예를 들어는 <xref:System.Windows.Documents.Span> (한 <xref:System.Windows.Documents.Inline>-파생 클래스) 하나만 사용할 수 있습니다 <xref:System.Windows.Documents.Inline> 자식 요소 하지만 <xref:System.Windows.Documents.Figure> (또한는 <xref:System.Windows.Documents.Inline>-파생 클래스) 하나만 사용할 수 있습니다 <xref:System.Windows.Documents.Block> 자식 요소입니다. 그러므로 이 다이어그램은 다른 요소에 포함될 수 있는 요소를 신속하게 판별하는 데 유용합니다. 예를 들어 다이어그램을 사용해 보겠습니다의 유동 콘텐츠를 생성 하는 방법을 결정 하는 <xref:System.Windows.Controls.RichTextBox>합니다.  
  
1.  A <xref:System.Windows.Controls.RichTextBox> 포함 해야 합니다는 <xref:System.Windows.Documents.FlowDocument> 를 포함 해야는 <xref:System.Windows.Documents.Block>-파생 된 개체입니다. 이전 다이어그램에 해당하는 세그먼트는 다음과 같습니다.  
  
     ![다이어그램: RichTextBox 포함 규칙](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough1.png "Flow_Ovw_SchemaWalkThrough1")  
  
     따라서 지금까지 태그는 다음과 같을 수 있습니다.  
  
     [!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough1)]  
  
2.  다이어그램에 따라 몇 가지 <xref:System.Windows.Documents.Block> 비롯 하 여 선택할 요소 <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.Table>, <xref:System.Windows.Documents.List>, 및 <xref:System.Windows.Documents.BlockUIContainer> (위 다이어그램에 블록 파생 클래스 참조). 원하는 경우를 가정해는 <xref:System.Windows.Documents.Table>합니다. 위의 다이어그램에 따라는 <xref:System.Windows.Documents.Table> 포함는 <xref:System.Windows.Documents.TableRowGroup> 포함 된 <xref:System.Windows.Documents.TableRow> 포함 하는 요소 <xref:System.Windows.Documents.TableCell> 포함 하는 요소는 <xref:System.Windows.Documents.Block>-파생 개체입니다. 다음은 해당 하는 세그먼트에 대 한 <xref:System.Windows.Documents.Table> 위의 다이어그램에서 가져옵니다.  
  
     ![다이어그램: 테이블의 부모&#47;자식 스키마](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough2.png "Flow_Ovw_SchemaWalkThrough2")  
  
     다음은 해당 태그입니다.  
  
     [!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough2)]  
  
3.  마찬가지로 하나 이상의 <xref:System.Windows.Documents.Block> 아래 필요한 요소는 <xref:System.Windows.Documents.TableCell>합니다. 간단하게 셀 안에 텍스트를 배치해 보겠습니다. 사용 하 여 수행할 수 있습니다는 <xref:System.Windows.Documents.Paragraph> 와 <xref:System.Windows.Documents.Run> 요소입니다. 다음의 해당 세그먼트를 보여 주는 다이어그램은 <xref:System.Windows.Documents.Paragraph> 걸릴 수 있습니다는 <xref:System.Windows.Documents.Inline> 요소를 한 <xref:System.Windows.Documents.Run> (한 <xref:System.Windows.Documents.Inline> 요소) 일반 텍스트만 사용할 수 있습니다.  
  
     ![다이어그램: 단락의 부모&#47;자식 스키마](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough3.png "Flow_Ovw_SchemaWalkThrough3")  
  
     ![다이어그램: 실행을 위한 부모&#47;자식 스키마](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough4.png "Flow_Ovw_SchemaWalkThrough4")  
  
 다음은 태그의 전체 예제입니다.  
  
 [!code-xaml[FlowOvwSnippets_snip#SchemaExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SchemaExample.xaml#schemaexamplewholepage)]  
  
<a name="Using_the_Content_Property"></a>   
## <a name="working-with-textelement-content-programmatically"></a>프로그래밍 방식으로 TextElement 콘텐츠 작업  
 콘텐츠는 <xref:System.Windows.Documents.TextElement> 컬렉션 등의 콘텐츠를 프로그래밍 방식으로 조작 하 여 구성 된 <xref:System.Windows.Documents.TextElement> 개체는 이러한 컬렉션을 사용 하 여 수행 됩니다. 사용 하는 세 가지 서로 다른 컬렉션 <xref:System.Windows.Documents.TextElement> -파생 된 클래스:  
  
-   <xref:System.Windows.Documents.InlineCollection>:의 컬렉션을 나타냅니다 <xref:System.Windows.Documents.Inline> 요소입니다. <xref:System.Windows.Documents.InlineCollection> 사용할 수 있는 자식 콘텐츠를 정의 고 <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Span>, 및 <xref:System.Windows.Controls.TextBlock> 요소입니다.  
  
-   <xref:System.Windows.Documents.BlockCollection>:의 컬렉션을 나타냅니다 <xref:System.Windows.Documents.Block> 요소입니다. <xref:System.Windows.Documents.BlockCollection>은 <xref:System.Windows.Documents.FlowDocument>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.ListItem>, <xref:System.Windows.Documents.TableCell>, <xref:System.Windows.Documents.Floater> 및 <xref:System.Windows.Documents.Figure> 요소의 사용할 수 있는 자식 콘텐츠를 정의합니다.  
  
-   <xref:System.Windows.Documents.ListItemCollection>순서 있는 특정 콘텐츠 항목을 나타내는: 유동 콘텐츠 요소 또는 순서가 지정 되지 않은 <xref:System.Windows.Documents.List>합니다.  
  
 조작할 수 있습니다 (추가 또는 제거 항목)의 해당 속성을 사용 하 여 이러한 컬렉션에서 **인라인**, **블록**, 및 **ListItems**합니다. 다음 예제는 범위를 사용 하 여의 내용을 조작 하는 방법을 보여 줍니다는 **인라인** 속성입니다.  
  
> [!NOTE]
>  테이블에서는 콘텐츠를 조작하는 데 여러 컬렉션을 사용하지만 이러한 컬렉션은 여기에서 다루지 않습니다. 자세한 내용은 참조 [테이블 개요](../../../../docs/framework/wpf/advanced/table-overview.md)합니다.  
  
 다음 예제에서는 새 <xref:System.Windows.Documents.Span> 개체, 한 다음 사용 하는 `Add` 두 텍스트를 추가 하는 방법을의 콘텐츠 자식으로 실행 되는 <xref:System.Windows.Documents.Span>합니다.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesAdd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesadd)]
 [!code-vb[SpanSnippets#_SpanInlinesAdd](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesadd)]  
  
 다음 예제에서는 새 <xref:System.Windows.Documents.Run> 요소를 맨 앞에 삽입 하는 <xref:System.Windows.Documents.Span>합니다.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesInsert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesinsert)]
 [!code-vb[SpanSnippets#_SpanInlinesInsert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesinsert)]  
  
 다음 예에서는 삭제 마지막 <xref:System.Windows.Documents.Inline> 요소에는 <xref:System.Windows.Documents.Span>합니다.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesRemoveLast](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesremovelast)]
 [!code-vb[SpanSnippets#_SpanInlinesRemoveLast](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesremovelast)]  
  
 다음 예제에서는 모든 내용을 지웁니다 (<xref:System.Windows.Documents.Inline> 요소)에서 고 <xref:System.Windows.Documents.Span>합니다.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesClear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesclear)]
 [!code-vb[SpanSnippets#_SpanInlinesClear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesclear)]  
  
<a name="Types_that_Share_this_Content_Model"></a>   
## <a name="types-that-share-this-content-model"></a>이 콘텐츠 모델을 공유하는 형식  
 다음 형식에서 상속 된 <xref:System.Windows.Documents.TextElement> 클래스 및이 개요에 설명 된 콘텐츠를 표시 하는 데 사용 될 수 있습니다.  
  
 <xref:System.Windows.Documents.Bold>, <xref:System.Windows.Documents.Figure>, <xref:System.Windows.Documents.Floater>, <xref:System.Windows.Documents.Hyperlink>, <xref:System.Windows.Documents.InlineUIContainer>, <xref:System.Windows.Documents.Italic>, <xref:System.Windows.Documents.LineBreak>, <xref:System.Windows.Documents.List>, <xref:System.Windows.Documents.ListItem>, <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Run>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.Span>, <xref:System.Windows.Documents.Table>, <xref:System.Windows.Documents.Underline>.  
  
 이 목록에만 함께 배포 하는 비추상 형식 포함는 [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)]합니다. 상속 하는 다른 형식을 사용할 수 있습니다 <xref:System.Windows.Documents.TextElement>합니다.  
  
<a name="Types_that_Can_Contain_ContentControl_Objects"></a>   
## <a name="types-that-can-contain-textelement-objects"></a>TextElement 개체를 포함할 수 있는 형식  
 참조 [WPF 콘텐츠 모델](../../../../docs/framework/wpf/controls/wpf-content-model.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Blocks 속성을 통한 FlowDocument 조작](../../../../docs/framework/wpf/advanced/how-to-manipulate-a-flowdocument-through-the-blocks-property.md)  
 [Blocks 속성을 통한 유동 콘텐츠 요소 조작](../../../../docs/framework/wpf/advanced/how-to-manipulate-flow-content-elements-through-the-blocks-property.md)  
 [Blocks 속성을 통한 FlowDocument 조작](../../../../docs/framework/wpf/advanced/how-to-manipulate-a-flowdocument-through-the-blocks-property.md)  
 [Columns 속성을 통해 테이블의 열 조작](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-columns-through-the-columns-property.md)  
 [RowGroups 속성을 통한 테이블의 행 그룹 조작](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)
