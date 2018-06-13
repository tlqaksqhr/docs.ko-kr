---
title: WPF의 코드 숨김 및 XAML
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [WPF], code-behind
- code-behind files [WPF], XAML
ms.assetid: 9df6d3c9-aed3-471c-af36-6859b19d999f
ms.openlocfilehash: 09d4f010ca53c5e3d2d9dede172e7ae2102261b9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33541550"
---
# <a name="code-behind-and-xaml-in-wpf"></a>WPF의 코드 숨김 및 XAML
<a name="introduction"></a> 코드 숨김은 태그 정의 된 개체와 결합 되는 코드를 설명 하는 데 사용 되는 용어는 경우는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 태그 컴파일된 페이지는 합니다. 이 항목에서는 코드에 대 한 대체 인라인 코드 메커니즘 및 코드 숨김에 대 한 요구 사항을 설명 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]합니다.  
  
 이 항목에는 다음과 같은 단원이 포함되어 있습니다.  
  
-   [필수 조건](#Prerequisites)  
  
-   [코드 숨김 및 XAML 언어](#codebehind_and_the_xaml_language)  
  
-   [코드 숨김, 이벤트 처리기 및 WPF의 Partial 클래스 요구 사항](#Code_behind__Event_Handler__and_Partial_Class)  
  
-   [x: 코드](#x_Code)  
  
-   [인라인 코드 제한 사항](#Inline_Code_Limitations)  
  
<a name="Prerequisites"></a>   
## <a name="prerequisites"></a>전제 조건  
 이 항목에서는 읽기는 [XAML 개요 (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md) 대 한 기본 지식이 있고는 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 및 개체 지향 프로그래밍 합니다.  
  
<a name="codebehind_and_the_xaml_language"></a>   
## <a name="code-behind-and-the-xaml-language"></a>코드 숨김 및 XAML 언어  
 XAML 언어 태그 파일 로부터 태그 파일을 코드 파일을 연결할 수 있도록 언어 수준 기능을 포함 합니다. XAML 언어 언어 기능을 정의 하는 구체적으로, [X:class 지시문](../../../../docs/framework/xaml-services/x-class-directive.md), [X:subclass 지시문](../../../../docs/framework/xaml-services/x-subclass-directive.md), 및 [X:classmodifier 지시문](../../../../docs/framework/xaml-services/x-classmodifier-directive.md)합니다. 정확히 어떻게 코드를 생성 하는 방법과 태그와 코드를 통합 하는 XAML 언어의 지정에 속하지 않습니다. 코드를 통합 하는 방법을 결정 하는 WPF와 같은 프레임 워크 에서만 사용 하려면 XAML 응용 프로그램 및 프로그래밍 모델 및 빌드에 작업 또는 기타 지원 하는 방법 모두 필요 합니다.  
  
<a name="Code_behind__Event_Handler__and_Partial_Class"></a>   
## <a name="code-behind-event-handler-and-partial-class-requirements-in-wpf"></a>코드 숨김, 이벤트 처리기 및 WPF의 Partial 클래스 요구 사항  
  
-   Partial 클래스는 루트 요소를 지 원하는 형식에서 파생 되어야 합니다.  
  
-   태그 컴파일 빌드 작업의 기본 동작에 따라 비워 있습니다 파생 partial 클래스 정의에 빈 코드 숨김 측에서 note 합니다. 컴파일된 결과 지정 하지 않더라도 부분 클래스에 대 한 기본 클래스로 지원 형식 페이지 루트를 가정 합니다. 그러나이 동작에 의존 하지 않습니다는 것이 좋습니다.  
  
-   코드 숨김에 작성 하는 이벤트 처리기 인스턴스 메서드여야 및 정적 메서드 일 수 없습니다. 로 식별 되는 CLR 네임 스페이스 내에서 partial 클래스에서 이러한 메서드를 정의 해야 `x:Class`합니다. 지시 하기 위해 이벤트 처리기의 이름을 한정할 수 없습니다 한 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서가를 다른 클래스 범위에서 이벤트 연결에 대 한 이벤트 처리기를 찾도록 합니다.  
  
-   처리기는 지원 형식 시스템의 적절 한 이벤트에 대 한 대리자를 일치 해야 합니다.  
  
-   Microsoft Visual Basic 언어에 대 한 특히 있습니다 사용할 수는 언어별 `Handles` 처리기 인스턴스 및 처리기 선언에서 특성을 사용 하 여 처리기를 연결 하는 대신에 이벤트와 연결할 키워드 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]합니다. 그러나이 기법에는 몇 가지 제한 때문에 `Handles` 키워드의 특정 기능을 모두 지원할 수 없는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 와 같은 특정 이벤트 시스템 라우트된 이벤트 시나리오 또는 연결 된 이벤트입니다. 자세한 내용은 참조 [Visual Basic 및 WPF 이벤트 처리](../../../../docs/framework/wpf/advanced/visual-basic-and-wpf-event-handling.md)합니다.  
  
<a name="x_Code"></a>   
## <a name="xcode"></a>x: 코드  
 [X:code](../../../../docs/framework/xaml-services/x-code-intrinsic-xaml-type.md) 지시문 요소에 정의 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]합니다. `x:Code` 지시문 요소 인라인 프로그래밍 코드를 포함할 수 있습니다. 인라인으로 정의 되는 코드와 상호 작용할 수는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 동일한 페이지에 있습니다. 다음 예제에서는 인라인 C# 코드를 보여 줍니다. 코드 내에 있는 통지는 `x:Code` 요소와 코드로 묶어야 `<CDATA[`... `]]>` 에 대 한 콘텐츠를 이스케이프 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]되도록는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서 (해석 중 하나는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 스키마 또는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 스키마) 내용을 해석 하려고 시도 하지 것입니다로 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]합니다.  
  
 [!code-xaml[XAMLOvwSupport#ButtonWithInlineCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page4.xaml#buttonwithinlinecode)]  
  
<a name="Inline_Code_Limitations"></a>   
## <a name="inline-code-limitations"></a>인라인 코드 제한 사항  
 방지 하거나 인라인 코드의 사용을 제한 해야 합니다. 아키텍처 및 코딩 원칙의 측면에서 태그 및 코드 숨김 분리 유지 디자이너와 개발자 역할 훨씬 더 분명 합니다. 자세한 기술 수준에 대해 인라인 코드를 작성 하는 코드 좋지 않을 수 있습니다를 작성 하려면에 항상 작성 하기 때문에 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] partial 클래스를 생성 하 고 기본 XML 네임 스페이스 매핑을 사용할 수 있습니다. 추가할 수 없으므로 `using` 문을 정규화 해야 다양 한는 [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] 설정한 호출 합니다. 기본 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 매핑에 포함 전부는 아니지만 가장 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 에 있는 네임 스페이스는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 어셈블리; 형식 및 다른 CLR 네임 스페이스 내에 포함 된 멤버에 대 한 호출을 정규화 해야 합니다. 또한 정의할 수 없습니다 것 partial 클래스 이외에 다른 인라인 코드에 및 멤버 또는 생성 된 partial 클래스 내에서 변수로 참조 하는 모든 사용자 코드 엔터티 존재 해야 합니다. 다른 특정 프로그래밍 같은 언어 기능이 매크로 또는 `#ifdef` 전역 변수 또는 빌드 변수에 대 한는 사용할 수 없습니다. 자세한 내용은 참조 [X:code 내장 XAML 형식](../../../../docs/framework/xaml-services/x-code-intrinsic-xaml-type.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [XAML 개요(WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [x:Code 내장 XAML 형식](../../../../docs/framework/xaml-services/x-code-intrinsic-xaml-type.md)  
 [WPF 응용 프로그램 빌드](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)  
 [XAML 구문 정보](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md)
