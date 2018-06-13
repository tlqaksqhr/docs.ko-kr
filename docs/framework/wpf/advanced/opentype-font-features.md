---
title: OpenType 글꼴 기능
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [WPF], OpenType
- typography [WPF], OpenType font technology
- OpenType font technology [WPF]
ms.assetid: 4061a9d1-fe8b-4921-9e17-18ec7d2e3ea2
ms.openlocfilehash: a8ee4107ee7db20f2948ea9a33ef853815a22665
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33549606"
---
# <a name="opentype-font-features"></a>OpenType 글꼴 기능
이 항목에서는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]에 있는 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 글꼴 기술의 주요 기능 일부에 대한 개요를 제공합니다.  
  

  
<a name="overview"></a>   
## <a name="opentype-font-format"></a>OpenType 글꼴 서식  
 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 글꼴 서식은 PostScript 글꼴 데이터에 대한 지원을 추가하는 [!INCLUDE[TLA#tla_truetype](../../../../includes/tlasharptla-truetype-md.md)] 글꼴 서식의 확장입니다. [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 글꼴 서식은 [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)]와 Adobe Corporation이 공동으로 개발했습니다. [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 글꼴 및 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 글꼴을 지원하는 운영 체제 서비스는 글꼴에 포함된 윤곽선이 [!INCLUDE[TLA2#tla_truetype](../../../../includes/tla2sharptla-truetype-md.md)] 윤곽선인지 아니면 CFF(PostScript) 윤곽선인지에 관계없이 글꼴을 설치하여 사용하는 간단한 방법을 사용자에게 제공합니다.  
  
 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 글꼴 서식은 다음과 같이 개발자 문제를 해결합니다.  
  
-   광범위한 다중 플랫폼 지원  
  
-   국가별 문자 집합에 대한 지원 향상  
  
-   글꼴 데이터 보호 향상  
  
-   보다 효율적인 글꼴 배포를 위한 파일 크기 축소  
  
-   고급 입력 체계 컨트롤을 위한 폭넓은 지원  
  
> [!NOTE]
>  Windows SDK에는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 응용 프로그램과 함께 사용할 수 있는 샘플 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 글꼴 집합이 포함되어 있습니다. 이 글꼴에서는 이 항목의 나머지 부분에서 보여 주는 대부분의 기능이 제공됩니다. 자세한 내용은 [샘플 OpenType 글꼴 팩](../../../../docs/framework/wpf/advanced/sample-opentype-font-pack.md)을 참조하세요.  
  
 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 글꼴 서식에 대한 자세한 내용은 [OpenType 사양](http://go.microsoft.com/fwlink/?LinkId=96731)을 참조하세요.  
  
### <a name="advanced-typographic-extensions"></a>고급 입력 체계 확장  
 고급 입력 체계 표([!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 레이아웃 표)는 [!INCLUDE[TLA2#tla_truetype](../../../../includes/tla2sharptla-truetype-md.md)] 또는 CFF 윤곽선으로 글꼴 기능을 확장합니다. [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 레이아웃 글꼴에는 고품질 국제 입력 체계를 지원하도록 글꼴 기능을 확장하는 추가 정보가 들어 있습니다. 대부분의 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 글꼴은 사용 가능한 전체 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 기능 중 하위 집합만 노출합니다. [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 글꼴은 다음과 같은 기능을 제공합니다.  
  
-   합자, 위치 형식, 대체 문자 및 기타 글꼴 대체를 지원하는 문자와 문자 모양 간의 다양한 매핑  
  
-   2차원 위치 지정 및 문자 모양 첨부 지원  
  
-   명시적인 스크립트 및 언어 정보가 글꼴에 포함되어 텍스트 처리 응용 프로그램에서 동작을 조정할 수 있습니다.  
  
 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 사양의 [“글꼴 파일 표”](http://www.microsoft.com/typography/otspec/otff.htm) 섹션에서 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 레이아웃 표에 대해 자세히 설명합니다.  
  
 이 개요의 나머지 부분에서는 확장성과 유연성 몇 가지 시각적으로 흥미로운 소개 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 의 속성에 의해 노출 되는 기능은 <xref:System.Windows.Documents.Typography> 개체입니다. 이 개체에 대한 자세한 내용은 [입력 체계 클래스](#typography_class)를 참조하세요.  
  
<a name="variants"></a>   
## <a name="variants"></a>변형  
 변형은 위 첨자 및 아래 첨자와 같은 다양한 입력 체계 스타일을 렌더링하는 데 사용됩니다.  
  
### <a name="superscripts-and-subscripts"></a>위 첨자 및 아래 첨자  
 <xref:System.Windows.Documents.Typography.Variants%2A> 속성의 오른쪽 위 아래 값을 설정할 수 있습니다는 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 글꼴입니다.  
  
 다음 텍스트는 Palatino Linotype 글꼴의 위 첨자를 표시합니다.  
  
 ![OpenType 위 첨자를 사용 하 여 텍스트](../../../../docs/framework/wpf/advanced/media/opentypefont14.gif "opentypefont14")  
OpenType 위 첨자를 사용하는 텍스트  
  
 속성을 사용 하 여은 글꼴에 대 한 위 첨자를 정의 하는 방법을 보여 주는 다음 태그 예제는 <xref:System.Windows.Documents.Typography> 개체입니다.  
  
 [!code-xaml[OpenTypeFontSamples#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#12)]  
  
 다음 텍스트는 Palatino Linotype 글꼴의 아래 첨자를 표시합니다.  
  
 ![OpenType 아래 첨자를 사용 하 여 텍스트](../../../../docs/framework/wpf/advanced/media/opentypefont15.gif "opentypefont15")  
OpenType 아래 첨자를 사용하는 텍스트  
  
 속성을 사용 하 여은 글꼴에 대 한 첨자를 정의 하는 방법을 보여 주는 다음 태그 예제는 <xref:System.Windows.Documents.Typography> 개체입니다.  
  
 [!code-xaml[OpenTypeFontSamples#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#13)]  
  
### <a name="decorative-uses-of-superscripts-and-subscripts"></a>위 첨자 및 아래 첨자의 장식 사용  
 위 첨자와 아래 첨자를 사용하여 대/소문자 혼용 텍스트의 장식 효과를 만들 수도 있습니다. 다음 텍스트는 Palatino Linotype 글꼴의 위 첨자 및 아래 첨자 텍스트를 표시합니다. 대문자는 영향을 받지 않습니다.  
  
 ![OpenType 위 첨자 및 아래 첨자를 사용 하 여 텍스트](../../../../docs/framework/wpf/advanced/media/opentypefont16.gif "opentypefont16")  
OpenType 위 첨자 및 아래 첨자를 사용하는 텍스트  
  
 위 첨자 및 아래 첨자의 속성을 사용 하 여 글꼴을 정의 하는 방법을 보여 주는 다음 태그 예제는 <xref:System.Windows.Documents.Typography> 개체입니다.  
  
 [!code-xaml[OpenTypeFontSamples#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#14)]  
  
<a name="capitals"></a>   
## <a name="capitals"></a>대문자  
 대문자는 대문자 스타일의 문자 모양으로 텍스트를 렌더링하는 일련의 입력 체계 형식입니다. 일반적으로 텍스트를 모두 대문자로 렌더링하면 글자 사이의 간격이 너무 좁아 보이고 글자의 무게와 비율상 너무 무거워 보일 수 있습니다. [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]은 작은 대문자, 꼬마 대문자, 제목 및 대문자 간격을 비롯하여 대문자에 대한 여러 가지 스타일 서식을 지원합니다. 이러한 스타일 서식을 사용하여 대문자 모양을 제어할 수 있습니다.  
  
 다음 텍스트는 “SmallCaps” 및 “AllSmallCaps”로 스타일이 지정된 문자 앞에 Pescadero 글꼴의 표준 대문자를 표시합니다. 이 경우 세 단어 모두 동일한 글꼴 크기가 사용됩니다.  
  
 ![OpenType 대문자를 사용 하 여 텍스트](../../../../docs/framework/wpf/advanced/media/opentypefont11.gif "opentypefont11")  
OpenType 대문자를 사용하는 텍스트  
  
 속성을 사용 하는 간격과 대문자를 정의 하는 방법을 보여 주는 다음 태그 예제는 <xref:System.Windows.Documents.Typography> 개체입니다. “SmallCaps” 형식을 사용하는 경우 선행 대문자는 무시됩니다.  
  
 [!code-xaml[OpenTypeFontSamples#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#9)]  
  
### <a name="titling-capitals"></a>제목 대문자  
 제목 대문자는 무게와 비율이 더 가볍고 일반 대문자보다 세련된 느낌을 주도록 디자인되었습니다. 제목 대문자는 일반적으로 큰 글꼴 크기의 머리글로 사용됩니다. 다음 텍스트는 Pescadero 글꼴의 일반 대문자 및 제목 대문자를 표시합니다. 두 번째 줄에 있는 텍스트의 획(stem) 너비가 더 좁은 것을 확인할 수 있습니다.  
  
 ![OpenType 제목 대문자를 사용 하 여 텍스트](../../../../docs/framework/wpf/advanced/media/opentypefont20.gif "OpenTypeFont20")  
OpenType 제목 대문자를 사용하는 텍스트  
  
 속성을 사용 하는 간격과 제목 대문자를 정의 하는 방법을 보여 주는 다음 태그 예제는 <xref:System.Windows.Documents.Typography> 개체입니다.  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet17](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet17)]  
  
### <a name="capital-spacing"></a>대문자 간격  
 대문자 간격은 텍스트에서 모두 대문자를 사용할 때 더 넓은 간격을 제공할 수 있도록 하는 기능입니다. 대문자는 대개 소문자와 함께 사용하도록 디자인되었습니다. 대문자와 소문자 사이에서는 적절해 보이는 간격이 모두 대문자를 사용할 때는 너무 좁게 보일 수 있습니다. 다음 텍스트는 Pescadero 글꼴의 일반 간격 및 대문자 간격을 표시합니다.  
  
 ![OpenType 대문자 간격을 사용 하 여 텍스트](../../../../docs/framework/wpf/advanced/media/opentypefont21.gif "OpenTypeFont21")  
OpenType 대문자 간격을 사용하는 텍스트  
  
 속성을 사용 하는 간격과의 대문자 간격을 정의 하는 방법을 보여 주는 다음 태그 예제는 <xref:System.Windows.Documents.Typography> 개체입니다.  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet18](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet18)]  
  
<a name="ligatures"></a>   
## <a name="ligatures"></a>합자  
 합자는 읽기 쉽거나 보기 좋은 텍스트를 만들기 위해 단일 문자 모양으로 구성된 두 개 이상의 문자 모양입니다. [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 글꼴은 네 가지 형식의 합자를 지원합니다.  
  
-   **표준 합자**. 가독성을 향상시키기 위해 디자인되었습니다. 표준 합자에는 “fi”, “fl” 및 “ff”가 포함됩니다.  
  
-   **컨텍스트 합자**. 합자를 구성하는 문자 간에 더 나은 결합 동작을 제공하여 가독성을 높이도록 디자인되었습니다.  
  
-   **임의 합자**. 장식용으로 디자인되었으며 가독성을 위해 별도로 디자인된 것은 아닙니다.  
  
-   **기록 합자**. 기록용으로 디자인되었으며 가독성을 위해 별도로 디자인된 것은 아닙니다.  
  
 다음 텍스트는 Pericles 글꼴에 대한 표준 합자 문자 모양을 표시합니다.  
  
 ![OpenType 표준 합자를 사용 하 여 텍스트](../../../../docs/framework/wpf/advanced/media/opentypefont04.gif "opentypefont04")  
OpenType 표준 합자를 사용하는 텍스트  
  
 속성을 사용 하 여은 글꼴에 대 한 표준 합자 문자 모양을 정의 하는 방법을 보여 주는 다음 태그 예제는 <xref:System.Windows.Documents.Typography> 개체입니다.  
  
 [!code-xaml[OpenTypeFontSamples#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#4)]  
  
 다음 텍스트는 Pericles 글꼴의 임의 합자 문자 모양을 표시합니다.  
  
 ![OpenType 임의 합자를 사용 하 여 텍스트](../../../../docs/framework/wpf/advanced/media/opentypefont05.gif "opentypefont05")  
OpenType 임의 합자를 사용하는 텍스트  
  
 속성을 사용 하 여은 글꼴에 대 한 임의 합자 문자 모양을 정의 하는 방법을 보여 주는 다음 태그 예제는 <xref:System.Windows.Documents.Typography> 개체입니다.  
  
 [!code-xaml[OpenTypeFontSamples#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#5)]  
  
 기본적으로 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]의 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 글꼴은 표준 합자를 사용합니다. 예를 들어 Palatino Linotype 글꼴을 사용하면 표준 합자 “fi”, “ff”및 “fl”이 결합된 문자 모양으로 나타납니다. 각 표준 합자의 문자 쌍이 서로 붙어 있음을 확인할 수 있습니다.  
  
 ![OpenType 표준 합자를 사용 하 여 텍스트](../../../../docs/framework/wpf/advanced/media/opentypefont06.gif "opentypefont06")  
OpenType 표준 합자를 사용하는 텍스트  
  
 그러나 표준 합자 기능을 사용하지 않도록 설정하여 “ff”와 같이 표준 합자가 결합된 문자 모양이 아닌 두 개의 별도 문자 모양으로 표시되도록 할 수 있습니다.  
  
 ![OpenType 표준 합자를 사용 하 여 텍스트 사용할 수 없게](../../../../docs/framework/wpf/advanced/media/opentypefont07.gif "opentypefont07")  
비활성화된 OpenType 표준 합자를 사용하는 텍스트  
  
 속성을 사용 하 여은 글꼴에 대 한 표준 합자 문자 모양을 사용 하지 않도록 설정 하는 방법을 보여 주는 다음 태그 예제는 <xref:System.Windows.Documents.Typography> 개체입니다.  
  
 [!code-xaml[OpenTypeFontSamples#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#6)]  
  
<a name="swashes"></a>   
## <a name="swashes"></a>선단 장식  
 선단 장식은 종종 붓글씨와 관련된 정교한 장식을 사용하는 장식용 문자 모양입니다. 다음 텍스트는 Pescadero 글꼴의 표준 및 선단 장식 문자 모양을 표시합니다.  
  
 ![OpenType 표준 및 선단 장식 문자 모양을 사용 하 여 텍스트](../../../../docs/framework/wpf/advanced/media/opentypefont08.gif "opentypefont08")  
OpenType 표준 및 선단 장식 문자 모양을 사용하는 텍스트  
  
 선단 장식은 종종 이벤트 발표와 같은 짧은 문장에서 장식 요소로 사용됩니다. 다음 텍스트는 선단 장식을 사용하여 이벤트 이름의 대문자를 강조합니다.  
  
 ![OpenType 선단 장식을 사용 하 여 텍스트](../../../../docs/framework/wpf/advanced/media/opentypefont09.gif "opentypefont09")  
OpenType 선단 장식을 사용하는 텍스트  
  
 선단 장식을 속성을 사용 하는 글꼴에 대 한 정의 하는 방법을 보여 주는 다음 태그 예제는 <xref:System.Windows.Documents.Typography> 개체입니다.  
  
 [!code-xaml[OpenTypeFontSamples#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#7)]  
  
### <a name="contextual-swashes"></a>컨텍스트 선단 장식  
 특정 조합의 선단 장식 문자 모양은 인접 문자에 내림 영자가 겹치는 것과 같이 보기 좋지 않은 모양이 될 수 있습니다. 컨텍스트 선단 장식을 사용하면 더 좋은 모양을 만드는 대체 선단 장식 문자 모양을 사용할 수 있습니다. 다음 텍스트는 동일한 단어에 컨텍스트 선단 장식이 적용되기 전후의 모습을 보여 줍니다.  
  
 ![OpenType 컨텍스트 선단 장식을 사용 하 여 텍스트](../../../../docs/framework/wpf/advanced/media/opentypefont19.gif "OpenTypeFont19")  
OpenType 컨텍스트 선단 장식을 사용하는 텍스트  
  
 속성을 사용 하는 간격과 컨텍스트 선단 장식을 정의 하는 방법을 보여 주는 다음 태그 예제는 <xref:System.Windows.Documents.Typography> 개체입니다.  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet16)]  
  
<a name="alternates"></a>   
## <a name="alternates"></a>대체 문자  
 대체 문자는 표준 문자 모양으로 대체될 수 있는 문자 모양입니다. 다음 예제에서 사용된 Pericles 글꼴과 같은 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 글꼴에는 텍스트의 다른 모양을 만드는 데 사용할 수 있는 대체 문자 모양이 포함될 수 있습니다. 다음 텍스트는 Pericles 글꼴의 표준 문자 모양을 표시합니다.  
  
 ![OpenType 표준 문자 모양을 사용 하 여 텍스트](../../../../docs/framework/wpf/advanced/media/opentypefont01.gif "opentypefont01")  
OpenType 표준 문자 모양을 사용하는 텍스트  
  
 Pericles [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 글꼴에는 표준 문자 모양 집합에 스타일 대체 문자를 제공하는 추가 문자 모양이 포함되어 있습니다. 다음 텍스트는 스타일 대체 문자 모양을 표시합니다.  
  
 ![OpenType 스타일 대체 문자를 사용 하 여 텍스트](../../../../docs/framework/wpf/advanced/media/opentypefont02.gif "opentypefont02")  
OpenType 스타일 대체 문자 모양을 사용하는 텍스트  
  
 속성을 사용 하 여은 글꼴 스타일 대체 문자 모양을 정의 하는 방법을 보여 주는 다음 태그 예제는 <xref:System.Windows.Documents.Typography> 개체입니다.  
  
 [!code-xaml[OpenTypeFontSamples#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#2)]  
  
 다음 텍스트는 Pericles 글꼴에 대한 여러 가지 다른 스타일 대체 문자 모양을 표시합니다.  
  
 ![OpenType 스타일 대체 문자를 사용 하 여 텍스트](../../../../docs/framework/wpf/advanced/media/opentypefont03.gif "opentypefont03")  
OpenType 스타일 대체 문자 모양을 사용하는 텍스트  
  
 다음 태그 예제에서는 이러한 다른 스타일 대체 문자 모양을 정의하는 방법을 보여 줍니다.  
  
 [!code-xaml[OpenTypeFontSamples#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#3)]  
  
### <a name="random-contextual-alternates"></a>임의 컨텍스트 대체 문자  
 임의 컨텍스트 대체 문자는 단일 문자에 대해 여러 개의 대체 문자 모양을 제공합니다. 이 기능은 스크립트 유형의 글꼴로 구현될 때 임의로 선택한 외관상 약간 다른 문자 집합을 사용하여 필기를 시뮬레이트할 수 있습니다. 다음 텍스트는 Lindsey 글꼴에 대한 임의 컨텍스트 대체 문자를 사용합니다. 문자 “a”의 모양이 약간 다른 것을 확인할 수 있습니다.  
  
 ![OpenType 임의 컨텍스트 대체를 사용 하 여 텍스트](../../../../docs/framework/wpf/advanced/media/opentypefont23.gif "OpenTypeFont23")  
OpenType 임의 컨텍스트 대체 항목을 사용한 텍스트  
  
 속성을 사용 하 여 Lindsey 글꼴에 대 한 임의 컨텍스트 대체 항목을 정의 하는 방법을 보여 주는 다음 태그 예제는 <xref:System.Windows.Documents.Typography> 개체입니다.  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/Window1.xaml#opentypefontsnippet20)]  
  
### <a name="historical-forms"></a>기록 형식  
 기록 형식은 과거에는 일반적이었던 입력 체계 규칙입니다. 다음 텍스트는 Palatino Linotype 글꼴에 대한 기록 형식 문자 모양을 사용하여 “Boston, Massachusetts” 구문을 표시합니다.  
  
 ![OpenType 기록 폼을 사용 하 여 텍스트](../../../../docs/framework/wpf/advanced/media/opentypefont10.gif "opentypefont10")  
OpenType 기록 폼을 사용하는 텍스트  
  
 속성을 사용 하 여은 글꼴에 대 한 기록 폼을 정의 하는 방법을 보여 주는 다음 태그 예제는 <xref:System.Windows.Documents.Typography> 개체입니다.  
  
 [!code-xaml[OpenTypeFontSamples#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#8)]  
  
<a name="numerical_styles"></a>   
## <a name="numerical-styles"></a>숫자 스타일  
 OpenType 글꼴은 텍스트의 숫자 값으로 사용할 수 있는 많은 기능을 지원합니다.  
  
### <a name="fractions"></a>소수  
 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 글꼴은 슬래시를 사용하거나 위아래로 표현된 분수 스타일을 지원합니다.  
  
 다음 텍스트는 Palatino Linotype 글꼴의 분수 스타일을 표시합니다.  
  
 ![OpenType를 사용 하 여 텍스트의 슬래시 및 상하 형 분수](../../../../docs/framework/wpf/advanced/media/opentypefont12.gif "opentypefont12")  
OpenType 슬래시 및 상하형 분수를 사용하는 텍스트  
  
 분수의 속성을 사용 하 여은 글꼴 스타일을 정의 하는 방법을 보여 주는 다음 태그 예제는 <xref:System.Windows.Documents.Typography> 개체입니다.  
  
 [!code-xaml[OpenTypeFontSamples#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#10)]  
  
### <a name="old-style-numerals"></a>이전 스타일 숫자  
 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 글꼴은 이전 스타일 숫자 형식을 지원합니다. 이 형식은 더 이상 표준이 아닌 스타일의 숫자를 표시할 때 유용합니다. 다음 텍스트는 Palatino Linotype 글꼴의 표준 및 이전 스타일 숫자 형식으로 된 18세기 날짜를 표시합니다.  
  
 ![OpenType 이전 스타일 숫자를 사용 하 여 텍스트](../../../../docs/framework/wpf/advanced/media/opentypefont24.gif "OpenTypeFont24")  
OpenType 이전 스타일 숫자를 사용하는 텍스트  
  
 다음 텍스트는 Palatino Linotype 글꼴의 표준 숫자 뒤에 이전 스타일 숫자를 표시합니다.  
  
 ![OpenType 이전 스타일 숫자 집합을 사용 하 여 텍스트](../../../../docs/framework/wpf/advanced/media/opentypefont13.gif "opentypefont13")  
OpenType의 이전 스타일 숫자 집합을 사용하는 텍스트  
  
 속성을 사용 하 여은 글꼴에 대 한 이전 스타일 숫자를 정의 하는 방법을 보여 주는 다음 태그 예제는 <xref:System.Windows.Documents.Typography> 개체입니다.  
  
 [!code-xaml[OpenTypeFontSamples#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#11)]  
  
### <a name="proportional-and-tabular-figures"></a>가변 폭 및 테이블 형식 숫자  
 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 글꼴은 숫자를 사용할 때 너비 정렬을 제어하기 위해 가변 폭 및 테이블 형식 숫자 기능을 지원합니다. 가변 폭 숫자는 각 숫자의 너비를 다르게 처리합니다. 예를 들어 “1”은 “5”보다 너비가 좁습니다. 테이블 형식 숫자는 같은 너비의 숫자로 처리되어 세로로 정렬되므로 금융 형식 정보의 가독성이 높아집니다.  
  
 다음 텍스트는 Miramonte 글꼴을 사용하여 첫 번째 열에 두 개의 가변 폭 숫자를 표시합니다. 숫자 “5”와 “1” 사이의 너비 차이를 확인할 수 있습니다. 두 번째 열은 테이블 형식 숫자 기능을 사용하여 너비가 조정된 동일한 두 개의 숫자 값을 보여 줍니다.  
  
 ![OpenType 가변 폭 및 표 형식 숫자를 사용 하 여 텍스트](../../../../docs/framework/wpf/advanced/media/opentypefont22.gif "OpenTypeFont22")  
OpenType 가변 폭 및 테이블 형식 숫자를 사용하는 텍스트  
  
 속성을 사용 하 여은 글꼴, 숫자와 테이블 형식 숫자를 정의 하는 방법을 보여 주는 다음 태그 예제는 <xref:System.Windows.Documents.Typography> 개체입니다.  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/Window1.xaml#opentypefontsnippet19)]  
  
### <a name="slashed-zero"></a>슬래시 0  
 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 글꼴은 문자 “O”와 숫자 “0”의 차이를 강조하기 위해 슬래시 0 숫자 형식을 지원합니다. 슬래시 0 숫자는 금융 정보 및 비즈니스 정보의 식별자에 주로 사용됩니다.  
  
 다음 텍스트는 Miramonte 글꼴을 사용하는 샘플 주문 식별자를 나타냅니다. 첫 번째 줄에는 표준 숫자가 사용됩니다. 두 번째 줄에서는 대문자 “O” 문자와의 대비를 높이기 위해 슬래시 0 숫자가 사용되었습니다.  
  
 ![OpenType를 사용 하 여 텍스트 슬래시 0 숫자](../../../../docs/framework/wpf/advanced/media/opentypefont17.gif "OpenTypeFont17")  
OpenType 슬래시 0 숫자를 사용하는 텍스트  
  
 다음 태그 예제에서는 정의 하는 방법을 보여 줍니다. 슬래시 0 숫자 속성을 사용 하는 글꼴에 대 한는 <xref:System.Windows.Documents.Typography> 개체입니다.  
  
 [!code-xaml[OpenTypeFontSamples#OpenTypeFontSnippet15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet15)]  
  
<a name="typography_class"></a>   
## <a name="typography-class"></a>입력 체계 클래스  
 <xref:System.Windows.Documents.Typography> 개체 기능 집합을 제공 하는 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 글꼴을 지원 합니다. 속성을 설정 하 여 <xref:System.Windows.Documents.Typography> 태그에서 쉽게 작성할 수 있습니다 활용 하는 문서 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 기능입니다.  
  
 다음 텍스트는 “SmallCaps” 및 “AllSmallCaps”로 스타일이 지정된 문자 앞에 Pescadero 글꼴의 표준 대문자를 표시합니다. 이 경우 세 단어 모두 동일한 글꼴 크기가 사용됩니다.  
  
 ![OpenType 대문자를 사용 하 여 텍스트](../../../../docs/framework/wpf/advanced/media/opentypefont11.gif "opentypefont11")  
OpenType 대문자를 사용하는 텍스트  
  
 속성을 사용 하는 간격과 대문자를 정의 하는 방법을 보여 주는 다음 태그 예제는 <xref:System.Windows.Documents.Typography> 개체입니다. “SmallCaps” 형식을 사용하는 경우 선행 대문자는 무시됩니다.  
  
 [!code-xaml[OpenTypeFontSamples#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#9)]  
  
 다음 코드 예제에서는 이전 태그 예제와 동일한 작업을 수행합니다.  
  
 [!code-csharp[TypographyCodeSnippets#TypographyCodeSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TypographyCodeSnippets/CSharp/Page1.xaml.cs#typographycodesnippet1)]
 [!code-vb[TypographyCodeSnippets#TypographyCodeSnippet1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TypographyCodeSnippets/visualbasic/page1.xaml.vb#typographycodesnippet1)]  
  
### <a name="typography-class-properties"></a>입력 체계 클래스 속성  
 다음 표에서 속성, 값 및의 기본 설정을 <xref:System.Windows.Documents.Typography> 개체입니다.  
  
|속성|값|기본값|  
|--------------|----------------|-------------------|  
|<xref:System.Windows.Documents.Typography.AnnotationAlternates%2A>|숫자 값-바이트|0|  
|<xref:System.Windows.Documents.Typography.Capitals%2A>|<xref:System.Windows.FontCapitals.AllPetiteCaps> &#124; <xref:System.Windows.FontCapitals.AllSmallCaps> &#124; <xref:System.Windows.FontCapitals.Normal> &#124; <xref:System.Windows.FontCapitals.PetiteCaps> &#124; <xref:System.Windows.FontCapitals.SmallCaps> &#124; <xref:System.Windows.FontCapitals.Titling> &#124; <xref:System.Windows.FontCapitals.Unicase>|<xref:System.Windows.FontCapitals.Normal?displayProperty=nameWithType>|  
|<xref:System.Windows.Documents.Typography.CapitalSpacing%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.CaseSensitiveForms%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.ContextualAlternates%2A>|<xref:System.Boolean>|`true`|  
|<xref:System.Windows.Documents.Typography.ContextualLigatures%2A>|<xref:System.Boolean>|`true`|  
|<xref:System.Windows.Documents.Typography.ContextualSwashes%2A>|숫자 값-바이트|0|  
|<xref:System.Windows.Documents.Typography.DiscretionaryLigatures%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.EastAsianExpertForms%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.EastAsianLanguage%2A>|<xref:System.Windows.FontEastAsianLanguage.HojoKanji> &#124; <xref:System.Windows.FontEastAsianLanguage.Jis04> &#124; <xref:System.Windows.FontEastAsianLanguage.Jis78> &#124; <xref:System.Windows.FontEastAsianLanguage.Jis83> &#124; <xref:System.Windows.FontEastAsianLanguage.Jis90> &#124; <xref:System.Windows.FontEastAsianLanguage.NlcKanji> &#124; <xref:System.Windows.FontEastAsianLanguage.Normal> &#124; <xref:System.Windows.FontEastAsianLanguage.Simplified> &#124; <xref:System.Windows.FontEastAsianLanguage.Traditional> &#124; <xref:System.Windows.FontEastAsianLanguage.TraditionalNames>|<xref:System.Windows.FontEastAsianLanguage.Normal?displayProperty=nameWithType>|  
|<xref:System.Windows.Documents.Typography.EastAsianWidths%2A>|<xref:System.Windows.FontEastAsianWidths.Full> &#124; <xref:System.Windows.FontEastAsianWidths.Half> &#124; <xref:System.Windows.FontEastAsianWidths.Normal> &#124; <xref:System.Windows.FontEastAsianWidths.Proportional> &#124; <xref:System.Windows.FontEastAsianWidths.Quarter> &#124; <xref:System.Windows.FontEastAsianWidths.Third>|<xref:System.Windows.FontEastAsianWidths.Normal?displayProperty=nameWithType>|  
|<xref:System.Windows.Documents.Typography.Fraction%2A>|<xref:System.Windows.FontFraction.Normal> &#124; <xref:System.Windows.FontFraction.Slashed> &#124; <xref:System.Windows.FontFraction.Stacked>|<xref:System.Windows.FontFraction.Normal?displayProperty=nameWithType>|  
|<xref:System.Windows.Documents.Typography.HistoricalForms%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.HistoricalLigatures%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.Kerning%2A>|<xref:System.Boolean>|`true`|  
|<xref:System.Windows.Documents.Typography.MathematicalGreek%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.NumeralAlignment%2A>|<xref:System.Windows.FontNumeralAlignment.Normal> &#124; <xref:System.Windows.FontNumeralAlignment.Proportional> &#124; <xref:System.Windows.FontNumeralAlignment.Tabular>|<xref:System.Windows.FontNumeralAlignment.Normal?displayProperty=nameWithType>|  
|<xref:System.Windows.Documents.Typography.NumeralStyle%2A>|<xref:System.Boolean>|<xref:System.Windows.FontNumeralStyle.Normal?displayProperty=nameWithType>|  
|<xref:System.Windows.Documents.Typography.SlashedZero%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StandardLigatures%2A>|<xref:System.Boolean>|`true`|  
|<xref:System.Windows.Documents.Typography.StandardSwashes%2A>|숫자 값-바이트|0|  
|<xref:System.Windows.Documents.Typography.StylisticAlternates%2A>|숫자 값-바이트|0|  
|<xref:System.Windows.Documents.Typography.StylisticSet1%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet2%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet3%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet4%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet5%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet6%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet7%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet8%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet9%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet10%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet11%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet12%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet13%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet14%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet15%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet16%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet17%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet18%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet19%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.StylisticSet20%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.Variants%2A>|<xref:System.Windows.FontVariants.Inferior> &#124; <xref:System.Windows.FontVariants.Normal> &#124; <xref:System.Windows.FontVariants.Ordinal> &#124; <xref:System.Windows.FontVariants.Ruby> &#124; <xref:System.Windows.FontVariants.Subscript> &#124; <xref:System.Windows.FontVariants.Superscript>|<xref:System.Windows.FontVariants.Normal?displayProperty=nameWithType>|  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Documents.Typography>  
 [OpenType 사양](http://go.microsoft.com/fwlink/?LinkId=96731)  
 [WPF의 입력 체계](../../../../docs/framework/wpf/advanced/typography-in-wpf.md)  
 [샘플 OpenType 글꼴 팩](../../../../docs/framework/wpf/advanced/sample-opentype-font-pack.md)  
 [응용 프로그램과 함께 글꼴 패키징](../../../../docs/framework/wpf/advanced/packaging-fonts-with-applications.md)
