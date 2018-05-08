---
title: 사용자 지정 형식 및 라이브러리에 대한 XAML 관련 CLR 특성
ms.date: 03/30/2017
helpviewer_keywords:
- CLR attributes for custom types [XAML Services]
ms.assetid: 5dfb299a-b6e2-41b8-8694-e6ac987547f1
ms.openlocfilehash: fc99ada6a3bc8465d22527a7ef985f9b057bcf77
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="xaml-related-clr-attributes-for-custom-types-and-libraries"></a>사용자 지정 형식 및 라이브러리에 대한 XAML 관련 CLR 특성
이 항목에서는.NET Framework XAML 서비스에서 정의 된 공용 언어 런타임 (CLR) 특성을 설명 합니다. 또한 다른 CLR 특성.NET Framework에 정의 된 어셈블리 또는 형식에 대 한 응용 프로그램에 대 한 XAML 관련 시나리오를 설명 합니다. 이러한 CLR 특성으로 어셈블리, 형식 또는 멤버를 설정 하면 해당 형식과 관련 된 XAML 형식 시스템 정보를 제공 합니다. 정보 또는 사용 하 여.NET Framework XAML 서비스 XAML 노드 스트림을 직접 처리 하기 위한 전용된 XAML 판독기 및 XAML 작성기를 통해 모든 XAML 소비자에 게 제공 됩니다.  
  
## <a name="xaml-related-clr-attributes-for-custom-types-and-custom-members"></a>사용자 지정 형식 및 사용자 지정 멤버에 대 한 XAML 관련 CLR 특성  
 CLR 특성을 사용 하 여 형식을 정의 하 전체 CLR을 사용 하는, 그렇지 않으면 이러한 특성은 사용할 수 없습니다 과정이 수반 됩니다. 백업 유형을 정의 하는 CLR을 사용 하는 경우.NET Framework XAML 서비스 XAML 작성기에서 사용 하는 기본 XAML 스키마 컨텍스트 백업 어셈블리에 대해 리플렉션을 통해 CLR 특성이 읽을 수 있습니다.  
  
 다음 섹션에서는 사용자 정의 형식 또는 사용자 지정 멤버에 적용할 수 있는 XAML 관련 특성을 설명 합니다. 각 CLR 특성 XAML 형식 시스템에 관련 된 정보를 전달 합니다. 로드 경로에서는 정보 특성 사용된 하는 데 도움이 XAML 판독기가 유효한 XAML 노드 스트림을 형성 또는 XAML 작성기가 유효한 개체 그래프를 생성 하는 데 도움이 됩니다. 파일에서 경로, XAML 형식 시스템 정보를 다시 구성 하는 유효한 XAML 노드 스트림을 형성 하는 XAML 판독기를 사용 하거나 특성 사용된 정보 또는 serialization 힌트 또는 XAML 작성기 또는 기타 XAML 소비자에 대 한 요구 사항을 선언 합니다.  
  
### <a name="ambientattribute"></a>AmbientAttribute  
 **참조 설명서:**  <xref:System.Windows.Markup.AmbientAttribute>  
  
 **적용 대상:** 클래스, 속성, 또는 `get` 연결 가능한 속성을 지 원하는 접근자 멤버입니다.  
  
 **인수:** 없음  
  
 <xref:System.Windows.Markup.AmbientAttribute> 속성 또는 특성 사용된 하 여 형식에 사용 하는 모든 속성 XAML의 앰비언트 속성 개념에 따라 해석 되어야 함을 나타냅니다. 앰비언트 개념은 XAML 프로세서가 멤버의 형식 소유자를 결정하는 방법과 관련됩니다. 앰비언트 속성 값 사용 가능 하도록 파서 컨텍스트에서 하지만 일반적인 형식 멤버 조회가 바로 XAML 노드 만들려는 집합에 대 한 일시 중단 되는 개체 그래프를 만들 때 필요한 속성이입니다.  
  
 앰비언트 개념은 CLR 특성이 정의 하는 방법의 측면에서 속성으로 표현 되지 않는 연결 가능한 멤버에 적용할 수 있습니다 <xref:System.AttributeTargets>합니다. 메서드 특성 사용만의 경우에 적용 해야는 `get` 사용을 지 원하는 연결할 수 있는 XAML에 대 한 접근자입니다.  
  
