---
title: WPF의 입력 체계
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], about typography
ms.assetid: 06cbf17b-6eff-4fe5-949d-2dd533e4e1f4
ms.openlocfilehash: 45f74a4dd2164f332314ad79a18eab49efb520d6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33549129"
---
# <a name="typography-in-wpf"></a>WPF의 입력 체계
이 항목에서는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 주요 입력 체계 기능을 소개합니다. 이러한 기능에는 텍스트 렌더링의 향상된 품질 및 성능, [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 입력 체계 지원, 향상된 국가별 텍스트, 향상된 글꼴 지원 및 새 텍스트 API(응용 프로그래밍 인터페이스)가 포함됩니다.  
  

  
<a name="Improved_Quality_and_Performance_of_Text"></a>   
## <a name="improved-quality-and-performance-of-text"></a>텍스트의 향상된 품질 및 성능  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 텍스트는 [!INCLUDE[TLA#tla_ct](../../../../includes/tlasharptla-ct-md.md)]을 사용하여 렌더링되어 텍스트의 명확성 및 가독성이 향상됩니다. [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]은 랩톱 화면, Pocket PC 화면, 평면 모니터 등 기존의 LCD(액정 디스플레이)에서 보다 쉽게 텍스트를 읽을 수 있도록 하기 위해 [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)]에서 개발한 소프트웨어 기술입니다. [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]은 픽셀의 소수 부분에 문자를 맞춰 보다 정밀하게 실제 모양으로 텍스트를 표시할 수 있는 하위 픽셀 렌더링을 사용합니다. 해상도를 더 세밀하게 지원할수록 텍스트의 미세한 부분까지 더 선명하게 표시되므로 오랫동안 더 쉽게 읽을 수 있습니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]의 [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)]에서 향상된 또 다른 기능은 y 방향 앤티앨리어싱으로, 텍스트 문자에서 얕은 곡선의 위쪽과 아래쪽을 다듬습니다. [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] 기능에 대한 자세한 내용은 [ClearType 개요](../../../../docs/framework/wpf/advanced/cleartype-overview.md)를 참조하세요.  
  
 ![ClearType y 텍스트&#45;anti 방향&#45;앨리어싱](../../../../docs/framework/wpf/advanced/media/typographyinwpf02.gif "TypographyInWPF02")  
ClearType y 방향 앤티앨리어싱으로 표시된 텍스트  
  
 컴퓨터가 최소 수준의 하드웨어 요구를 충족하는 경우 전체 텍스트 렌더링 파이프라인은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 하드웨어 가속일 수 있습니다. 하드웨어를 사용하여 수행할 수 없는 렌더링은 소프트웨어 렌더링으로 대체됩니다. 하드웨어 가속은 개별 문자 모양 저장, 문자 모양을 문자 모양 실행으로 합성, 효과 적용에서 최종 표시된 출력에 [!INCLUDE[TLA2#tla_ct](../../../../includes/tla2sharptla-ct-md.md)] 혼합 알고리즘 적용에 이르는 모든 단계의 텍스트 렌더링 파이프라인에 영향을 줍니다. 하드웨어 가속에 대한 자세한 내용은 [그래픽 렌더링 계층](../../../../docs/framework/wpf/advanced/graphics-rendering-tiers.md)을 참조하세요.  
  
 ![텍스트 렌더링 파이프라인의 다이어그램](../../../../docs/framework/wpf/advanced/media/typographyinwpf01.png "TypographyInWPF01")  
텍스트 렌더링 파이프라인의 다이어그램  
  
 또한 문자나 문자 모양으로 애니메이션된 텍스트는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서 사용되는 그래픽 하드웨어 기능을 최대한 활용합니다. 그 결과 부드러운 텍스트 애니메이션이 만들어집니다.  
  
<a name="Rich_Typography"></a>   
## <a name="rich-typography"></a>풍부한 입력 체계  
 [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] 글꼴 형식은 [!INCLUDE[TLA#tla_truetype](../../../../includes/tlasharptla-truetype-md.md)] 글꼴 형식의 확장입니다. [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] 글꼴 형식은 [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)]와 Adobe에서 공동 개발했으며 풍부한 고급 입력 체계 기능을 제공합니다. <xref:System.Windows.Documents.Typography> 개체는 다양 한 고급 기능을 노출 [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] 대체 스타일 및 선단 장식을 등의 글꼴입니다. [!INCLUDE[TLA2#tla_lhsdk](../../../../includes/tla2sharptla-lhsdk-md.md)]는 Pericles 및 Pescadero 글꼴과 같이 풍부한 기능으로 디자인된 샘플 [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] 글꼴 모음을 제공합니다. 자세한 내용은 [샘플 OpenType 글꼴 팩](../../../../docs/framework/wpf/advanced/sample-opentype-font-pack.md)을 참조하세요.  
  
 Pericles [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] 글꼴에는 표준 문자 모양 집합에 스타일 대체 문자를 제공하는 추가 문자 모양이 포함되어 있습니다. 다음 텍스트는 스타일 대체 문자 모양을 표시합니다.  
  
 ![OpenType 스타일 대체 문자를 사용 하 여 텍스트](../../../../docs/framework/wpf/advanced/media/opentypefont02.gif "opentypefont02")  
OpenType 스타일 대체 문자 모양을 사용하는 텍스트  
  
 선단 장식은 종종 붓글씨와 관련된 정교한 장식을 사용하는 장식용 문자 모양입니다. 다음 텍스트는 Pescadero 글꼴의 표준 및 선단 장식 문자 모양을 표시합니다.  
  
 ![OpenType 표준 및 선단 장식 문자 모양을 사용 하 여 텍스트](../../../../docs/framework/wpf/advanced/media/opentypefont08.gif "opentypefont08")  
OpenType 표준 및 선단 장식 문자 모양을 사용하는 텍스트  
  
 [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] 기능에 대한 자세한 내용은 [OpenType 글꼴 기능](../../../../docs/framework/wpf/advanced/opentype-font-features.md)을 참조하세요.  
  
<a name="Enhanced_International_Text_Support"></a>   
## <a name="enhanced-international-text-support"></a>향상된 국가별 텍스트 지원  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 다음과 같은 기능을 제공하여 향상된 국가별 텍스트를 지원합니다.  
  
-   모든 쓰기 시스템에서 적응형 단위를 사용하는 자동 줄 간격.  
  
-   광범위한 국가별 텍스트 지원. 자세한 내용은 [WPF의 세계화](../../../../docs/framework/wpf/advanced/globalization-for-wpf.md)를 참조하세요.  
  
-   언어 기반 줄 바꿈, 하이픈 및 양쪽 맞춤.  
  
<a name="Enhanced_Font_Support"></a>   
## <a name="enhanced-font-support"></a>향상된 글꼴 지원  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 다음과 같은 기능을 제공하여 향상된 글꼴을 지원합니다.  
  
-   모든 텍스트에 대한 유니코드. 글꼴 동작 및 선택에 문자 집합이나 코드 페이지가 더 이상 필요하지 않습니다.  
  
-   시스템 로캘과 같이 전역 설정에 독립적인 글꼴 동작.  
  
-   별도 <xref:System.Windows.FontWeight>, <xref:System.Windows.FontStretch>, 및 <xref:System.Windows.FontStyle> 형식을 정의 하기 위한는 <xref:System.Windows.Media.FontFamily>합니다. [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] 프로그래밍에서보다 더 많은 유연성을 제공하며, 기울임꼴과 굵게의 부울 조합을 사용하여 글꼴 패밀리를 정의합니다.  
  
-   글꼴 이름과 독립적으로 처리되는 쓰기 방향(가로 및 세로).  
  
-   [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)] 파일에서 합성 글꼴 기술을 사용하여 글꼴 연결 및 글꼴 대체. 합성 글꼴은 모든 범위의 다국어 글꼴 생성을 허용합니다. 또한 합성 글꼴은 없는 문자 모양을 표시하지 않는 메커니즘을 제공합니다. 자세한 내용은의 설명을 참조는 <xref:System.Windows.Media.FontFamily> 클래스입니다.  
  
-   단일 언어 글꼴 그룹을 사용하여 합성 글꼴에서 국가별 글꼴 작성. 따라서 여러 언어에 대한 글꼴을 개발할 때 리소스 비용이 절감됩니다.  
  
-   합성 글꼴을 문서에 포함하여 문서에 이식성 제공. 자세한 내용은의 설명을 참조는 <xref:System.Windows.Media.FontFamily> 클래스입니다.  
  
<a name="New_Text_APIs"></a>   
## <a name="new-text-application-programming-interfaces-apis"></a>새 텍스트 API(응용 프로그래밍 인터페이스)  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 응용 프로그램에 텍스트를 포함할 때 개발자가 사용할 여러 가지 텍스트 [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]를 제공합니다. 이러한 [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]는 세 가지 범주로 그룹화됩니다.  
  
-   **레이아웃 및 사용자 인터페이스**. [!INCLUDE[TLA#tla_gui](../../../../includes/tlasharptla-gui-md.md)]에 대한 일반적인 텍스트 컨트롤입니다.  
  
-   **간단한 텍스트 그리기**. 개체에 직접 텍스트를 그릴 수 있습니다.  
  
-   **고급 텍스트 서식 지정**. 사용자 지정 텍스트 엔진을 구현할 수 있습니다.  
  
### <a name="layout-and-user-interface"></a>레이아웃 및 사용자 인터페이스  
 가장 높은 수준의 기능을 텍스트에서 [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] 일반적인 제공 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 와 같은 컨트롤 <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.TextBlock>, 및 <xref:System.Windows.Controls.TextBox>합니다. 이러한 컨트롤은 응용 프로그램 내에서 기본 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 요소를 제공하며, 텍스트를 제공하고 텍스트와 상호 작용하는 쉬운 방법을 제공합니다. 와 같은 컨트롤 <xref:System.Windows.Controls.RichTextBox> 및 <xref:System.Windows.Controls.PasswordBox> 더 고급 또는 텍스트 처리 특수화 사용 합니다. 와 같은 클래스 <xref:System.Windows.Documents.TextRange>, <xref:System.Windows.Documents.TextSelection>, 및 <xref:System.Windows.Documents.TextPointer> 유용한 텍스트 조작 합니다. 이러한 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 컨트롤 속성을와 같은 제공 <xref:System.Windows.Controls.Control.FontFamily%2A>, <xref:System.Windows.Controls.Control.FontSize%2A>, 및 <xref:System.Windows.Controls.Control.FontStyle%2A>, 텍스트를 렌더링 하는 데 사용 되는 글꼴을 제어할 수 있도록 합니다.  
  
#### <a name="using-bitmap-effects-transforms-and-text-effects"></a>비트맵 효과, 변환 및 텍스트 효과 사용  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에서는 비트맵 효과, 변환 및 텍스트 효과 같은 기능을 사용하여 시각적으로 흥미로운 텍스트를 만들 수 있습니다. 다음 예제에서는 일반적인 형식의 그림자 효과가 적용된 텍스트를 보여 줍니다.  
  
 ![Softness 인 텍스트 그림자 &#61; 0.25](../../../../docs/framework/wpf/advanced/media/shadowtext01.jpg "ShadowText01")  
그림자가 적용된 텍스트  
  
 다음 예제에서는 그림자 효과와 노이즈가 적용된 텍스트를 보여 줍니다.  
  
 ![노이즈가 있는 텍스트 그림자](../../../../docs/framework/wpf/advanced/media/shadowtext04.jpg "ShadowText04")  
그림자와 노이즈가 적용된 텍스트  
  
 다음 예제에서는 후광 효과가 적용된 텍스트를 보여 줍니다.  
  
 ![OuterGlowBitmapEffect를 사용한 텍스트 그림자](../../../../docs/framework/wpf/advanced/media/shadowtext05.jpg "ShadowText05")  
후광 효과가 적용된 텍스트  
  
 다음 예제에서는 흐림 효과가 적용된 텍스트를 보여 줍니다.  
  
 ![BlurBitmapEffect를 사용한 텍스트 그림자](../../../../docs/framework/wpf/advanced/media/shadowtext06.jpg "ShadowText06")  
흐리게 효과가 적용된 텍스트  
  
 다음 예에서는 텍스트의 두 번째 라인은 x축을 따라 배율을 150% 조정하여 보여주고, 텍스트의 세 번째 라인은 y축을 따라 배율을 150% 조정하여 보여줍니다.  
  
 ![ScaleTransform을 사용 하 여 배율 조정 된 텍스트](../../../../docs/framework/wpf/advanced/media/transformedtext02.jpg "TransformedText02")  
ScaleTransform을 사용한 텍스트  
  
 다음 예에서는 x축을 따라 기울어진 텍스트를 보여줍니다.  
  
 ![SkewTransform을 사용 하 여 기울인 텍스트](../../../../docs/framework/wpf/advanced/media/transformedtext03.jpg "TransformedText03")  
SkewTransform을 사용한 텍스트  
  
 A <xref:System.Windows.Media.TextEffect> 개체는 텍스트 문자열의 문자 하나 이상의 그룹으로 텍스트를 처리할 수 있는 도우미 개체입니다. 다음 예제에서는 개별 문자가 회전되는 것을 보여 줍니다. 각 문자는 1초 간격으로 개별적으로 회전합니다.  
  
 ![텍스트 효과 회전 텍스트의 스크린 샷](../../../../docs/framework/wpf/advanced/media/texteffect01.jpg "TextEffect01")  
회전 텍스트 효과 애니메이션의 예  
  
#### <a name="using-flow-documents"></a>유동 문서 사용  
 공통 외에도 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 컨트롤 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 텍스트 표현에는 레이아웃 컨트롤을 제공 합니다.-는 <xref:System.Windows.Documents.FlowDocument> 요소입니다. <xref:System.Windows.Documents.FlowDocument> 요소와 함께에서 <xref:System.Windows.Controls.DocumentViewer> 요소를 레이아웃 요구를 다양 한으로 텍스트의 양이 많은 컨트롤을 제공 합니다. 통해 고급 입력 체계에 대 한 액세스를 제공 하는 레이아웃 컨트롤은 <xref:System.Windows.Documents.Typography> 개체와 다른 글꼴 관련 속성 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 컨트롤입니다.  
  
 다음 예제에서 호스트 되는 텍스트 콘텐츠는 <xref:System.Windows.Controls.FlowDocumentReader>, 검색, 탐색, 페이지 매김, 및 콘텐츠 크기 조정 지원을 제공 합니다.  
  
 ![OpenType 글꼴 사용 샘플 스크린 샷](../../../../docs/framework/wpf/advanced/media/typographyinwpf-03.png "TypographyInWPF_03")  
FlowDocumentReader에서 호스트되는 텍스트  
  
 자세한 내용은 [WPF의 문서](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)를 참조하세요.  
  
### <a name="lightweight-text-drawing"></a>간단한 텍스트 그리기  
 에 직접 텍스트를 그릴 수 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 사용 하 여 개체는 <xref:System.Windows.Media.DrawingContext.DrawText%2A> 의 메서드는 <xref:System.Windows.Media.DrawingContext> 개체입니다. 이 메서드를 사용 하려면 만듭니다는 <xref:System.Windows.Media.FormattedText> 개체입니다. 이 개체를 사용하면 여러 줄 텍스트를 그릴 수 있으며 이 텍스트에 있는 각 문자의 서식은 개별적으로 지정할 수 있습니다. 기능은 <xref:System.Windows.Media.FormattedText> 대부분의 Win32 API에서 DrawText 플래그의 기능을 포함 하는 개체입니다. 또한는 <xref:System.Windows.Media.FormattedText> 예: 텍스트의 범위를 초과 하는 경우 줄임표가 표시 되는 줄임표 지원 기능을 포함 하는 개체입니다. 다음 예제에서는 두 번째와 세 번째 단어에 적용된 선형 그라데이션을 포함하여 여러 서식이 적용된 텍스트를 보여 줍니다.  
  
 ![FormattedText 개체를 사용 하 여 표시 되는 텍스트](../../../../docs/framework/wpf/advanced/media/formattedtext01.jpg "FormattedText01")  
FormattedText 개체를 사용하여 표시한 텍스트  
  
 서식 있는 텍스트를 변환할 수 있습니다 <xref:System.Windows.Media.Geometry> 개체를 다른 형식의 텍스트를 흥미로운 시각적으로 만들 수 있습니다. 예를 들어, 만들 수는 <xref:System.Windows.Media.Geometry> 텍스트 문자열의 윤곽선을 기반으로 하는 개체입니다.  
  
 ![선형 그라데이션 브러시를 사용 하 여 텍스트 윤곽선](../../../../docs/framework/wpf/advanced/media/outlinedtext02.jpg "OutlinedText02")  
선형 그라데이션 브러시를 사용하여 표시한 텍스트 윤곽선  
  
 다음 예에서는 변환된 텍스트의 스트로크, 채우기 및 강조 표시를 수정하여 시각적으로 흥미로운 시각 효과를 만드는 여러 방법에 대해 설명합니다.  
  
 ![채우기와 스트로크에 다른 색으로 텍스트](../../../../docs/framework/wpf/advanced/media/outlinedtext03.jpg "OutlinedText03")  
스트로크와 채우기를 다른 색상으로 설정하는 예  
  
 ![스트로크에 이미지 브러시가 적용 된 텍스트](../../../../docs/framework/wpf/advanced/media/outlinedtext04.jpg "OutlinedText04")  
스트로크에 적용한 이미지 브러시의 예  
  
 ![스트로크에 이미지 브러시가 적용 된 텍스트](../../../../docs/framework/wpf/advanced/media/outlinedtext05.jpg "OutlinedText05")  
스트로크와 강조 표시에 적용된 이미지 브러시의 예  
  
 대 한 자세한 내용은 <xref:System.Windows.Media.FormattedText> 개체, 참조 [그리기 형식의 텍스트](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md)합니다.  
  
### <a name="advanced-text-formatting"></a>고급 텍스트 서식 지정  
 텍스트의 고급 회원 가장 [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)], [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 를 사용 하 여 사용자 지정 텍스트 레이아웃을 만들 수는 기능을 제공는 <xref:System.Windows.Media.TextFormatting.TextFormatter> 개체와 다른 형식에는 <xref:System.Windows.Media.TextFormatting> 네임 스페이스입니다. <xref:System.Windows.Media.TextFormatting.TextFormatter> 및 문자 형식으로 단락 스타일을 사용자 고유의 정의 지 원하는 사용자 지정 텍스트 레이아웃을 구현할 수 줄 바꿈 규칙 및 국제 텍스트에 대 한 다른 레이아웃 기능 관련된 클래스를 사용 합니다. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 텍스트 레이아웃 지원의 기본 구현을 재정의하려는 경우는 거의 없습니다. 그러나 텍스트 편집 컨트롤이나 응용 프로그램을 만들려는 경우 기본 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 구현이 아닌 다른 구현이 필요할 수 있습니다.  
  
 일반 텍스트와 달리 [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)], <xref:System.Windows.Media.TextFormatting.TextFormatter> 콜백 메서드의 집합을 통해 텍스트 레이아웃 클라이언트와 상호 작용 합니다. 클라이언트의 구현에서 이러한 메서드를 제공할 필요는 <xref:System.Windows.Media.TextFormatting.TextSource> 클래스입니다. 다음 다이어그램에서는 클라이언트 응용 프로그램 간의 텍스트 레이아웃 상호 작용 및 <xref:System.Windows.Media.TextFormatting.TextFormatter>합니다.  
  
 ![텍스트 레이아웃 클라이언트 및 TextFormatter의 다이어그램](../../../../docs/framework/wpf/advanced/media/textformatter01.png "TextFormatter01")  
응용 프로그램과 TextFormatter 간의 상호 작용  
  
 사용자 지정 텍스트 레이아웃을 만드는 방법에 대한 자세한 내용은 [고급 텍스트 서식 지정](../../../../docs/framework/wpf/advanced/advanced-text-formatting.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Media.FormattedText>  
 <xref:System.Windows.Media.TextFormatting.TextFormatter>  
 [ClearType 개요](../../../../docs/framework/wpf/advanced/cleartype-overview.md)  
 [OpenType 글꼴 기능](../../../../docs/framework/wpf/advanced/opentype-font-features.md)  
 [서식 있는 텍스트 그리기](../../../../docs/framework/wpf/advanced/drawing-formatted-text.md)  
 [고급 텍스트 서식 지정](../../../../docs/framework/wpf/advanced/advanced-text-formatting.md)  
 [텍스트](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)  
 [Microsoft 입력 체계](http://www.microsoft.com/typography/default.mspx)
