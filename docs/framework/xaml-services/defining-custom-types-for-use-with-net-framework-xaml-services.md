---
title: "Defining Custom Types for Use with .NET Framework XAML Services | Microsoft Docs"
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
  - "defining custom types [XAML Services]"
ms.assetid: c2667cbd-2f46-4a7f-9dfc-53696e35e8e4
caps.latest.revision: 11
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 11
---
# Defining Custom Types for Use with .NET Framework XAML Services
비즈니스 개체이거나 특정 프레임워크에 대한 종속성이 없는 형식인 사용자 지정 형식을 정의하는 경우 XAML에 해당하는 특정한 최선의 방법을 따를 수 있습니다.  이러한 최선의 방법을 따르는 경우 .NET Framework XAML 서비스와 XAML 판독기 및 XAML 작성기는 형식의 XAML 특성을 검색하고 XAML 형식 시스템을 사용하여 XAML 노드 스트림에서 형식을 적절하게 표현할 수 있습니다.  이 항목에서는 형식 정의, 멤버 정의 및 형식 또는 멤버의 CLR 특성 설정에 대한 최선의 방법을 설명합니다.  
  
## XAML의 생성자 패턴 및 형식 정의  
 사용자 지정 클래스가 XAML에서 개체 요소로 인스턴스화되기 위해서는 다음 요구 사항을 충족해야 합니다.  
  
-   사용자 지정 클래스가 공용 클래스여야 하고 매개 변수가 없는 기본 공용 생성자를 노출해야 합니다.  구조체에 대한 자세한 내용은 다음 단원을 참조하십시오.  
  
-   사용자 지정 클래스가 중첩 클래스가 아니어야 합니다.  전체 이름 경로의 추가 "점"은 클래스\-네임스페이스 구분을 모호하게 하며 연결된 속성 등의 다른 XAML 기능을 방해합니다.  
  
 개체가 개체 요소로 인스턴스화될 수 있으면 생성된 개체는 해당 개체를 기본 형식으로 사용하는 모든 속성의 속성 요소 형식을 채울 수 있습니다.  
  
 값 변환기를 사용하도록 설정한 경우 이러한 조건을 충족하지 않는 형식에 대한 개체 값을 여전히 제공할 수 있습니다.  자세한 내용은 [Type Converters and Markup Extensions for XAML](../../../docs/framework/xaml-services/type-converters-and-markup-extensions-for-xaml.md)을 참조하십시오.  
  
### 구조체  
 구조체는 CLR 정의에 따라 XAML에서 항상 생성될 수 있습니다.  이는 CLR 컴파일러가 암시적으로 구조체에 대한 기본 생성자를 만들기 때문입니다.  이 생성자는 모든 속성 값을 기본값으로 초기화합니다.  
  
 그러나 경우에 따라서는 구조체의 기본 생성 동작을 사용하지 않는 것이 바람직할 수 있습니다.  이는 구조체가 값을 채우고 개념적으로 공용 구조체로 사용되기 위한 것일 수 있기 때문입니다.  공용 구조체의 경우 포함된 값의 해석이 서로 달라서 어느 속성도 설정할 수 없습니다.  WPF 어휘에서 이러한 구조체의 예는 <xref:System.Windows.GridLength>입니다.  이러한 구조체는 구조체의 값에 대해 서로 다른 해석이나 모드를 만드는 문자열 규칙을 사용하여 값을 특성 형식으로 표현할 수 있도록 형식 변환기를 구현해야 합니다.  이러한 구조체는 기본값이 아닌 생성자를 통해 코드를 생성하는 경우에도 이와 유사한 동작을 노출해야 합니다.  
  
### 인터페이스  
 인터페이스는 멤버의 기본 형식으로 사용할 수 있습니다.  XAML 형식 시스템은 할당 가능한 목록을 확인하고 값으로 제공된 개체가 인터페이스에 할당될 수 있다고 예상합니다.  할당 가능한 관련 형식이 XAML 생성 요구 사항을 지원하는 한 인터페이스가 XAML 형식으로 표시되어야 하는 방식은 문제가 되지 않습니다.  
  
### 팩터리 메서드  
 팩터리 메서드는 XAML 2009의 기능입니다.  팩터리 메서드는 개체에 기본 생성자가 있어야 한다는 XAML 원칙을 수정합니다.  이 항목에서는 팩터리 메서드에 대해 설명하지 않습니다.  [x:FactoryMethod Directive](../../../docs/framework/xaml-services/x-factorymethod-directive.md)를 참조하십시오.  
  
