---
title: "Default XAML Schema Context and WPF XAML Schema Context | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 04e06a15-09b3-4210-9bdf-9a64c2eccb83
caps.latest.revision: 7
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 7
---
# Default XAML Schema Context and WPF XAML Schema Context
XAML 스키마 컨텍스트는 특정 XAML 어휘를 사용하는 XAML 프로덕션이 개체 쓰기 동작과 상호 작용하는 방식을 한정하는 개념적 엔터티입니다. 이러한 상호 작용 방식에는 형식 매핑 확인 방식, 어셈블리 로드 방식, 특정 판독기 및 작성기 설정의 해석 방식 등이 포함됩니다.  이 항목에서는 .NET Framework XAML 서비스의 기능과 CLR 형식 시스템을 기반으로 하는 관련된 기본 XAML 스키마 컨텍스트에 대해 설명합니다.  또한 이 항목에서는 WPF에 사용되는 XAML 스키마 컨텍스트에 대해서도 설명합니다.  
  
## 기본 XAML 스키마 컨텍스트  
 .NET Framework XAML 서비스에서는 기본 XAML 스키마 컨텍스트를 구현하고 사용합니다.  기본 XAML 스키마 컨텍스트 동작은 <xref:System.Xaml.XamlSchemaContext> 클래스의 API에서 항상 완전히 표시되지는 않습니다.  그러나 대부분의 경우 기본 XAML 스키마 컨텍스트의 영향을 받는 동작은 <xref:System.Xaml.XamlMember>나 <xref:System.Xaml.XamlType> 같은 XAML 형식 시스템의 공통 API를 통해, 또는 기본 XAML 스키마 컨텍스트를 사용하는 XAML 판독기 및 XAML 작성기에 노출된 API를 통해 관찰 가능합니다.  
  
 <xref:System.Xaml.XamlSchemaContext> 생성자를 호출하여 기본 동작을 캡슐화하는 <xref:System.Xaml.XamlSchemaContext>를 만들 수 있습니다.  이 생성자는 기본 XAML 스키마 컨텍스트를 명시적으로 만듭니다.  <xref:System.Xaml.XamlSchemaContext> 입력 매개 변수를 명시적으로 사용하지 않는 API를 사용하여 XAML 판독기 또는 XAML 작성기를 초기화할 경우에는 동일한 기본 XAML 스키마가 암시적으로 만들어집니다.  
  
 기본 XAML 스키마 컨텍스트의 형식 매핑 동작은 CLR 리플렉션을 기반으로 합니다.  여기에는 정의하는 CLR <xref:System.Type>과 관련 <xref:System.Reflection.PropertyInfo> 또는 <xref:System.Reflection.MethodInfo>에 대한 검사가 포함됩니다.  또한 CLR 지원 형식을 사용하는 XAML 형식 또는 XAML 멤버 정보에 대한 세부 사항을 채우기 위해 형식 또는 멤버의 CLR 특성이 사용됩니다.  필요한 정보는 CLR 형식 시스템에서 제공되므로 기본 XAML 스키마 컨텍스트에는 `Invoker` 패턴과 같은 형식 시스템 확장 기술이 필요하지 않습니다.  
  
 어셈블리 로드 논리의 경우 기본 XAML 스키마 컨텍스트는 주로 XAML 네임스페이스 매핑에서 제공되는 어셈블리 값을 기반으로 합니다.  또한 내부 형식을 로드하는 등의 시나리오에서는 <xref:System.Xaml.XamlReaderSettings.LocalAssembly%2A>가 로드할 어셈블리에 대한 힌트를 제공할 수 있습니다.  
  
