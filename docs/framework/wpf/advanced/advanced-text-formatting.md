---
title: "고급 텍스트 서식 지정 | Microsoft Docs"
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
  - "서식 지정[WPF]"
  - "텍스트[WPF]"
  - "입력 체계, 텍스트 서식 지정"
ms.assetid: f0a7986e-f5b2-485c-a27d-f8e922022212
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# 고급 텍스트 서식 지정
[!INCLUDE[TLA#tla_wpf](../../../../includes/tlasharptla-wpf-md.md)]는 응용 프로그램에 텍스트를 포함하는 데 사용할 수 있는 강력한 [!INCLUDE[TLA#tla_api#plural](../../../../includes/tlasharptla-apisharpplural-md.md)] 집합을 제공합니다.  <xref:System.Windows.Controls.TextBlock>과 같은 레이아웃 및 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]는 텍스트를 표현하는 데 가장 일반적으로 사용되는 요소를 제공합니다.  <xref:System.Windows.Media.GlyphRunDrawing> 및 <xref:System.Windows.Media.FormattedText>와 같은 그리기 [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]는 서식 있는 텍스트를 그리기에 포함할 수 있는 방법을 제공합니다.  가장 고급 수준에서 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]는 텍스트 저장소 관리, 텍스트 런\(Text Run\) 서식 관리 및 포함된 개체 관리와 같은 텍스트 표현의 모든 측면을 제어하는 데 사용할 수 있는 확장 가능한 텍스트 서식 엔진을 제공합니다.  
  
 이 항목에서는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]의 텍스트 서식 지정에 대해 소개합니다.  여기에서는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 텍스트 서식 엔진의 용도 및 클라이언트 구현에 대해 주로 다룹니다.  
  
> [!NOTE]
>  이 문서에 나오는 모든 코드 예제는 [Advanced Text Formatting 샘플](http://go.microsoft.com/fwlink/?LinkID=159965)에서 찾을 수 있습니다.  
  
   
  
<a name="prereq"></a>   
## 사전 요구 사항  
 이 항목에서는 사용자가 텍스트 표현에 사용되는 고급 수준의 [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]에 대해 잘 알고 있다고 가정합니다.  대부분의 사용자 시나리오에서는 이 항목에서 설명하는 고급 텍스트 서식 지정 [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]가 필요하지 않습니다.  다른 텍스트 [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]에 대한 소개를 보려면 [WPF의 문서](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)를 참조하십시오.  
  
<a name="section1"></a>   
## 고급 텍스트 서식 지정  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]의 텍스트 레이아웃 및 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 컨트롤은 서식 있는 텍스트를 간편하게 응용 프로그램에 포함하는 데 사용할 수 있는 서식 속성을 제공합니다.  이러한 컨트롤은 텍스트의 서체, 크기 및 색을 비롯하여 텍스트 표현을 처리하는 데 사용할 수 있는 다양한 속성을 제공합니다.  일반적인 상황에서는 이러한 컨트롤로 응용 프로그램에서 대부분의 텍스트 표현을 처리할 수 있습니다.  하지만 몇 가지 고급 시나리오에서는 텍스트 표현을 제어하는 것뿐만 아니라 텍스트 저장소도 제어해야 합니다.  [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]는 이러한 용도로 사용할 수 있는 확장 가능한 텍스트 서식 엔진을 제공합니다.  
  
 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]의 고급 텍스트 서식 기능은 텍스트 서식 엔진, 텍스트 저장소. 텍스트 런 및 서식 속성으로 이루어집니다.  텍스트 서식 엔진인 <xref:System.Windows.Media.TextFormatting.TextFormatter>는 텍스트를 표현하는 데 사용할 텍스트 줄을 만듭니다.  이 작업은 줄 서식 지정 프로세스를 시작하고 텍스트 포맷터의 <xref:System.Windows.Media.TextFormatting.TextFormatter.FormatLine%2A>을 호출하여 수행됩니다.  텍스트 포맷터는 저장소의 <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A> 메서드를 호출하여 텍스트 저장소에서 텍스트 런을 검색합니다.  그런 다음 텍스트 포맷터가 <xref:System.Windows.Media.TextFormatting.TextRun> 개체를 <xref:System.Windows.Media.TextFormatting.TextLine> 개체로 만든 다음 검사나 표시를 위해 응용 프로그램에 제공합니다.  
  
<a name="section2"></a>   
## 텍스트 포맷터 사용  
 <xref:System.Windows.Media.TextFormatting.TextFormatter>는 텍스트 서식 지정과 텍스트 줄 바꿈을 위한 서비스를 제공하는 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] 텍스트 서식 엔진입니다.  또한 텍스트 포맷터는 여러 텍스트 문자 형식과 단락 스타일을 처리할 수 있으며 국가별 텍스트 레이아웃을 지원합니다.  
  
 기존의 텍스트 [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)]와 달리 <xref:System.Windows.Media.TextFormatting.TextFormatter>는 콜백 메서드 집합을 통해 텍스트 레이아웃 클라이언트와 상호 작용합니다.  이를 위해 클라이언트는 <xref:System.Windows.Media.TextFormatting.TextSource> 클래스 구현에서 이러한 메서드를 제공해야 합니다.  다음 다이어그램에서는 클라이언트 응용 프로그램과 <xref:System.Windows.Media.TextFormatting.TextFormatter>의 텍스트 레이아웃 상호 작용을 보여 줍니다.  
  
 ![텍스트 레이아웃 클라이언트 및 TextFormatter의 다이어그램](../../../../docs/framework/wpf/advanced/media/textformatter01.png "TextFormatter01")  
