---
title: "WPF의 전역화 | Microsoft Docs"
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
  - "전역화(globalization)"
  - "국가별 사용자 인터페이스, XAML"
  - "XAML, 전역화(globalization)"
  - "XAML, 국가별 사용자 인터페이스"
ms.assetid: 4571ccfe-8a60-4f06-9b37-7ac0b1c2d10f
caps.latest.revision: 35
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 31
---
# WPF의 전역화
이 항목에서는 글로벌 시장을 위한 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 응용 프로그램을 작성할 때 알아야 하는 문제를 소개합니다.  전역화 프로그래밍 요소는 [!INCLUDE[TLA#tla_net](../../../../includes/tlasharptla-net-md.md)]의 `System.Globalization`에 정의됩니다.  
  
   
  
<a name="xaml_globalization"></a>   
## XAML 전역화  
 [!INCLUDE[TLA#tla_xml](../../../../includes/tlasharptla-xml-md.md)]에 기초하는 [!INCLUDE[TLA#tla_xaml#initcap](../../../../includes/tlasharptla-xamlsharpinitcap-md.md)]에서는 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 사양에 정의된 전역화 지원을 활용합니다.  다음 단원에서는 사용자가 알고 있어야 하는 몇 가지 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 기능에 대해 설명합니다.  
  
<a name="char_reference"></a>   
### 문자 참조  
 문자 참조는 자신이 나타내는 특정 [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] 문자의 번호를 10진수 또는 16진수로 제공합니다.  다음 예제에서는 10진수 문자 참조를 보여 줍니다.  
  
```  
Ϩ  
```  
  
 다음 예제에서는 16진수 문자 참조를 보여 줍니다.  16진수 숫자 앞에 **x**가 있습니다.  
  
```  
Ϩ  
```  
  
<a name="encoding"></a>   
### 인코딩  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에서 지원되는 인코딩은 [!INCLUDE[TLA#tla_ascii](../../../../includes/tlasharptla-ascii-md.md)], [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)] UTF\-16 및 UTF\-8입니다.  인코딩 문은 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 문서의 시작 부분에 있습니다.  인코딩 특성이 없는 경우 바이트 순서가 없으면 파서에서 기본값은 UTF\-8로 설정됩니다.  UTF\-8 및 UTF\-16은 기본 설정 인코딩입니다.  UTF 7은 지원되지 않습니다.  다음 예제에서는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일에서 UTF\-8 인코딩을 지정하는 방법을 보여 줍니다.  
  
```  
?xml encoding="UTF-8"?  
```  
  
<a name="lang_attrib"></a>   
### Language 특성  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]은 [xml:lang](../../../../docs/framework/xaml-services/xml-lang-handling-in-xaml.md)을 사용하여 요소의 언어 특성을 나타냅니다.  <xref:System.Globalization.CultureInfo> 클래스를 활용하기 위해서는 언어 특성 값이 <xref:System.Globalization.CultureInfo>를 통해 미리 정의된 문화권 이름 중 하나여야 합니다.  [xml:lang](../../../../docs/framework/xaml-services/xml-lang-handling-in-xaml.md)은 요소 트리에서 상속될 수 있으며\(XML 규칙에 의해, 종속성 속성 상속 때문일 필요는 없음\) 명시적으로 할당되지 않은 경우 기본값은 빈 문자열입니다.  
  
 언어 특성은 언어를 지정하는 데 매우 유용합니다.  예를 들어 프랑스, 퀘벡, 벨기에 및 스위스에서 프랑스어는 맞춤법, 어휘 및 발음이 다릅니다.  또한 중국어, 일본어 및 한국어는 [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)]의 코드 포인트를 공유하지만 표의 문자 모양이 다르고 완전히 다른 글꼴을 사용합니다.  
  
 다음 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 예제에서는 `fr-CA` 언어 특성을 사용하여 캐나다 프랑스어를 지정합니다.  
  
```  
<TextBlock xml:lang="fr-CA">Découvrir la France</TextBlock>  
```  
  
<a name="unicode"></a>   
### Unicode  
 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]은 서로게이트를 비롯한 모든 [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)] 기능을 지원합니다.  문자 집합은 [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)]에 매핑할 수 있는 경우 지원됩니다.  예를 들어 GB18030은 CFK\(중국어, 일본어 및 한국어\) Extension A 및 B 및 서로게이트 쌍에 매핑되는 일부 문자가 도입되었으므로 완전히 지원됩니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램에서는 문자열에 서로게이트 쌍 또는 결합 문자가 있는지 알지 못하더라도 <xref:System.Globalization.StringInfo>을 사용하여 문자열을 조작할 수 있습니다.  
  
