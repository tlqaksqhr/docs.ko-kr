---
title: XAML 서비스
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], System.Xaml concepts
- XAML Services in WPF [XAML Services]
- System.Xaml [XAML Services], conceptual documentation
ms.assetid: 0e11f386-808c-4eae-9ba6-029ad7ba2211
ms.openlocfilehash: fbe67e81bdc461e290b5cdbb9e1050aec32ce8fa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33566836"
---
# <a name="xaml-services"></a>XAML 서비스
이 항목에서는.NET Framework XAML 서비스 라고 하는 기술 집합의 기능을 설명 합니다. 대부분의 서비스 및 설명 된 Api에 도입 된 어셈블리는 System.Xaml 어셈블리에 있는 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] .NET core 어셈블리 집합. 판독기와 기록기를 지 원하는 스키마 및 스키마 클래스 팩터리를 포함 하는 서비스 클래스, XAML 언어 지원 내장 함수 및 다른 XAML 언어 기능의 특성을 지정 합니다.  
  
## <a name="about-this-documentation"></a>이 설명서에 대 한  
 .NET Framework XAML 서비스에 대 한 개념 설명서는 XAML 언어 및 어떻게이 수에 적용 특정 프레임 워크 예를 들어 사용 경험이 있다고 가정 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] Windows Workflow Foundation 또는 특정 기술 기능 영역에서 예를 들어 빌드 사용자 지정 기능에 <xref:Microsoft.Build.Framework.XamlTypes>합니다. 이 설명서는 표시 언어, XAML 구문 용어 또는 기타 소개 자료로 XAML의 기본 사항을 설명 하는 시도 하지 않습니다. 대신,이 설명서 특히 System.Xaml 어셈블리 라이브러리에서 사용할 수 있는.NET Framework XAML 서비스를 사용 하 여에 중점을 둡니다. XAML 언어 통합 및 확장성 시나리오에는 이러한 Api 대부분입니다. 여기에 다음이 포함 될 수 있습니다.  
  
-   기본 XAML 판독기 또는 (XAML 노드 스트림을 직접 처리, 사용자 고유의 XAML 판독기 또는 XAML 작성기 파생) XAML 작성기의 기능을 확장 합니다.  
  
-   특정 프레임 워크 종속성을 갖지 않는 XAML을 사용할 수 있는 사용자 지정 형식 정의 및 해당 XAML을 전달 하기 위해 형식을 설정 하면.NET Framework XAML 서비스에 시스템 특성을 입력 합니다.  
  
-   XAML 판독기 또는 XAML 작성기 또는 XAML 마크업 소스에 대 한 대화형 편집기 비주얼 디자이너와 같은 응용 프로그램의 구성 요소로 호스트 합니다.  
  
-   XAML 값 변환기 (태그 확장, 사용자 지정 형식에 대 한 형식 변환기)을 작성 합니다.  
  
-   사용자 지정 XAML 스키마 컨텍스트 정의 (지원 형식 소스에 대 한 대체 어셈블리 로드 기법을 사용 하 여 어셈블리를 반영 하; CLR을 사용 하지 않는 로드 된 어셈블리 개념을 사용 하 여 알려진 형식 조회 기법을 사용 하 여 항상 대신; `AppDomain` 및 관련된 보안 모델)입니다.  
  
-   기본 XAML 형식 시스템을 확장 합니다.  
  