응용 프로그램과 TextFormatter의 상호 작용  
  
 텍스트 포맷터는 <xref:System.Windows.Media.TextFormatting.TextSource>의 구현인 텍스트 저장소에서 서식 있는 텍스트 줄을 검색하는 데 사용됩니다.  이 작업은 먼저 <xref:System.Windows.Media.TextFormatting.TextFormatter.Create%2A> 메서드를 사용하여 텍스트 포맷터의 인스턴스를 만들어 수행됩니다.  이 메서드는 텍스트 포맷터의 인스턴스를 만든 다음 최대 줄 높이 및 너비 값을 설정합니다.  텍스트 포맷터 인스턴스를 만드는 작업이 끝나면 곧바로 <xref:System.Windows.Media.TextFormatting.TextFormatter.FormatLine%2A> 메서드를 호출하여 줄 생성 프로세스가 시작됩니다.  이때 <xref:System.Windows.Media.TextFormatting.TextFormatter>가 텍스트 소스로 콜백하여 텍스트 런의 텍스트 및 서식 지정 매개 변수를 검색함으로써 줄을 만듭니다.  
  
 다음 예제에서는 텍스트 저장소에 서식을 지정하는 프로세스를 보여 줍니다.  먼저 <xref:System.Windows.Media.TextFormatting.TextFormatter> 개체를 사용하여 텍스트 저장소에서 텍스트 줄을 검색한 다음 <xref:System.Windows.Media.DrawingContext>에 그릴 수 있도록 텍스트 줄에 서식을 지정합니다.  
  
 [!code-csharp[TextFormatterExample#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextFormatterExample/CSharp/Window1.xaml.cs#100)]
 [!code-vb[TextFormatterExample#100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextFormatterExample/VisualBasic/Window1.xaml.vb#100)]  
  
<a name="section3"></a>   
## 클라이언트 텍스트 저장소 구현  
 텍스트 서식 엔진을 확장하는 경우 텍스트 저장소의 모든 측면을 구현하고 관리해야 하며  이는 결코 간단한 작업이 아닙니다.  텍스트 저장소는 텍스트 런 속성, 단락 속성, 포함된 개체 및 이와 비슷한 콘텐츠를 추적하는 역할을 합니다.  또한 텍스트 저장소는 텍스트 포맷터가 <xref:System.Windows.Media.TextFormatting.TextLine> 개체를 만드는 데 사용하는 개별 <xref:System.Windows.Media.TextFormatting.TextRun> 개체를 텍스트 포맷터에게 제공합니다.  
  
 텍스트 저장소의 가상화를 처리하려면 <xref:System.Windows.Media.TextFormatting.TextSource>에서 텍스트 저장소를 파생해야 합니다.  <xref:System.Windows.Media.TextFormatting.TextSource>는 텍스트 포맷터가 텍스트 저장소에서 텍스트 런을 검색하는 데 사용하는 메서드를 정의합니다.  <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A>은 텍스트 포맷터가 줄 서식 지정에 사용된 텍스트 런을 검색하는 데 사용하는 메서드입니다.  텍스트 포맷터는 다음 조건 중 하나가 발생할 때까지 <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A>을 반복해서 호출합니다.  
  
-   <xref:System.Windows.Media.TextFormatting.TextEndOfLine> 또는 서브클래스가 반환될 때까지  
  
-   텍스트 런의 누적된 너비가 텍스트 포맷터를 만들기 위한 호출 또는 텍스트 포맷터의 <xref:System.Windows.Media.TextFormatting.TextFormatter.FormatLine%2A> 메서드 호출에 지정된 최대 줄 너비를 초과할 때까지  
  
-   "CF", "LF" 또는 "CRLF"와 같은 [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] 줄 바꿈 시퀀스가 반환될 때까지  
  
<a name="section4"></a>   
## 텍스트 런 제공  
 텍스트 서식 지정 프로세스의 핵심은 텍스트 포맷터와 텍스트 저장소의 상호 작용에 있습니다.  사용자의 <xref:System.Windows.Media.TextFormatting.TextSource> 구현은 <xref:System.Windows.Media.TextFormatting.TextRun> 개체 및 텍스트 런의 서식 지정에 사용할 속성을 텍스트 포맷터에 제공합니다.  이러한 상호 작용은 텍스트 포맷터가 호출하는 <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A> 메서드를 통해 처리됩니다.  
  
 다음 표에서는 미리 정의된 몇 가지 <xref:System.Windows.Media.TextFormatting.TextRun> 개체를 보여 줍니다.  
  
|TextRun 유형|용도|  
|----------------|--------|  
|<xref:System.Windows.Media.TextFormatting.TextCharacters>|문자 모양에 대한 표현을 다시 텍스트 포맷터에 전달하는 데 사용되는 특수 텍스트 런입니다.|  
|<xref:System.Windows.Media.TextFormatting.TextEmbeddedObject>|측정, 적중 텍스트 및 그리기가 전체적으로 수행되는 콘텐츠\(예: 텍스트 내의 이미지 또는 단추\)를 제공하는 데 사용되는 특수 텍스트 런입니다.|  
|<xref:System.Windows.Media.TextFormatting.TextEndOfLine>|줄 끝을 표시하는 데 사용되는 특수 텍스트 런입니다.|  
|<xref:System.Windows.Media.TextFormatting.TextEndOfParagraph>|단락 끝을 표시하는 데 사용되는 특수 텍스트 런입니다.|  
|<xref:System.Windows.Media.TextFormatting.TextEndOfSegment>|세그먼트의 끝\(예: 이전 <xref:System.Windows.Media.TextFormatting.TextModifier> 실행의 영향을 받는 범위의 끝\)을 표시하는 데 사용되는 특수 텍스트 런입니다.|  
|<xref:System.Windows.Media.TextFormatting.TextHidden>|숨겨진 문자의 범위를 표시하는 데 사용되는 특수 텍스트 런입니다.|  
|<xref:System.Windows.Media.TextFormatting.TextModifier>|해당 범위 내에서 텍스트 런의 속성을 수정하는 데 사용되는 특수 텍스트 런입니다.  범위는 일치하는 다음 <xref:System.Windows.Media.TextFormatting.TextEndOfSegment> 텍스트 런이나 다음 <xref:System.Windows.Media.TextFormatting.TextEndOfParagraph>로 확장됩니다.|  
  
 미리 정의된 <xref:System.Windows.Media.TextFormatting.TextRun> 개체는 서브클래싱될 수 있습니다.  따라서 텍스트 소스는 사용자 지정 데이터가 포함된 텍스트 런을 텍스트 포맷터에 제공할 수 있습니다.  
  
 다음 예제에서는 <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A> 메서드를 보여 줍니다.  이 텍스트 저장소는 처리를 위해 텍스트 포맷터에 <xref:System.Windows.Media.TextFormatting.TextRun> 개체를 반환합니다.  
  
 [!code-csharp[TextFormatterExample#101](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextFormatterExample/CSharp/CustomTextSource.cs#101)]
 [!code-vb[TextFormatterExample#101](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextFormatterExample/VisualBasic/CustomTextSource.vb#101)]  
  
> [!NOTE]
>  이 예제에서는 텍스트 저장소가 모든 텍스트에 동일한 텍스트 속성을 제공합니다.  고급 텍스트 저장소의 경우 문자마다 서로 다른 속성을 가질 수 있도록 고유의 범위 관리를 구현해야 합니다.  
  
<a name="section5"></a>   
## 서식 속성 지정  
 <xref:System.Windows.Media.TextFormatting.TextRun> 개체에 서식을 지정할 때는 텍스트 저장소가 제공하는 속성을 사용합니다.  이러한 속성은 <xref:System.Windows.Media.TextFormatting.TextParagraphProperties>와 <xref:System.Windows.Media.TextFormatting.TextRunProperties>라는 두 가지 형식으로 제공됩니다.  <xref:System.Windows.Media.TextFormatting.TextParagraphProperties>는 <xref:System.Windows.TextAlignment> 및 <xref:System.Windows.FlowDirection>과 같이 단락 전체에 적용되는 속성을 처리합니다.  <xref:System.Windows.Media.TextFormatting.TextRunProperties>는 전경 브러시, <xref:System.Windows.Media.Typeface> 및 글꼴 크기와 같이 단락 내의 각 텍스트 런마다 달라질 수 있는 속성입니다.  사용자 지정 단락과 사용자 지정 텍스트 런 속성 형식을 구현하려면 응용 프로그램에서 각각 <xref:System.Windows.Media.TextFormatting.TextParagraphProperties> 및 <xref:System.Windows.Media.TextFormatting.TextRunProperties>에서 파생되는 클래스를 만들어야 합니다.  
  
## 참고 항목  
 [WPF의 입력 체계](../../../../docs/framework/wpf/advanced/typography-in-wpf.md)   
 [WPF의 문서](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)