---
title: "OpenType 글꼴 기능 | Microsoft Docs"
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
  - "OpenType 글꼴"
  - "서체, OpenType 글꼴 기술"
  - "OpenType 글꼴 기술"
ms.assetid: 4061a9d1-fe8b-4921-9e17-18ec7d2e3ea2
caps.latest.revision: 38
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 37
---
# OpenType 글꼴 기능
이 항목의 주요 기능 중 일부에 대 한 개요를 제공 합니다. [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 글꼴 기술의 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]합니다.  
  
   
  
<a name="overview"></a>   
## <a name="opentype-font-format"></a>OpenType 글꼴 서식  
 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 글꼴 형식은의 확장은 [!INCLUDE[TLA#tla_truetype](../../../../includes/tlasharptla-truetype-md.md)] 글꼴 형식은 PostScript 글꼴 데이터에 대 한 지원을 추가 합니다. [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 글꼴 서식을 공동으로 개발한 [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)] 와 Adobe Corporation. [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]글꼴 및 운영 체제 서비스는 지원 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 글꼴은 글꼴에 포함 되어 있는지 여부를 설치 하 고 글꼴을 사용 하는 간단한 방법 사용자에 게를 제공 [!INCLUDE[TLA2#tla_truetype](../../../../includes/tla2sharptla-truetype-md.md)] 윤곽선 또는 CFF (PostScript) 개요.  
  
 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 글꼴 형식은 다음과 같은 개발자 문제 해결:  
  
-   다중 플랫폼 지원 증가 합니다.  
  
-   국제 공용 문자 집합에 대 한 지원 향상입니다.  
  
-   글꼴 데이터에 대 한 더 나은 보호 합니다.  
  
-   글꼴 배포 보다 효율적으로 만들 작은 파일 크기.  
  
-   고급 인쇄 컨트롤에 대 한 광범위 한 지원입니다.  
  
> [!NOTE]
>  Windows SDK 샘플의 집합을 포함 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 글꼴에 사용할 수 있는 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 응용 프로그램입니다. 이러한 글꼴에는이 항목의 나머지 부분에서 설명 하는 기능을 대부분을 제공 합니다. 자세한 내용은 참조 [샘플 OpenType 글꼴 팩](../../../../docs/framework/wpf/advanced/sample-opentype-font-pack.md)합니다.  
  
 참조는 [OpenType 사양](http://go.microsoft.com/fwlink/?LinkId=96731) 대 한 자세한 내용은 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 글꼴 형식입니다.  
  
### <a name="advanced-typographic-extensions"></a>고급 글꼴 표시 확장  
 고급 글꼴 표시 테이블 ([!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 레이아웃 표)으로 글꼴의 기능을 확장 [!INCLUDE[TLA2#tla_truetype](../../../../includes/tla2sharptla-truetype-md.md)] 또는 CFF 간략하게 설명 합니다. [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]레이아웃 글꼴 고품질 국제 입력 체계를 지원 하기 위해 글꼴의 기능을 확장 하는 추가 정보를 포함 합니다. 대부분 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 글꼴 총의 하위 집합만 노출 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 사용할 수 있는 기능입니다. [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]글꼴은 다음과 같은 기능을 제공합니다.  
  
-   문자와 지 원하는 합자, 위치 형태, 대체 및 다른 글꼴 대체 문자 모양 사이의 다양 한 매핑을 합니다.  
  
-   2 차원 위치 지정 및 문자 모양 첨부를 지원 합니다.  
  
-   명시적 스크립트와 언어에에서 포함 된 정보 글꼴, 텍스트 처리 응용 프로그램의 동작을 적절 하 게 조정할 수 있도록 합니다.  
  
 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 레이아웃 표에서 자세히 설명 되어는 ["글꼴 파일 테이블"](http://www.microsoft.com/typography/otspec/otff.htm) 의 섹션은 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 사양입니다.  
  
 이 개요의 나머지 부분에서는 확장성과 유연성 몇 가지 시각적으로 흥미로운 소개 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 의 속성에 의해 노출 되는 기능에서 <xref:System.Windows.Documents.Typography> 개체입니다. 이 개체에 대 한 자세한 내용은 참조 하십시오. [입력 체계 클래스](#typography_class)합니다.  
  
<a name="variants"></a>   
## <a name="variants"></a>변형  
 변형 위 첨자 및 아래 첨자와 같은 다른 글꼴 표시 스타일을 렌더링 하는 데 사용 됩니다.  
  
### <a name="superscripts-and-subscripts"></a>위 첨자 및 아래 첨자  
 <xref:System.Windows.Documents.Typography.Variants%2A> 속성을 사용 하면 위 첨자 및 아래 첨자 값을 설정 하는 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 글꼴입니다.  
  
 다음 텍스트는 글꼴에 대 한 위 첨자를 표시합니다.  
  
 ![OpenType 위 첨자를 사용 하 여 텍스트](../../../../docs/framework/wpf/advanced/media/opentypefont14.png "opentypefont14")  
OpenType 위 첨자를 사용하는 텍스트  
  
 다음 태그 예제에서는 속성을 사용 하 여은 글꼴에 대 한 위 첨자를 정의 하는 방법을 보여 줍니다.는 <xref:System.Windows.Documents.Typography> 개체입니다.  
  
 [!code-xml[OpenTypeFontSamples#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#12)]  
  
 다음 텍스트는 글꼴에 대 한 아래 첨자를 표시합니다.  
  
 ![OpenType 아래 첨자를 사용 하 여 텍스트](../../../../docs/framework/wpf/advanced/media/opentypefont15.png "opentypefont15")  
OpenType 아래 첨자를 사용하는 텍스트  
  
 다음 태그 예제에서는 아래 첨자의 속성을 사용 하 여은 글꼴에 대 한 정의 하는 방법을 보여 줍니다.는 <xref:System.Windows.Documents.Typography> 개체입니다.  
  
 [!code-xml[OpenTypeFontSamples#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#13)]  
  
### <a name="decorative-uses-of-superscripts-and-subscripts"></a>위 첨자 및 아래 첨자의 장식 사용  
 또한 위 첨자 및 아래 첨자 혼합 사례 텍스트 장식 효과 만들기 위해 사용할 수 있습니다. 다음은 글꼴에 대 한 위 첨자 및 아래 첨자 텍스트를 표시합니다. 참고 대문자 영향을 받지 않습니다.  
  
 ![OpenType 위 첨자 및 아래 첨자를 사용 하 여 텍스트](../../../../docs/framework/wpf/advanced/media/opentypefont16.png "opentypefont16")  
OpenType 위 첨자 및 아래 첨자를 사용하는 텍스트  
  
 다음 태그 예제에서는 위 첨자 및 아래 첨자의 속성을 사용 하는 글꼴에 대 한 정의 하는 방법을 보여 줍니다.는 <xref:System.Windows.Documents.Typography> 개체입니다.  
  
 [!code-xml[OpenTypeFontSamples#14](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#14)]  
  
<a name="capitals"></a>   
## <a name="capitals"></a>대문자  
 대문자는 자본 스타일 문자 모양에 텍스트를 렌더링 하는 입력 폼의 집합. 일반적으로 텍스트를 모두 대문자로로 렌더링할 때 문자 사이의 간격이 너무 좁고 무게와 너무 많은 글자의 비율을 차지 합니다. [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]작은 대문자를 포함 하 여 대문자, 꼬마 대문자, 제목, 및 대문자 간격에 대 한 다양 한 스타일 형식 지원 합니다. 이러한 스타일 형식을 사용 대문자의 모양을 제어할 수 있습니다.  
  
 다음 텍스트 간격과 "SmallCaps" 및 "AllSmallCaps" 스타일의 문자에 대 한 표준 대문자로 표시 합니다. 이 경우에 동일한 글꼴 크기는 세 단어 모두에 사용 됩니다.  
  
 ![OpenType 대문자를 사용 하 여 텍스트](../../../../docs/framework/wpf/advanced/media/opentypefont11.png "opentypefont11")  
OpenType 대문자를 사용하는 텍스트  
  
 다음 태그 예제에서는 속성을 사용 하는 간격과 대문자를 정의 하는 방법을 보여 줍니다.는 <xref:System.Windows.Documents.Typography> 개체입니다. "SmallCaps" 형식이 사용 되며 모든 선행 대문자는 무시 됩니다.  
  
 [!code-xml[OpenTypeFontSamples#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#9)]  
  
### <a name="titling-capitals"></a>제목 대문자  
 제목 대문자 두께가 얇고 비율 되며 일반 대문자 보다 더 세련 된 느낌을 줄 수 있도록 설계 됩니다. 제목 대문자 머리글로 큰 글꼴 크기에 일반적으로 사용 됩니다. 다음 텍스트는 간격과 대 한 문자와 일반 대문자 표시 됩니다. 적은 획 너비의 두 번째 줄에 텍스트를 확인 합니다.  
  
 ![OpenType 제목 대문자를 사용 하 여 텍스트](../../../../docs/framework/wpf/advanced/media/opentypefont20.png "OpenTypeFont20")  
OpenType 제목 대문자를 사용하는 텍스트  
  
 다음 태그 예제에서는 속성을 사용 하는 간격과 제목 대문자를 정의 하는 방법을 보여 줍니다.는 <xref:System.Windows.Documents.Typography> 개체입니다.  
  
 [!code-xml[OpenTypeFontSamples#OpenTypeFontSnippet17](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet17)]  
  
### <a name="capital-spacing"></a>대문자 간격  
 대문자 간격 기능은 텍스트의 모든 대문자를 사용 하는 경우 간격을 더 많이 제공할 수 있습니다. 대문자는 일반적으로 소문자로 blend 디자인 합니다. 사이의 적당 표시 하는 간격 및 대문자 및 소문자 보이지만 너무 밀접 하 게 모든 대문자를 사용 하는 경우. 다음 텍스트는 간격과 일반 대문자 간격을 표시합니다.  
  
 ![OpenType 대문자 간격을 사용 하 여 텍스트](../../../../docs/framework/wpf/advanced/media/opentypefont21.png "OpenTypeFont21")  
OpenType 대문자 간격을 사용하는 텍스트  
  
 다음 태그 예제에서는 속성을 사용 하는 간격과의 대문자 간격을 정의 하는 방법을 보여 줍니다.는 <xref:System.Windows.Documents.Typography> 개체입니다.  
  
 [!code-xml[OpenTypeFontSamples#OpenTypeFontSnippet18](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet18)]  
  
<a name="ligatures"></a>   
## <a name="ligatures"></a>합자  
 합자는 두 개 이상의 모양 읽기 가능 인지 또는 매력적인 텍스트를 만들기 위해 단일 문자 모양으로 합한입니다. [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]글꼴 네 가지 유형의 합자를 지원합니다.  
  
-   **표준 합자**합니다. 가독성을 향상 시키기 위해 설계 되었습니다. 표준 합자 "fi", "fl" 및 "ff"를 포함 합니다.  
  
-   **컨텍스트 합자**합니다. 합자를 구성 하는 문자 사이 더 나은 연결 동작을 제공 하 여 가독성을 향상 시키기 위해 설계 되었습니다.  
  
-   **임의 합자**합니다. 마감, 장식 및 가독성을 위해 특별히 디자인 된 하지 하도록 설계 되었습니다.  
  
-   **기록 합자**합니다. 기록과 가독성을 위해 특별히 디자인 된 하지 하도록 설계 되었습니다.  
  
 다음은 글꼴에 대 한 표준 합자 문자 모양을 표시합니다.  
  
 ![OpenType 표준 합자를 사용 하 여 텍스트](../../../../docs/framework/wpf/advanced/media/opentypefont04.png "opentypefont04")  
OpenType 표준 합자를 사용하는 텍스트  
  
 다음 태그 예제에서는 속성을 사용 하 여은 글꼴에 대 한 표준 합자 문자 모양을 정의 하는 방법을 보여 줍니다.는 <xref:System.Windows.Documents.Typography> 개체입니다.  
  
 [!code-xml[OpenTypeFontSamples#4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#4)]  
  
 다음은 글꼴에 대 한 임의 합자 문자 모양을 표시합니다.  
  
 ![OpenType 임의 합자를 사용 하 여 텍스트](../../../../docs/framework/wpf/advanced/media/opentypefont05.png "opentypefont05")  
OpenType 임의 합자를 사용하는 텍스트  
  
 다음 태그 예제에서는 속성을 사용 하 여은 글꼴에 대 한 임의 합자 문자 모양을 정의 하는 방법을 보여 줍니다.는 <xref:System.Windows.Documents.Typography> 개체입니다.  
  
 [!code-xml[OpenTypeFontSamples#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#5)]  
  
 기본적으로 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 에서 글꼴 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 표준 합자를 사용 합니다. 예를 들어은 사용 하는 경우 표준 합자 "fi", "ff" 및 "fl"으로 표시 조합된 문자 모양이 합니다. 각 표준 합자에 대 한 문자 쌍의 터치 서로 있는지 확인 합니다.  
  
 ![OpenType 표준 합자를 사용 하 여 텍스트](../../../../docs/framework/wpf/advanced/media/opentypefont06.png "opentypefont06")  
OpenType 표준 합자를 사용하는 텍스트  
  
 그러나 "ff"와 같은 표준 합자를 결합 된 문자 모양이 아닌 두 개의 개별 문자 모양으로 표시 되도록 표준 합자 기능을 비활성화할 수 있습니다.  
  
 ![비활성화 된 OpenType 표준 합자를 사용 하 여 텍스트](../../../../docs/framework/wpf/advanced/media/opentypefont07.png "opentypefont07")  
비활성화된 OpenType 표준 합자를 사용하는 텍스트  
  
 다음 태그 예제에서는의 속성을 사용 하 여은 글꼴에 대 한 표준 합자 문자 모양을 사용 하지 않도록 설정 하는 방법을 보여 줍니다.는 <xref:System.Windows.Documents.Typography> 개체입니다.  
  
 [!code-xml[OpenTypeFontSamples#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#6)]  
  
<a name="swashes"></a>   
## <a name="swashes"></a>선단 장식  
 선단 장식을 자주 서 법과 관련 된 정교한 장식을 사용 하는 장식 문자 모양이 됩니다. 다음 텍스트는 간격과 대 한 표준 및 선단 장식 문자 모양을 표시합니다.  
  
 ![OpenType 표준 및 선단 장식 문자 모양을 사용 하는 텍스트](../../../../docs/framework/wpf/advanced/media/opentypefont08.png "opentypefont08")  
OpenType 표준 및 선단 장식 문자 모양을 사용하는 텍스트  
  
 선단 장식 이벤트 알림과 같은 짧은 구 요소로 자주 사용 됩니다. 이벤트의 이름을 대문자를 강조 하기 위해 선단 장식을 사용 하는 다음 텍스트입니다.  
  
 ![OpenType 선단 장식을 사용 하는 텍스트](../../../../docs/framework/wpf/advanced/media/opentypefont09.png "opentypefont09")  
OpenType 선단 장식을 사용하는 텍스트  
  
 다음 태그 예제에서는 속성을 사용 하는 글꼴에 대 한 선단 장식을 정의 하는 방법을 보여 줍니다.는 <xref:System.Windows.Documents.Typography> 개체입니다.  
  
 [!code-xml[OpenTypeFontSamples#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#7)]  
  
### <a name="contextual-swashes"></a>컨텍스트 선단 장식  
 특정 조합의 선단 장식 문자는 인접 한 문자에서 겹치는 디센더와 같은 이상한 모양이 발생할 수 있습니다. 컨텍스트 선단 장식을 사용 하 여 더 나은 모양이 대체 선단 장식 문자 모양을 사용할 수 있습니다. 다음 텍스트에서는 컨텍스트 선단 장식을 적용 된 후 전과 같은 단어를 보여 줍니다.  
  
 ![OpenType 컨텍스트 선단 장식을 사용 하는 텍스트](../../../../docs/framework/wpf/advanced/media/opentypefont19.png "OpenTypeFont19")  
OpenType 컨텍스트 선단 장식을 사용하는 텍스트  
  
 다음 태그 예제에서는 속성을 사용 하는 간격과 컨텍스트 선단 장식을 정의 하는 방법을 보여 줍니다.는 <xref:System.Windows.Documents.Typography> 개체입니다.  
  
 [!code-xml[OpenTypeFontSamples#OpenTypeFontSnippet16](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet16)]  
  
<a name="alternates"></a>   
## <a name="alternates"></a>대체 항목  
 대체는 표준 문자 대신 사용할 수 있는 모양입니다. [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]다음 예제에서 사용 하는 등의 글꼴, 텍스트에 대 한 다른 모양을 만드는 데 사용할 수 있는 대체 문자를 포함할 수 있습니다. 다음은 글꼴에 대 한 표준 문자 모양을 표시합니다.  
  
 ![OpenType 표준 문자 모양을 사용 하는 텍스트](../../../../docs/framework/wpf/advanced/media/opentypefont01.png "opentypefont01")  
OpenType 표준 문자 모양을 사용하는 텍스트  
  
 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 글꼴 스타일 대체 문자 모양 표준 집합을 제공 하는 추가 문자를 포함 합니다. 다음 텍스트에 스타일 대체 문자 모양을 표시합니다.  
  
 ![OpenType 스타일 대체 문자를 사용 하 여 텍스트](../../../../docs/framework/wpf/advanced/media/opentypefont02.png "opentypefont02")  
OpenType 스타일 대체 문자 모양을 사용하는 텍스트  
  
 다음 태그 예제에서는 속성을 사용 하 여은 글꼴 스타일 대체 문자 모양을 정의 하는 방법을 보여 줍니다.는 <xref:System.Windows.Documents.Typography> 개체입니다.  
  
 [!code-xml[OpenTypeFontSamples#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#2)]  
  
 다음 텍스트에는 몇 가지 다른 스타일 대체 문자는 글꼴에 대 한 표시 됩니다.  
  
 ![OpenType 스타일 대체 문자를 사용 하 여 텍스트](../../../../docs/framework/wpf/advanced/media/opentypefont03.png "opentypefont03")  
OpenType 스타일 대체 문자 모양을 사용하는 텍스트  
  
 다음 태그 예제에는 이러한 다른 스타일 대체 문자 모양을 정의 하는 방법을 보여 줍니다.  
  
 [!code-xml[OpenTypeFontSamples#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#3)]  
  
### <a name="random-contextual-alternates"></a>임의 컨텍스트 대체 항목  
 단일 문자에 대 한 여러 대체 문자 모양을 제공 하는 임의 컨텍스트 대체 합니다. 스크립트 유형 글꼴을 구현 하는 경우이 기능 집합의 모양이 약간의 차이가 임의로 선택한 문자 모양으로 사용 하 여 필기를 시뮬레이션할 수 있습니다. 다음 텍스트 Lindsey 글꼴에 대 한 임의 컨텍스트 대체 항목을 사용합니다. 문자 "a"의 모양이 약간씩 다릅니다  
  
 ![OpenType 임의 컨텍스트 대체를 사용 하 여 텍스트](../../../../docs/framework/wpf/advanced/media/opentypefont23.png "OpenTypeFont23")  
OpenType 임의 컨텍스트 대체 항목을 사용한 텍스트  
  
 다음 태그 예제에서는 속성을 사용 하 여 Lindsey 글꼴에 대 한 임의 컨텍스트 대체 항목을 정의 하는 방법을 보여 줍니다.는 <xref:System.Windows.Documents.Typography> 개체입니다.  
  
 [!code-xml[OpenTypeFontSamples#OpenTypeFontSnippet20](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/Window1.xaml#opentypefontsnippet20)]  
  
### <a name="historical-forms"></a>기록 폼  
 기록 폼은 과거의 일반적 사용 되 던 글꼴 표시 규칙입니다. 다음 텍스트를 "보스톤, 매사추세츠" 라는 구가 표시은 글꼴에 대 한 문자 모양에 대 한 기록 형식을 사용 합니다.  
  
 ![OpenType 기록 폼을 사용 하 여 텍스트](../../../../docs/framework/wpf/advanced/media/opentypefont10.png "opentypefont10")  
OpenType 기록 폼을 사용하는 텍스트  
  
 다음 태그 예제에서는 속성을 사용 하 여은 글꼴에 대 한 기록 폼을 정의 하는 방법을 보여 줍니다.는 <xref:System.Windows.Documents.Typography> 개체입니다.  
  
 [!code-xml[OpenTypeFontSamples#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#8)]  
  
<a name="numerical_styles"></a>   
## <a name="numerical-styles"></a>숫자 스타일  
 OpenType 글꼴 많은 수의 텍스트의 숫자 값에 사용할 수 있는 기능을 지원 합니다.  
  
### <a name="fractions"></a>분수  
 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]글꼴 스타일 분수를 슬래시, 누적 등을 지원 합니다.  
  
 다음 텍스트 분수 스타일은 글꼴에 대 한 표시 됩니다.  
  
 ![OpenType를 사용 하 여 텍스트의 슬래시 및 상하 형 분수](../../../../docs/framework/wpf/advanced/media/opentypefont12.png "opentypefont12")  
OpenType 슬래시 및 상하형 분수를 사용하는 텍스트  
  
 다음 태그 예제에서는 분수의 속성을 사용 하 여은 글꼴 스타일을 정의 하는 방법을 보여 줍니다.는 <xref:System.Windows.Documents.Typography> 개체입니다.  
  
 [!code-xml[OpenTypeFontSamples#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#10)]  
  
### <a name="old-style-numerals"></a>이전 스타일 숫자  
 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]글꼴에는 이전 스타일 숫자 형식을 지원합니다. 이 형식은 표준 더 이상 되지 않는 스타일의 숫자를 표시할 때 유용 합니다. 다음 텍스트는 표준 및 이전 스타일은 글꼴에 대 한 숫자 형식의에 18 세기 날짜를 표시합니다.  
  
 ![OpenType 이전 스타일 숫자를 사용 하 여 텍스트](../../../../docs/framework/wpf/advanced/media/opentypefont24.png "OpenTypeFont24")  
OpenType 이전 스타일 숫자를 사용하는 텍스트  
  
 다음 텍스트 뒤에 이전 스타일 숫자는 글꼴에 대 한 표준 숫자를 표시 합니다.  
  
 ![OpenType 이전 스타일 숫자 집합을 사용 하 여 텍스트](../../../../docs/framework/wpf/advanced/media/opentypefont13.png "opentypefont13")  
OpenType의 이전 스타일 숫자 집합을 사용하는 텍스트  
  
 다음 태그 예제에서는 속성을 사용 하 여은 글꼴에 대 한 이전 스타일 숫자를 정의 하는 방법을 보여 줍니다.는 <xref:System.Windows.Documents.Typography> 개체입니다.  
  
 [!code-xml[OpenTypeFontSamples#11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#11)]  
  
### <a name="proportional-and-tabular-figures"></a>숫자와 표 형식 숫자  
 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]글꼴 숫자를 사용할 때 너비의 맞춤을 제어 하는 가변 폭 및 표 형식 숫자 기능을 지원 합니다. 가변 폭 각 숫자를 다른 너비로 처리-"1"은 "5" 보다 더 작게 설정할 합니다. 표 형식 숫자를 세로로 맞춰져 재무 형식 정보를 쉽게 읽을 수 있도록 같은 너비 숫자로 처리 됩니다.  
  
 다음 텍스트는 첫 번째 열에 두 개의 가변 폭을 표시 합니다. Note 너비의 차이 숫자 "5" 및 "1"입니다. 두 번째 열 너비가 표 형식 숫자 기능을 사용 하 여 조정 된 동일한 두 개의 숫자 값을 보여 줍니다.  
  
 ![OpenType 가변 폭 / 표 형식 숫자를 사용 하 여 텍스트](../../../../docs/framework/wpf/advanced/media/opentypefont22.png "OpenTypeFont22")  
OpenType 가변 폭 및 표 형식 숫자를 사용 하 여 텍스트  
  
 다음 태그 예제에서는 가변 폭 및 표 형식 숫자 값의 속성을 사용 하 여은 글꼴에 대 한 정의 하는 방법을 보여 줍니다.는 <xref:System.Windows.Documents.Typography> 개체입니다.  
  
 [!code-xml[OpenTypeFontSamples#OpenTypeFontSnippet19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/Window1.xaml#opentypefontsnippet19)]  
  
### <a name="slashed-zero"></a>슬래시&0;  
 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)]글꼴 지원 있도록 슬래시&0; 숫자 형식을 문자 "O"와 "0" 숫자 간의 차이 강조 하기 위해. 슬래시&0; 숫자는 재무 및 비즈니스 정보에는 식별자에 자주 사용 됩니다.  
  
 다음은 샘플 주문 식별자를 표시 합니다. 첫 번째 줄에는 표준 숫자가 사용 합니다. 사용 되는 두 번째 줄 슬래시&0; 숫자를 대문자 "O"와 더 잘 대비 합니다.  
  
 ![OpenType를 사용 하 여 텍스트의 슬래시&0; 숫자](../../../../docs/framework/wpf/advanced/media/opentypefont17.png "OpenTypeFont17")  
OpenType 슬래시&0; 숫자를 사용하는 텍스트  
  
 다음 태그 예제에서는 정의 하는 방법을 보여 줍니다. 슬래시&0; 숫자 속성을 사용 하 여은 글꼴의 <xref:System.Windows.Documents.Typography> 개체입니다.  
  
 [!code-xml[OpenTypeFontSamples#OpenTypeFontSnippet15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#opentypefontsnippet15)]  
  
<a name="typography_class"></a>   
## <a name="typography-class"></a>입력 체계 클래스  
 <xref:System.Windows.Documents.Typography> 개체 기능 집합을 노출 하는 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 글꼴을 지원 합니다. 속성을 설정 하 여 <xref:System.Windows.Documents.Typography> 태그를 쉽게 작성할 수 있습니다 활용 하는 문서 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 기능입니다.  
  
 다음 텍스트 간격과 "SmallCaps" 및 "AllSmallCaps" 스타일의 문자에 대 한 표준 대문자로 표시 합니다. 이 경우에 동일한 글꼴 크기는 세 단어 모두에 사용 됩니다.  
  
 ![OpenType 대문자를 사용 하 여 텍스트](../../../../docs/framework/wpf/advanced/media/opentypefont11.png "opentypefont11")  
OpenType 대문자를 사용하는 텍스트  
  
 다음 태그 예제에서는 속성을 사용 하는 간격과 대문자를 정의 하는 방법을 보여 줍니다.는 <xref:System.Windows.Documents.Typography> 개체입니다. "SmallCaps" 형식이 사용 되며 모든 선행 대문자는 무시 됩니다.  
  
 [!code-xml[OpenTypeFontSamples#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/OpenTypeFontSamples/CS/PageOne.xaml#9)]  
  
 다음 코드 예제에서는 이전 태그 예제와 동일한 작업을 수행합니다.  
  
 [!code-csharp[TypographyCodeSnippets#TypographyCodeSnippet1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TypographyCodeSnippets/CSharp/Page1.xaml.cs#typographycodesnippet1)]
 [!code-vb[TypographyCodeSnippets#TypographyCodeSnippet1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TypographyCodeSnippets/visualbasic/page1.xaml.vb#typographycodesnippet1)]  
  
### <a name="typography-class-properties"></a>입력 체계 클래스 속성  
 다음 표에서 속성, 값 및 기본 설정의는 <xref:System.Windows.Documents.Typography> 개체입니다.  
  
|속성|값|기본값|  
|--------------|----------------|-------------------|  
|<xref:System.Windows.Documents.Typography.AnnotationAlternates%2A>|숫자 값-바이트|0|  
|<xref:System.Windows.Documents.Typography.Capitals%2A>|<xref:System.Windows.FontCapitals> | <xref:System.Windows.FontCapitals> | <xref:System.Windows.FontCapitals> | <xref:System.Windows.FontCapitals> | <xref:System.Windows.FontCapitals> | <xref:System.Windows.FontCapitals> | <xref:System.Windows.FontCapitals>|<xref:System.Windows.FontCapitals?displayProperty=fullName>|  
|<xref:System.Windows.Documents.Typography.CapitalSpacing%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.CaseSensitiveForms%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.ContextualAlternates%2A>|<xref:System.Boolean>|`true`|  
|<xref:System.Windows.Documents.Typography.ContextualLigatures%2A>|<xref:System.Boolean>|`true`|  
|<xref:System.Windows.Documents.Typography.ContextualSwashes%2A>|숫자 값-바이트|0|  
|<xref:System.Windows.Documents.Typography.DiscretionaryLigatures%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.EastAsianExpertForms%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.EastAsianLanguage%2A>|<xref:System.Windows.FontEastAsianLanguage> | <xref:System.Windows.FontEastAsianLanguage> | <xref:System.Windows.FontEastAsianLanguage> | <xref:System.Windows.FontEastAsianLanguage> | <xref:System.Windows.FontEastAsianLanguage> | <xref:System.Windows.FontEastAsianLanguage> | <xref:System.Windows.FontEastAsianLanguage> | <xref:System.Windows.FontEastAsianLanguage> | <xref:System.Windows.FontEastAsianLanguage> | <xref:System.Windows.FontEastAsianLanguage>|<xref:System.Windows.FontEastAsianLanguage?displayProperty=fullName>|  
|<xref:System.Windows.Documents.Typography.EastAsianWidths%2A>|<xref:System.Windows.FontEastAsianWidths> | <xref:System.Windows.FontEastAsianWidths> | <xref:System.Windows.FontEastAsianWidths> | <xref:System.Windows.FontEastAsianWidths> | <xref:System.Windows.FontEastAsianWidths> | <xref:System.Windows.FontEastAsianWidths>|<xref:System.Windows.FontEastAsianWidths?displayProperty=fullName>|  
|<xref:System.Windows.Documents.Typography.Fraction%2A>|<xref:System.Windows.FontFraction> | <xref:System.Windows.FontFraction> | <xref:System.Windows.FontFraction>|<xref:System.Windows.FontFraction?displayProperty=fullName>|  
|<xref:System.Windows.Documents.Typography.HistoricalForms%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.HistoricalLigatures%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.Kerning%2A>|<xref:System.Boolean>|`true`|  
|<xref:System.Windows.Documents.Typography.MathematicalGreek%2A>|<xref:System.Boolean>|`false`|  
|<xref:System.Windows.Documents.Typography.NumeralAlignment%2A>|<xref:System.Windows.FontNumeralAlignment> | <xref:System.Windows.FontNumeralAlignment> | <xref:System.Windows.FontNumeralAlignment>|<xref:System.Windows.FontNumeralAlignment?displayProperty=fullName>|  
|<xref:System.Windows.Documents.Typography.NumeralStyle%2A>|<xref:System.Boolean>|<xref:System.Windows.FontNumeralStyle?displayProperty=fullName>|  
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
|<xref:System.Windows.Documents.Typography.Variants%2A>|<xref:System.Windows.FontVariants> | <xref:System.Windows.FontVariants> | <xref:System.Windows.FontVariants> | <xref:System.Windows.FontVariants> | <xref:System.Windows.FontVariants> | <xref:System.Windows.FontVariants>|<xref:System.Windows.FontVariants?displayProperty=fullName>|  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Documents.Typography>   
 [OpenType 사양](http://go.microsoft.com/fwlink/?LinkId=96731)   
 [WPF의 입력 체계](../../../../docs/framework/wpf/advanced/typography-in-wpf.md)   
 [샘플 OpenType 글꼴 팩](../../../../docs/framework/wpf/advanced/sample-opentype-font-pack.md)   
 [응용 프로그램과 함께 글꼴 패키징](../../../../docs/framework/wpf/advanced/packaging-fonts-with-applications.md)