## 열거형  
 열거형에는 XAML 네이티브 형식 변환 동작이 있습니다.  XAML에서 지정된 열거형 상수 이름은 기본 열거형 형식에 대해 확인되며 XAML 개체 작성기에 열거형 값을 반환합니다.  
  
 XAML은 <xref:System.FlagsAttribute>가 적용된 열거형에 대해 플래그 스타일 사용을 지원합니다.  자세한 내용은 [XAML 구문 정보](../../../ocs/framework/wpf/advanced/xaml-syntax-in-detail.md)를 참조하십시오.  [XAML 구문 정보](../../../ocs/framework/wpf/advanced/xaml-syntax-in-detail.md)는 WPF 사용자를 대상으로 작성되었지만 해당 항목에 있는 대부분의 정보는 특정 구현 프레임워크에 한정되지 않는 XAML과 관련이 있습니다.  
  
## 멤버 정의  
 형식은 XAML 사용을 위한 멤버를 정의할 수 있습니다.  XAML에서 사용할 수 없는 형식이라도 XAML에서 사용할 수 있는 멤버를 정의할 수 있습니다.  이는 CLR 상속 때문에 가능합니다.  멤버를 상속하는 일부 형식이 XAML 사용을 형식으로 지원하고 멤버가 기본 형식에 대한 XAML 사용을 지원하거나 네이티브 XAML 구문을 사용할 수 있는 한 해당 멤버는 XAML에서 사용 가능합니다.  
  
### 속성  
 일반적인 CLR `get` 및 `set` 접근자 패턴과 언어에 적합한 키워드를 사용하여 공용 CLR 속성으로 속성을 정의하는 경우 XAML 형식 시스템은 <xref:System.Xaml.XamlMember.IsReadPublic%2A> 및 <xref:System.Xaml.XamlMember.IsWritePublic%2A>과 같은 <xref:System.Xaml.XamlMember> 속성에 대해 제공된 적절한 정보와 함께 속성을 멤버로 보고할 수 있습니다.  
  
 특정 속성은 <xref:System.ComponentModel.TypeConverterAttribute>를 적용하여 텍스트 구문을 사용하도록 설정할 수 있습니다.  자세한 내용은 [Type Converters and Markup Extensions for XAML](../../../docs/framework/xaml-services/type-converters-and-markup-extensions-for-xaml.md)을 참조하십시오.  
  
 텍스트 구문이나 네이티브 XAML 변환이 없고 태그 확장 사용과 같은 추가 간접 참조가 없는 경우 속성의 형식\(XAML 형식 시스템에서 <xref:System.Xaml.XamlMember.TargetType%2A>\)은 대상 형식을 CLR 형식으로 처리하여 XAML 개체 작성기에 인스턴스를 반환할 수 있어야 합니다.  
  
 XAML 2009를 사용하는 경우 앞의 고려 사항이 충족되지 않으면 [x:Reference Markup Extension](../../../docs/framework/xaml-services/x-reference-markup-extension.md)을 사용하여 값을 제공할 수 있지만 이는 형식 정의 문제보다는 사용 문제에 가깝습니다.  
  
### 이벤트  
 공용 CLR 이벤트로 이벤트를 정의하는 경우 XAML 형식 시스템은 <xref:System.Xaml.XamlMember.IsEvent%2A>가 `true`인 멤버로 이벤트를 보고할 수 있습니다.  이벤트 처리기 작성은 .NET Framework XAML 서비스 기능의 범위에 속하지 않으며 특정 프레임워크 및 구현에 달려 있습니다.  
  
### 메서드  
 메서드의 인라인 코드는 기본 XAML 기능이 아닙니다.  대부분의 경우 XAML에서 메서드 멤버를 직접 참조하지 않으며 XAML에서 메서드의 역할은 특정 XAML 패턴을 지원하는 것뿐입니다.  [x:FactoryMethod Directive](../../../docs/framework/xaml-services/x-factorymethod-directive.md)은 예외입니다.  
  
### 필드  
 CLR 디자인 지침에서는 비정적 필드의 사용을 권장하지 않습니다.  정적 필드의 경우 [x:Static Markup Extension](../../../docs/framework/xaml-services/x-static-markup-extension.md)을 통해서만 정적 필드 값에 액세스할 수 있습니다. 이 경우 [x:Static](../../../docs/framework/xaml-services/x-static-markup-extension.md) 사용에 대한 필드를 노출하기 위해 CLR 정의에서 어떠한 특별한 작업도 수행하지 않습니다.  
  