-   사용 하는 `Lookup` 또는 `Invoker` XAML에 영향을 줄 수 있는 기술을 시스템과 형식 지원의 평가 입력 합니다.  
  
 XAML에 대 한 소개 자료에 대 한 원하는 경우 시도해 보십시오 [XAML 개요 (WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)합니다. 해당 항목에 설명 XAML 새로운 대상 그룹에 대 한 두 가지를 모두 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] 및 XAML 태그와 XAML 언어 기능을 사용 하 여에 있습니다. 또 다른 유용한 문서가에서 소개 자료는 [XAML 언어 사양](http://go.microsoft.com/fwlink/?LinkId=114525)합니다.  
  
## <a name="net-framework-xaml-services-and-systemxaml-in-the-net-architecture"></a>.NET framework XAML 서비스 및 System.Xaml에.NET 아키텍처  
 Microsoft.NET Framework의 이전 버전의 Microsoft.NET Framework에서 구축 된 프레임 워크에 의해 구현 되었습니다 XAML 언어 기능에 대 한 지원이 ([!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], Windows Workflow Foundation 및 Windows Communication Foundation (WCF)), 즉 동작과 사용 하는 API 사용 하 던 특정 프레임 워크에 따라 다양 합니다. XAML이 포함 파서와 해당 개체 그래프 생성 메커니즘, XAML 언어 내장 함수, serialization 지원 및 등입니다.  
  
 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)],.NET Framework XAML 서비스와 System.Xaml 어셈블리는 XAML 언어 기능을 지원 하기 위해 필요한 대부분을 정의 합니다. 이 XAML 판독기 및 XAML 작성기에 대 한 기본 클래스를 포함합니다. 프레임 워크별 XAML 구현 중 하나에 존재 하지 않는.NET Framework XAML 서비스에 추가 된 가장 중요 한 기능에는 xaml 형식 시스템 표현입니다. 형식 시스템 표현을 프레임 워크의 특정 기능에 의존 하지 않고 XAML 기능에 집중 하는 개체 지향 방식으로 XAML을 표시 합니다.  
  
 XAML 형식 시스템 태그 형식 또는 XAML 원본의;의 실행 시간 특성에 의해 제한 되지 않습니다. 및 모든 특정 지원 형식 시스템에 의해 제한 됩니다. XAML 형식 시스템 형식, 멤버, XAML 스키마 컨텍스트, XML 수준 개념 및 다른 XAML 언어 개념 또는 XAML 내장 함수에 대 한 개체 표현을 포함합니다. 사용 하 여 XAML 형식 시스템을 확장 또는에서는 XAML 판독기 및 XAML 작성기와 같은 클래스에서 파생 되며 프레임 워크는 기술 또는 사용 하는 응용 프로그램에서 사용 하는 특정 기능에 대 한 XAML 표현의 기능을 확장할 수 또는 XAML을 내보냅니다. XAML 스키마 컨텍스트 개념 XAML 개체 작성기 구현, 컨텍스트와 XAML 노드에서 어셈블리 정보를 통해 전달 되는 기술 지원 형식 시스템의 조합을 통해 실제 개체 그래프 쓰기 작업 수 소스입니다. 대 한 자세한 내용은 XAML 스키마 개념입니다. 참조 [기본 XAML 스키마 컨텍스트 및 WPF XAML 스키마 컨텍스트](../../../docs/framework/xaml-services/default-xaml-schema-context-and-wpf-xaml-schema-context.md)합니다.  
  
## <a name="xaml-node-streams-xaml-readers-and-xaml-writers"></a>XAML 노드 스트림, XAML 판독기 및 XAML 작성기  
 .NET Framework XAML 서비스 XAML 언어와 언어도 XAML을 사용 하는 특정 기술 간 관계에서 수행 하는 역할을 이해 하려면 XAML 노드 스트림 및 해당 개념과 API 셰이프 하는 방법의 개념을 이해 하면 도움이 되 고 용어입니다. XAML 노드 스트림의 XAML 언어 표시와 XAML 나타내거나 정의 하는 개체 그래프 사이의 개념적 중간입니다.  
  
-   XAML 판독기는 어떤 형태로 XAML을 처리 하 고 XAML 노드 스트림을 생성 하는 엔터티입니다. API에는 XAML 판독기에서 기본 클래스로 표현 됩니다 <xref:System.Xaml.XamlReader>합니다.  
  
-   XAML 작성기는 XAML 노드 스트림을 처리 하 고 다른 항목을 생성 하는 엔터티입니다. API에는 XAML 작성기 기본 클래스에 의해 표시 됩니다 <xref:System.Xaml.XamlWriter>합니다.  
  
 XAML과 관련 된 두 개의 가장 일반적인 시나리오는 개체 그래프를 인스턴스화하는 XAML을 로드 및 응용 프로그램 또는 도구에서 개체 그래프를 저장 및 한 XAML 표현 (일반적으로 텍스트 파일로 저장 된 태그 형식)를 생성 합니다. XAML을 로드 하 고 개체 그래프를 만든 라고이 설명서는 로드 경로. 저장 하거나 기존 개체 그래프를 XAML로 직렬화 하는 방법은이 설명서를 저장 경로.  
  
 가장 일반적인 유형의 로드 경로 다음과 같이 설명할 수 있습니다.  
  