## WPF XAML 스키마 컨텍스트  
 WPF 구현에서는 기본이 아닌 XAML 스키마 컨텍스트를 구현하여 도입할 수 있는 기능 종류를 알기 쉬운 그림으로 제공하므로 이 항목에서는 WPF XAML 스키마 컨텍스트에 대해 설명합니다.  또한 WPF XAML을 다루는 WPF 설명서에도 XAML 스키마 컨텍스트의 개념에 대한 설명은 그다지 많지 않습니다. XAML 스키마 컨텍스트에서 가능한 동작은 기본 XAML 스키마 컨텍스트의 작동 방식과 함께 설명해야만 완전하게 이해할 수 있습니다.  WPF XAML 스키마 컨텍스트에서는 다음 동작을 구현합니다.  
  
 **조회 재정의:** WPF에는 <xref:System.Windows.Markup.ContentPropertyAttribute> 특성이 설정되지 않아도 작동하는 XAML 콘텐츠 속성이 있는 몇 가지 XAML용 콘텐츠 모델이 있습니다.  WPF용 <xref:System.Xaml.XamlType.LookupContentProperty%2A> 재정의에서 이 동작을 구현합니다.  
  
 **WPF 식에 대한 지연:** WPF에는 런타임 컨텍스트를 사용할 수 있을 때까지 값을 지연시키는 특징적인 몇 가지 식 클래스가 있습니다.  템플릿 확장도 지연 기술을 기반으로 하는 런타임 동작입니다.  
  
 **형식 시스템 조회 최적화:** WPF에는 수백 개의 WPF 정의 클래스로 상속되는 기본 클래스 멤버 정의를 포함하여 광범위한 XAML 어휘 및 개체 모델이 있습니다.  또한 WPF 자체는 여러 어셈블리에 분산되어 있습니다.  WPF는 조회 테이블과 기타 기술을 사용하여 형식 조회를 최적화합니다.  이를 통해 기본 XAML 스키마 컨텍스트와 해당 CLR 기반 형식 조회의 성능이 향상됩니다.  조회 테이블에 없는 경우 동작에는 기본 XAML 스키마 컨텍스트와 유사한 XAML 스키마 컨텍스트 기술이 사용됩니다.  
  
 **XamlType 및 XamlMember 확장:** WPF는 종속성 속성으로 속성 개념을 확장하고, 라우트된 이벤트로 이벤트 개념을 확장합니다.  이러한 개념에 대해 XAML 처리 작업을 위한 가시성을 높이기 위해 WPF에서는 <xref:System.Xaml.XamlType> 및 <xref:System.Xaml.XamlMember>를 확장하고, 종속성 속성 및 라우트된 이벤트 특징을 보고하는 내부 속성을 추가합니다.  
  
### WPF XAML 스키마 컨텍스트 액세스  
 WPF <xref:System.Windows.Markup.XamlReader?displayProperty=fullName> 또는 <xref:System.Windows.Markup.XamlWriter?displayProperty=fullName>를 기반으로 하는 XAML 기술을 사용하는 경우 XAML 판독기 및 XAML 작성기 구현에 WPF XAML 스키마 컨텍스트를 이미 사용하고 있는 것입니다.  
  
 WPF XAML 스키마 컨텍스트로 초기화하지 않는 다른 XAML 판독기 및 XAML 작성기 구현을 사용하는 경우에는 <xref:System.Windows.Markup.XamlReader.GetWpfSchemaContext%2A?displayProperty=fullName>를 통해 유효한 WPF XAML 스키마 컨텍스트를 가져올 수 있습니다.  그런 다음 <xref:System.Xaml.XamlSchemaContext>를 사용하는 다른 API에 대한 초기화를 수행할 때 이 값을 사용할 수 있습니다.  예를 들어 초기화를 위해 <xref:System.Xaml.XamlXmlReader.%23ctor%2A>를 호출하고 WPF XAML 스키마 컨텍스트를 전달할 수 있습니다.  또는 XAML 형식 시스템 작업에 WPF XAML 스키마 컨텍스트를 사용할 수도 있습니다.  여기에는 <xref:System.Xaml.XamlType> 또는 <xref:System.Xaml.XamlMember>의 생성 초기화나 <xref:System.Xaml.XamlSchemaContext.GetXamlType%2A?displayProperty=fullName> 호출이 포함될 수 있습니다.  
  
 순수한 XAML 노드 스트림의 관점에서 WPF XAML의 일부 요소에 액세스할 때 일부 WPF 프레임워크 기능은 아직 작동하지 않을 수 있습니다.  예를 들어 컨트롤용 WPF 템플릿은 아직 적용되어 있지 않습니다.  따라서 런타임에 완전한 시각적 트리로 채워질 수 있는 속성에 액세스할 경우에는 템플릿을 참조하는 속성 값만 볼 수 있습니다.  WPF 태그 확장을 위해 제공되는 서비스 컨텍스트도 런타임이 아닌 상황에서 제공될 경우에는 정확하지 않을 수 있으며, 이로 인해 개체 그래프를 쓰려고 할 때 예외가 발생할 수 있습니다.  
  
## XAML 및 어셈블리 로딩  
 XAML 및 .NET Framework XAML 서비스를 위한 어셈블리 로딩은 <xref:System.AppDomain>의 CLR 정의 개념과 통합됩니다.  XAML 스키마 컨텍스트는 <xref:System.AppDomain> 및 기타 요소를 사용하여 어셈블리 로드 방법이나 런타임 또는 디자인 타임에 형식을 찾을 방법을 해석합니다.  이 논리는 XAML이 XAML 판독기를 위한 느슨한 XAML인지, `XamlBuildTask`에 의해 DLL로 컴파일된 XAML인지, WPF의 `PresentationBuildTask`에 의해 생성된 BAML인지에 따라 약간씩 달라집니다.  
  
 WPF의 XAML 스키마 컨텍스트는 WPF 응용 프로그램 모델과 통합되며, WPF 응용 프로그램 모델에서는 <xref:System.AppDomain>뿐 아니라 WPF 구현 정보에 해당하는 다른 요소도 사용합니다.  
  