### <a name="constructorargumentattribute"></a>ConstructorArgumentAttribute  
 **참조 설명서:**  <xref:System.Windows.Markup.ConstructorArgumentAttribute>  
  
 **적용 대상:** 클래스  
  
 **인수:** 단일 생성자 인수를 일치 하는 속성의 이름을 지정 하는 문자열입니다.  
  
 <xref:System.Windows.Markup.ConstructorArgumentAttribute> 지정 된 이름의 속성이 생성 정보를 제공 하 고 기본이 아닌 생성자 구문을 사용 하 여 개체를 초기화할 수 있습니다를 지정 합니다. 이 정보는 주로 XAML serialization용입니다. 자세한 내용은 <xref:System.Windows.Markup.ConstructorArgumentAttribute>을 참조하세요.  
  
### <a name="contentpropertyattribute"></a>ContentPropertyAttribute  
 **참조 설명서:**  <xref:System.Windows.Markup.ContentPropertyAttribute>  
  
 **적용 대상:** 클래스  
  
 **인수:** 특성이 지정 된 형식의 멤버의 이름을 지정 하는 문자열입니다.  
  
 <xref:System.Windows.Markup.ContentPropertyAttribute> 해당 형식에 대 한 XAML 콘텐츠 속성으로는 인수 이름이 지정 된 속성이 사용할 수 있는지를 나타냅니다. XAML 콘텐츠 속성 정의를 정의 하는 형식에 할당할 수 있는 모든 파생된 형식 상속 합니다. 적용 하 여 특정 파생 유형에 정의 재정의할 수 <xref:System.Windows.Markup.ContentPropertyAttribute> 파생 형식에 특정 합니다.  
  
 XAML 콘텐츠 속성으로 사용 되는 속성에 대 한 XAML 사용에 속성 요소는 속성에 대 한 태그를 생략할 수 있습니다. 일반적으로 콘텐츠 및 포함 모델에 대 한 간소화 된 XAML 태그를 개선 하는 XAML 콘텐츠 속성을 지정할 수 있습니다. 한 명의 멤버만 XAML 콘텐츠 속성으로 지정할 수 있으므로 있습니다 해야 하는 경우가 일부의 컨테이너에 대 한 형식의 속성으로 지정 해야 하는 XAML 콘텐츠 속성인 되도록 디자인 선택 합니다. 다른 컨테이너 속성은 명시적 속성 요소와 함께 사용 되어야 합니다.  
  
 XAML 노드 스트림의 XAML 콘텐츠 속성을 계속 나타날 `StartMember` 및 `EndMember` 에 대 한 속성의 이름을 사용 하 여 노드는 <xref:System.Xaml.XamlMember>합니다. XAML 콘텐츠 속성인 구성원 인지 확인 하려면는 <xref:System.Xaml.XamlType> 에서 값의 `StartObject` 놓고의 값을 가져올 <xref:System.Xaml.XamlType.ContentProperty%2A>합니다.  
  
### <a name="contentwrapperattribute"></a>ContentWrapperAttribute  
 **참조 설명서:**  <xref:System.Windows.Markup.ContentWrapperAttribute>  
  
 **적용 대상:** 클래스, 특히 컬렉션 형식.  
  
 **인수:** A <xref:System.Type> 외부 콘텐츠에 대 한 콘텐츠 래퍼 형식으로 사용할 형식을 지정 하 합니다.  
  
 <xref:System.Windows.Markup.ContentWrapperAttribute> 외부 콘텐츠를 래핑하는 데 사용 될 연결 된 컬렉션 형식에 하나 이상의 형식을 지정 합니다. 외부 콘텐츠를 콘텐츠 속성의 형식에 형식 시스템 제약 조건이 캡처하지 않으면 소유 하는 형식에 대 한 XAML 사용은 지원 가능한 콘텐츠 사례의 모든 사례를 참조 합니다. 특정 유형의 콘텐츠 강력한 형식의 제네릭 있는 문자열을 지원할 수에 대 한 XAML을 지원 하는 예를 들어 <xref:System.Collections.ObjectModel.Collection%601>합니다. 콘텐츠 래퍼는 마이그레이션 텍스트 관련 콘텐츠 모델 같은 컬렉션에 대 한 할당 가능한 값의 XAML의 개념으로 기존의 태그 규칙을 마이그레이션하는 데 유용 합니다.  
  
 둘 이상의 콘텐츠 래퍼 종류를 지정 하려면 특성을 여러 번 적용 합니다.  
  