<a name="design_intl_ui_with_xaml"></a>   
## XAML을 사용하여 국가별 사용자 인터페이스 디자인  
 이 단원에서는 응용 프로그램을 작성할 때 고려해야 하는 [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] 기능에 대해 설명합니다.  
  
<a name="intl_text"></a>   
### 국가별 텍스트  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]에는 모든 [!INCLUDE[TLA#tla_winfx](../../../../includes/tlasharptla-winfx-md.md)] 지원 쓰기 시스템을 위한 기본 제공 처리가 포함되어 있습니다.  
  
 현재 다음과 같은 스크립트가 지원됩니다.  
  
-   아랍어  
  
-   벵골어  
  
-   데바나가리어  
  
-   키릴 자모  
  
-   그리스어  
  
-   구자라트어  
  
-   굴묵키어  
  
-   히브리어  
  
-   표의 문자 스크립트  
  
-   카나다어  
  
-   라오스어  
  
-   라틴어  
  
-   말라얄람어  
  
-   몽골어  
  
-   오디아어  
  
-   시리아어  
  
-   타밀어  
  
-   텔루구어  
  
-   타나 문자  
  
-   태국어\*  
  
-   티베트어  
  
 \*이 릴리스에서 태국어 텍스트의 표시 및 편집은 지원되지만 단어 분리는 지원되지 않습니다.  
  
 현재 다음과 같은 스크립트는 지원되지 않습니다.  
  
-   크메르어  
  
-   옛한글  
  
-   미얀마어  
  
