---
title: "유동 문서 개요"
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
- 'documents [WPF], flow documents [WPF], , '
- ', '
- flow documents [WPF]
ms.assetid: ef236a50-d44f-43c8-ba7c-82b0c733c0b7
caps.latest.revision: "39"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 10f7eda2b6761a825dcb2b24ae9f11b2e1262d7e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="flow-document-overview"></a>유동 문서 개요
유동 문서는 보기와 가독성을 최적화하도록 설계되었습니다. 유동 문서는 미리 정의된 하나의 레이아웃으로 설정되는 것이 아니라, 창 크기, 장치 해상도 및 선택적 사용자 기본 설정 등의 런타임 변수에 따라 동적으로 콘텐츠를 조정하고 리플로우합니다. 유동 문서에서는 페이지 매김 및 열과 같은 고급 문서 기능을 제공합니다. 이 항목에서는 유동 문서의 개요와 해당 문서를 작성하는 방법을 제공합니다.  
  

  
<a name="what_is_a_flow_document"></a>   
## <a name="what-is-a-flow-document"></a>유동 문서의 정의  
 유동 문서는 창 크기, 장치 해상도 및 기타 환경 변수에 따라 “콘텐츠의 흐름을 변경”하도록 설계되었습니다. 또한 유동 문서에는 검색, 가독성을 최적화하는 보기 모드 및 글꼴의 모양과 크기를 변경하는 기능 등의 여러 기본 제공 기능이 포함되어 있습니다. 유동 문서는 문서 이용 시 용이한 가독성이 주된 요인인 시나리오에서 최적으로 활용할 수 있습니다. 반대로 고정 문서는 정적 프레젠테이션을 사용하도록 설계되어 있습니다. 소스 콘텐츠의 정확도가 중요한 경우 고정 문서를 사용해야 합니다. 참조 [WPF의 문서](../../../../docs/framework/wpf/advanced/documents-in-wpf.md) 다른 형식의 문서에 대 한 자세한 내용은 합니다.  
  
 다음 그림에서는 여러 다른 크기의 창에 표시되는 샘플 유동 문서를 보여줍니다. 표시 영역이 변경됨에 따라 사용 가능한 공간을 최적으로 활용하기 위해 콘텐츠의 흐름을 변경합니다.  
  
 ![유동 문서 콘텐츠 흐름 변경](../../../../docs/framework/wpf/advanced/media/edocs-flowdocument.png "eDocs_FlowDocument")  
  
 위의 이미지에서와 같이 유동 콘텐츠에는 단락, 목록, 이미지 등의 많은 구성 요소가 포함될 수 있습니다. 이러한 구성 요소는 태그의 요소 및 프로시저 코드의 개체에 해당합니다. 나중에 자세히 이러한 클래스에 대해 이동지 것입니다는 [관련 클래스 흐름](#flow_related_classes) 이 개요의 섹션입니다. 지금은 목록을 일부 굵은 텍스트와 단락으로 구성 된 흐름 문서를 만드는 간단한 코드 예제에서는 다음과 같습니다.
  
 [!code-xaml[FlowOvwSnippets_snip#SimpleFlowExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SimpleFlowExample.xaml#simpleflowexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#SimpleFlowCodeOnlyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/SimpleFlowExample.cs#simpleflowcodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#SimpleFlowCodeOnlyExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/SimpleFlowExample.vb#simpleflowcodeonlyexamplewholepage)]  
  
 아래 그림에서는 이 코드 조각을 보여줍니다.  
  
 ![스크린 샷: 렌더링된 FlowDocument 예제](../../../../docs/framework/wpf/advanced/media/flow-ovw-first-example.png "Flow_Ovw_First_Example")  
  
 이 예제는 <xref:System.Windows.Controls.FlowDocumentReader> 컨트롤은 유동 콘텐츠를 호스트 하는 데 사용 합니다. 참조 [유동 문서 형식](#flow_document_types) 유동 콘텐츠 컨트롤을 호스트에 대 한 자세한 내용은 합니다. <xref:System.Windows.Documents.Paragraph><xref:System.Windows.Documents.List>, <xref:System.Windows.Documents.ListItem>, 및 <xref:System.Windows.Documents.Bold> 요소 태그에서의 순서에 따라 콘텐츠 형식을 제어 하기 위해 사용 됩니다. 예를 들어는 <xref:System.Windows.Documents.Bold> 요소가 단락에 텍스트의 일부만 포함; 결과적으로, 텍스트의 해당 부분에만 굵게 표시 합니다. HTML을 사용해 본 적이 있으면 익숙할 것입니다.  
  
 위의 그림에서 강조 표시 된 대로 유동 문서에 기본 제공 되는 몇 가지 기능이 있습니다.
  
-   검색: 전체 문서에서 전체 텍스트 검색을 수행할 수 있습니다.  
  
-   보기 모드: 단일 페이지(한 번에 한 페이지) 보기 모드, 한 번에 두 페이지(책 읽기 형식) 보기 모드 및 연속 스크롤링(바닥이 없음) 보기 모드 중에서 선호하는 보기 모드를 선택할 수 있습니다.  이러한 보기 모드에 대 한 자세한 내용은 참조 하십시오. <xref:System.Windows.Controls.FlowDocumentReaderViewingMode>합니다.  
  
-   페이지 탐색 컨트롤: 문서의 보기 모드에서 페이지를 사용하면 페이지 탐색 컨트롤에 다음 페이지(아래쪽 화살표) 또는 이전 페이지(위쪽 화살표)로 이동하는 단추 외에도 현재 페이지 번호와 총 페이지 수 표시기도 포함되어 있습니다. 키보드 화살표 키를 사용하여 페이지 넘기기도 수행할 수 있습니다.  
  
-   확대/축소: 확대/축소 컨트롤을 사용하면 더하기 또는 빼기 단추를 클릭하여 각각 확대/축소 수준을 늘리거나 줄일 수 있습니다. 확대/축소 컨트롤에는 확대/축소 수준을 조정하는 슬라이더도 포함되어 있습니다. 자세한 내용은 <xref:System.Windows.Controls.FlowDocumentReader.Zoom%2A>을 참조하십시오.  
  
 이러한 기능은 유동 콘텐츠를 호스트하는 데 사용되는 컨트롤을 통해 수정할 수 있습니다. 다음 섹션에서는 여러 다른 컨트롤에 대해 설명합니다.  
  
<a name="flow_document_types"></a>   
## <a name="flow-document-types"></a>유동 문서 형식  
 유동 문서 콘텐츠 표시 및 표시 방법은 유동 콘텐츠를 호스트하는 데 사용되는 개체에 따라 달라집니다. 유동 콘텐츠 보기를 지 원하는 컨트롤을 4 개의: <xref:System.Windows.Controls.FlowDocumentReader>, <xref:System.Windows.Controls.FlowDocumentPageViewer>, <xref:System.Windows.Controls.RichTextBox>, 및 <xref:System.Windows.Controls.FlowDocumentScrollViewer>합니다. 이러한 컨트롤은 아래에서 간략하게 설명합니다.  
  
 **참고:** <xref:System.Windows.Documents.FlowDocument> 되므로 이러한 컨트롤 보기의 모든 직접 호스트 유동 콘텐츠를 해야 하는 한 <xref:System.Windows.Documents.FlowDocument> 흐름 콘텐츠 호스트할 수 있도록 합니다.  
  
### <a name="flowdocumentreader"></a>FlowDocumentReader  
 <xref:System.Windows.Controls.FlowDocumentReader>사용자가 동적으로 단일 페이지 (페이지-에-) 보기 모드를 한 번에 두 페이지 (책 읽기 형식) 보기 모드 및 연속 스크롤 (바닥 없음) 보기 모드를 포함 하 여 다양 한 보기 모드 사이 선택할 수 있는 기능이 포함 되어 있습니다. 이러한 보기 모드에 대 한 자세한 내용은 참조 하십시오. <xref:System.Windows.Controls.FlowDocumentReaderViewingMode>합니다. 동적으로 다른 보기 모드 사이 전환 하는 기능이 필요 하지 않은 경우 <xref:System.Windows.Controls.FlowDocumentPageViewer> 및 <xref:System.Windows.Controls.FlowDocumentScrollViewer> 간단한 유동 특정 보기 모드에서 수정 된 콘텐츠 뷰어를 제공 합니다.  
  
### <a name="flowdocumentpageviewer-and-flowdocumentscrollviewer"></a>FlowDocumentPageViewer 및 FlowDocumentScrollViewer  
 <xref:System.Windows.Controls.FlowDocumentPageViewer>콘텐츠 페이지 런타임을 표시 하는 동안 보기 모드로 <xref:System.Windows.Controls.FlowDocumentScrollViewer> 콘텐츠 연속 스크롤 모드를 표시 합니다. 둘 다 <xref:System.Windows.Controls.FlowDocumentPageViewer> 및 <xref:System.Windows.Controls.FlowDocumentScrollViewer> 특정 보기 모드에 고정 됩니다. 비교할 <xref:System.Windows.Controls.FlowDocumentReader>, 사용자 동적으로 다양 한 보기 모드 중에서 선택할 수 있는 기능이 포함 되어 (에서 제공 됨는 <xref:System.Windows.Controls.FlowDocumentReaderViewingMode> 열거형), 더 많은 리소스를 보다 많이 사용 되 고 커밋되지만 <xref:System.Windows.Controls.FlowDocumentPageViewer> 또는 <xref:System.Windows.Controls.FlowDocumentScrollViewer>합니다.  
  
 기본적으로 세로 스크롤 막대는 항상 표시되며 가로 스크롤 막대는 필요한 경우 표시됩니다. 기본값에 대 한 UI <xref:System.Windows.Controls.FlowDocumentScrollViewer> 도구 모음을 포함 하지 않습니다; 그러나는 <xref:System.Windows.Controls.FlowDocumentScrollViewer.IsToolBarVisible%2A> 기본 제공 도구 모음을 사용 하도록 설정 하려면 속성을 사용할 수 있습니다.  
  
### <a name="richtextbox"></a>RichTextBox  
 사용 된 <xref:System.Windows.Controls.RichTextBox> 사용자 유동 콘텐츠를 편집할 수 있도록 하려는 경우. 예를 들어을 조작할 수 있는 편집기를 만들려는 경우 사물 표, 기울임꼴 등 및 굵게 서식 등과, 사용 된 <xref:System.Windows.Controls.RichTextBox>합니다. 참조 [RichTextBox 개요](../../../../docs/framework/wpf/controls/richtextbox-overview.md) 자세한 정보에 대 한 합니다.  
  
 **참고:** 내의 유동 콘텐츠는 <xref:System.Windows.Controls.RichTextBox> 유동 콘텐츠를 다른 컨트롤에 포함 된 경우와 동일 하 게 작동 하지 않습니다. 예를 들어 열이 없는에 <xref:System.Windows.Controls.RichTextBox> 따라서 아니요 자동 크기 조정 동작 하 고 있습니다. 일반적으로 기본 제공된 기능을 검색, 모드, 페이지 탐색 및 확대/축소 보기와 같은 유동 콘텐츠 내에서 사용할 수 없는 또한는 <xref:System.Windows.Controls.RichTextBox>합니다.  
  
<a name="creating_flow_content"></a>   
## <a name="creating-flow-content"></a>유동 콘텐츠 만들기  
 유동 콘텐츠는 텍스트, 이미지, 테이블을 포함 하 여 다양 한 요소로 구성 된 복잡 하 고도 될 수 있습니다 <xref:System.Windows.UIElement> 컨트롤 같은 클래스를 파생 합니다. 복합 유동 콘텐츠를 만드는 방법을 파악하려면 다음 사항의 중요합니다.  
  
-   **유동 관련 클래스**: 유동 콘텐츠에서 사용된 각 클래스에는 특정 용도가 있습니다. 또한 유동 클래스 사이의 계층 구조 관계를 파악하면 클래스 사용 방식을 이해할 수 있습니다. 예를 들어에서 파생 된 클래스는 <xref:System.Windows.Documents.Block> 클래스는 클래스에서 파생 되는 동안 다른 개체를 포함 하는 데 사용 됩니다 <xref:System.Windows.Documents.Inline> 표시 되는 개체를 포함 합니다.  
  
-   **콘텐츠 스키마**: 유동 문서에는 상당한 수의 중첩 요소가 필요할 수 있습니다. 콘텐츠 스키마는 요소 간 가능한 부모/자식 관계를 지정합니다.  
  
 다음 섹션에서는 이러한 각 영역에 대해 자세히 살펴봅니다.  
  
<a name="flow_related_classes"></a>   
## <a name="flow-related-classes"></a>유동 관련 클래스  
 아래 다이어그램에서는 유동 콘텐츠와 가장 일반적으로 사용되는 개체를 보여줍니다.  
  
 ![다이어그램: 유동 콘텐츠 요소 클래스 계층 구조](../../../../docs/framework/wpf/advanced/media/flow-class-hierarchy.png "Flow_Class_Hierarchy")  
  
 유동 콘텐츠에 사용되는 중요한 범주는 다음 두 가지가 있습니다.  
  
1.  **블록 파생 클래스**: “블록 콘텐츠 요소” 또는 “블록 요소”라고도 합니다. 상속 되는 요소 <xref:System.Windows.Documents.Block> 공통 부모에서 요소를 그룹화 하거나 그룹에 공통 특성을 적용 하려면 사용할 수 있습니다.  
  
2.  **인라인 파생 클래스**: “인라인 콘텐츠 요소” 또는 “인라인 요소”라고도 합니다. 상속 되는 요소 <xref:System.Windows.Documents.Inline> 블록 요소 또는 다른 인라인 요소에 포함 됩니다. 인라인 요소는 종종 화면에 렌더링되는 콘텐츠의 직접 컨테이너로 사용됩니다. 예를 들어 한 <xref:System.Windows.Documents.Paragraph> (블록 요소)를 포함할 수는 <xref:System.Windows.Documents.Run> (인라인 요소) 이지만 <xref:System.Windows.Documents.Run> 실제로 화면에 렌더링 되는 텍스트를 포함 합니다.  
  
 이러한 두 범주의 각 클래스는 아래 간략하게 설명되어 있습니다.  
  
### <a name="block-derived-classes"></a>블록 파생 클래스  
 **단락**  
  
 <xref:System.Windows.Documents.Paragraph>대개 사용 그룹 콘텐츠를 단락으로 합니다. 가장 간단하고 가장 일반적으로 단락을 이용하는 경우는 텍스트 단락을 만드는 것입니다.  
  
 [!code-xaml[FlowOvwSnippets_snip#ParagraphExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/ParagraphExample.xaml#paragraphexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#ParagraphCodeOnlyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/ParagraphExample.cs#paragraphcodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#ParagraphCodeOnlyExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/ParagraphExample.vb#paragraphcodeonlyexamplewholepage)]  
  
 그러나 아래에 나온 것 처럼 다른 인라인 파생 된 요소를 포함할 수도 있습니다. 
  
 **섹션**  
  
 <xref:System.Windows.Documents.Section>다른 포함 하기 위해서만 사용 되는 <xref:System.Windows.Documents.Block>-요소를 파생 합니다. 포함된 요소에 기본 서식 지정을 적용하지 않습니다. 그러나 모든 속성 값 집합에는 <xref:System.Windows.Documents.Section> 해당 자식 요소에 적용 됩니다. 또한 섹션을 사용하면 프로그래밍 방식으로 자식 컬렉션을 반복할 수 있습니다. <xref:System.Windows.Documents.Section>에 비슷한 방법으로 사용 되는 \<DIV > html에서 태그입니다.  
  
 아래 예제에서는 세 개의 단락 하나에 정의 된 <xref:System.Windows.Documents.Section>합니다. 섹션에 있는 한 <xref:System.Windows.Documents.TextElement.Background%2A> 속성 값이 빨간색으로 단락의 배경색에 따라서 빨간색 이기도 합니다.  
  
 [!code-xaml[FlowOvwSnippets_snip#SectionExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SectionExample.xaml#sectionexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#SectionCodeOnlyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/SectionExample.cs#sectioncodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#SectionCodeOnlyExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/SectionExample.vb#sectioncodeonlyexamplewholepage)]  
  
 **BlockUIContainer**  
  
 <xref:System.Windows.Documents.BlockUIContainer>수 있도록 <xref:System.Windows.UIElement> 요소 (즉, 한 <xref:System.Windows.Controls.Button>) 블록 파생 유동 콘텐츠 내에 포함 될 수 있습니다. <xref:System.Windows.Documents.InlineUIContainer>(아래 참조)는 포함 하는 데 사용 되 <xref:System.Windows.UIElement> 인라인 파생 유동 콘텐츠 요소입니다. <xref:System.Windows.Documents.BlockUIContainer>및 <xref:System.Windows.Documents.InlineUIContainer> 은 사용 하는 다른 방법이 없기 때문에 중요 한 <xref:System.Windows.UIElement> 이러한 두 요소 중 어느 하나에 포함 되지 않은 콘텐츠 흐름에서.  
  
 사용 하는 방법을 보여 주는 다음 예제는 <xref:System.Windows.Documents.BlockUIContainer> 요소 호스트를 <xref:System.Windows.UIElement> 유동 콘텐츠 내에서 개체입니다.  
  
 [!code-xaml[SpanSnippets#_BlockUIXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml#_blockuixaml)]  
  
 다음 그림은 이 예제에서 렌더링하는 방법을 보여줍니다.  
  
 ![스크린 샷: 유동 콘텐츠에 포함된 UIElement](../../../../docs/framework/wpf/advanced/media/blockuicontainer.png "BlockUIContainer")  
  
 **목록**  
  
 <xref:System.Windows.Documents.List>글머리 기호 또는 숫자 목록을 만드는 데 사용 됩니다. 설정의 <xref:System.Windows.Documents.List.MarkerStyle%2A> 속성을는 <xref:System.Windows.TextMarkerStyle> 열거형 값의 목록 스타일을 결정 합니다. 아래 예에서는 간단한 목록을 만드는 방법을 보여줍니다.  
  
 [!code-xaml[FlowOvwSnippets_snip#ListExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/ListExample.xaml#listexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#ListCodeOnlyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/ListExample.cs#listcodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#ListCodeOnlyExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/ListExample.vb#listcodeonlyexamplewholepage)]  
  
 **참고:** <xref:System.Windows.Documents.List> 는 사용 하는 유일한 흐름 요소는 <xref:System.Windows.Documents.ListItemCollection> 자식 요소를 관리 하도록 합니다.  
  
 **Table**  
  
 <xref:System.Windows.Documents.Table>테이블을 만드는 데 사용 됩니다. <xref:System.Windows.Documents.Table>비슷합니다는 <xref:System.Windows.Controls.Grid> 요소 하지만 더 많은 기능이 있으며, 따라서 큰 리소스 오버 헤드가 필요 합니다. 때문에 <xref:System.Windows.Controls.Grid> 는 <xref:System.Windows.UIElement>에 포함 되지 않은 유동 콘텐츠를 사용할 수 없습니다는 <xref:System.Windows.Documents.BlockUIContainer> 또는 <xref:System.Windows.Documents.InlineUIContainer>합니다. 대 한 자세한 내용은 <xref:System.Windows.Documents.Table>, 참조 [테이블 개요](../../../../docs/framework/wpf/advanced/table-overview.md)합니다.  
  
### <a name="inline-derived-classes"></a>인라인 파생 클래스  
 **실행**  
  
 <xref:System.Windows.Documents.Run>서식 없는 텍스트를 포함 하는 데 사용 됩니다. 예상 대로 <xref:System.Windows.Documents.Run> 유동 콘텐츠 개체를에서 광범위 하 게 사용할 수 있습니다. 그러나 태그에서에서 <xref:System.Windows.Documents.Run> 요소가 명시적으로 사용 하는 데 필요 합니다. <xref:System.Windows.Documents.Run>코드를 사용 하 여 유동 문서를 조작 하거나 만들 때 사용 해야 합니다. 예를 들어, 첫 번째 항목 아래 태그에서에서 <xref:System.Windows.Documents.Paragraph> 지정는 <xref:System.Windows.Documents.Run> 되지만 명시적으로 두 번째 요소는 그렇지 않습니다. 두 단락 모두 동일한 출력을 생성합니다.  
  
 [!code-xaml[FlowOvwSnippets_snip#RunExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/RunSnippetsExample.xaml#runexample1)]  
  
 **참고:** 부터 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)], <xref:System.Windows.Documents.Run.Text%2A> 의 속성은 <xref:System.Windows.Documents.Run> 개체 속성은 종속성 속성입니다. 바인딩할 수 있습니다는 <xref:System.Windows.Documents.Run.Text%2A> 같은 속성에 대 한 데이터 소스는 <xref:System.Windows.Controls.TextBlock>합니다. <xref:System.Windows.Documents.Run.Text%2A> 속성이 단방향 바인딩을 완벽 하 게 지원 합니다. <xref:System.Windows.Documents.Run.Text%2A> 속성을 제외 하 고 양방향 바인딩도 지원 <xref:System.Windows.Controls.RichTextBox>합니다. 예제를 보려면 <xref:System.Windows.Documents.Run.Text%2A?displayProperty=nameWithType>를 참조하십시오.  
  
 **Span**  
  
 <xref:System.Windows.Documents.Span>다른 인라인 콘텐츠 요소를 그룹화합니다. 고유 없습니다 렌더링이 내 콘텐츠의 적용 되는 <xref:System.Windows.Documents.Span> 요소입니다. 그러나 요소에서 상속 되는 <xref:System.Windows.Documents.Span> 포함 하 여 <xref:System.Windows.Documents.Hyperlink>, <xref:System.Windows.Documents.Bold>, <xref:System.Windows.Documents.Italic> 및 <xref:System.Windows.Documents.Underline> 텍스트에 서식을 적용지 않습니다.  
  
 다음은의 예는 <xref:System.Windows.Documents.Span> 텍스트를 포함 하 여 인라인 콘텐츠를 포함 하는 데 사용 되는 <xref:System.Windows.Documents.Bold> 요소 및 <xref:System.Windows.Controls.Button>합니다.  
  
 [!code-xaml[FlowOvwSnippets_snip#SpanExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SpanExample.xaml#spanexamplewholepage)]  
  
 다음 스크린샷은 이 예제에서 렌더링하는 방법을 보여줍니다.  
  
 ![스크린 샷: 렌더링된 Span 예제](../../../../docs/framework/wpf/advanced/media/flow-spanexample.gif "Flow_SpanExample")  
  
 **InlineUIContainer**  
  
 <xref:System.Windows.Documents.InlineUIContainer>수 있도록 <xref:System.Windows.UIElement> 요소 (예:과 같은 컨트롤 <xref:System.Windows.Controls.Button>)에 포함할는 <xref:System.Windows.Documents.Inline> 콘텐츠 요소입니다. 이 요소는 해당 하는 인라인 <xref:System.Windows.Documents.BlockUIContainer> 위에서 설명한 합니다. 다음은 사용 하는 예제 <xref:System.Windows.Documents.InlineUIContainer> 삽입 하는 <xref:System.Windows.Controls.Button> 에서 인라인으로 <xref:System.Windows.Documents.Paragraph>합니다.  
  
 [!code-xaml[FlowOvwSnippets_snip#InlineUIContainerExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/InlineUIContainerExample.xaml#inlineuicontainerexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#InlineUIContainerCodeOnlyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/InlineUIContainerExample.cs#inlineuicontainercodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#InlineUIContainerCodeOnlyExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/InlineUIContainerExample.vb#inlineuicontainercodeonlyexamplewholepage)]  
  
 **참고:** <xref:System.Windows.Documents.InlineUIContainer> 태그에서 명시적으로 사용할 필요가 없습니다. 생략 하면는 <xref:System.Windows.Documents.InlineUIContainer> 코드를 컴파일할 때 계속 만들 수 있습니다.  
  
 **Figure 및 Floater**  
  
 <xref:System.Windows.Documents.Figure>및 <xref:System.Windows.Documents.Floater> 독립적 주 콘텐츠 흐름으로 지정할 수 있는 배치 속성을 가진 흐름 문서에 콘텐츠를 포함 하는 데 사용 됩니다. <xref:System.Windows.Documents.Figure>또는 <xref:System.Windows.Documents.Floater> 를 삽입할 느슨하게 관련 광고 등의 콘텐츠 또는 요소를 강조 표시 하거나 콘텐츠, 이미지 또는 기타 콘텐츠, 기본 콘텐츠 흐름 내에서 지 원하는 호스트에 일부를 주로 사용 됩니다.  
  
 다음 예제에서는 포함 하는 방법을 보여 줍니다.는 <xref:System.Windows.Documents.Figure> 텍스트를 단락으로 합니다.  
  
 [!code-xaml[FlowOvwSnippets_snip#FigureExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/FigureExample.xaml#figureexamplewholepage)]  
  
 [!code-csharp[FlowOvwSnippets_procedural_snip#FigureCodeOnlyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/CSharp/FigureExample.cs#figurecodeonlyexamplewholepage)]
 [!code-vb[FlowOvwSnippets_procedural_snip#FigureCodeOnlyExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowOvwSnippets_procedural_snip/VisualBasic/FigureExample.vb#figurecodeonlyexamplewholepage)]  
  
 다음 그림은 이 예제에서 렌더링하는 방법을 보여줍니다.  
  
 ![스크린샷: Figure 예](../../../../docs/framework/wpf/advanced/media/flow-ovw-figure-example.png "Flow_Ovw_Figure_Example")  
  
 <xref:System.Windows.Documents.Figure>및 <xref:System.Windows.Documents.Floater> 다른 점이 몇 가지 및 다양 한 시나리오에 사용 됩니다.  
  
 **Figure:**  
  
-   배치 가능: 페이지, 콘텐츠, 열 또는 단락을 기준으로 고정하도록 가로 및 세로 앵커를 설정할 수 있습니다. 사용할 수도 있습니다는 <xref:System.Windows.Documents.Figure.HorizontalOffset%2A> 및 <xref:System.Windows.Documents.Figure.VerticalOffset%2A> 임의의 오프셋을 지정 하는 속성입니다.  
  
-   둘 이상의 열을 조정할: 설정할 수 있습니다 <xref:System.Windows.Documents.Figure> 높이 너비 페이지, 콘텐츠 또는 열 높이 또는 너비의 배수로 합니다. 페이지와 콘텐츠의 경우 1보다 큰 배수는 허용되지 않습니다. 예를 들어의 너비를 설정할 수 있습니다는 <xref:System.Windows.Documents.Figure> "0.5 페이지" 또는 "0.25 콘텐츠" 또는 "열의 2"입니다. 높이와 너비를 절대 픽셀 값으로 설정할 수도 있습니다.  
  
-   페이지: 경우 내에서 콘텐츠는 <xref:System.Windows.Documents.Figure> 맞지 않으면는 <xref:System.Windows.Documents.Figure>, 않습니다 렌더링 하 고 나머지 콘텐츠 손실 됩니다.  
  
 **Floater:**  
  
-   배치할 수 없으며 공간이 사용 가능하게 되면 렌더링됩니다. 오프셋 또는 앵커를 설정할 수 없습니다는 <xref:System.Windows.Documents.Floater>합니다.  
  
-   둘 이상의 열을 조정할 수 없습니다: 기본적으로 <xref:System.Windows.Documents.Floater> 크기입니다. 에 <xref:System.Windows.Documents.Floater.Width%2A> 하나 이상의 열을 하나 이상의 열 너비는 무시 됩니다 및 floater 보다 큰 경우이 값은 있지만 절대 픽셀 값으로 설정할 수 있는 속성의 크기는 합니다. 올바른 픽셀 너비를 설정 하 여 크기를 1 개 미만의 열 수 있지만 크기 조정 하지 않으므로 열을 기준 "0.5Column"에 올바른 식이 아닙니다. <xref:System.Windows.Documents.Floater> 너비입니다. <xref:System.Windows.Documents.Floater>높이 속성이 있고 그것이 높이 설정할 수 없습니다, 높이 내용에 따라 다릅니다.  
  
-   <xref:System.Windows.Documents.Floater>페이지를 매깁니다: 두 개 이상의 열 높이를 확장 하는 내용을 지정 된 너비에 floater 중단 하 고 다음 열이 고, 다음 페이지, 등의 페이지를 매깁니다.  
  
 <xref:System.Windows.Documents.Figure>크기를 제어 하려면 독립 실행형 콘텐츠를 저장 하는 좋은 장소가 위치 지정 및 지정된 된 크기에 콘텐츠를 표시할 수 있는지 확인 합니다. <xref:System.Windows.Documents.Floater>기본 페이지 콘텐츠를 비슷하게 진행 하지만 것에서 분리 되어 더 많은-흐름이 흥미롭게 좋은 위치가입니다.  
  
 **LineBreak**  
  
 <xref:System.Windows.Documents.LineBreak>줄 바꿈을 유동 콘텐츠 내에 발생 하도록 하면 됩니다. 다음 예에서는 <xref:System.Windows.Documents.LineBreak>의 사용법을 보여줍니다.  
  
 [!code-xaml[FlowOvwSnippets_snip#LineBreakExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/LineBreakExample.xaml#linebreakexamplewholepage)]  
  
 다음 스크린샷은 이 예제에서 렌더링하는 방법을 보여줍니다.  
  
 ![스크린샷: LineBreak 예제](../../../../docs/framework/wpf/advanced/media/flow-ovw-linebreakexample.png "Flow_Ovw_LineBreakExample")  
  
### <a name="flow-collection-elements"></a>유동 컬렉션 요소  
 많은 위의 예제에는 <xref:System.Windows.Documents.BlockCollection> 및 <xref:System.Windows.Documents.InlineCollection> 유동 콘텐츠를 프로그래밍 방식으로 구성 하는 데 사용 됩니다. 예를 들어, 요소를 추가 하는 <xref:System.Windows.Documents.Paragraph>, 구문을 사용할 수 있습니다.  
  
 `…`  
  
 `myParagraph.Inlines.Add(new Run("Some text"));`  
  
 `…`  
  
 이렇게 하면 추가 <xref:System.Windows.Documents.Run> 에 <xref:System.Windows.Documents.InlineCollection> 의 <xref:System.Windows.Documents.Paragraph>합니다.  이 암시적와 동일 하 게 <xref:System.Windows.Documents.Run> 내에서 발견 한 <xref:System.Windows.Documents.Paragraph> 태그에서:  
  
 `…`  
  
 `<Paragraph>`  
  
 `Some Text`  
  
 `</Paragraph>`  
  
 `…`  
  
 사용 하 여의 예로 <xref:System.Windows.Documents.BlockCollection>, 다음 예제에서는 새 <xref:System.Windows.Documents.Section> 다음 사용 하 여는 **추가** 새 메서드 <xref:System.Windows.Documents.Paragraph> 에 <xref:System.Windows.Documents.Section> 내용을 합니다.  
  
 [!code-csharp[FlowDocumentSnippets#_SectionBlocksAdd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentSnippets/CSharp/Window1.xaml.cs#_sectionblocksadd)]
 [!code-vb[FlowDocumentSnippets#_SectionBlocksAdd](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentSnippets/visualbasic/window1.xaml.vb#_sectionblocksadd)]  
  
 유동 컬렉션에 항목을 추가할 수 있을 뿐만 아니라 항목을 제거할 수도 있습니다.  다음 예에서는 삭제 마지막 <xref:System.Windows.Documents.Inline> 요소에는 <xref:System.Windows.Documents.Span>합니다.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesRemoveLast](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesremovelast)]
 [!code-vb[SpanSnippets#_SpanInlinesRemoveLast](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesremovelast)]  
  
 다음 예제에서는 모든 내용을 지웁니다 (<xref:System.Windows.Documents.Inline> 요소)에서 고 <xref:System.Windows.Documents.Span>합니다.  
  
 [!code-csharp[SpanSnippets#_SpanInlinesClear](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SpanSnippets/CSharp/Window1.xaml.cs#_spaninlinesclear)]
 [!code-vb[SpanSnippets#_SpanInlinesClear](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SpanSnippets/visualbasic/window1.xaml.vb#_spaninlinesclear)]  
  
 프로그래밍 방식으로 유동 콘텐츠에 대해 작업할 때 이러한 컬렉션을 광범위하게 사용할 가능성이 큽니다.  
  
 흐름 요소를 사용 하는지 여부는 <xref:System.Windows.Documents.InlineCollection> (인라인) 또는 <xref:System.Windows.Documents.BlockCollection> (블록) 해당 자식 포함 하도록 요소 어떤 유형의 자식 요소에 따라 달라 집니다 (<xref:System.Windows.Documents.Block> 또는 <xref:System.Windows.Documents.Inline>) 부모 포함 될 수 있습니다. 유동 콘텐츠 요소의 포함 규칙은 다음 섹션의 콘텐츠 스키마에 요약되어 있습니다.  
  
 **참고:** 유동 콘텐츠를 함께 사용 하는 컬렉션의 세 번째 형식인는 <xref:System.Windows.Documents.ListItemCollection>,이 컬렉션은에 사용 하지만 <xref:System.Windows.Documents.List>합니다. 또한, 함께 사용 하는 몇 개의 컬렉션이 많습니다. <xref:System.Windows.Documents.Table>합니다. 참조 [테이블 개요](../../../../docs/framework/wpf/advanced/table-overview.md) 자세한 정보에 대 한 합니다.  
  
<a name="content_schema"></a>   
## <a name="content-schema"></a>콘텐츠 스키마  
 여러 다른 수의 플로우 콘텐츠 요소가 있으므로, 요소에 포함될 수 있는 자식 요소의 유형을 계속 추적하는 것은 어려울 수 있습니다. 아래 다이어그램에는 유동 요소의 포함 규칙이 요약되어 있습니다. 화살표는 가능한 부모/자식 관계를 나타냅니다.  
  
 ![다이어그램: 유동 콘텐츠 포함 스키마](../../../../docs/framework/wpf/advanced/media/flow-content-schema.png "Flow_Content_Schema")  
  
 위의 다이어그램에서 볼 수 있듯이 요소에 대해 허용 되는 자식이 결정 되지 않습니다 반드시 되었는지 여부에 <xref:System.Windows.Documents.Block> 요소 또는 <xref:System.Windows.Documents.Inline> 요소입니다. 예를 들어는 <xref:System.Windows.Documents.Span> (한 <xref:System.Windows.Documents.Inline> 요소) 하나만 사용할 수 있습니다 <xref:System.Windows.Documents.Inline> 동안 자식 요소는 <xref:System.Windows.Documents.Figure> (도 <xref:System.Windows.Documents.Inline> 요소) 하나만 사용할 수 있습니다 <xref:System.Windows.Documents.Block> 자식 요소입니다. 그러므로 이 다이어그램은 다른 요소에 포함될 수 있는 요소를 신속하게 판별하는 데 유용합니다. 예를 들어 다이어그램을 사용해 보겠습니다의 유동 콘텐츠를 생성 하는 방법을 결정 하는 <xref:System.Windows.Controls.RichTextBox>합니다.  
  
 **1.** A <xref:System.Windows.Controls.RichTextBox> 포함 해야 합니다는 <xref:System.Windows.Documents.FlowDocument> 를 포함 해야는 <xref:System.Windows.Documents.Block>-파생 된 개체입니다. 위의 다이어그램에 해당되는 세그먼트는 다음과 같습니다.  
  
 ![다이어그램: RichTextBox 포함 규칙](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough1.png "Flow_Ovw_SchemaWalkThrough1")  
  
 따라서 지금까지 태그는 다음과 같을 수 있습니다.  
  
 [!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough1)]  
  
 **2.** 다이어그램에 따라 몇 가지 <xref:System.Windows.Documents.Block> 비롯 하 여 선택할 요소 <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Documents.Section>, <xref:System.Windows.Documents.Table>, <xref:System.Windows.Documents.List>, 및 <xref:System.Windows.Documents.BlockUIContainer> (위의 블록에서 파생 된 클래스 참조). 원하는 경우를 가정해는 <xref:System.Windows.Documents.Table>합니다. 위의 다이어그램에 따라는 <xref:System.Windows.Documents.Table> 포함는 <xref:System.Windows.Documents.TableRowGroup> 포함 된 <xref:System.Windows.Documents.TableRow> 요소를 포함 하는 <xref:System.Windows.Documents.TableCell> 포함 하는 요소는 <xref:System.Windows.Documents.Block>-파생 된 개체입니다. 다음은 해당 하는 세그먼트에 대 한 <xref:System.Windows.Documents.Table> 위의 다이어그램에서 가져옵니다.  
  
 ![다이어그램: 테이블의 부모&#47;자식 스키마](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough2.png "Flow_Ovw_SchemaWalkThrough2")  
  
 다음은 해당 태그입니다.  
  
 [!code-xaml[FlowOvwSnippets_snip#SchemaWalkThrough2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/MiscSnippets.xaml#schemawalkthrough2)]  
  
 **3.** 마찬가지로 하나 이상의 <xref:System.Windows.Documents.Block> 아래 필요한 요소는 <xref:System.Windows.Documents.TableCell>합니다. 간단하게 셀 안에 텍스트를 배치해 보겠습니다. 사용 하 여 수행할 수 있습니다는 <xref:System.Windows.Documents.Paragraph> 와 <xref:System.Windows.Documents.Run> 요소입니다. 다음의 해당 세그먼트를 보여 주는 다이어그램은 <xref:System.Windows.Documents.Paragraph> 걸릴 수 있습니다는 <xref:System.Windows.Documents.Inline> 요소를 한 <xref:System.Windows.Documents.Run> (한 <xref:System.Windows.Documents.Inline> 요소) 일반 텍스트만 사용할 수 있습니다.  
  
 ![다이어그램: 단락의 부모&#47;자식 스키마](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough3.png "Flow_Ovw_SchemaWalkThrough3")  
  
 ![다이어그램: 실행을 위한 부모&#47;자식 스키마](../../../../docs/framework/wpf/advanced/media/flow-ovw-schemawalkthrough4.png "Flow_Ovw_SchemaWalkThrough4")  
  
 다음은 태그의 전체 예제입니다.  
  
 [!code-xaml[FlowOvwSnippets_snip#SchemaExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowOvwSnippets_snip/CS/SchemaExample.xaml#schemaexamplewholepage)]  
  
<a name="customizing_text"></a>   
## <a name="customizing-text"></a>텍스트 사용자 지정  
 일반적으로 텍스트는 유동 문서에서 가장 많이 사용되는 콘텐츠 형식입니다. 위에 소개된 개체는 텍스트 렌더링 방식에 관한 대부분의 요소를 제어하는 데 사용할 수 있지만, 이 섹션에서 다루는 텍스트 사용자 지정에 사용하는 메서드는 다릅니다.  
  
### <a name="text-decorations"></a>텍스트 장식  
 텍스트 장식을 사용하면 텍스트에 밑줄, 윗줄, 기준선 및 취소선 효과를 적용할 수 있습니다(아래 그림 참조). 이러한 장식을 사용 하 여 추가 된 <xref:System.Windows.Documents.Inline.TextDecorations%2A> 포함 개체의 숫자에 의해 노출 되는 속성 <xref:System.Windows.Documents.Inline>, <xref:System.Windows.Documents.Paragraph>, <xref:System.Windows.Controls.TextBlock>, 및 <xref:System.Windows.Controls.TextBox>합니다.  
  
 다음 예제에서는 <xref:System.Windows.Documents.Paragraph.TextDecorations%2A>의 <xref:System.Windows.Documents.Paragraph> 속성을 설정하는 방법을 보여 줍니다.  
  
 [!code-xaml[InlineSnippets#_Paragraph_TextDecXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InlineSnippets/CSharp/Window1.xaml#_paragraph_textdecxaml)]  
  
 [!code-csharp[InlineSnippets#_Paragraph_TextDec](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InlineSnippets/CSharp/Window1.xaml.cs#_paragraph_textdec)]
 [!code-vb[InlineSnippets#_Paragraph_TextDec](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InlineSnippets/visualbasic/window1.xaml.vb#_paragraph_textdec)]  
  
 다음 그림은 이 예제에서 렌더링하는 방법을 보여줍니다.  
  
 ![스크린 샷: 기본 취소선 효과가 적용된 텍스트](../../../../docs/framework/wpf/advanced/media/inline-textdec-strike.png "Inline_TextDec_Strike")  
  
 다음 그림 표시 방법을 **윗줄**, **초기**, 및 **밑줄** 장식이 각각 렌더링 합니다.  
  
 ![스크린 샷: 윗줄 TextDecorator](../../../../docs/framework/wpf/advanced/media/inline-textdec-over.png "Inline_TextDec_Over")  
  
 ![스크린 샷: 텍스트의 기본 기준선 효과](../../../../docs/framework/wpf/advanced/media/inline-textdec-base.png "Inline_TextDec_Base")  
  
 ![스크린 샷: 밑줄 효과가 적용된 텍스트](../../../../docs/framework/wpf/advanced/media/inline-textdec-under.png "Inline_TextDec_Under")  
  
### <a name="typography"></a>입력 체계  
 <xref:System.Windows.Documents.TextElement.Typography%2A> 대부분 흐름 관련 콘텐츠를 포함 하 여 속성을 노출 <xref:System.Windows.Documents.TextElement>, <xref:System.Windows.Documents.FlowDocument>, <xref:System.Windows.Controls.TextBlock>, 및 <xref:System.Windows.Controls.TextBox>합니다. 이 속성은 텍스트의 입력 체계 특성/변형(즉, 소문자 및 대문자, 위 첨자 및 아래 첨자 작성 등)을 제어하는 데 사용합니다.  
  
 설정 하는 방법을 보여 주는 다음 예제는 <xref:System.Windows.Documents.TextElement.Typography%2A> 특성을 사용 하 여 <xref:System.Windows.Documents.Paragraph> 예제 요소로 합니다.  
  
 [!code-xaml[TextElementSnippets#_TextElement_TypogXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml#_textelement_typogxaml)]  
  
 다음 그림은 이 예제에서 렌더링하는 방법을 보여줍니다.  
  
 ![스크린 샷: 입력 체계가 변경된 텍스트](../../../../docs/framework/wpf/advanced/media/textelement-typog.png "TextElement_Typog")  
  
 반면 다음 그림은 기본 입력 체계 속성이 있는 비슷한 예제가 렌더링되는 방식을 보여줍니다.  
  
 ![스크린 샷: 입력 체계가 변경된 텍스트](../../../../docs/framework/wpf/advanced/media/textelement-typog-default.png "TextElement_Typog_Default")  
  
 설정 하는 방법을 보여 주는 다음 예제는 <xref:System.Windows.Controls.TextBox.Typography%2A> 속성 프로그래밍 방식으로 합니다.  
  
 [!code-csharp[TextElementSnippets#_TextElement_Typog](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextElementSnippets/CSharp/Window1.xaml.cs#_textelement_typog)]
 [!code-vb[TextElementSnippets#_TextElement_Typog](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextElementSnippets/visualbasic/window1.xaml.vb#_textelement_typog)]  
  
 참조 [wpf에서 입력 체계](../../../../docs/framework/wpf/advanced/typography-in-wpf.md) 입력 체계에 대 한 자세한 내용은 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [텍스트](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)  
 [WPF의 입력 체계](../../../../docs/framework/wpf/advanced/typography-in-wpf.md)  
 [방법 항목](../../../../docs/framework/wpf/advanced/flow-content-elements-how-to-topics.md)  
 [TextElement 콘텐츠 모델 개요](../../../../docs/framework/wpf/advanced/textelement-content-model-overview.md)  
 [RichTextBox 개요](../../../../docs/framework/wpf/controls/richtextbox-overview.md)  
 [WPF의 문서](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [테이블 개요](../../../../docs/framework/wpf/advanced/table-overview.md)  
 [주석 개요](../../../../docs/framework/wpf/advanced/annotations-overview.md)