### <a name="dependsonattribute"></a>DependsOnAttribute  
 **참조 설명서:**  <xref:System.Windows.Markup.DependsOnAttribute>  
  
 **적용 대상:** 속성  
  
 **인수:** 특성이 지정 된 종류의 다른 멤버의 이름을 지정 하는 문자열입니다.  
  
 <xref:System.Windows.Markup.DependsOnAttribute> 특성이 지정 된 속성이 다른 속성의 값에 따라 달라 집니다 나타냅니다. 이 특성 속성 정의에 적용 하면 종속 속성 XAML 개체 작성에서 먼저 처리 됩니다. 사용 <xref:System.Windows.Markup.DependsOnAttribute> 유효한 개체 만들기에 대 한 구문 분석은 특정 순서를 따라야 합니다 위치 형식에 대 한 속성 예외적인 경우를 지정 합니다.  
  
 여러를 적용할 수 있습니다 <xref:System.Windows.Markup.DependsOnAttribute> 속성 정의에 사례입니다.  
  
### <a name="markupextensionreturntypeattribute"></a>MarkupExtensionReturnTypeAttribute  
 **참조 설명서:**  <xref:System.Windows.Markup.MarkupExtensionReturnTypeAttribute>  
  
 **적용 대상:** 기대할 수 있는 클래스는 <xref:System.Windows.Markup.MarkupExtension> 파생 형식입니다.  
  
 **인수:** A <xref:System.Type> 으로 기대 하는 가장 정확한 형식을 지정 하는 `ProvideValue` 특성 사용의 결과 <xref:System.Windows.Markup.MarkupExtension>합니다.  
  
 자세한 내용은 참조 [XAML 개요에 대 한 태그 확장](../../../docs/framework/xaml-services/markup-extensions-for-xaml-overview.md)합니다.  
  
### <a name="namescopepropertyattribute"></a>NameScopePropertyAttribute  
 **참조 설명서:**  <xref:System.Windows.Markup.NameScopePropertyAttribute>  
  
 **적용 대상:** 클래스  
  
 **인수:** 두 가지 형태의 attribution 지원:  
  
-   특성 사용된 하는 형식에는 속성의 이름을 지정 하는 문자열입니다.  
  
-   속성의 이름을 지정 하는 문자열 및 <xref:System.Type> 명명된 된 속성을 정의 하는 형식에 대 한 합니다. XAML 이름 범위 속성으로 연결 가능한 멤버를 지정 하는 데이 폼은입니다.  
  
 <xref:System.Windows.Markup.NameScopePropertyAttribute> 특성 사용된 클래스에 대 한 XAML 이름 범위 값을 제공 하는 속성을 지정 합니다. XAML 이름 범위 속성을 구현 하는 개체를 참조 해야 하는 <xref:System.Windows.Markup.INameScope> 실제 XAML 이름 범위, 해당 저장소와 해당 동작을 저장 합니다.  
  
### <a name="runtimenamepropertyattribute"></a>RuntimeNamePropertyAttribute  
 **참조 설명서:**  <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>  
  
 **적용 대상:** 클래스  
  
 **인수:** 특성이 지정 된 형식에 런타임 이름 속성의 이름을 지정 하는 문자열입니다.  
  
 <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> XAML에 매핑되는 특성 형식 속성을 보고 [X:name 지시문](../../../docs/framework/xaml-services/x-name-directive.md)합니다. 속성 형식 이어야 합니다 <xref:System.String> 하며 읽기/쓰기 여야 합니다.  
  
 정의 하는 형식에 할당할 수 있는 모든 파생된 형식에 상속 됩니다. 적용 하 여 특정 파생 유형에 정의 재정의할 수 <xref:System.Windows.Markup.RuntimeNamePropertyAttribute> 파생 형식에 특정 합니다.  
  
### <a name="trimsurroundingwhitespaceattribute"></a>TrimSurroundingWhitespaceAttribute  
 **참조 설명서:**  <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>  
  
 **적용 대상:** 형식  
  
 **인수:** 없음.  
  
 <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute> 공백과 중요 한 콘텐츠 내에서 자식 요소로 표시 될 수 있는 특정 형식에 적용 됩니다 (들어 있는 컬렉션에 포함 된 콘텐츠 <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>). <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute> 저장에 주로 관련 된 경로, 하지만 로드 경로에서 XAML 형식 시스템에서 사용할 수 있는 검사 하 여 <xref:System.Xaml.XamlType.TrimSurroundingWhitespace%2A?displayProperty=nameWithType>합니다. 자세한 내용은 참조 [XAML의 공백 처리](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md)합니다.  
  