-   스리랑카어  
  
 모든 쓰기 시스템 엔진은 [!INCLUDE[TLA#tla_opentype](../../../../includes/tlasharptla-opentype-md.md)] 글꼴을 지원합니다.  [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] 글꼴은 글꼴 작성자가 더 나은 국가별 및 고급 입력 글꼴을 디자인할 수 있게 하는 [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] 레이아웃 테이블을 포함할 수 있습니다.  [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] 글꼴 레이아웃 테이블에는 텍스트 처리 응용 프로그램에서 텍스트 레이아웃을 향상시킬 수 있게 하는 문자 모양 대체, 문자 모양 배치, 양쪽 맞춤 및 기준선 배치에 대한 정보가 포함되어 있습니다.  
  
 [!INCLUDE[TLA2#tla_opentype](../../../../includes/tla2sharptla-opentype-md.md)] 글꼴에서는 [!INCLUDE[TLA2#tla_unicode](../../../../includes/tla2sharptla-unicode-md.md)] 인코딩을 사용하여 큰 문자 모양 집합을 처리할 수 있습니다.  이러한 인코딩은 광범위한 국가별 지원 및 입력 문자 모양 변형을 허용합니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 텍스트 렌더링은 해상도 독립성을 지원하는 [!INCLUDE[TLA#tla_ct](../../../../includes/tlasharptla-ct-md.md)] 하위 픽셀 기술에 의해 구동됩니다.  따라서 가독성이 크게 향상되고 모든 스크립트에 고품질 잡지 스타일 문서를 지원하는 기능이 제공됩니다.  
  
<a name="intl_layout"></a>   
### 국가별 레이아웃  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]는 가로, 양방향 및 세로 레아아웃을 지원하는 매우 편리한 방법을 제공합니다.  프레젠테이션 프레임워크에서 <xref:System.Windows.FrameworkElement.FlowDirection%2A> 속성을 사용하여 레이아웃을 정의할 수 있습니다.  흐름 방향 패턴은 다음과 같습니다.  
  
-   *LeftToRight* \- 라틴어, 동아시아 언어 등을 위한 가로 레이아웃  
  
-   *RightToLeft* \- 아랍어, 히브리어 등을 위한 양방향  
  
<a name="developing_localizable_apps"></a>   
## 지역화할 수 있는 응용 프로그램 개발  
 글로벌 사용을 위한 응용 프로그램을 작성할 경우 응용 프로그램을 지역화할 수 있어야 한다는 것을 염두에 두어야 합니다.  다음 항목에서는 고려해야 할 사항을 제공합니다.  
  
<a name="mui"></a>   
### 다국어 사용자 인터페이스  
 MUI\(다국어 사용자 인터페이스\)는 [!INCLUDE[TLA2#tla_ui#plural](../../../../includes/tla2sharptla-uisharpplural-md.md)]를 한 언어에서 다른 언어로 전환하기 위한 [!INCLUDE[TLA#tla_ms](../../../../includes/tlasharptla-ms-md.md)] 지원입니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램은 어셈블리 모델을 사용하여 MUI를 지원합니다.  하나의 응용 프로그램이 언어 중립적 어셈블리뿐만 아니라 언어 종속적 위성 리소스 어셈블리를 포함합니다.  진입점은 주 어셈블리의 관리되는 .EXE입니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 리소스 로더는 [!INCLUDE[TLA2#tla_netframewk](../../../../includes/tla2sharptla-netframewk-md.md)]의 리소스 관리자를 활용하여 리소스 조회 및 대체\(fallback\)를 지원합니다.  여러 언어 위성 어셈블리가 동일한 주 어셈블리와 함께 작동합니다.  로드되는 리소스 어셈블리는 현재 스레드의 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A>에 따라 달라집니다.  
  
<a name="localizable_ui"></a>   
### 지역화 가능한 사용자 인터페이스  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램은 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]을 사용하여 해당 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 정의합니다.  [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]을 사용하면 개발자는 속성 및 논리 집합과 함께 개체의 계층을 지정할 수 있습니다.  [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]의 주된 용도는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램을 개발하는 것이지만 임의 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 개체의 계층을 지정하는 데 사용할 수 있습니다.  대부분의 개발자는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]을 사용하여 응용 프로그램의 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 지정하고 [!INCLUDE[TLA#tla_cshrp](../../../../includes/tlasharptla-cshrp-md.md)] 등과 같은 프로그래밍 언어를 사용하여 사용자 상호 작용에 반응합니다.  
  
 리소스 관점에서 보면 언어 독립적인 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 설명하도록 디자인된 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일은 리소스 요소입니다. 따라서 이 파일의 최종 배포 형식은 국가별 언어를 지원하도록 지역화 가능해야 합니다.  [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에서 이벤트를 처리할 수 없으므로 대부분의 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 응용 프로그램에는 이 작업을 수행하기 위한 코드 블록이 포함되어 있습니다.  자세한 내용은 [XAML 개요\(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)를 참조하십시오.  [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일이 BAML 형태의 XAML로 토큰화될 때 코드가 제거되고 다른 바이너리로 컴파일됩니다. BAML 형태의 XAML 파일, 이미지 및 기타 형식은 다른 언어로 지역화할 수 있는 위성 리소스 어셈블리에 포함되거나 지역화가 필요하지 않은 경우 주 어셈블리에 포함됩니다.  
  
> [!NOTE]
>  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램에서는 문자열 테이블, 이미지 등을 비롯한 모든 [!INCLUDE[TLA2#tla_netframewk](../../../../includes/tla2sharptla-netframewk-md.md)] [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 리소스가 지원됩니다.  
  
<a name="building_localizable_apps"></a>   
### 지역화할 수 있는 응용 프로그램 빌드  
 지역화는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]를 다른 문화권에 맞게 적용하는 것을 의미합니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램을 지역화할 수 있게 하려면 개발자는 모든 지역화 가능한 리소스를 리소스 어셈블리에 빌드해야 합니다.  리소스 어셈블리는 다른 언어로 지역화되며 코드 숨김은 로드할 리소스 관리 [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)]를 사용합니다.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 응용 프로그램에 필요한 파일 중 하나는 프로젝트 파일\(.proj\)입니다.  응용 프로그램에서 사용하는 모든 리소스는 이 프로젝트 파일에 포함되어야 합니다.  .csproj 파일에서 제공된 다음 예제에서는 이 작업을 수행하는 방법을 보여 줍니다.  
  
```  
<Resource Include="data\picture1.jpg"/>  
<EmbeddedResource Include="data\stringtable.en-US.restext"/>  
```  
  
 응용 프로그램에서 리소스를 사용하려면 <xref:System.Resources.ResourceManager>를 인스턴스화하고 사용할 리소스를 로드합니다.  다음 예제에서는 이 작업을 수행하는 방법을 보여 줍니다.  
  
 [!code-csharp[LocalizationResources#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LocalizationResources/CSharp/page1.xaml.cs#2)]  
  
<a name="using_clickonce"></a>   
## 지역화된 응용 프로그램과 함께 ClickOnce 사용  
 ClickOnce는 [!INCLUDE[TLA#tla_visualstu2005](../../../../includes/tlasharptla-visualstu2005-md.md)]와 함께 제공되는 새로운 Windows Forms 배포 기술입니다.  이 기술을 통해 응용 프로그램 설치 및 웹 응용 프로그램의 업그레이드를 수행할 수 있습니다.  ClickOnce와 함께 배포된 응용 프로그램이 지역화될 경우 지역화된 문화권에서만 볼 수 있습니다.  예를 들어 배포된 응용 프로그램이 일본어로 지역화된 경우 영어 [!INCLUDE[TLA2#tla_win](../../../../includes/tla2sharptla-win-md.md)]가 아니라 일본어 [!INCLUDE[TLA#tla_win](../../../../includes/tlasharptla-win-md.md)]에서만 볼 수 있습니다.  그러나 일본어 사용자가 영어 버전의 [!INCLUDE[TLA2#tla_win](../../../../includes/tla2sharptla-win-md.md)]를 실행하는 경우가 흔히 있기 때문에 이로 인해 문제가 발생합니다.  
  
 이 문제의 해결 방법은 중립적 언어 대체\(fallback\) 특성을 설정하는 것입니다.  응용 프로그램 개발자는 선택적으로 주 어셈블리에서 리소스를 제거하고 특정 문화권에 해당하는 위성 어셈블리에서 리소스를 찾을 수 있다는 것을 지정할 수 있습니다.  이 프로세스를 제어하려면 <xref:System.Resources.NeutralResourcesLanguageAttribute>를 사용합니다.  <xref:System.Resources.NeutralResourcesLanguageAttribute> 클래스의 생성자에는 두 개의 서명이 있습니다. 그 중 하나는 <xref:System.Resources.ResourceManager>가 대체\(fallback\) 리소스를 추출해야 하는 위치인 주 어셈블리 또는 위성 어셈블리를 지정하기 위해 <xref:System.Resources.UltimateResourceFallbackLocation> 매개 변수를 가집니다.  다음 예제에서는 이 특성을 사용하는 방법을 보여 줍니다.  최종 대체\(fallback\) 위치의 경우 <xref:System.Resources.ResourceManager>는 현재 실행 중인 어셈블리 디렉터리의 하위 디렉터리인 "de"에서 리소스를 찾습니다.  
  
```  
[assembly: NeutralResourcesLanguageAttribute(  
    "de" , UltimateResourceFallbackLocation.Satellite)]  
  
```  
  
## 참고 항목  
 [WPF 전역화 및 지역화 개요](../../../../docs/framework/wpf/advanced/wpf-globalization-and-localization-overview.md)