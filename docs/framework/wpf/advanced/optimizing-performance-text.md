---
title: "성능 최적화: 텍스트 | Microsoft Docs"
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
  - "텍스트 렌더링"
  - "하이퍼링크"
  - "서식 있는 텍스트[WPF]"
  - "텍스트, 성능"
  - "문자 모양"
ms.assetid: 66b1b9a7-8618-48db-b616-c57ea4327b98
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# 성능 최적화: 텍스트
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]지원 기능을 갖춘을 사용 하 여 텍스트 내용을 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 컨트롤입니다. 일반적 텍스트 렌더링 세 계층에서으로 나눌 수 있습니다.  
  
1.  사용 하는 <xref:System.Windows.Documents.Glyphs> 및 <xref:System.Windows.Media.GlyphRun> 개체를 직접.  
  
2.  사용 하 여 <xref:System.Windows.Media.FormattedText> 개체입니다.  
  
3.  와 같은 고급 컨트롤을 사용 하 여 <xref:System.Windows.Controls.TextBlock> 및 <xref:System.Windows.Documents.FlowDocument> 개체입니다.  
  
 이 항목 렌더링 성능 권장 사항 텍스트를 제공합니다.  
  
   
  
<a name="Glyph_Level"></a>   
## <a name="rendering-text-at-the-glyph-level"></a>문자 모양 수준에 텍스트를 렌더링합니다.  
 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]직접 액세스 하 여 문자 모양 수준의 태그를 포함 하 여 고급 텍스트 지원을 제공 <xref:System.Windows.Documents.Glyphs> 가로채 고 포맷 한 후 텍스트를 유지 하려는 고객에 대 한 합니다. 이러한 기능은 중요 한 지원을 제공 다양 한 텍스트에 대 한 각각 다음과 같은 시나리오의 요구 사항을 렌더링 합니다.  
  
-   고정 된 형식의 문서의 화면 표시 합니다.  
  
-   시나리오를 인쇄 합니다.  
  
    -   [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]장치 프린터 언어로 합니다.  
  
    -   [!INCLUDE[TLA#tla_mxdw](../../../../includes/tlasharptla-mxdw-md.md)].  
  
    -   이전 프린터 드라이버에서 출력 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] 고정된 형식으로 응용 프로그램입니다.  
  
    -   인쇄 스풀 형식입니다.  
  
-   이전 버전의에 대 한 클라이언트를 포함 하는 고정 된 형식의 문서 표현 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] 및 기타 컴퓨팅 장치입니다.  
  