### <a name="typeconverterattribute"></a>TypeConverterAttribute  
 **참조 설명서:**  <xref:System.ComponentModel.TypeConverterAttribute>  
  
 **적용 대상:** 클래스, 속성, 메서드 (유일한 XAML 유효한 메서드 사례는는 `get` 지 원하는 연결 가능한 멤버 접근자) 합니다.  
  
 **인수:** 는 <xref:System.Type> 의 <xref:System.ComponentModel.TypeConverter>합니다.  
  
 <xref:System.ComponentModel.TypeConverterAttribute> XAML에서 컨텍스트는 사용자 지정 참조 <xref:System.ComponentModel.TypeConverter>합니다. 이 <xref:System.ComponentModel.TypeConverter> 사용자 정의 형식 또는 해당 형식의 멤버에 대 한 형식 변환 동작을 제공 합니다.  
  
 적용 된 <xref:System.ComponentModel.TypeConverterAttribute> 특성을 참조 하는 형식 변환기 구현 형식입니다. 클래스, 구조체 또는 인터페이스에서 XAML을 위한 형식 변환기를 정의할 수 있습니다. 변환에서는 기본적으로 활성화 되어 있는지, 열거형에 대 한 형식 변환을 제공 필요가 없습니다.  
  
 형식 변환기는 의도 한 대상 유형으로 특성이 나 초기화 텍스트 태그에서 사용 되는 문자열에서 변환할 수 있어야 합니다. 자세한 내용은 참조 [TypeConverters 및 XAML](../../../docs/framework/wpf/advanced/typeconverters-and-xaml.md)합니다.  
  
 XAML 위한 형식 변환기 동작에는 형식의 모든 값을 적용 하는 대신 특정 속성에 구성 될 수도 있습니다. 이 경우, 적용 <xref:System.ComponentModel.TypeConverterAttribute> 속성 정의에 (외부 정의 특정 하지 `get` 및 `set` 정의).  
  
 사용자 지정 연결 가능한 멤버의 XAML 사용에 대 한 형식 변환기 동작을 적용 하 여 할당 될 수 있습니다 <xref:System.ComponentModel.TypeConverterAttribute> 에 `get` XAML 사용을 지 원하는 메서드 접근자입니다.  
  
 비슷한 <xref:System.ComponentModel.TypeConverter>, <xref:System.ComponentModel.TypeConverterAttribute> XAML 도입 되기 전에.NET Framework에 존재 하 고 형식 변환기 모델 다른 목적으로 제공 합니다. 참조 하 고 사용 하기 위해 <xref:System.ComponentModel.TypeConverterAttribute>를 완전히 정규화 하거나 제공 해야 합니다는 `using` 문을 <xref:System.ComponentModel>합니다. 프로젝트에는 시스템 어셈블리는 포함 해야 합니다.  
  
### <a name="uidpropertyattribute"></a>UidPropertyAttribute  
 **참조 설명서:**  <xref:System.Windows.Markup.UidPropertyAttribute>  
  
 **적용 대상:** 클래스  
  
 **인수:** 관련 속성 이름으로 참조 하는 문자열입니다.  
  
 별칭을 지정 하는 클래스의 CLR 속성을 나타냅니다는 [X:uid 지시문](../../../docs/framework/xaml-services/x-uid-directive.md)합니다.  
  
### <a name="usableduringinitializationattribute"></a>UsableDuringInitializationAttribute  
 **참조 설명서:**  <xref:System.Windows.Markup.UsableDuringInitializationAttribute>  
  
 **적용 대상:** 클래스  
  
 **인수:** 부울 값입니다. 특성의 의도 한 목적을 위해 사용 하는 경우이 항상로 지정할 수 `true`합니다.  
  
 이 형식이 XAML 개체 그래프를 만드는 동안 하향식으로 빌드되는지 여부를 나타냅니다. 고급 개념은 밀접 한 관련이 있을 프로그래밍 모델의 정의입니다. 자세한 내용은 <xref:System.Windows.Markup.UsableDuringInitializationAttribute>을 참조하세요.  
  
