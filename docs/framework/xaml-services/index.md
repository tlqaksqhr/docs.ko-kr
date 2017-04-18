---
title: "XAML Services | Microsoft Docs"
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
  - "XAML [XAML Services], System.Xaml concepts"
  - "XAML Services in WPF [XAML Services]"
  - "System.Xaml [XAML Services], conceptual documentation"
ms.assetid: 0e11f386-808c-4eae-9ba6-029ad7ba2211
caps.latest.revision: 13
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 13
---
# XAML Services
이 항목에서는 .NET Framework XAML 서비스라는 기술 집합의 기능에 대해 설명합니다.  설명하는 서비스와 API는 대부분 System.Xaml 어셈블리에 있습니다. 이 어셈블리는 .NET 핵심 어셈블리의 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] 집합과 함께 도입되었습니다.  서비스에는 판독기 및 작성기, 스키마 클래스 및 스키마 지원, 팩터리, 클래스의 특성 설정, XAML 언어 내장 항목 지원 및 기타 XAML 언어 기능이 포함됩니다.  
  
## 설명서 정보  
 .NET Framework XAML 서비스에 대한 개념 설명서에서는 사용자가 이전에 XAML 언어를 사용한 적이 있으며 XAML 언어를 특정 프레임워크\(예: [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 또는 [!INCLUDE[TLA#tla_workflow](../../../includes/tlasharptla-workflow-md.md)]\) 또는 특정 기술 기능 영역\(예: <xref:Microsoft.Build.Framework.XamlTypes>의 빌드 사용자 지정 기능\)에 적용할 수 있는 방법을 알고 있다고 가정합니다.  이 설명서에서는 태그 언어, XAML 구문 용어 또는 기타 소개 자료로 XAML에 대한 기본 사항을 설명하지는 않습니다.  그 대신 이 설명서에서는 System.Xaml 어셈블리 라이브러리에서 사용하도록 설정되는 .NET Framework XAML 서비스 사용에 초점을 둡니다.  여기에서 API의 대부분은 XAML 언어 통합 및 확장성 시나리오에 대한 것입니다.  여기에는 다음이 포함될 수 있습니다.  
  
-   기본 XAML 판독기 또는 XAML 작성기의 기능 확장\(XAML 노드 스트림 직접 처리, 사용자 고유의 XAML 판독기 또는 XAML 작성기 파생\)  
  
-   특정 프레임워크 종속성이 없는 XAML 사용 가능 사용자 지정 형식 정의 및 XAML 형식 시스템 특성을 .NET Framework XAML 서비스에 전달하도록 형식에 특성 설정  
  
-   XAML 태그 소스의 대화형 편집기나 비주얼 디자이너와 같은 응용 프로그램의 구성 요소로 XAML 판독기 또는 XAML 작성기 호스팅  
  
-   XAML 값 변환기 작성\(태그 확장, 사용자 지정 형식에 대한 형식 변환기\)  
  
-   사용자 지정 XAML 스키마 컨텍스트 정의\(지원 형식 소스에 대체 어셈블리 로드 기법 사용, 어셈블리를 항상 리플렉션하는 대신 알려진 형식 조회 기법 사용, CLR `AppDomain` 및 관련 보안 모델을 사용하지 않는 로드된 어셈블리 개념 사용\)  
  
-   기본 XAML 형식 시스템 확장  
  
-   XAML 형식 시스템과 형식 지원의 평가 방식에 영향을 미치기 위해 `Lookup` 또는 `Invoker` 기법 사용  
  
 XAML을 언어적 측면에서 소개하는 자료를 보려면 [XAML 개요\(WPF\)](../../../ocs/framework/wpf/advanced/xaml-overview-wpf.md)를 참조하십시오.  해당 항목에서는 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)]에 대한 경험이 없고 XAML 태그 및 XAML 언어 기능을 사용한 적이 없는 사용자를 대상으로 XAML에 대해 설명합니다.  또 다른 유용한 문서는 [XAML 언어 사양](http://go.microsoft.com/fwlink/?LinkId=114525)에 있는 소개 자료입니다.  
  
## .NET 아키텍처의 .NET Framework XAML 서비스 및 System.Xaml  
 이전 버전의 [!INCLUDE[TLA#tla_netframewk](../../../includes/tlasharptla-netframewk-md.md)]에서는 XAML 언어 기능 지원이 [!INCLUDE[TLA#tla_netframewk](../../../includes/tlasharptla-netframewk-md.md)]\([!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], [!INCLUDE[TLA#tla_workflow](../../../includes/tlasharptla-workflow-md.md)] 및 [!INCLUDE[vsindigo](../../../includes/vsindigo-md.md)]\)에서 작성된 프레임워크에 의해 구현되었으므로 사용 중인 특정 프레임워크에 따라 동작과 API가 다양했습니다.  여기에는 XAML 파서 및 개체 그래프 생성 메커니즘, XAML 언어 내장 항목, serialization 지원 등이 포함됩니다.  
  
 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]에서 .NET Framework XAML 서비스와 System.Xaml 어셈블리는 XAML 언어 기능을 지원하는 데 필요한 많은 항목을 정의합니다.  여기에는 XAML 판독기 및 XAML 작성기용 기본 클래스가 포함됩니다.  .NET Framework XAML 서비스에 추가된 기능 중 프레임워크별 XAML 구현에 존재하지 않았던 가장 중요한 기능은 XAML에 대한 형식 시스템 표현입니다.  형식 시스템 표현은 프레임워크의 특정 기능에 의존하지 않고 XAML 기능에 집중하는 개체 지향 방식으로 XAML을 제공합니다.  
  
 XAML 형식 시스템은 XAML 원본의 태그 형식 또는 런타임 세부 사항이나 특정 지원 형식 시스템에 의해 제한되지 않습니다.  XAML 형식 시스템은 형식, 멤버, XAML 스키마 컨텍스트, XML 수준 개념 및 기타 XAML 언어 개념이나 XAML 내장 형식에 대한 개체 표현을 포함합니다.  XAML 형식 시스템을 사용하거나 확장하면 XAML 판독기 및 XAML 작성기와 같은 클래스에서 파생될 수 있고 XAML 표현의 기능을 XAML을 사용하거나 내보내는 프레임워크, 기술 또는 응용 프로그램에 의해 활성화되는 특정 기능으로 확장할 수 있습니다.  XAML 스키마 컨텍스트의 개념에서는 XAML 개체 작성기 구현, 컨텍스트에서 어셈블리 정보를 통해 전달되는 기술의 지원 형식 시스템 및 XAML 노드 소스의 조합에서 실제적인 개체 그래프 작성 작업을 수행할 수 있습니다.  XAML 스키마 개념에 대한 자세한 내용은  [Default XAML Schema Context and WPF XAML Schema Context](../../../docs/framework/xaml-services/default-xaml-schema-context-and-wpf-xaml-schema-context.md)를 참조하십시오.  
  
## XAML 노드 스트림, XAML 판독기, XAML 작성기  
 XAML 언어와 XAML을 언어로 사용하는 특정 기술 간의 관계에서 .NET Framework XAML 서비스가 수행하는 역할을 이해하려면 XAML 노드 스트림의 개념 및 어떻게 API와 용어가 XAML 노드 스트림을 통해 형성되는지를 이해하는 것이 도움이 됩니다.  XAML 노드 스트림은 XAML 언어 표현 및 XAML이 나타내거나 정의하는 개체 그래프 간의 개념적 매개물입니다.  
  
-   XAML 판독기는 일정한 형태로 XAML을 처리하고 XAML 노드 스트림을 생성하는 엔터티입니다.  API에서는 기본 클래스 <xref:System.Xaml.XamlReader>가 XAML 판독기를 나타냅니다.  
  
-   XAML 작성기는 XAML 노드 스트림을 처리하고 다른 항목을 생성하는 엔터티입니다.  API에서는 기본 클래스 <xref:System.Xaml.XamlWriter>가 XAML 작성기를 나타냅니다.  
  
 XAML과 관련된 가장 일반적인 두 가지 시나리오는 개체 그래프를 인스턴스화하기 위해 XAML을 로드하는 경우와 응용 프로그램 또는 도구에서 개체 그래프를 저장하고 XAML 표현\(일반적으로 텍스트 파일로 저장된 태그 형식\)을 생성하는 경우입니다.  XAML을 로드하고 개체 그래프를 만드는 것을 이 설명서에서는 흔히 로드 경로라고 합니다.  XAML에 기존 개체 그래프를 저장 또는 serialize하는 것을 이 설명서에서는 흔히 저장 경로라고 합니다.  
  
 가장 일반적인 유형의 로드 경로는 다음과 같이 설명할 수 있습니다.  
  
-   UTF로 인코딩된 XML 형식이며 텍스트 파일로 저장된 XAML 표현으로 시작합니다.  
  
-   해당 XAML을 <xref:System.Xaml.XamlXmlReader>에 로드합니다.  <xref:System.Xaml.XamlXmlReader>는 <xref:System.Xaml.XamlReader> 서브클래스입니다.  
  
-   결과는 XAML 노드 스트림입니다.  <xref:System.Xaml.XamlXmlReader>\/<xref:System.Xaml.XamlReader> API를 사용하여 XAML 노드 스트림의 개별 노드에 액세스할 수 있습니다.  여기서 가장 일반적인 작업은 "현재 레코드" 비유를 사용하여 각 노드를 처리하면서 XAML 노드 스트림에서 앞으로 이동하는 것입니다.  
  
-   결과 노드를 XAML 노드 스트림에서 <xref:System.Xaml.XamlObjectWriter> API에 전달합니다.  <xref:System.Xaml.XamlObjectWriter>는 <xref:System.Xaml.XamlWriter> 서브클래스입니다.  
  
-   <xref:System.Xaml.XamlObjectWriter>는 소스 XAML 노드 스트림에서의 진행률에 따라 한 번에 한 개체씩 개체 그래프를 기록합니다.  이 작업은 지원 형식 시스템 및 프레임워크의 어셈블리와 유형에 액세스할 수 있는 XAML 스키마 컨텍스트 및 구현의 지원을 통해 수행됩니다.  
  
-   XAML 노드 스트림의 끝에서 <xref:System.Xaml.XamlObjectWriter.Result%2A>를 호출하여 개체 그래프의 루트 개체를 가져옵니다.  
  
 가장 일반적인 유형의 저장 경로는 다음과 같이 설명할 수 있습니다.  
  
-   전체 응용 프로그램 런타임의 개체 그래프, 런타임의 UI 콘텐츠와 상태 또는 전체 응용 프로그램의 개체 표현에 대한 런타임의 더 작은 세그먼트로 시작합니다.  
  
-   응용 프로그램 루트, 문서 루트와 같은 논리 시작 개체에서 개체를 <xref:System.Xaml.XamlObjectReader>에 로드합니다.  <xref:System.Xaml.XamlObjectReader>는 <xref:System.Xaml.XamlReader> 서브클래스입니다.  
  
-   결과는 XAML 노드 스트림입니다.  <xref:System.Xaml.XamlObjectReader>\/<xref:System.Xaml.XamlReader> API를 사용하여 XAML 노드 스트림의 개별 노드에 액세스할 수 있습니다.  여기서 가장 일반적인 작업은 "현재 레코드" 비유를 사용하여 각 노드를 처리하면서 XAML 노드 스트림에서 앞으로 이동하는 것입니다.  
  
-   결과 노드를 XAML 노드 스트림에서 <xref:System.Xaml.XamlXmlWriter> API에 전달합니다.  <xref:System.Xaml.XamlXmlWriter>는 <xref:System.Xaml.XamlWriter> 서브클래스입니다.  
  
-   <xref:System.Xaml.XamlXmlWriter>는 XAML을 XML UTF 인코딩으로 기록합니다.  이를 텍스트 파일, 스트림 또는 다른 형태로 저장할 수 있습니다.  
  
-   <xref:System.Xaml.XamlXmlWriter.Flush%2A>를 호출하여 최종 출력을 가져옵니다.  
  
 XAML 노드 스트림이 개념에 대한 자세한 내용은 [Understanding XAML Node Stream Structures and Concepts](../../../docs/framework/xaml-services/understanding-xaml-node-stream-structures-and-concepts.md)를 참조하십시오.  
  
### XamlServices 클래스  
 항상 XAML 노드 스트림을 다루어야 하는 것은 아닙니다.  기본 로드 경로 또는 기본 저장 경로가 필요할 경우 <xref:System.Xaml.XamlServices> 클래스에서 API를 사용할 수 있습니다.  
  
-   <xref:System.Xaml.XamlServices.Load%2A>의 여러 시그니처가 로드 경로를 구현합니다.  파일 또는 스트림을 로드하거나 해당 판독기의 API를 통해 로드하여 XAML 입력을 래핑하는 <xref:System.Xml.XmlReader>, <xref:System.IO.TextReader> 또는 <xref:System.Xaml.XamlReader>를 로드할 수 있습니다.  
  
-   <xref:System.Xaml.XamlServices.Save%2A>의 여러 시그니처가 개체 그래프를 저장하고 출력을 스트림, 파일 또는 <xref:System.Xml.XmlWriter>\/<xref:System.IO.TextWriter> 인스턴스로 생성합니다.  
  
-   <xref:System.Xaml.XamlServices.Transform%2A>은 로드 경로 및 저장 경로를 단일 작업으로 연결하여 XAML을 변환합니다.  다른 스키마 컨텍스트 또는 다른 지원 형식 시스템을 <xref:System.Xaml.XamlReader> 및 <xref:System.Xaml.XamlWriter>에 사용하여 결과 XAML이 변환되는 방법에 영향을 줄 수 있습니다.  
  
 <xref:System.Xaml.XamlServices>를 사용하는 방법에 대한 자세한 내용은 [XAMLServices Class and Basic XAML Reading or Writing](../../../docs/framework/xaml-services/xamlservices-class-and-basic-xaml-reading-or-writing.md)를 참조하십시오.  
  
## XAML 형식 시스템  
 XAML 형식 시스템은 XAML 노드 시스템의 지정된 개별 노드와 작동하는 데 필요한 API를 제공합니다.  
  
 <xref:System.Xaml.XamlType>은 시작 개체 노드 및 종료 개체 노드 간에 처리하고 있는 개체를 나타냅니다.  
  
 <xref:System.Xaml.XamlMember>는 시작 멤버 노드 및 종료 멤버 노드 간에 처리하고 있는 개체 멤버를 나타냅니다.  
  
 <xref:System.Xaml.XamlType.GetAllMembers%2A> 및 <xref:System.Xaml.XamlType.GetMember%2A>, <xref:System.Xaml.XamlMember.DeclaringType%2A> 등의 API는 <xref:System.Xaml.XamlType> 및 <xref:System.Xaml.XamlMember> 간의 관계를 보고합니다.  
  
 .NET Framework XAML 서비스에서 구현되는 XAML 형식 시스템의 기본 동작은 리플렉션을 사용한 어셈블리의 CLR 형식에 대한 정적 분석과 공용 언어 런타임에 기초합니다.  따라서 특정 CLR 형식에 대해 XAML 형식 시스템의 기본 구현은 해당 형식 및 해당 멤버의 XAML 스키마를 노출할 수 있으며 XAML 형식 시스템과 관련하여 이를 보고합니다.  기본 XAML 형식 시스템에서 형식의 할당 가능성에 대한 개념은 CLR 상속에 매핑되며 인스턴스, 값 형식 등의 개념도 CLR의 지원 동작 및 기능에 매핑됩니다.  
  
## XAML 언어 기능에 대한 참조  
 XAML을 지원하기 위해 .NET Framework XAML 서비스는 XAML 언어 XAML 네임스페이스에 대해 정의된 XAML 언어 개념의 특정 구현을 제공합니다.  이러한 구현은 특정 참조 페이지로 문서화됩니다.  언어 기능은 .NET Framework XAML 서비스에서 정의된 XAML 판독기 또는 XAML 작성기에 의해 처리될 때 이러한 언어 기능이 동작하는 방식의 측면에서 문서화됩니다.  자세한 내용은 [XAML Namespace \(x:\) Language Features](../../../docs/framework/xaml-services/xaml-namespace-x-language-features.md)을 참조하십시오.