#### XAML 판독기 입력\(느슨한 XAML\)  
  
1.  XAML 스키마 컨텍스트는 응용 프로그램의 <xref:System.AppDomain>을 반복하여 가장 최근에 로드한 어셈블리에서부터 해당 이름의 모든 요소와 일치하는 이미 로드된 어셈블리를 찾습니다.  일치하는 어셈블리가 있으면 이 어셈블리가 확인에 사용됩니다.  
  
2.  그렇지 않은 경우에는 CLR <xref:System.Reflection.Assembly>API를 기반으로 하는 다음 기술 중 하나가 어셈블리를 로드하는 데 사용됩니다.  
  
    -   매핑에서 이름이 정규화된 경우 정규화된 이름에 대해 <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=fullName>를 호출합니다.  
  
    -   이전 단계에 실패할 경우 약식 이름과 공개 키 토큰\(있는 경우\)을 사용하여 <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=fullName>를 호출합니다.  
  
    -   매핑에서 이름이 정규화되지 않은 경우 <xref:System.Reflection.Assembly.LoadWithPartialName%2A?displayProperty=fullName>을 호출합니다.  
  
#### XamlBuildTask  
 `XamlBuildTask`는 [!INCLUDE[vsindigo](../../../includes/vsindigo-md.md)] 및 [!INCLUDE[TLA#tla_workflow](../../../includes/tlasharptla-workflow-md.md)]에 사용됩니다.  
  
 `XamlBuildTask`를 통한 어셈블리 참조는 항상 정규화되어야 합니다.  
  
1.  정규화된 이름에 대해 <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=fullName>를 호출합니다.  
  
2.  이전 단계에 실패할 경우 약식 이름과 공개 키 토큰\(있는 경우\)을 사용하여 <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=fullName>를 호출합니다.  
  
#### BAML\(PresentationBuildTask\)  
 BAML의 어셈블리 로드에는 BAML을 구성 요소로 포함하는 초기 어셈블리의 로드와 BAML 프러덕션에서 참조되는 모든 형식에 대한 형식 지원 어셈블리 로드의 두 가지 측면이 있습니다.  
  
##### 초기 태그에 대한 어셈블리 로드:  
 태그를 로드할 소스 어셈블리에 대한 참조는 항상 정규화되지 않습니다.  
  
1.  WPF XAML 스키마 컨텍스트는 WPF 응용 프로그램의 <xref:System.AppDomain>을 반복하여 가장 최근에 로드한 어셈블리에서부터 해당 이름의 모든 요소와 일치하는 이미 로드된 어셈블리를 찾습니다.  일치하는 어셈블리가 있으면 이 어셈블리가 확인에 사용됩니다.  
  
2.  이전 단계에 실패할 경우 약식 이름과 공개 키 토큰\(있는 경우\)을 사용하여 <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=fullName>를 호출합니다.  
  
##### BAML 형식에 의한 어셈블리 참조:  
 BAML 프로덕션에서 사용되는 형식에 대한 어셈블리 참조는 항상 빌드 작업의 출력으로 정규화됩니다.  
  
1.  WPF XAML 스키마 컨텍스트는 WPF 응용 프로그램의 <xref:System.AppDomain>을 반복하여 가장 최근에 로드한 어셈블리에서부터 해당 이름의 모든 요소와 일치하는 이미 로드된 어셈블리를 찾습니다.  일치하는 어셈블리가 있으면 이 어셈블리가 확인에 사용됩니다.  
  
2.  그렇지 않은 경우에는 다음 기술 중 하나가 어셈블리를 로드하는 데 사용됩니다.  
  
    -   정규화된 이름에 대해 <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=fullName>를 호출합니다.  
  
    -   약식 이름 \+ 공개 키 토큰 조합이 로드한 BAML의 소스 어셈블리와 일치하는 경우 이 어셈블리를 사용합니다.  
  
    -   약식 이름 \+ 공개 키 토큰을 사용하여 <xref:System.Reflection.Assembly.Load%28System.String%29?displayProperty=fullName>를 호출합니다.  
  
## 참고 항목  
 [Understanding XAML Node Stream Structures and Concepts](../../../docs/framework/xaml-services/understanding-xaml-node-stream-structures-and-concepts.md)