### <a name="valueserializerattribute"></a>ValueSerializerAttribute  
 **참조 설명서:**  <xref:System.Windows.Markup.ValueSerializerAttribute>  
  
 **적용 대상:** 클래스, 속성, 메서드 (유일한 XAML 유효한 메서드 사례는는 `get` 지 원하는 연결 가능한 멤버 접근자) 합니다.  
  
 **인수:** A <xref:System.Type> 특성이 지정 된 형식의 모든 속성을 직렬화 할 때 사용할 값 serializer 지원 클래스를 지정 하는 또는 특정 특성 속성을 사용 합니다.  
  
 <xref:System.Windows.Markup.ValueSerializer> 자세한 상태와 컨텍스트를 필요로 하는 값 serialization 클래스 지정는 <xref:System.ComponentModel.TypeConverter> 않습니다. <xref:System.Windows.Markup.ValueSerializer> 적용 하 여 연결 가능한 멤버와 연결할 수는 <xref:System.Windows.Markup.ValueSerializerAttribute> 특성에는 정적 `get` 연결 가능한 멤버에 대 한 접근자 메서드. 값 serialization도 적용 됩니다. 열거형, 인터페이스 및 구조체에 대 한 하지만 대리자에 대 한 합니다.  
  
### <a name="whitespacesignificantcollectionattribute"></a>WhitespaceSignificantCollectionAttribute  
 **참조 설명서:**  <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>  
  
 **적용 대상:** 클래스, 특히 개체 요소 주위의 공백을 UI 표현에 중요할 수 있습니다를 혼합 된 콘텐츠를 호스팅할 것으로 예상 되는 컬렉션 형식.  
  
 **인수:** 없음.  
  
 <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute> 컬렉션 형식이 컬렉션 내에서 XAML 노드 스트림의 값 노드 있는 XAML 프로세서에서 중요 한 공백인으로 처리 한다는 것을 나타냅니다. 자세한 내용은 참조 [XAML의 공백 처리](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md)합니다.  
  
### <a name="xamldeferloadattribute"></a>XamlDeferLoadAttribute  
 **참조 설명서:**  <xref:System.Windows.Markup.XamlDeferLoadAttribute>  
  
 **적용 대상:** 클래스 속성입니다.  
  
 **인수:** 지원 두 attribution 형식을 문자열로, 구성 또는 형식을로 <xref:System.Type>합니다. <xref:System.Windows.Markup.XamlDeferLoadAttribute>을 참조하세요.  
  
 클래스 또는 속성에 XAML에 대 한 지연 된 로드 사용 (예: 템플릿 동작의 경우) 및 지연 동작 및 해당 대상/콘텐츠 형식을 사용할 수 있는 클래스를 보고를 나타냅니다.  
  
### <a name="xamlsetmarkupextensionattribute"></a>XamlSetMarkupExtensionAttribute  
 **참조 설명서:**  <xref:System.Windows.Markup.XamlSetMarkupExtensionAttribute>  
  
 **적용 대상:** 클래스  
  
 **인수:** 콜백의 이름을 지정 합니다.  
  
 클래스는 하나 이상의 해당 속성에 대 한 값을 제공 하는 태그 확장을 사용할 수 및 XAML 작성기 클래스의 속성에 대해 태그 확장 설정 작업을 수행 하기 전에 호출 해야 하는 처리기 참조를 나타냅니다.  
  
### <a name="xamlsettypeconverterattribute"></a>XamlSetTypeConverterAttribute  
 **참조 설명서:**  <xref:System.Windows.Markup.XamlSetTypeConverterAttribute>  
  
 **적용 대상:** 클래스  
  
 **인수:** 콜백의 이름을 지정 합니다.  
  
 클래스는 하나 이상의 해당 속성에 대 한 값을 제공 하는 형식 변환기를 사용할 수 및 XAML 작성기 클래스의 속성에 대해 형식 변환기 설정 작업을 수행 하기 전에 호출 해야 하는 처리기 참조를 나타냅니다.  
  
