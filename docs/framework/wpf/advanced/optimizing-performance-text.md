---
title: "성능 최적화: 텍스트"
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
- rendering text [WPF]
- hyperlinks [WPF]
- formatted text [WPF]
- text [WPF], performance
- glyphs [WPF]
ms.assetid: 66b1b9a7-8618-48db-b616-c57ea4327b98
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f345893ca79d820ebb066d920cb49c6c46c47297
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="optimizing-performance-text"></a>성능 최적화: 텍스트
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 다양한 기능의 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 컨트롤을 사용하여 텍스트 콘텐츠를 표시할 수 있습니다. 일반적으로 세 가지 계층으로 텍스트 렌더링을 나눌 수 있습니다.  
  
1.  사용 하 여 <xref:System.Windows.Documents.Glyphs> 및 <xref:System.Windows.Media.GlyphRun> 개체를 직접 합니다.  
  
2.  사용 하 여 <xref:System.Windows.Media.FormattedText> 개체입니다.  
  
3.  와 같은 개략적인 컨트롤을 사용 하 여 <xref:System.Windows.Controls.TextBlock> 및 <xref:System.Windows.Documents.FlowDocument> 개체입니다.  
  
 이 항목에서는 텍스트 렌더링 성능 권장 사항을 제공합니다.  
  
  
<a name="Glyph_Level"></a>   
## <a name="rendering-text-at-the-glyph-level"></a>문자 모양 수준에서 텍스트 렌더링  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에 대 한 직접 액세스를 사용 하 여 문자 모양 수준의 태그를 포함 하 여 고급 텍스트 지원 <xref:System.Windows.Documents.Glyphs> 가로채 고 텍스트를 포맷 한 후 유지 하려는 고객에 대 한 합니다. 이러한 기능을 통해 다음과 같은 각 시나리오의 다양한 텍스트 렌더링 요구 사항을 충족시킬 수 있습니다.  
  
-   고정된 형식 문서의 화면 표시  
  
