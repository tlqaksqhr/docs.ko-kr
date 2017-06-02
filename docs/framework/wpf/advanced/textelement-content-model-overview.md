---
title: "TextElement 콘텐츠 모델 개요 | Microsoft Docs"
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
  - "문서, 유동 문서"
  - "유동 콘텐츠 요소[WPF], TextElement 콘텐츠 모델"
  - "유동 문서"
  - "TextElement 콘텐츠 모델"
ms.assetid: d0a7791c-b090-438c-812f-b9d009d83ee9
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# TextElement 콘텐츠 모델 개요
이 콘텐츠 모델 개요에서는 <xref:System.Windows.Documents.TextElement>에 대해 지원되는 콘텐츠를 설명합니다.  <xref:System.Windows.Documents.Paragraph> 클래스는 <xref:System.Windows.Documents.TextElement> 형식입니다.  콘텐츠 모델은 다른 부분에 포함할 수 있는 개체\/요소에 대해 설명합니다.  이 개요에서는 <xref:System.Windows.Documents.TextElement>에서 파생된 개체에 대해 사용된 콘텐츠 모델을 요약하여 보여 줍니다.  자세한 내용은 [유동 문서 개요](../../../../docs/framework/wpf/advanced/flow-document-overview.md)를 참조하십시오.  
  
   
  
<a name="text_element_classes"></a>   
## 콘텐츠 모델 다이어그램  
 다음 다이어그램에서는 <xref:System.Windows.Documents.TextElement>에서 파생된 클래스에 대한 콘텐츠 모델을 비롯하여 다른 비 `TextElement` 클래스가 이 모델에 맞추는 방법을 요약하여 보여 줍니다.  
  
 ![다이어그램: 유동 콘텐츠 포함 스키마](../../../../docs/framework/wpf/advanced/media/flow-content-schema.png "Flow\_Content\_Schema")  
  
 앞의 다이어그램에서 볼 수 있듯이 요소에 허용되는 자식은 클래스가 <xref:System.Windows.Documents.Block> 클래스에서 파생된 것인지 아니면 <xref:System.Windows.Documents.Inline> 클래스에서 파생된 것인지 여부에 따라서만 결정되는 것은 아닙니다.  예를 들어 <xref:System.Windows.Documents.Span>\(<xref:System.Windows.Documents.Inline> 파생 클래스\)은 <xref:System.Windows.Documents.Inline> 자식 요소만 가질 수 있지만 <xref:System.Windows.Documents.Figure>\(<xref:System.Windows.Documents.Inline> 파생 클래스\)는 <xref:System.Windows.Documents.Block> 자식 요소만 가질 수 있습니다.  따라서 다이어그램은 다른 요소에 포함할 수 있는 요소를 신속하게 확인하는 데 유용합니다.  예를 들어 <xref:System.Windows.Controls.RichTextBox>의 유동 콘텐츠를 생성하는 방법을 확인하기 위해 다이어그램을 사용해 보겠습니다.  
  