### <a name="xmllangpropertyattribute"></a>XmlLangPropertyAttribute  
 **참조 설명서:**  <xref:System.Windows.Markup.XmlLangPropertyAttribute>  
  
 **적용 대상:** 클래스  
  
 **인수:** 별칭을 속성의 이름을 지정 하는 문자열 `xml:lang` 특성이 지정 된 형식에 있습니다.  
  
 <xref:System.Windows.Markup.XmlLangPropertyAttribute> XML에 매핑되는 특성 형식 속성을 보고 `lang` 지시문입니다. 속성은 형식의 반드시 없습니다 <xref:System.String>, 있지만 (가능 특정 속성 또는 속성의 형식과 형식 변환기를 연결 하 여) 문자열에서 할당 되어야 합니다. 속성은 읽기/쓰기 여야 합니다.  
  
 매핑 시나리오 `xml:lang` XMLDOM을 사용 하 여 특별히 처리 하지 않고는 런타임 개체 모델에서 지정 된 XML 언어 정보에 액세스할 수 있도록 합니다.  
  
 정의 하는 형식에 할당할 수 있는 모든 파생된 형식에 상속 됩니다. 적용 하 여 특정 파생 유형에 정의 재정의할 수 <xref:System.Windows.Markup.XmlLangPropertyAttribute> 특정에서 파생 된 유형인 일반적인 시나리오는 라고 합니다.  
  
## <a name="xaml-related-clr-attributes-at-the-assembly-level"></a>어셈블리 수준에서 XAML 관련 CLR 특성  
 다음 섹션에서는 형식 또는 멤버 정의에 적용 되지 않습니다 되지만 어셈블리에 적용 되는 XAML 관련 특성을 설명 합니다. 이러한 특성은 XAML에서 사용 하도록 사용자 지정 형식을 포함 하는 라이브러리 정의의 전반적인 목표와 관련이 있습니다. 특성 중 일부 의미 하지는 않습니다 영향 범위는 XAML 노드 스트림에서 직접 있지만 노드 스트림에서 다른 소비자가 사용할에 전달 됩니다. 소비자는 정보에 대 한 디자인 환경 또는 XAML 네임 스페이스 정보가 필요 하 고 접두사 정보를 연결 하는 serialization 프로세스를 포함 합니다. XAML 스키마 컨텍스트 (.NET Framework XAML 서비스 기본값 포함)도이 정보를 사용 합니다.  
  
### <a name="xmlnscompatiblewithattribute"></a>XmlnsCompatibleWithAttribute  
 **참조 설명서:**  <xref:System.Windows.Markup.XmlnsCompatibleWithAttribute>  
  
 **인수:**  
  
-   포함할 XAML 네임 스페이스 식별자를 지정 하는 문자열입니다.  
  
-   이전 인수에서 XAML 네임 스페이스를 포함할 수 있는 XAML 네임 스페이스 식별자를 지정 하는 문자열입니다.  
  
 <xref:System.Windows.Markup.XmlnsCompatibleWithAttribute> 다른 XAML 네임 스페이스는 XAML 네임 스페이스에 포함 될 수 있는지를 지정 합니다. 일반적으로 포함 하는 XAML 네임 스페이스는 표시에 이전에 정의 된 <xref:System.Windows.Markup.XmlnsDefinitionAttribute>합니다. 이 기술은 수 있습니다는 라이브러리에서 그리고 이전 버전의 어휘에 대해 이전에 정의 된 태그와 호환 되도록 하려면 XAML 어휘 버전 관리에 사용 합니다.  
  
### <a name="xmlnsdefinitionattribute"></a>XmlnsDefinitionAttribute  
 **참조 설명서:**  <xref:System.Windows.Markup.XmlnsDefinitionAttribute>  
  
 **인수:**  
  
-   정의 하는 XAML 네임 스페이스의 식별자를 지정 하는 문자열입니다.  
  
-   CLR 네임 스페이스의 이름을 지정 하는 문자열입니다. CLR 네임 스페이스는 어셈블리에 public 형식을 정의 해야 하 고 XAML 사용을 위해 사용 해야 하는 CLR 네임 스페이스 형식 중 하나 이상.  
  
 <xref:System.Windows.Markup.XmlnsDefinitionAttribute> XAML 네임 스페이스와 XAML 개체 작성기 또는 XAML 스키마 컨텍스트에서 형식 확인에 사용 되는 CLR 네임 스페이스 간 어셈블리별 매핑을 지정 합니다.  
  
 둘 이상의 <xref:System.Windows.Markup.XmlnsDefinitionAttribute> 어셈블리에 적용할 수 있습니다. 다음과 같은 이유로 모든 조합에 대해이 작업을 수행할 수 있습니다.  
  