> [!NOTE]
>  <xref:System.Windows.Documents.Glyphs> 및 <xref:System.Windows.Media.GlyphRun> 고정 형식 문서 표시 및 인쇄 시나리오에 대 한 설계 되었습니다. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]일반 레이아웃에 대 한 몇 가지 요소를 제공 하 고 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 시나리오와 같은 <xref:System.Windows.Controls.Label> 및 <xref:System.Windows.Controls.TextBlock>합니다. 레이아웃에 대 한 자세한 내용은 및 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 시나리오 참조는 [WPF의 입력 체계](../../../../docs/framework/wpf/advanced/typography-in-wpf.md)합니다.  
  
 다음 예제에 대 한 속성을 정의 하는 방법을 보여 줍니다는 <xref:System.Windows.Documents.Glyphs> 개체 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]합니다. <xref:System.Windows.Documents.Glyphs> 개체의 출력을 보여는 <xref:System.Windows.Media.GlyphRun> 에서 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]합니다. 예제에서는 가정 Arial, Courier New, 및 Times New Roman 글꼴에 설치 되어 있는지는 **C:\WINDOWS\Fonts** 로컬 컴퓨터의 폴더에 있습니다.  
  
 [!code-xml[GlyphsOvwSample1#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GlyphsOvwSample1/CS/default.xaml#1)]  
  
### <a name="using-drawglyphrun"></a>DrawGlyphRun를 사용 하 여  
 사용자 지정 컨트롤 있고 문자 모양을 렌더링, 사용 하려는 경우는 <xref:System.Windows.Media.DrawingContext.DrawGlyphRun%2A> 메서드.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]또한 사용자 지정 텍스트를 사용 하는 서식 지정에 대 한 하위 수준 서비스를 제공 된 <xref:System.Windows.Media.FormattedText> 개체입니다. 에 텍스트를 렌더링 하는 가장 효율적인 방법은 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 사용 하 여 문자 모양 수준에서 텍스트 콘텐츠를 생성 하는 것 <xref:System.Windows.Documents.Glyphs> 및 <xref:System.Windows.Media.GlyphRun>합니다. 그러나 이러한 효율성 비용은 사용 하기 쉬운 서식 있는 텍스트를 기본 제공 기능 손실의 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 와 같은 컨트롤 <xref:System.Windows.Controls.TextBlock> 및 <xref:System.Windows.Documents.FlowDocument>합니다.  
  
<a name="FormattedText_Object"></a>   
## <a name="formattedtext-object"></a>FormattedText 개체  
 <xref:System.Windows.Media.FormattedText> 개체를 사용 하는 각 문자는 텍스트에 서식을 지정할 수 있는 개별적으로 여러 줄 텍스트를 그릴 수 있습니다. 자세한 내용은 참조 [드로잉 서식의 텍스트](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md)합니다.  
  
 서식 있는 텍스트를 만들려면 호출는 <xref:System.Windows.Media.FormattedText.%23ctor%2A> 를 만드는 생성자는 <xref:System.Windows.Media.FormattedText> 개체입니다. 초기 서식 있는 텍스트 문자열을 만든 후에 다양 한 서식 스타일을 적용할 수 있습니다. 응용 프로그램에서 자체 레이아웃을 구현 하려는 경우는 <xref:System.Windows.Media.FormattedText> 개체는 같은 컨트롤을 사용 하 여 보다 낫습니다 <xref:System.Windows.Controls.TextBlock>합니다. 대 한 자세한 내용은 <xref:System.Windows.Media.FormattedText> 개체, 참조 [드로잉 서식의 텍스트](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md) 합니다.  
  
 <xref:System.Windows.Media.FormattedText> 개체는 낮은 수준의 텍스트 서식 지정 기능을 제공 합니다. 하나 이상의 문자를 여러 가지 서식 스타일을 적용할 수 있습니다. 예를 들어 모두 호출할 수 있습니다는 <xref:System.Windows.Media.FormattedText.SetFontSize%2A> 및 <xref:System.Windows.Media.FormattedText.SetForegroundBrush%2A> 텍스트의 처음&5; 개 문자의 서식을 변경 하는 방법입니다.  
  
 다음 코드 예제는 <xref:System.Windows.Media.FormattedText> 개체를 렌더링 합니다.  
  
 [!code-csharp[formattedtextsnippets#FormattedTextSnippets1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FormattedTextSnippets/CSharp/Window1.xaml.cs#formattedtextsnippets1)]
 [!code-vb[formattedtextsnippets#FormattedTextSnippets1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FormattedTextSnippets/visualbasic/window1.xaml.vb#formattedtextsnippets1)]  
  
<a name="FlowDocument_TextBlock_Label"></a>   
## <a name="flowdocument-textblock-and-label-controls"></a>FlowDocument, TextBlock 및 레이블 컨트롤  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]화면에 텍스트를 그리기 위한 여러 컨트롤이 포함 되어 있습니다. 각 컨트롤 서로 다른 시나리오를 대상으로 하 고 기능 및 제한의 고유한 목록에 있습니다.  
  
### <a name="flowdocument-impacts-performance-more-than-textblock-or-label"></a>FlowDocument 성능에 미치는 영향 이상 TextBlock 또는 레이블  
 일반적으로 <xref:System.Windows.Controls.TextBlock> 제한 텍스트 지원에 대 한 간략 한 문장 등 필요한 경우 요소를 사용 합니다는 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]합니다. <xref:System.Windows.Controls.Label> 최소 텍스트 지원이 필요한 경우 사용할 수 있습니다. <xref:System.Windows.Documents.FlowDocument> 요소를 지 원하는 풍부한 콘텐츠를 표시 flowable 다시 문서에 대 한 컨테이너로 사용 되며 따라서를 사용 하 여 보다 성능에 큰 영향을에 <xref:System.Windows.Controls.TextBlock> 또는 <xref:System.Windows.Controls.Label> 컨트롤입니다.  
  
 대 한 자세한 내용은 <xref:System.Windows.Documents.FlowDocument>, 참조 [유동 문서 개요](../../../../docs/framework/wpf/advanced/flow-document-overview.md)합니다.  
  
### <a name="avoid-using-textblock-in-flowdocument"></a>FlowDocument에 텍스트 블록을 사용 하지 마십시오  
 <xref:System.Windows.Controls.TextBlock> 요소에서 파생 된 <xref:System.Windows.UIElement>합니다. <xref:System.Windows.Documents.Run> 요소에서 파생 됩니다 <xref:System.Windows.Documents.TextElement>, 적은 비용으로 보다 사용 되는 <xref:System.Windows.UIElement>-파생 개체입니다. 사용 가능한 경우 <xref:System.Windows.Documents.Run> 대신 <xref:System.Windows.Controls.TextBlock> 텍스트의 콘텐츠를 표시할는 <xref:System.Windows.Documents.FlowDocument>합니다.  
  
 다음 태그 샘플 내에서 텍스트 콘텐츠를 설정 하는 두 가지 방법을 보여 줍니다는 <xref:System.Windows.Documents.FlowDocument>:  
  
 [!code-xml[Performance#PerformanceSnippet13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/FlowDocument.xaml#performancesnippet13)]  
  
### <a name="avoid-using-run-to-set-text-properties"></a>텍스트 속성을 설정 하려면 실행을 사용 하지 마십시오  
 일반적으로 사용 하는 <xref:System.Windows.Documents.Run> 내는 <xref:System.Windows.Controls.TextBlock> 은 더 많은 성능 명시적를 사용 하지 않는 인스턴스보다 <xref:System.Windows.Documents.Run> 개체를 전혀 합니다. 사용 하는 경우는 <xref:System.Windows.Documents.Run> 텍스트 속성을 설정 하려면 해당 속성에 직접 설정의 <xref:System.Windows.Controls.TextBlock> 대신 합니다.  
  
 다음 태그 예제에서는 경우 text 속성을 설정 하는의 두 가지는 <xref:System.Windows.Controls.TextBlock.FontWeight%2A> 속성:  
  
 [!code-xml[Performance#PerformanceSnippet12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Window1.xaml#performancesnippet12)]  
  
 다음 표에서 1000을 표시 하는 비용을 보여 줍니다. <xref:System.Windows.Controls.TextBlock> 개체와 사용 하지 않는 명시적인 <xref:System.Windows.Documents.Run>합니다.  
  
|**텍스트 블록 형식**|**만든 시간 (밀리초)**|**렌더링 시간 (밀리초)**|  
|------------------------|------------------------------|----------------------------|  
|실행 설정의 텍스트 속성|146|540|  
|TextBlock 텍스트 속성 설정|43|453|  
  
### <a name="avoid-databinding-to-the-labelcontent-property"></a>Label.Content 속성에 데이터 바인딩 방지  
 있는 경우를 가정해 보십시오는 <xref:System.Windows.Controls.Label> 에서 자주 업데이트 되는 개체는 <xref:System.String> 소스입니다. 경우 데이터 바인딩에 <xref:System.Windows.Controls.Label> 요소의 <xref:System.Windows.Controls.ContentControl.Content%2A> 속성을는 <xref:System.String> 소스 개체를 성능이 저하 될 수 있습니다. 소스 때마다 <xref:System.String> 업데이트 되 면 이전 <xref:System.String> 개체는 삭제 되 고 새 <xref:System.String> 만들어집니다-때문에 <xref:System.String> 개체는 변경할 수, 수정할 수 없습니다. 이 인해는 <xref:System.Windows.Controls.ContentPresenter> 의 <xref:System.Windows.Controls.Label> 개체를 해당 이전 콘텐츠를 삭제 하 고 새 표시할 콘텐츠를 새 재생성 <xref:System.String>합니다.  
  
 이 문제에 대 한 해결책은 간단 합니다. 하는 경우는 <xref:System.Windows.Controls.Label> 사용자 지정으로 설정 되지 않은 <xref:System.Windows.Controls.ContentControl.ContentTemplate%2A> 값을 바꿉니다는 <xref:System.Windows.Controls.Label> 와 <xref:System.Windows.Controls.TextBlock> 및 데이터 바인딩 해당 <xref:System.Windows.Controls.TextBlock.Text%2A> 속성을 원본 문자열입니다.  
  
|**데이터 바인딩된 속성**|**업데이트 시간 (밀리초)**|  
|-----------------------------|----------------------------|  
|Label.Content|835|  
|TextBlock.Text|242|  
  
<a name="Hyperlink"></a>   
## <a name="hyperlink"></a>하이퍼링크  
 <xref:System.Windows.Documents.Hyperlink> 개체는 인라인 수준의 유동 콘텐츠 요소를 유동 콘텐츠 내에서 하이퍼링크를 호스팅할 수 있습니다.  
  
### <a name="combine-hyperlinks-in-one-textblock-object"></a>하나의 TextBlock 개체에 대 한 하이퍼링크 결합  
 여러 대상의 사용을 최적화할 수 <xref:System.Windows.Documents.Hyperlink> 동일한 내에서 함께 그룹화 하 여 요소 <xref:System.Windows.Controls.TextBlock>합니다. 응용 프로그램에서 사용자가 만든 개체의 수를 최소화할 수 있습니다. 예를 들어 다음과 같은 여러 개의 하이퍼링크를 표시 수 있습니다.  
  
 MSN 홈 | 내 MSN  
  
 다음 태그 예제에서는 여러 <xref:System.Windows.Controls.TextBlock> 하이퍼링크를 표시 하는 데 사용 되는 요소:  
  
 [!code-xml[Performance#PerformanceSnippet9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet9)]  
  
 다음 태그 예제에서는 단일을 사용 하 여이 이번에 하이퍼링크를 표시 하는 보다 효율적인 방법을 보여 줍니다. <xref:System.Windows.Controls.TextBlock>:  
  
 [!code-xml[Performance#PerformanceSnippet10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet10)]  
  
### <a name="showing-underlines-on-hyperlinks-only-on-mouseenter-events"></a>MouseEnter 이벤트에만 하이퍼링크에 밑줄이 표시  
 A <xref:System.Windows.TextDecoration> 개체는 텍스트에 추가할 수 있는 시각적 장식 합니다; 하지만 인스턴스화할 때 성능이 저하 될 수 것입니다. 광범위 하 게 사용의 경우 <xref:System.Windows.Documents.Hyperlink> 요소를 고려와 같은 경우 트리거될 때만 밑줄이 표시는 <xref:System.Windows.ContentElement.MouseEnter> 이벤트입니다. 자세한 내용은 참조 [지정 여부 하이퍼링크에 밑줄이](../../../../docs/framework/wpf/advanced/how-to-specify-whether-a-hyperlink-is-underlined.md)합니다.  
  
 ![Textdecoration을 표시 하는 하이퍼링크](../../../../docs/framework/wpf/advanced/media/textdecoration03.png "TextDecoration03")  
MouseEnter에 표시 되는 하이퍼링크  
  
 태그 샘플은 다음 한 <xref:System.Windows.Documents.Hyperlink> 와 밑줄 없이 정의 합니다.  
  
 [!code-xml[Performance#PerformanceSnippet11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet11)]  
  
 다음 표에서 1000 표시의 성능 저하를 보여 줍니다. <xref:System.Windows.Documents.Hyperlink> 집합과 밑줄이 없는 요소입니다.  
  
|**하이퍼링크**|**만든 시간 (밀리초)**|**렌더링 시간 (밀리초)**|  
|-------------------|------------------------------|----------------------------|  
|밑줄|289|1130|  
|밑줄 없음|299|776|  
  
<a name="Text_Formatting_Features"></a>   
## <a name="text-formatting-features"></a>텍스트 서식 지정 기능  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]서식 있는 텍스트는 자동 하이픈 넣기와 같은 서비스를 제공 합니다. 이러한 서비스 응용 프로그램 성능에 영향을 줄 수 하 고 필요한 경우에 사용 해야 합니다.  
  
### <a name="avoid-unnecessary-use-of-hyphenation"></a>불필요 한 하이픈 넣기 사용 방지  
 자동 하이픈 넣기 하이픈 중단점을 줄의 텍스트를 찾고 있으며 선에 대 한 추가 중단 위치 <xref:System.Windows.Controls.TextBlock> 및 <xref:System.Windows.Documents.FlowDocument> 개체입니다. 기본적으로 자동 하이픈 넣기 기능은 이러한 개체에서 비활성화 되었습니다. 개체의 IsHyphenationEnabled 속성을 설정 하 여이 기능을 사용할 수 `true`합니다. 하지만,이 기능을 사용 하면 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 시작 하려면 [!INCLUDE[TLA#tla_com](../../../../includes/tlasharptla-com-md.md)] 상호 운용성, 응용 프로그램 성능에 영향을 줄 수 있습니다. 필요할 경우에 자동 하이픈을 사용 하지 않는 것이 좋습니다.  
  
### <a name="use-figures-carefully"></a>그림을 신중 하 게 사용  
 A <xref:System.Windows.Documents.Figure> 요소 유동 콘텐츠는 콘텐츠 페이지 내에서 절대적으로 배치 될 수 있는 부분을 나타냅니다. 일부 경우에는 <xref:System.Windows.Documents.Figure> 레이아웃이 이미 콘텐츠 위치로 충돌 하는 경우를 자동으로 다시 포맷 하는 전체 페이지 않을 수 있습니다. 그룹화 하거나 하 여 불필요 한 다시 포맷의 가능성을 최소화할 수 <xref:System.Windows.Documents.Figure> 고정된 페이지 크기 시나리오에서 콘텐츠의 맨 위 근처 선언 또는 서로 옆에 있는 요소입니다.  
  
### <a name="optimal-paragraph"></a>최적 단락  
 최적 단락 기능은 <xref:System.Windows.Documents.FlowDocument> 개체 공백을 가능한 균등 하 게 분산 되도록 단락을 배치 합니다. 기본적으로 최적 단락 기능은 사용할 수 없습니다. 개체의 설정 하 여이 기능을 사용할 수 <xref:System.Windows.Documents.FlowDocument.IsOptimalParagraphEnabled%2A> 속성을 `true`합니다. 그러나이 기능을 사용 하면 응용 프로그램의 성능이 영향을 줍니다. 필요할 경우에 최적 단락 기능은 사용 하지 않는 것이 좋습니다.  
  
## <a name="see-also"></a>참고 항목  
 [WPF 응용 프로그램 성능 최적화](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)   
 [응용 프로그램 성능 계획](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)   
 [하드웨어 이용](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)   
 [레이아웃 및 디자인](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)   
 [2 차원 그래픽 및 이미징](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)   
 [개체 동작](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)   
 [응용 프로그램 리소스](../../../../docs/framework/wpf/advanced/optimizing-performance-application-resources.md)   
 [데이터 바인딩](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)   
 [기타 성능 권장 사항](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)