-   인쇄 시나리오  
  
    -   장치 프린터 언어로서의 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]  
  
    -   [!INCLUDE[TLA#tla_mxdw](../../../../includes/tlasharptla-mxdw-md.md)].  
  
    -   이전 프린터 드라이버, [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] 응용 프로그램에서 고정된 형식으로의 출력  
  
    -   인쇄 스풀 형식  
  
-   이전 버전의 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] 및 기타 컴퓨팅 장치에 대한 클라이언트를 포함하는 고정된 형식 문서 표시  
  
> [!NOTE]
>  <xref:System.Windows.Documents.Glyphs>및 <xref:System.Windows.Media.GlyphRun> 고정 형식의 문서 표시 및 인쇄 시나리오에 대 한 설계 합니다. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]일반 레이아웃에 대 한 여러 요소를 제공 하 고 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 시나리오와 같은 <xref:System.Windows.Controls.Label> 및 <xref:System.Windows.Controls.TextBlock>합니다. 레이아웃 및 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 시나리오에 대한 자세한 내용은 [WPF의 입력 체계](../../../../docs/framework/wpf/advanced/typography-in-wpf.md)를 참조하세요.  
  
 다음 예제에 대 한 속성을 정의 하는 방법을 보여 줍니다는 <xref:System.Windows.Documents.Glyphs> 개체 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]합니다. <xref:System.Windows.Documents.Glyphs> 개체의 출력을 나타냅니다는 <xref:System.Windows.Media.GlyphRun> 에서 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]합니다. 이 예제에서는 로컬 컴퓨터의 **C:\WINDOWS\Fonts** 폴더에 Arial, Courier New 및 Times New Roman 글꼴이 설치되어 있다고 가정합니다.  
  
 [!code-xaml[GlyphsOvwSample1#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSample1/CS/default.xaml#1)]  
  
### <a name="using-drawglyphrun"></a>DrawGlyphRun 사용  
 사용자 지정 컨트롤 및 문자 모양을 렌더링을 사용 하려는 경우는 <xref:System.Windows.Media.DrawingContext.DrawGlyphRun%2A> 메서드.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]또한 사용자 지정 텍스트를 사용 하 여 서식 지정에 대 한 하위 수준 서비스를 제공는 <xref:System.Windows.Media.FormattedText> 개체입니다. 텍스트를 렌더링 하는 가장 효율적인 방법은 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 사용 하 여 문자 모양 수준에서 텍스트 콘텐츠를 생성 하는 것 <xref:System.Windows.Documents.Glyphs> 및 <xref:System.Windows.Media.GlyphRun>합니다. 그러나 이러한 효율성 비용은 기본 제공 기능이 있는 사용 하기 쉬운 서식 있는 텍스트 서식 지정이 손실의 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 와 같은 컨트롤 <xref:System.Windows.Controls.TextBlock> 및 <xref:System.Windows.Documents.FlowDocument>합니다.  
  
<a name="FormattedText_Object"></a>   
## <a name="formattedtext-object"></a>FormattedText 개체  
 <xref:System.Windows.Media.FormattedText> 개체를 사용 하는 각 문자는 텍스트에 서식을 지정할 수 있는 개별적으로 여러 줄 텍스트를 그릴 수 있습니다. 자세한 내용은 [서식 있는 텍스트 그리기](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md)를 참조하세요.  
  
 서식 있는 텍스트를 만들려면 호출는 <xref:System.Windows.Media.FormattedText.%23ctor%2A> 를 만드는 생성자는 <xref:System.Windows.Media.FormattedText> 개체입니다. 첫 서식 있는 텍스트 문자열을 만든 다음 다양한 서식 지정 스타일을 적용할 수 있습니다. 응용 프로그램에서 자체 레이아웃을 구현 하려는 경우 하면 <xref:System.Windows.Media.FormattedText> 개체는 같은 컨트롤을 사용 하 여 보다 낫습니다 <xref:System.Windows.Controls.TextBlock>합니다. 대 한 자세한 내용은 <xref:System.Windows.Media.FormattedText> 개체, 참조 [그리기 형식의 텍스트](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md) 합니다.  
  
 <xref:System.Windows.Media.FormattedText> 개체 하위 수준 텍스트 서식 지정 기능을 제공 합니다. 하나 이상의 문자에 여러 서식 지정 스타일을 적용할 수 있습니다. 예를 들어 모두 호출할 수 있습니다는 <xref:System.Windows.Media.FormattedText.SetFontSize%2A> 및 <xref:System.Windows.Media.FormattedText.SetForegroundBrush%2A> 텍스트의 처음 5 개 문자 서식을 변경 하는 방법입니다.  
  
 다음 코드 예제에서는 한 <xref:System.Windows.Media.FormattedText> 개체를 렌더링 합니다.  
  
 [!code-csharp[formattedtextsnippets#FormattedTextSnippets1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FormattedTextSnippets/CSharp/Window1.xaml.cs#formattedtextsnippets1)]
 [!code-vb[formattedtextsnippets#FormattedTextSnippets1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FormattedTextSnippets/visualbasic/window1.xaml.vb#formattedtextsnippets1)]  
  
<a name="FlowDocument_TextBlock_Label"></a>   
## <a name="flowdocument-textblock-and-label-controls"></a>FlowDocument, TextBlock 및 Label 컨트롤  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 화면에 텍스트를 그리는 데 사용하는 여러 컨트롤이 포함되어 있습니다. 각 컨트롤은 다른 시나리오를 대상으로 하며 고유 기능 및 제한 사항 목록을 가지고 있습니다.  
  
### <a name="flowdocument-impacts-performance-more-than-textblock-or-label"></a>FlowDocument가 TextBlock 또는 Label 이외의 성능에 미치는 영향  
 일반적으로 <xref:System.Windows.Controls.TextBlock> 요소 제한 텍스트 지원에 대 한 간단한 문장을 같이 필요한 경우 사용 되어야 합니다는 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]합니다. <xref:System.Windows.Controls.Label>텍스트를 최소한 지원이 필요한 경우 사용할 수 있습니다. <xref:System.Windows.Documents.FlowDocument> 요소를 지 원하는 풍부한 콘텐츠를 표시 다시 flowable 문서에 대 한 컨테이너로 사용 되며 따라서 사용 하 여 보다 성능에 큰 영향을에 <xref:System.Windows.Controls.TextBlock> 또는 <xref:System.Windows.Controls.Label> 컨트롤입니다.  
  
 대 한 자세한 내용은 <xref:System.Windows.Documents.FlowDocument>, 참조 [문서 개요 흐름](../../../../docs/framework/wpf/advanced/flow-document-overview.md)합니다.  
  
### <a name="avoid-using-textblock-in-flowdocument"></a>FlowDocument에서 TextBlock 사용 안 함  
 <xref:System.Windows.Controls.TextBlock> 요소에서 파생 됩니다 <xref:System.Windows.UIElement>합니다. <xref:System.Windows.Documents.Run> 요소에서 파생 됩니다 <xref:System.Windows.Documents.TextElement>, 보다 사용 하는 데 비용이 적게 드는 되는 <xref:System.Windows.UIElement>-파생 된 개체입니다. 사용 가능한 경우 <xref:System.Windows.Documents.Run> 대신 <xref:System.Windows.Controls.TextBlock> 텍스트의 콘텐츠를 표시 하기 위한는 <xref:System.Windows.Documents.FlowDocument>합니다.  
  
 다음 태그 샘플 내에서 텍스트 콘텐츠를 설정 하는 두 가지 방법을 보여 줍니다는 <xref:System.Windows.Documents.FlowDocument>:  
  
 [!code-xaml[Performance#PerformanceSnippet13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/FlowDocument.xaml#performancesnippet13)]  
  
### <a name="avoid-using-run-to-set-text-properties"></a>텍스트 속성을 설정하여 실행 사용 방지  
 일반적으로 사용 하 여는 <xref:System.Windows.Documents.Run> 내는 <xref:System.Windows.Controls.TextBlock> 는 더 많은 성능 명시적를 사용 하지 않는 인스턴스보다 <xref:System.Windows.Documents.Run> 전혀 개체입니다. 사용 하는 경우는 <xref:System.Windows.Documents.Run> 텍스트 속성을 설정 하려면 해당 속성을 직접 설정의 <xref:System.Windows.Controls.TextBlock> 대신 합니다.  
  
 다음 태그 예제에서는 경우 text 속성을 설정의 두 가지는 <xref:System.Windows.Controls.TextBlock.FontWeight%2A> 속성:  
  
 [!code-xaml[Performance#PerformanceSnippet12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml#performancesnippet12)]  
  
 다음 표에서 비용을 1000 표시 <xref:System.Windows.Controls.TextBlock> 개체와 사용 하지 않는 명시적 <xref:System.Windows.Documents.Run>합니다.  
  
|**TextBlock 형식**|**만든 시간(ms)**|**렌더링 시간(ms)**|  
|------------------------|------------------------------|----------------------------|  
|Run 설정 텍스트 속성|146|540|  
|TextBlock 설정 텍스트 속성|43|453|  
  
### <a name="avoid-databinding-to-the-labelcontent-property"></a>Label.Content 속성에 데이터 바인딩 방지  
 있는 경우를 가정해 보십시오는 <xref:System.Windows.Controls.Label> 에서 자주 업데이트 되는 개체는 <xref:System.String> 소스입니다. 경우 데이터 바인딩에 <xref:System.Windows.Controls.Label> 요소의 <xref:System.Windows.Controls.ContentControl.Content%2A> 속성을는 <xref:System.String> 소스 개체를 성능 저하를 발생할 수 있습니다. 원본에서 사용자가 <xref:System.String> 업데이트 되 면 이전 <xref:System.String> 개체는 삭제 되 고 새 <xref:System.String> 다시-때문에 <xref:System.String> 개체는 변경할 수, 수정할 수 없습니다. 이 인해는 <xref:System.Windows.Controls.ContentPresenter> 의 <xref:System.Windows.Controls.Label> 개체를 해당 이전 콘텐츠를 삭제 하 고 새 표시할 수 있는 새 콘텐츠를 다시 생성 <xref:System.String>합니다.  
  
 이 문제에 대한 해결책은 간단합니다. 경우는 <xref:System.Windows.Controls.Label> 사용자 지정으로 설정 되지 않은 <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> , 대체 값의 <xref:System.Windows.Controls.Label> 와 <xref:System.Windows.Controls.TextBlock> 및 데이터 바인딩 해당 <xref:System.Windows.Controls.TextBlock.Text%2A> 속성 소스 문자열을 합니다.  
  
|**데이터 바인딩된 속성**|**업데이트 시간(ms)**|  
|-----------------------------|----------------------------|  
|Label.Content|835|  
|TextBlock.Text|242|  
  
<a name="Hyperlink"></a>   
## <a name="hyperlink"></a>하이퍼링크  
 <xref:System.Windows.Documents.Hyperlink> 개체는 유동 콘텐츠 내에서 하이퍼링크를 호스팅할 수 있도록 하는 인라인 수준의 유동 콘텐츠 요소입니다.  
  
### <a name="combine-hyperlinks-in-one-textblock-object"></a>하나의 TextBlock 개체에 대한 하이퍼링크 결합  
 여러의 사용을 최적화할 수 <xref:System.Windows.Documents.Hyperlink> 동일한 내에서 함께 그룹화 하 여 요소 <xref:System.Windows.Controls.TextBlock>합니다. 이렇게 하면 응용 프로그램에서 만드는 개체의 수를 최소화할 수 있습니다. 예를 들어 다음과 같은 여러 개의 하이퍼링크를 표시할 수 있습니다.  
  
 MSN 홈 &#124; 내 MSN  
  
 다음 태그 예에서는 여러 <xref:System.Windows.Controls.TextBlock> 하이퍼링크를 표시 하는 데 사용 되는 요소:  
  
 [!code-xaml[Performance#PerformanceSnippet9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet9)]  
  
 다음 태그 예에서는 단일을 사용 하 여이 이번에 하이퍼링크를 표시 하는 보다 효율적인 방법을 <xref:System.Windows.Controls.TextBlock>:  
  
 [!code-xaml[Performance#PerformanceSnippet10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet10)]  
  
### <a name="showing-underlines-on-hyperlinks-only-on-mouseenter-events"></a>MouseEnter 이벤트에만 하이퍼링크에 밑줄 표시  
 A <xref:System.Windows.TextDecoration> 개체는 텍스트에 추가할 수 있는 시각적 장식, 인스턴스화할 때 성능이 저하 수, 합니다. 광범위 하 게 사용의 경우 <xref:System.Windows.Documents.Hyperlink> 요소를 고려 이벤트와 같은 트리거될 때만 밑줄이 표시는 <xref:System.Windows.ContentElement.MouseEnter> 이벤트입니다. 자세한 내용은 [하이퍼링크에 밑줄이 그어지는지 여부 지정](../../../../docs/framework/wpf/advanced/how-to-specify-whether-a-hyperlink-is-underlined.md)을 참조하세요.  
  
 ![Textdecoration을 표시 하는 하이퍼링크](../../../../docs/framework/wpf/advanced/media/textdecoration03.png "TextDecoration03")  
MouseEnter에 표시되는 하이퍼링크  
  
 태그 샘플은 다음 한 <xref:System.Windows.Documents.Hyperlink> 와 밑줄 없는 정의:  
  
 [!code-xaml[Performance#PerformanceSnippet11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet11)]  
  
 다음 표에서 1000을 표시 하는 성능 비용을 보여 줍니다. <xref:System.Windows.Documents.Hyperlink> 와 밑줄 없는 요소입니다.  
  
|**하이퍼링크**|**만든 시간(ms)**|**렌더링 시간(ms)**|  
|-------------------|------------------------------|----------------------------|  
|밑줄 있음|289|1130|  
|밑줄 없음|299|776|  
  
<a name="Text_Formatting_Features"></a>   
## <a name="text-formatting-features"></a>텍스트 서식 지정 기능  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 자동 하이픈 넣기 등 서식 있는 텍스트 서식 지정 서비스를 제공합니다. 이러한 서비스는 응용 프로그램 성능에 영향을 줄 수 있으며 필요한 경우에만 사용해야 합니다.  
  
### <a name="avoid-unnecessary-use-of-hyphenation"></a>불필요한 하이픈 넣기 사용 안 함  
 자동 하이픈 하이픈 중단점을 줄의 텍스트를 찾고 알리고의 선에 추가 중단 위치 <xref:System.Windows.Controls.TextBlock> 및 <xref:System.Windows.Documents.FlowDocument> 개체입니다. 기본적으로 이러한 개체에서는 자동 하이픈 넣기 기능이 사용하지 않도록 설정됩니다. 개체의 IsHyphenationEnabled 속성을 `true`로 설정하여 이 기능을 사용하도록 설정할 수 있습니다. 그러나 이 기능을 사용하면 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 [!INCLUDE[TLA#tla_com](../../../../includes/tlasharptla-com-md.md)] 상호 운용성이 시작되어 응용 프로그램 성능에 영향을 미칠 수 있습니다. 꼭 필요한 경우가 아니면 자동 하이픈 넣기를 사용하지 않는 것이 좋습니다.  
  
### <a name="use-figures-carefully"></a>신중하게 그림 사용  
 A <xref:System.Windows.Documents.Figure> 요소 콘텐츠 페이지 내에서 절대 위치 일 수 있는 유동 콘텐츠의 일부를 나타냅니다. 일부 경우에는 <xref:System.Windows.Documents.Figure> 위치로 레이아웃이 되어 이미 콘텐츠를와 충돌 하는 경우에 자동으로 다시 포맷 하는 전체 페이지를 발생할 수 있습니다. 하거나 그룹화 하 여 불필요 한 다시 포맷 한 가능성을 최소화할 수 있습니다 <xref:System.Windows.Documents.Figure> 서로 또는 고정된 페이지 크기 시나리오에서는 맨 위 근처 선언 옆에 있는 요소입니다.  
  
### <a name="optimal-paragraph"></a>최적 단락  
 최적의 단락 기능은 <xref:System.Windows.Documents.FlowDocument> 개체 공백 최대한 일정 하 게 분포 되도록 단락을 배치 합니다. 기본적으로 최적 단락 기능은 사용하지 않도록 설정됩니다. 개체의 설정 하 여이 기능을 활성화할 수 <xref:System.Windows.Documents.FlowDocument.IsOptimalParagraphEnabled%2A> 속성을 `true`합니다. 그러나 이 기능을 사용하면 응용 프로그램 성능에 영향을 미칩니다. 꼭 필요한 경우가 아니면 최적 단락 기능을 사용하지 않는 것이 좋습니다.  
  
## <a name="see-also"></a>참고 항목  
 [WPF 응용 프로그램 성능 최적화](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)  
 [응용 프로그램 성능 계획](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)  
 [하드웨어 이용](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)  
 [레이아웃 및 디자인](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)  
 [2차원 그래픽 및 이미징](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)  
 [개체 동작](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)  
 [응용 프로그램 리소스](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)  
 [데이터 바인딩](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)  
 [기타 성능 권장 사항](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)
