---
title: 기본 XAML 스키마 컨텍스트 및 WPF XAML 스키마 컨텍스트
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 04e06a15-09b3-4210-9bdf-9a64c2eccb83
caps.latest.revision: 7
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ae7bd21f7dcb60f8cec3e9e4592969c63234cf13
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="default-xaml-schema-context-and-wpf-xaml-schema-context"></a>기본 XAML 스키마 컨텍스트 및 WPF XAML 스키마 컨텍스트
XAML 스키마 컨텍스트는 특정 XAML 어휘를 사용 하는 XAML 프로덕션 형식 매핑을 확인 하는 방법을, 어셈블리를 로드 하는 방법, 특정 어떻게 판독기 및 작성기를 포함 하 여 동작을 작성 하는 개체 상호 작용 하는 방법을 정규화 하는 개념적 엔터티 설정은 해석 됩니다. 이 항목에서는 CLR 형식 시스템을 기반으로 하는 연결 된 기본 XAML 스키마 컨텍스트 및.NET Framework XAML 서비스의 기능을 설명 합니다. 이 항목에서는 WPF에 사용 되는 XAML 스키마 컨텍스트를 설명 합니다.  
  
## <a name="default-xaml-schema-context"></a>기본 XAML 스키마 컨텍스트  
 .NET framework XAML 서비스 둘 다 구현 하 고 기본 XAML 스키마 컨텍스트를 사용 합니다. 기본 XAML 스키마 컨텍스트 동작은 항상의 API에 완전히 표시 되는 <xref:System.Xaml.XamlSchemaContext> 클래스입니다. 그러나 대부분의 경우에서 기본 XAML 스키마 컨텍스트 영향을 주는 동작은 XAML 형식 시스템의 멤버와 같이 공용 API 통해 observable <xref:System.Xaml.XamlMember> 또는 <xref:System.Xaml.XamlType>, 또는 XAML 판독기 및 XAML 작성기를 사용 하는에 노출 하는 Api를 통해 기본 XAML 스키마 컨텍스트입니다.  
  
 만들 수는 <xref:System.Xaml.XamlSchemaContext> 호출 하 여 기본 동작을 캡슐화 하는 <xref:System.Xaml.XamlSchemaContext> 생성자입니다. 이 명시적으로 기본 XAML 스키마 컨텍스트를 만듭니다. XAML 판독기 또는 명시적으로 사용 하지 않는 Api를 사용 하 여 XAML 작성기를 초기화 하는 경우 같은 기본 XAML 스키마 컨텍스트 암시적으로 생성 되는 <xref:System.Xaml.XamlSchemaContext> 입력된 매개 변수입니다.  
  
 기본 XAML 스키마 컨텍스트는 해당 형식 매핑 동작에 대 한 CLR 리플렉션을 사용합니다. 여기에 정의 하는 CLR 검사 <xref:System.Type>, 및 관련 <xref:System.Reflection.PropertyInfo> 또는 <xref:System.Reflection.MethodInfo>합니다. 또한 형식 또는 멤버의 CLR 특성이 XAML 형식 또는 CLR 지원 형식을 사용 하는 XAML 멤버 정보에 대 한 구체적인 정보를 입력 하는 데 사용 됩니다. 기본 XAML 스키마 컨텍스트과 같은 형식 시스템 확장 기술이 필요 하지 않습니다는 `Invoker` 패턴 필요한 정보를 CLR 형식 시스템에서 사용할 수 있습니다.  
  
 어셈블리 로드 논리에 대 한 기본 XAML 스키마 컨텍스트는 XAML 네임 스페이스 매핑을에서 제공 되는 어셈블리 값에 주로 사용 합니다. 또한 <xref:System.Xaml.XamlReaderSettings.LocalAssembly%2A> 어셈블리를 내부 형식을 로드 하는 등의 시나리오에 대 한 로드 힌트 수 있습니다.  
  