1.  <xref:System.Windows.Controls.RichTextBox>는 <xref:System.Windows.Documents.Block> 파생 개체를 포함해야 하는 <xref:System.Windows.Documents.FlowDocument>를 포함해야 합니다.  다음은 이전 다이어그램의 해당 세그먼트입니다.  
  
     ![다이어그램: RichTextBox 포함 규칙](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough1.png "Flow\_Ovw\_SchemaWalkThrough1")  
  
     따라서 지금까지의 태그는 다음과 같습니다.  
  
     [!code-xml[FlowOvwSnippets_snip#SchemaWalkThrough1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough1)]  
  
2.  다이어그램에 따르면 <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.Table>, <xref:System.Windows.Documents.List> 및 <xref:System.Windows.Documents.BlockUIContainer>를 비롯하여 선택할 여러 <xref:System.Windows.Documents.Block> 요소가 있습니다\(이전 다이어그램에서 Block 파생 클래스 참조\).  <xref:System.Windows.Documents.Table>이 필요하다고 가정해 봅니다.  이전 다이어그램에 따르면 <xref:System.Windows.Documents.Table>에는 <xref:System.Windows.Documents.TableRow> 요소를 포함하는 <xref:System.Windows.Documents.TableRowGroup>이 있으며 여기에는 <xref:System.Windows.Documents.Block> 파생 개체를 포함하는 <xref:System.Windows.Documents.TableCell> 요소가 포함됩니다.  다음은 이전 다이어그램에서 가져온 <xref:System.Windows.Documents.Table>에 대한 해당 세그먼트입니다.  
  
     ![다이어그램: Table에 대한 부모&#47;자식 스키마](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough2.png "Flow\_Ovw\_SchemaWalkThrough2")  
  
     다음은 해당 태그입니다.  
  
     [!code-xml[FlowOvwSnippets_snip#SchemaWalkThrough2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough2)]  
  
3.  이 경우에도 <xref:System.Windows.Documents.TableCell> 아래에 하나 이상의 <xref:System.Windows.Documents.Block> 요소가 필요합니다.  간단하게 약간의 텍스트를 셀 안에 배치해 보겠습니다.  이렇게 하려면 <xref:System.Windows.Documents.Run> 요소와 함께 <xref:System.Windows.Documents.Paragraph>를 사용하면 됩니다.  다음은 <xref:System.Windows.Documents.Paragraph>가 <xref:System.Windows.Documents.Inline> 요소를 사용할 수 있고 <xref:System.Windows.Documents.Run>\(<xref:System.Windows.Documents.Inline> 요소\)이 일반 텍스트만 사용할 수 있다는 것을 보여 주는 다이어그램의 해당 세그먼트입니다.  
  
     ![다이어그램: Paragraph에 대한 부모&#47;자식 스키마](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough3.png "Flow\_Ovw\_SchemaWalkThrough3")  
  
     ![다이어그램: Run에 대한 부모&#47;자식 스키마](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough4.png "Flow\_Ovw\_SchemaWalkThrough4")  
  
 다음은 태그의 전체 예제입니다.  
  
 [!code-xml[FlowOvwSnippets_snip#SchemaExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SchemaExample.xaml#schemaexamplewholepage)]  
  
<a name="Using_the_Content_Property"></a>   
## 프로그래밍 방식으로 TextElement 콘텐츠 작업  
 <xref:System.Windows.Documents.TextElement>의 콘텐츠는 컬렉션에 의해 구성되므로 이러한 컬렉션을 사용하여 <xref:System.Windows.Documents.TextElement> 개체의 콘텐츠를 프로그래밍 방식으로 조작할 수 있습니다.  <xref:System.Windows.Documents.TextElement> 파생 클래스에 의해 사용되는 다양한 컬렉션은 다음 세 가지입니다.  
  
-   <xref:System.Windows.Documents.InlineCollection>: <xref:System.Windows.Documents.Inline> 요소의 컬렉션을 나타냅니다.  <xref:System.Windows.Documents.InlineCollection>은 <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Span> 및 <xref:System.Windows.Controls.TextBlock> 요소의 사용할 수 있는 자식 콘텐츠를 정의합니다.  
  
-   <xref:System.Windows.Documents.BlockCollection>: <xref:System.Windows.Documents.Block> 요소의 컬렉션을 나타냅니다.  <xref:System.Windows.Documents.BlockCollection>은 <xref:System.Windows.Documents.FlowDocument>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.ListItem>, <xref:System.Windows.Documents.TableCell>, <xref:System.Windows.Documents.Floater> 및 <xref:System.Windows.Documents.Figure> 요소의 사용할 수 있는 자식 콘텐츠를 정의합니다.  
  
-   <xref:System.Windows.Documents.ListItemCollection>: 순서가 지정되거나 순서가 지정되지 않은 <xref:System.Windows.Documents.List>의 특정 콘텐츠 항목을 나타내는 유동 콘텐츠 요소입니다.  
  
 이러한 컬렉션에서 **Inlines**, **Blocks** 및 **ListItems**의 각 속성을 사용하여 조작\(항목 추가 또는 제거\)할 수 있습니다.  다음 예제에서는 **Inlines** 속성을 사용하여 Span의 콘텐츠를 조작하는 방법을 보여 줍니다.  
  
> [!NOTE]
>  테이블에서는 여러 컬렉션을 사용하여 해당 콘텐츠를 조작하지만 여기서는 다루지 않습니다.  자세한 내용은 [표 개요](../../../../docs/framework/wpf/advanced/table-overview.md)를 참조하십시오.  
  
 다음 예제에서는 새 <xref:System.Windows.Documents.Span> 개체를 만든 다음 `Add` 메서드를 사용하여 두 텍스트 런\(Text Run\)을 <xref:System.Windows.Documents.Span>의 콘텐츠 자식으로 실행할 추가합니다.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesAdd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesadd)]
 [!code-vb[SpanSnippets#_SpanInlinesAdd](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesadd)]  
  
 다음 예제에서는 새 <xref:System.Windows.Documents.Run> 요소를 만들어 <xref:System.Windows.Documents.Span>의 시작 부분에 삽입합니다.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesInsert](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesinsert)]
 [!code-vb[SpanSnippets#_SpanInlinesInsert](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesinsert)]  
  
 다음 예제에서는 <xref:System.Windows.Documents.Span>에서 마지막 <xref:System.Windows.Documents.Inline> 요소를 삭제합니다.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesRemoveLast](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesremovelast)]
 [!code-vb[SpanSnippets#_SpanInlinesRemoveLast](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesremovelast)]  
  
 다음 예제에서는 <xref:System.Windows.Documents.Span>에서 모든 콘텐츠\(<xref:System.Windows.Documents.Inline> 요소\)를 지웁니다.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesClear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesclear)]
 [!code-vb[SpanSnippets#_SpanInlinesClear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesclear)]  
  
<a name="Types_that_Share_this_Content_Model"></a>   
## 이 콘텐츠 모델을 공유하는 형식  
 다음 형식은 <xref:System.Windows.Documents.TextElement> 클래스에서 상속되며 이 개요에서 설명한 콘텐츠를 표시하는 데 사용될 수 있습니다.  
  
 <xref:System.Windows.Documents.Bold>, <xref:System.Windows.Documents.Figure>, <xref:System.Windows.Documents.Floater>, <xref:System.Windows.Documents.Hyperlink>, <xref:System.Windows.Documents.InlineUIContainer>, <xref:System.Windows.Documents.Italic>, <xref:System.Windows.Documents.LineBreak>, <xref:System.Windows.Documents.List>, <xref:System.Windows.Documents.ListItem>, <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Run>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.Span>, <xref:System.Windows.Documents.Table>, <xref:System.Windows.Documents.Underline>.  
  
 이 목록에는 [!INCLUDE[TLA2#tla_winfxsdk](../../../../includes/tla2sharptla-winfxsdk-md.md)]와 함께 배포되는 비추상 형식만 포함됩니다.  <xref:System.Windows.Documents.TextElement>에서 상속되는 다른 형식을 사용할 수 있습니다.  
  
<a name="Types_that_Can_Contain_ContentControl_Objects"></a>   
## TextElement 개체를 포함할 수 있는 형식  
 [WPF 콘텐츠 모델](../../../../docs/framework/wpf/controls/wpf-content-model.md)를 참조하십시오.  
  
## 참고 항목  
 [Blocks 속성을 통한 FlowDocument 조작](../../../../docs/framework/wpf/advanced/how-to-manipulate-a-flowdocument-through-the-blocks-property.md)   
 [Blocks 속성을 통한 유동 콘텐츠 요소 조작](../../../../docs/framework/wpf/advanced/how-to-manipulate-flow-content-elements-through-the-blocks-property.md)   
 [Blocks 속성을 통한 FlowDocument 조작](../../../../docs/framework/wpf/advanced/how-to-manipulate-a-flowdocument-through-the-blocks-property.md)   
 [Columns 속성을 통해 표의 열 조작](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-columns-through-the-columns-property.md)   
 [RowGroups 속성을 통한 표의 행 그룹 조작](../../../../docs/framework/wpf/advanced/how-to-manipulate-table-row-groups-through-the-rowgroups-property.md)