-   런타임 API 액세스;의 논리적 구성에 대 한 여러 CLR 네임 스페이스를 포함 하는 라이브러리 디자인 그러나 동일한 XAML 네임 스페이스를 참조 하 여 XAML 사용할 수 있도록 하려면 해당 네임 스페이스의 모든 형식 바랍니다. 이 경우, 적용 여러 <xref:System.Windows.Markup.XmlnsDefinitionAttribute> 동일한를 사용 하 여 특성 <xref:System.Windows.Markup.XmlnsDefinitionAttribute.XmlNamespace%2A> 하지만 서로 다른 값 <xref:System.Windows.Markup.XmlnsDefinitionAttribute.ClrNamespace%2A> 값입니다. 기본 XAML 네임 스페이스에도 일반적으로 사용 되도록 해당 프레임 워크 또는 응용 프로그램에서 하려는 XAML 네임 스페이스에 대 한 매핑을 정의 하는 경우 특히 유용 합니다.  
  
-   여러 CLR 네임 스페이스를 포함 하는 라이브러리 디자인 및 해당 CLR 네임 스페이스의 형식 사용을 의도적으로 XAML 네임 스페이스 분리 합니다.  
  
-   어셈블리의 CLR 네임 스페이스를 정의 하 고 둘 이상의 XAML 네임 스페이스를 통해 액세스할 수 있도록 합니다. 이 시나리오에는 동일한 코드 베이스를 사용 하 여 여러 개의 어휘를 지 원하는 경우 발생 합니다.  
  
-   XAML 언어 지원을 하나 이상의 CLR 네임 스페이스를 정의합니다. 이러한 경우는 <xref:System.Windows.Markup.XmlnsDefinitionAttribute.XmlNamespace%2A> 값 해야 `http://schemas.microsoft.com/winfx/2006/xaml`합니다.  
  
### <a name="xmlnsprefixattribute"></a>XmlnsPrefixAttribute  
 **참조 설명서:**  <xref:System.Windows.Markup.XmlnsPrefixAttribute>  
  
 **인수:**  
  
-   XAML 네임 스페이스 식별자를 지정 하는 문자열입니다.  
  
-   권장 되는 접두사를 지정 하는 문자열입니다.  
  
 <xref:System.Windows.Markup.XmlnsDefinitionAttribute> XAML 네임 스페이스에 대해 사용 하도록 권장 되는 접두사를 지정 합니다. 접두사는.NET Framework XAML 서비스에서 serialize 된 XAML 파일에서 특성과 해당 요소를 작성할 때 유용한 <xref:System.Xaml.XamlXmlWriter>, 또는 XAML 구현 라이브러리 XAML 디자인 환경과 상호 작용 하는 경우 편집 기능입니다.  
  
 둘 이상의 <xref:System.Windows.Markup.XmlnsPrefixAttribute> 어셈블리에 적용할 수 있습니다. 다음과 같은 이유로 모든 조합에 대해이 작업을 수행할 수 있습니다.  
  
-   어셈블리에 둘 이상의 XAML 네임 스페이스에 대 한 형식을 정의합니다. 이 경우 각 XAML 네임 스페이스에 대 한 서로 다른 접두사 값을 정의 해야 합니다.  
  
-   여러 개의 어휘를 지 원하는 및 각 어휘 및 XAML 네임 스페이스에 대해 서로 다른 접두사를 사용 합니다.  
  
-   어셈블리에서 XAML 언어 지원을 정의 하 고는 <xref:System.Windows.Markup.XmlnsDefinitionAttribute> 에 대 한 `http://schemas.microsoft.com/winfx/2006/xaml`합니다. 이 경우 일반적으로 승격 해야 접두사 `x`합니다.  
  
> [!NOTE]
>  .NET framework XAML 서비스 XAML 관련 특성 정의 <xref:System.Windows.Markup.RootNamespaceAttribute>합니다. 이 특성은 프로젝트 시스템 지원에 대 한 어셈블리 수준 특성 및는 XAML 사용자 정의 형식과 관련이 없습니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Attribute>  
 [.NET Framework XAML 서비스에서 사용할 사용자 지정 형식 정의](../../../docs/framework/xaml-services/defining-custom-types-for-use-with-net-framework-xaml-services.md)