## <a name="wpf-xaml-schema-context"></a>WPF XAML 스키마 컨텍스트  
 WPF XAML 스키마 컨텍스트는 WPF 구현은 기능 기본이 아닌 XAML 스키마 컨텍스트를 구현 하 여 유발 될 수 있는 종류의 흥미로운 그림을 제공 하기 때문에이 항목에 설명 되어 있습니다. 또한 XAML 스키마 컨텍스트 개념에서에서 설명 하지 않은 매우 유사 WPF XAML; 해결할 수 있는 WPF 설명서 XAML 스키마 컨텍스트를 사용 하면 동작만 함께 기본 XAML 스키마 컨텍스트 작동 방식을 설명 하는 경우 완벽 하 게 이해할 수 있습니다. WPF XAML 스키마 컨텍스트는 다음과 같은 동작을 구현 합니다.  
  
 **조회를 재정의:** WPF XAML을 위한 몇 가지 정적 콘텐츠 모델에 있는 되지 않아도 작동 하는 XAML 콘텐츠 속성 <xref:System.Windows.Markup.ContentPropertyAttribute> 특성을 사용 합니다. <xref:System.Xaml.XamlType.LookupContentProperty%2A> WPF에 대 한 재정의이 동작을 구현 합니다.  
  
 **WPF 식에 대 한 지연:** WPF 런타임 컨텍스트를 사용할 수 있는 될 때까지 값을 지연 하는 몇 가지 식 클래스를 제공 합니다. 또한 템플릿 확장은 지연 기술을 사용 하는 런타임 동작입니다.  
  
 **형식 시스템 조회 최적화:** WPF는 광범위 한 XAML 어휘 및 개체 모델을 수백 개의 WPF 정의 클래스를 상속 하는 기본 클래스 멤버 정의 포함 하는 합니다. 또한 WPF 자체 여러 어셈블리에 분산 되어 있습니다. WPF는 조회 테이블 및 기타 기술을 사용 하 여 형식 조회를 최적화 합니다. 기본 XAML 스키마 컨텍스트 및 형식 CLR 기반 조회를 통해 향상 된 성능을 제공합니다. 동작 형식 조회 테이블에 존재 하지 않는 경우에 XAML 스키마 컨텍스트 기술이 유사한 기본 XAML 스키마 컨텍스트를 사용 합니다.  
  
 **XamlType 및 XamlMember 확장:** WPF 종속성 속성을 가진 속성 개념을 확장 하 고 라우트된 이벤트와 이벤트 개념입니다. WPF는 확장을 부여 하려면 이러한 개념을 보다 명확 하 게 XAML 처리 작업에 대 한 <xref:System.Xaml.XamlType> 및 <xref:System.Xaml.XamlMember>, 종속성 속성을 보고 하 고 라우트된 이벤트 특징 하는 내부 속성을 추가 합니다.  
  
### <a name="accessing-the-wpf-xaml-schema-context"></a>WPF XAML 스키마 컨텍스트 액세스  
 WPF를 기반으로 하는 XAML 기술을 사용 하는 경우 <xref:System.Windows.Markup.XamlReader?displayProperty=nameWithType> 또는 <xref:System.Windows.Markup.XamlWriter?displayProperty=nameWithType>, WPF XAML 스키마 컨텍스트는 이미 해당 XAML 판독기 및 XAML 작성기 구현의에서 사용 합니다.  
  
 작동 하는 WPF XAML 스키마 컨텍스트를 가져올 수 있습니다를 사용 하는 다른 XAML 판독기 또는 초기화 하지 않는 XAML 작성기 구현의 WPF XAML 스키마 컨텍스트를 사용 하는 경우 <xref:System.Windows.Markup.XamlReader.GetWpfSchemaContext%2A?displayProperty=nameWithType>합니다. 사용 하는 다른 API에 대 한 초기화로이 값을 사용할 수 있습니다는 <xref:System.Xaml.XamlSchemaContext>합니다. 예를 들어, 호출할 수 있습니다 <xref:System.Xaml.XamlXmlReader.%23ctor%2A> 초기화 및 WPF XAML 스키마 컨텍스트를 전달 합니다. 또는 XAML 형식 시스템 작업에 대 한 WPF XAML 스키마 컨텍스트를 사용할 수 있습니다. 생성 초기화가 포함 된 <xref:System.Xaml.XamlType> 또는 <xref:System.Xaml.XamlMember>, 또는 호출 <xref:System.Xaml.XamlSchemaContext.GetXamlType%2A?displayProperty=nameWithType>합니다.  
  
 순수 XAML 노드 스트림의 관점에서 WPF XAML의 특정 측면을 액세스 하면 WPF 프레임 워크 기능 중 일부를 수 있습니다 아직 작동 하지 note 합니다. 예를 들어 컨트롤에 대 한 WPF 템플릿 아직 적용 되지 않습니다. 따라서 런타임 시 완전 한 시각적 트리도 채워질 수 있습니다 하는 속성에 액세스 하는 경우 서식 파일을 참조 하는 속성 값만 볼 수 있습니다. WPF 태그 확장에 대 한 제공 하는 서비스 컨텍스트에 또한 올바르지 않을 런타임이 아닌 상황에서 제공 하는 경우 및 개체 그래프를 작성 하려고 시도할 때 예외가 발생할 수 있습니다.  
  