-   U t F-인코딩된 XML 형식으로 XAML 표현을 시작 하 고 텍스트 파일로 저장 합니다.  
  
-   에 해당 XAML 로드 <xref:System.Xaml.XamlXmlReader>합니다. <xref:System.Xaml.XamlXmlReader> 이 <xref:System.Xaml.XamlReader> 하위 클래스입니다.  
  
-   XAML 노드 스트림을 만들어집니다. 사용 하 여 XAML 노드 스트림의 개별 노드에 액세스할 수 있습니다 <xref:System.Xaml.XamlXmlReader>  /  <xref:System.Xaml.XamlReader> API입니다. 여기서는 가장 일반적인 작업은 "현재 레코드"를 사용 하 여 각 노드를 처리 하는 XAML 노드 스트림에서 진행을 위한 의미 합니다.  
  
-   결과 노드를 XAML 노드 스트림에서 전달는 <xref:System.Xaml.XamlObjectWriter> API입니다. <xref:System.Xaml.XamlObjectWriter> 이 <xref:System.Xaml.XamlWriter> 하위 클래스입니다.  
  
-   <xref:System.Xaml.XamlObjectWriter> 소스 XAML 노드 스트림을 통해 진행 상황에 따라에서 개체 그래프를 한 번에 하나의 개체를 씁니다. 이 항목은 XAML 스키마 컨텍스트 및 종류는 지원 형식 시스템 및 프레임 워크의와 어셈블리에 액세스할 수 있는 구현의 지원을 사용 하 여 수행 됩니다.  
  
-   호출 <xref:System.Xaml.XamlObjectWriter.Result%2A> 개체 그래프의 루트 개체를 가져오기 위해 XAML 노드 스트림의 끝에 있습니다.  
  
 가장 일반적인 유형의 저장 경로 다음과 같이 설명할 수 있습니다.  
  
-   전체 응용 프로그램 실행 시간, UI 콘텐츠 및 상태는 실행된 시간 또는 런타임 시 전체 응용 프로그램의 개체 표현의 더 작은 세그먼트 개체 그래프를 시작 합니다.  
  
-   응용 프로그램 루트 또는 문서 루트 같은 논리적 시작 개체에서 개체를 로드 <xref:System.Xaml.XamlObjectReader>합니다. <xref:System.Xaml.XamlObjectReader> 이 <xref:System.Xaml.XamlReader> 하위 클래스입니다.  
  
-   XAML 노드 스트림을 만들어집니다. 사용 하 여 XAML 노드 스트림의 개별 노드에 액세스할 수 있습니다 <xref:System.Xaml.XamlObjectReader> 및 <xref:System.Xaml.XamlReader> API입니다. 여기서는 가장 일반적인 작업은 "현재 레코드"를 사용 하 여 각 노드를 처리 하는 XAML 노드 스트림에서 진행을 위한 의미 합니다.  
  
-   결과 노드를 XAML 노드 스트림에서 전달는 <xref:System.Xaml.XamlXmlWriter> API입니다. <xref:System.Xaml.XamlXmlWriter> 이 <xref:System.Xaml.XamlWriter> 하위 클래스입니다.  
  
-   <xref:System.Xaml.XamlXmlWriter> 인코딩 XML utf에서 XAML을 작성 합니다. 이 스트림, 또는 다른 형태로 텍스트 파일로 저장할 수 있습니다.  
  
-   호출 <xref:System.Xaml.XamlXmlWriter.Flush%2A> 최종 출력을 가져올 수 있습니다.  
  
 XAML 노드 스트림 개념에 대 한 자세한 내용은 참조 [이해 XAML 노드 스트림 구조 및 개념](../../../docs/framework/xaml-services/understanding-xaml-node-stream-structures-and-concepts.md)합니다.  
  