## 연결 가능한 멤버  
 연결 가능한 멤버는 정의하는 형식에 대한 접근자 메서드 패턴을 통해 XAML에 노출됩니다.  정의하는 형식 자체는 XAML에서 개체로 사용 가능할 필요가 없습니다.  실제로 일반적인 패턴은 연결 가능한 멤버를 소유하고 관련 동작을 구현하지만 UI 표현과 같은 다른 기능은 제공하지 않는 역할로 서비스 클래스를 선언하는 것입니다.  다음 단원을 위해 자리 표시자 *PropertyName*은 연결 가능한 멤버의 이름을 나타냅니다.  이 이름은 [XamlName 문법](../../../docs/framework/xaml-services/xamlname-grammar.md)에서 유효해야 합니다.  
  
 이러한 패턴과 형식의 다른 메서드 간의 이름 충돌에 유의해야 합니다.  이러한 패턴 중 하나와 일치하는 멤버가 있으면 사용자의 의도와 관계없이 XAML 프로세서에서 이 멤버를 연결 가능한 멤버 사용 경로로 해석할 수 있습니다.  
  
#### GetPropertyName 접근자  
 `Get` *PropertyName* 접근자의 시그니처는 다음과 같아야 합니다.  
  
 `public static object Get` *PropertyName* `(object`  `target` `)`  
  
-   `target` 개체는 구현에서 더 구체적인 형식으로 지정할 수 있습니다.  이를 사용하여 연결 가능한 멤버의 사용 범위를 지정할 수 있습니다. 원하는 범위를 벗어나는 사용은 잘못된 캐스팅 예외를 throw하고 이 예외는 XAML 구문 분석 오류에 의해 표시됩니다.  매개 변수 이름 `target`은 요구 사항이 아니지만 대부분의 구현에 사용되는 규칙에 따라 `target`으로 명명되었습니다.  
  
-   반환 값은 각 구현에서 더 구체적인 형식으로 지정할 수 있습니다.  
  
 연결 가능한 멤버의 특성 사용에 대한 <xref:System.ComponentModel.TypeConverter> 사용 텍스트 구문을 지원하려면 <xref:System.ComponentModel.TypeConverterAttribute>를 `Get`*PropertyName* 접근자에 적용합니다.  `set` 대신 `get`에 적용하는 것이 복잡해보일 수 있지만 이 규칙은 디자이너 시나리오에서 유용한 serialize할 수 있는 읽기 전용 연결 가능한 멤버라는 개념을 지원할 수 있습니다.  
  
#### SetPropertyName 접근자  
 Set*PropertyName* 접근자에 대한 시그니처는 다음과 같아야 합니다.  
  
 `public static void Set` *PropertyName* `(object`  `target` `, object`  `value` `)`  
  
-   `target` 개체는 이전 단원에서 설명한 동일한 논리와 결과를 사용하여 사용자 구현에서 더욱 구체적인 형식으로 지정될 수 있습니다.  
  
-   `value` 개체는 구현에서 더 구체적인 형식으로 지정할 수 있습니다.  
  
 이 메서드의 값은 XAML 사용에서 제공되는 입력이며 일반적으로 특성 형식입니다.  특성 형식에서는 텍스트 구문에 대한 값 변환기 지원이 있어야 하며 `Get`*PropertyName* 접근자에 특성을 설정합니다.  
  
### 연결 가능한 멤버 저장소  
 접근자 메서드는 일반적으로 연결 가능한 멤버 값을 개체 그래프에 배치하거나 개체 그래프에서 값을 검색하여 올바르게 serialize기 위한 수단을 제공하는 데는 충분하지 않습니다.  이 기능을 제공하려면 이전 접근자 시그니처의 `target` 개체가 값을 저장할 수 있는 개체여야 합니다.  저장 메커니즘은 연결 가능한 멤버가 멤버 목록에 없는 경우 멤버를 대상에 연결할 수 있다는 연결 가능한 멤버 원칙과 일관성이 있어야 합니다.  .NET Framework XAML 서비스에서는 <xref:System.Xaml.IAttachedPropertyStore> 및 <xref:System.Xaml.AttachablePropertyServices> API를 통해 연결 가능한 멤버 저장소에 대한 구현 기술을 제공합니다.  <xref:System.Xaml.IAttachedPropertyStore>는 XAML 작성기에서 저장소 구현을 검색하는 데 사용되며 접근자의 `target`인 형식에 대해 구현되어야 합니다.  정적 <xref:System.Xaml.AttachablePropertyServices> API는 접근자의 본문 내에서 사용되며, 연결 가능한 멤버를 <xref:System.Xaml.AttachableMemberIdentifier>로 참조합니다.  
  