## <a name="xaml-and-assembly-loading"></a>XAML 및 어셈블리 로딩  
 XAML 및.NET Framework XAML 서비스에 대 한 로드 된 어셈블리의 CLR 정의 개념와 통합 되어 <xref:System.AppDomain>합니다. 사용에 따라 런타임 또는 디자인 타임에 형식을 찾을 또는 어셈블리를 로드 하는 방법을 해석 하는 XAML 스키마 컨텍스트 <xref:System.AppDomain> 및 기타 요인입니다. 논리가 XAML XAML 판독기에 대 한 느슨한 XAML 인지에 따라 약간 다릅니다는 XAML에서 DLL로 컴파일 `XamlBuildTask`, BAML에서 WPF의 생성 또는 `PresentationBuildTask`합니다.  
  
 WPF는 XAML 스키마 컨텍스트를 사용 하는 WPF 응용 프로그램 모델와 통합 되어 <xref:System.AppDomain> WPF 구현 세부 있는 다른 요소 뿐만 아니라 합니다.  
  
#### <a name="xaml-reader-input-loose-xaml"></a>XAML 판독기 입력 (느슨한 XAML)  
  
1.  반복 하는 XAML 스키마 컨텍스트는 <xref:System.AppDomain> 이름의 모든 요소와 일치 하는 이미 로드 된 어셈블리를 찾고, 응용 프로그램의 가장 최근에 로드 에서부터 어셈블리입니다. 일치 하는 항목이 있으면 해당 어셈블리 확인에 사용 됩니다.  
  
2.  CLR에 따라 다음 기술 중 하나는 그렇지 않은 경우 <xref:System.Reflection.Assembly> API는 어셈블리를 로드 하는 데 사용 됩니다.  
  
    -   매개 변수 매핑에서 이름의 정규화 하는 경우 호출 <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> 정규화 된 이름에서.  
  
    -   이전 단계가 실패 하면 짧은 이름 (및 공개 키 토큰이 있는 경우) 사용 하 여 호출할 <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>합니다.  
  
    -   이름, 매개 변수 매핑에서 정규화 된 경우 호출 <xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=nameWithType>합니다.  
  
#### <a name="xamlbuildtask"></a>XamlBuildTask  
 `XamlBuildTask` Windows Communication Foundation (WCF), Windows Workflow Foundation에 사용 됩니다.  
  
 어셈블리 참조를 통해 `XamlBuildTask` 는 항상 정규화 합니다.  
  
1.  호출 <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> 정규화 된 이름에서.  
  
2.  이전 단계가 실패 하면 짧은 이름 (및 공개 키 토큰이 있는 경우) 사용 하 여 호출할 <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>합니다.  
  
#### <a name="baml-presentationbuildtask"></a>BAML (PresentationBuildTask)  
 다음 두 가지 BAML에 대 한 어셈블리 로드를: BAML을 구성 요소로 포함 하는 초기 어셈블리를 로드 하 고 BAML 프로덕션에서 참조 하는 모든 형식에 대 한 형식 지원 어셈블리를 로드 합니다.  
  
##### <a name="assembly-load-for-initial-markup"></a>초기 태그에 대 한 어셈블리를 로드 합니다.  
 태그를 로드할 어셈블리에 대 한 참조 항상 정규화 되지 않습니다.  
  
1.  반복 하는 WPF XAML 스키마 컨텍스트는 <xref:System.AppDomain> 는 이름의 모든 요소와 일치 하는 이미 로드 된 어셈블리를 찾습니다는 WPF 응용 프로그램의 가장 최근에 로드 에서부터 어셈블리입니다. 일치 하는 항목이 있으면 해당 어셈블리 확인에 사용 됩니다.  
  
2.  이전 단계가 실패 하면 짧은 이름 (및 공개 키 토큰이 있는 경우) 사용 하 여 호출할 <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>합니다.  
  
##### <a name="assembly-references-by-baml-types"></a>BAML 형식에서 어셈블리 참조:  
 BAML 프로덕션에 사용 되는 형식에 대 한 어셈블리 참조는 정규화 된 빌드 작업의 출력으로 항상입니다.  
  
1.  반복 하는 WPF XAML 스키마 컨텍스트는 <xref:System.AppDomain> 는 이름의 모든 요소와 일치 하는 이미 로드 된 어셈블리를 찾습니다는 WPF 응용 프로그램의 가장 최근에 로드 에서부터 어셈블리입니다. 일치 하는 항목이 있으면 해당 어셈블리 확인에 사용 됩니다.  
  
2.  그렇지 않으면 어셈블리 로드 사용은 다음 방법 중 하나:  
  
    -   호출 <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType> 정규화 된 이름에서.  
  
    -   약식 이름 + 공개 키 토큰 조합이 BAML에서 로드 된 어셈블리와 일치 하는 경우 해당 어셈블리를 사용 합니다.  
  
    -   짧은 이름 + 공개 키 토큰을 사용 하 여 호출 <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=nameWithType>합니다.  
  
## <a name="see-also"></a>참고 항목  
 [XAML 노드 스트림 구조 및 개념 이해](../../../docs/framework/xaml-services/understanding-xaml-node-stream-structures-and-concepts.md)