### <a name="the-xamlservices-class"></a>XamlServices 클래스  
 항상 XAML 노드 스트림을 처리 하는 데 필요한 있는 것은 아닙니다. 기본 로드 경로 또는 저장 경로의 기본을 하려는 경우에 Api를 사용할 수 있습니다는 <xref:System.Xaml.XamlServices> 클래스입니다.  
  
-   다양 한 시그니처에 <xref:System.Xaml.XamlServices.Load%2A> 로드 경로 구현 합니다. 파일 또는 스트림을 로드 하거나 하거나 로드할 수 있습니다는 <xref:System.Xml.XmlReader>, <xref:System.IO.TextReader> 또는 <xref:System.Xaml.XamlReader> 해당 판독기의 Api로 로드 해 XAML 입력을 래핑하 하 합니다.  
  
-   다양 한 서명을 <xref:System.Xaml.XamlServices.Save%2A> 개체 그래프를 저장 하 고 출력을 스트림, 파일 또는 <xref:System.Xml.XmlWriter> / <xref:System.IO.TextWriter> 인스턴스.  
  
-   <xref:System.Xaml.XamlServices.Transform%2A> 로드 경로 저장을 연결 하 여 XAML을 변환 경로 단일 작업으로 합니다. 다른 스키마 컨텍스트 또는 다른 지원 형식 시스템에 사용 될 수 <xref:System.Xaml.XamlReader> 및 <xref:System.Xaml.XamlWriter>, 즉, 결과 XAML이 변환 되는 방식을 방식이 달라 집니다.  
  
 사용 하는 방법에 대 한 자세한 내용은 <xref:System.Xaml.XamlServices>, 참조 [XAMLServices 클래스 및 기본 XAML 읽기 또는 쓰기](../../../docs/framework/xaml-services/xamlservices-class-and-basic-xaml-reading-or-writing.md)합니다.  
  
## <a name="xaml-type-system"></a>XAML 형식 시스템  
 XAML 형식 시스템의 XAML 노드 스트림 지정 된 개별 노드를 사용 하는 데 필요한 Api를 제공 합니다.  
  
 <xref:System.Xaml.XamlType> 개체 노드 시작 및 종료 개체 노드 간의 처리 중인 개체에 대 한 표현이입니다.  
  
 <xref:System.Xaml.XamlMember> 멤버 노드 시작 및 끝 멤버 노드 간의 처리 하는 개체의 멤버에 대 한 표현이입니다.  
  
 등의 Api <xref:System.Xaml.XamlType.GetAllMembers%2A> 및 <xref:System.Xaml.XamlType.GetMember%2A> 및 <xref:System.Xaml.XamlMember.DeclaringType%2A> 간의 관계를 보고 한 <xref:System.Xaml.XamlType> 및 <xref:System.Xaml.XamlMember>합니다.  
  
 .NET Framework XAML 서비스에 의해 구현 된 XAML 형식 시스템의 기본 동작은 리플렉션을 사용 하 여 공용 언어 런타임 (CLR) 및 어셈블리의 CLR 형식의 정적 분석에 기반 합니다. 따라서 특정 CLR 형식에 대 한 XAML 형식 시스템의 기본 구현은 해당 형식 및 해당 멤버의 XAML 스키마를 노출할 수 있습니다 및 XAML 형식 시스템과 관련 하 여이 보고 합니다. 기본 XAML 형식 시스템에서 CLR 상속에 매핑될 형식의 할당 가능성의 개념 및 인스턴스, 값 형식 및 등의 개념 지원 동작 및 CLR의 기능에 매핑됩니다.  
  
## <a name="reference-for-xaml-language-features"></a>XAML 언어 기능에 대 한 참조  
 XAML을 지원 하려면.NET Framework XAML 서비스 XAML 언어 XAML 네임 스페이스에 대해 정의 된 모든 XAML 언어 개념의 특정 구현을 제공 합니다. 이러한 특정 참조 페이지로 설명 되어 있습니다. 언어 기능이 이러한 언어 기능은 XAML 판독기 또는.NET Framework XAML 서비스에서 정의 된 XAML 작성기에 의해 처리 된 경우의 동작 방법을의 관점에서 설명 되어 있습니다. 자세한 내용은 [XAML Namespace (x:) Language Features](../../../docs/framework/xaml-services/xaml-namespace-x-language-features.md)을 참조하세요.