## XAML 관련 CLR 특성  
 형식, 멤버 및 어셈블리의 특성을 올바르게 설정하는 것은 XAML 형식 시스템 정보를 .NET Framework XAML 서비스에 보고하는 데 중요합니다.  이는 .NET Framework XAML 서비스의 XAML 판독기 및 XAML 작성기를 직접 기반으로 하는 XAML 시스템에서 형식을 사용하려는 경우나 해당 XAML 판독기 및 XAML 작성기를 기반으로 하는 XAML 사용 프레임워크를 정의하거나 사용하는 경우에 관련이 있습니다.  
  
 사용자 지정 형식의 XAML 지원과 관련된 각 XAML 관련 특성의 목록은 [XAML\-Related CLR Attributes for Custom Types and Libraries](../../../docs/framework/xaml-services/xaml-related-clr-attributes-for-custom-types-and-libraries.md)을 참조하십시오.  
  
## 용도  
 사용자 지정 형식을 사용하려면 태그 작성자가 사용자 지정 형식이 포함된 어셈블리 및 CLR 네임스페이스의 접두사를 매핑해야 합니다.  이 항목에서는 이 절차에 대해 설명하지 않습니다.  
  
## 액세스 수준  
 XAML은 액세스 수준이 `internal`인 형식을 로드하고 인스턴스화하기 위한 수단을 제공합니다.  이 기능은 사용자 코드에서 형식을 정의한 다음 동일한 사용자 코드 범위의 일부인 태그에서 해당 클래스를 인스턴스화할 수 있도록 제공됩니다.  
  
 WPF에서는 UI 동작을 리팩터링하기 위한 수단으로 의도되었지만 지원 클래스를 `public`으로 선언하여 적용할 수 있는 확장 메커니즘은 아닌 <xref:System.Windows.Controls.UserControl>을 사용자 코드에서 정의하는 모든 경우가 이러한 예에 해당합니다.  이러한 <xref:System.Windows.Controls.UserControl>을 `internal` 액세스로 선언할 수 있지만 지원 코드가 해당 형식이 XAML 형식으로 참조되는 어셈블리와 동일한 어셈블리로 컴파일되는 경우에 한합니다.  
  
 완전 신뢰 상태에서 XAML을 로드하고 <xref:System.Xaml.XamlObjectWriter>를 사용하는 응용 프로그램의 경우 액세스 수준이 `internal`인 클래스를 로드하는 것이 항상 가능합니다.  
  
 부분 신뢰 상태에서 XAML을 로드하는 응용 프로그램의 경우, <xref:System.Xaml.Permissions.XamlAccessLevel>을 사용하여 액세스 수준 특성을 제어할 수 있습니다.  또한 WPF 템플릿 시스템과 같은 지연 메커니즘에서는 액세스 수준 권한을 전파하고 최종 런타임 확인을 위해 이를 유지할 수 있어야 합니다. 이는 <xref:System.Xaml.Permissions.XamlAccessLevel> 정보를 전달하여 내부적으로 처리됩니다.  
  
### WPF 구현  
 WPF XAML에서는 BAML이 부분 신뢰 상태로 로드되는 경우 BAML 소스인 어셈블리의 <xref:System.Xaml.Permissions.XamlAccessLevel.AssemblyAccessTo%2A>로 액세스가 제한되는 부분 신뢰 액세스 모델 참조를 사용합니다.  지연을 위해 WPF에서는 액세스 수준 정보를 전달하는 메커니즘으로 <xref:System.Xaml.IXamlObjectWriterFactory.GetParentSettings%2A?displayProperty=fullName>를 사용합니다.  
  
 WPF XAML 용어에서 *내부 형식*이란 참조하는 XAML도 포함하는 동일한 어셈블리에서 정의하는 형식입니다.  이러한 형식은 `xmlns:local="clr-namespace:WPFApplication1"`과 같이 매핑의 assembly\= 부분을 고의적으로 생략하는 XAML 네임스페이스를 통해 매핑될 수 있습니다.  BAML이 내부 형식을 참조하고 해당 형식의 액세스 수준이 `internal`인 경우 이를 통해 어셈블리에 대한 `GeneratedInternalTypeHelper` 클래스가 생성됩니다.  `GeneratedInternalTypeHelper`를 방지하려는 경우에는 `public` 액세스 수준을 사용하거나, 관련 클래스를 별도의 어셈블리에 관련 클래스를 팩터링하고 해당 어셈블리를 종속 어셈블리로 만들어야 합니다.  
  
## 참고 항목  
 [XAML\-Related CLR Attributes for Custom Types and Libraries](../../../docs/framework/xaml-services/xaml-related-clr-attributes-for-custom-types-and-libraries.md)   
 [XAML Services](../../../docs/framework/xaml-services/index.md)