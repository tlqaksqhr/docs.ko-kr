---
title: "WPF의 코드 숨김 및 XAML | Microsoft Docs"
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
  - "코드 숨김 파일, XAML"
  - "XAML, 코드 숨김"
ms.assetid: 9df6d3c9-aed3-471c-af36-6859b19d999f
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# WPF의 코드 숨김 및 XAML
<a name="introduction"></a> 코드 숨김은 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 페이지를 태그 컴파일할 때 태그 정의 개체와 결합되는 코드를 설명하기 위해 사용하는 용어입니다.  이 항목에서는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 코드에 대한 대체 인라인 코드 메커니즘 및 코드 숨김에 대한 요구 사항을 설명합니다.  
  
 이 항목에는 다음과 같은 단원이 포함되어 있습니다.  
  
-   [사전 요구 사항](#Prerequisites)  
  
-   [코드 숨김 및 XAML 언어](#codebehind_and_the_xaml_language)  
  
-   [WPF의 코드 숨김, 이벤트 처리기 및 partial 클래스 요구 사항](#Code_behind__Event_Handler__and_Partial_Class)  
  
-   [x:Code](#x_Code)  
  
-   [인라인 코드 제한](#Inline_Code_Limitations)  
  
<a name="Prerequisites"></a>   
## 사전 요구 사항  
 이 항목에서는 독자가 [XAML 개요\(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)를 읽었으며 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 및 개체 지향 프로그래밍에 대한 기본적인 지식을 갖고 있다고 가정합니다.  
  
<a name="codebehind_and_the_xaml_language"></a>   
## 코드 숨김 및 XAML 언어  
 XAML 언어에는 태그 파일 쪽에서 코드 파일을 태그 파일에 연결할 수 있는 언어 수준 기능이 포함되어 있습니다.  특히 XAML 언어는 언어 기능 [x:Class 지시문](../../../../docs/framework/xaml-services/x-class-directive.md), [x:Subclass 지시문](../../../../docs/framework/xaml-services/x-subclass-directive.md) 및 [x:ClassModifier 지시문](../../../../docs/framework/xaml-services/x-classmodifier-directive.md)를 정의합니다.  코드를 생성하는 방법과 태그와 코드를 통합하는 방법은 XAML 언어로 지정되지 않습니다.  코드를 통합하는 방법, 응용 프로그램 및 프로그래밍 모델에서 XAML을 사용하는 방법, 빌드 작업 또는 이 모든 작업에 필요한 기타 지원은 WPF와 같은 프레임워크에 의해 결정됩니다.  
  
<a name="Code_behind__Event_Handler__and_Partial_Class"></a>   
## WPF의 코드 숨김, 이벤트 처리기 및 partial 클래스 요구 사항  
  
-   partial 클래스는 루트 요소를 지원하는 형식에서 파생되어야 합니다.  
  
-   태그 컴파일 빌드 작업의 기본 동작에 따라 코드 숨김 쪽의 partial 클래스 정의에서 파생을 공백으로 둘 수 있습니다.  컴파일된 결과에서는 지정되지 않았더라도 페이지 루트의 지원 형식을 partial 클래스의 기본 클래스로 가정합니다.  하지만 이 동작을 사용하는 것이 최선의 방법은 아닙니다.  
  
-   코드 숨김으로 작성하는 이벤트 처리기는 인스턴스 메서드여야 하며 정적 메서드일 수 없습니다.  이러한 메서드는 `x:Class`로 식별된 CLR 네임스페이스 내의 partial 클래스로 정의되어야 합니다.  [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서가 다른 클래스 범위에서 이벤트 연결에 대한 이벤트 처리기를 찾도록 지시하기 위해 이벤트 처리기의 이름을 정규화할 수 없습니다.  
  
-   처리기는 지원 형식 시스템의 적절한 이벤트에 대한 대리자와 일치해야 합니다.  
  
-   [!INCLUDE[TLA#tla_visualb](../../../../includes/tlasharptla-visualb-md.md)] 언어의 경우에는 처리기를 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]의 특성에 연결하는 대신 언어 특정 `Handles` 키워드를 사용하여 처리기 선언에서 인스턴스 및 이벤트와 연결해야 합니다.  하지만 `Handles` 키워드는 특정 라우트된 이벤트 시나리오, 연결된 이벤트 등과 같은 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 이벤트 시스템의 모든 기능을 지원할 수는 없기 때문에 이 기술에는 몇 가지 제한이 따릅니다.  자세한 내용은 [Visual Basic 및 WPF 이벤트 처리](../../../../docs/framework/wpf/advanced/visual-basic-and-wpf-event-handling.md)를 참조하십시오.  
  
<a name="x_Code"></a>   
## x:Code  
 [x:Code](../../../../docs/framework/xaml-services/x-code-intrinsic-xaml-type.md)는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에 정의된 지시문 요소입니다. `x:Code` 지시문 요소는 인라인 프로그래밍 코드를 포함할 수 있습니다.  인라인으로 정의된 코드는 같은 페이지의 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]과 상호 작용할 수 있습니다.  다음 예제에서는 인라인 [!INCLUDE[TLA2#tla_cshrp](../../../../includes/tla2sharptla-cshrp-md.md)] 코드를 보여 줍니다.  코드는 `x:Code` 요소 안에 있으며 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서\([!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 스키마 또는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 스키마를 해석하는\)가 콘텐츠를 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] 그대로 해석하지 않도록 하기 위해 코드를 `<CDATA[`...`]]>`로 감싸서 [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]에 대한 콘텐츠를 이스케이프해야 합니다.  
  
 [!code-xml[XAMLOvwSupport#ButtonWithInlineCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/XAMLOvwSupport/CSharp/page4.xaml#buttonwithinlinecode)]  
  
<a name="Inline_Code_Limitations"></a>   
## 인라인 코드 제한  
 인라인 코드의 사용을 피하거나 제한해야 합니다.  아키텍처 및 코딩 원칙의 측면에서 보면 태그와 코드 숨김을 분리하면 디자이너와 개발자 역할을 더 구분할 수 있습니다.  더 기술적인 측면에서 보면 항상 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]의 생성된 partial 클래스에 작성하며 기본 XML 네임스페이스 매핑만 사용할 수 있기 때문에 인라인 코드로 코드를 작성하는 것은 어려운 작업일 수 있습니다.  `using` 문을 추가할 수 없기 때문에 [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] 호출 대부분을 정규화해야 합니다.  기본 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 매핑에는 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 어셈블리에 있는 [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] 네임스페이스 전부는 아니지만 대부분이 포함됩니다. 다른 CLR 네임스페이스에 포함된 형식 및 멤버에 대한 호출을 정규화해야 합니다.  또한 인라인 코드에서는 partial 클래스 이외의 다른 클래스를 정의할 수 없으며 참조하는 모든 사용자 코드 엔터티는 생성된 partial 클래스 내에서 멤버 또는 변수로 존재해야 합니다.  전역 변수 또는 빌드 변수에 대한 `#ifdef` 또는 매크로 등과 같은 다른 언어 특정 프로그래밍 기능도 사용할 수 없습니다.  자세한 내용은 [x:Code 내장 XAML 형식](../../../../docs/framework/xaml-services/x-code-intrinsic-xaml-type.md)를 참조하십시오.  
  
## 참고 항목  
 [XAML 개요\(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)   
 [x:Code 내장 XAML 형식](../../../../docs/framework/xaml-services/x-code-intrinsic-xaml-type.md)   
 [WPF 응용 프로그램 만들기](../../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)   
 [XAML 구문 정보](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md)