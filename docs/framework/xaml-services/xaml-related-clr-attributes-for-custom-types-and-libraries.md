---
title: "XAML-Related CLR Attributes for Custom Types and Libraries | Microsoft Docs"
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
  - "CLR attributes for custom types [XAML Services]"
ms.assetid: 5dfb299a-b6e2-41b8-8694-e6ac987547f1
caps.latest.revision: 8
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 8
---
# XAML-Related CLR Attributes for Custom Types and Libraries
이 항목에서는 .NET Framework XAML 서비스에서 정의되는 CLR\(공용 언어 런타임\) 특성에 대해 설명합니다.  또한 .NET Framework에서 정의되며 어셈블리나 형식에 적용하기 위한 XAML 관련 시나리오가 있는 기타 CLR 특성에 대해서도 설명합니다.  어셈블리, 형식 또는 멤버에 이러한 CLR 특성을 설정하면 해당 형식과 관련된 XAML 형식 시스템 정보가 제공됩니다.  정보는 XAML 노드 스트림을 직접 처리하거나 전용 XAML 판독기와 XAML 작성기를 통해 처리하기 위해 .NET Framework XAML 서비스를 사용하는 모든 XAML 소비자에게 제공됩니다.  
  
## 사용자 지정 형식 및 사용자 지정 멤버에 대한 XAML 관련 CLR 특성  
 CLR 특성을 사용하면 전체 CLR을 사용하여 형식을 정의하게 되는데, 이렇게 정의할 수 없으면 CLR 특성을 사용할 수 없습니다.  CLR을 사용하여 형식 지원을 정의하는 경우 .NET Framework XAML 서비스 XAML 작성기에서 사용하는 기본 XAML 스키마 컨텍스트는 지원 어셈블리에 대한 리플렉션을 통해 CLR 특성을 읽을 수 있습니다.  
  
 다음 단원에서는 사용자 지정 형식이나 사용자 지정 멤버에 적용할 수 있는 XAML 관련 특성에 대해 설명합니다.  각 CLR 특성은 XAML 형식 시스템과 관련된 정보를 전달합니다.  로드 경로에서 특성 사용 정보는 XAML 판독기가 유효한 XAML 노드 스트림을 형성하는 데 도움이 되거나 XAML 작성기가 유효한 개체 그래프를 생성하는 데 도움이 됩니다.  저장 경로에서 특성 사용 정보는 XAML 판독기가 XAML 형식 시스템 정보를 다시 구성하는 유효한 XAML 노드 스트림을 형성하는 데 도움이 되거나, XAML 작성기 또는 다른 XAML 소비자에 대한 serialization 힌트나 요구 사항을 선언합니다.  
  
### AmbientAttribute  
 **참조 설명서:**  <xref:System.Windows.Markup.AmbientAttribute>  
  
 **적용 대상:** 클래스, 속성, 또는 연결 가능한 속성을 지원하는 `get` 접근자 멤버  
  
 **인수:** 없음  
  
 <xref:System.Windows.Markup.AmbientAttribute>는 이 속성이나 해당 특성을 사용하는 형식이 사용되는 모든 속성이 XAML에서 앰비언트 속성 개념에 따라 해석되어야 함을 나타냅니다.  앰비언트 개념은 XAML 프로세서에서 멤버의 형식 소유자를 결정하는 방법과 관련이 있습니다.  앰비언트 속성은 개체 그래프를 만들 때 파서 컨텍스트에서 해당 속성 값을 사용할 수 있어야 하지만 바로 생성될 XAML 노드 집합을 위해 일반적인 형식 멤버 조회가 일시 중단된 속성입니다.  
  
 앰비언트 개념은 CLR 특성이 <xref:System.AttributeTargets>를 정의하는 방법의 측면에서 속성으로 표현되지 않는 연결 가능한 멤버에 적용될 수 있습니다.  메서드 특성 사용은 XAML의 연결 가능한 사용을 지원하는 `get` 접근자의 경우에만 적용되어야 합니다.  
  
### ConstructorArgumentAttribute  
 **참조 설명서:**  <xref:System.Windows.Markup.ConstructorArgumentAttribute>  
  
 **적용 대상:** 클래스  
  
 **인수:** 단일 생성자 인수와 일치하는 속성의 이름을 지정하는 문자열  
  
 <xref:System.Windows.Markup.ConstructorArgumentAttribute>는 기본값이 아닌 생성자 구문을 사용하여 개체를 초기화할 수 있고 지정된 이름의 속성이 생성 정보를 제공함을 지정합니다.  이 정보는 주로 XAML serialization에 사용됩니다.  자세한 내용은 <xref:System.Windows.Markup.ConstructorArgumentAttribute>를 참조하십시오.  
  
### ContentPropertyAttribute  
 **참조 설명서:**  <xref:System.Windows.Markup.ContentPropertyAttribute>  
  
 **적용 대상:** 클래스  
  
 **인수:** 특성을 사용하는 형식의 멤버 이름을 지정하는 문자열  
  
 <xref:System.Windows.Markup.ContentPropertyAttribute>는 인수로 이름이 지정된 속성이 해당 형식의 XAML 콘텐츠 속성으로 사용되도록 나타냅니다.  XAML 콘텐츠 속성 정의는 정의 형식에 할당 가능한 모든 파생 형식에 상속합니다.  특정 파생 형식에서 <xref:System.Windows.Markup.ContentPropertyAttribute>를 적용하여 해당 형식에서 정의를 재정의할 수 있습니다.  
  
 XAML 콘텐츠 속성 역할을 하는 속성의 경우 속성에 대한 속성 요소 태그가 XAML 사용에서 생략될 수 있습니다.  일반적으로 콘텐츠 및 포함 모델에 대한 XAML 태그의 효율성을 높이는 XAML 콘텐츠 속성을 지정합니다.  한 멤버만 XAML 콘텐츠 속성으로 지정할 수 있기 때문에 XAML 콘텐츠 속성으로 지정해야 하는 형식의 몇 가지 컨테이너 속성과 관련된 디자인 선택을 하는 경우가 있습니다.  다른 컨테이너 속성은 명시적 속성 요소와 함께 사용해야 합니다.  
  
 XAML 노드 스트림에서 XAML 콘텐츠 속성은 <xref:System.Xaml.XamlMember>의 속성 이름을 사용하여 `StartMember` 및 `EndMember` 노드를 계속 생성합니다.  멤버가 XAML 콘텐츠 속성인지 여부를 확인하려면 `StartObject` 위치에서 <xref:System.Xaml.XamlType> 값을 검사하고 <xref:System.Xaml.XamlType.ContentProperty%2A>의 값을 가져옵니다.  
  
### ContentWrapperAttribute  
 **참조 설명서:**  <xref:System.Windows.Markup.ContentWrapperAttribute>  
  
 **적용 대상:** 클래스\(특히 컬렉션 형식\)  
  
 **인수:** 외래 콘텐츠의 콘텐츠 래퍼 형식으로 사용할 형식을 지정하는 <xref:System.Type>  
  
 <xref:System.Windows.Markup.ContentWrapperAttribute>는 외래 콘텐츠를 래핑하는 데 사용할 연결된 컬렉션 형식에 대한 하나 이상의 형식을 지정합니다.  외래 콘텐츠는 콘텐츠 속성의 형식에 대한 형식 시스템 제약 조건이 소유하는 형식에 대한 XAML 사용에서 지원할 가능한 모든 콘텐츠 사례를 캡처하지 않는 경우를 나타냅니다.  예를 들어 특정 형식의 콘텐츠에 대한 XAML은 강력한 형식의 제네릭 <xref:System.Collections.ObjectModel.Collection%601>에 있는 문자열을 지원할 수 있습니다.  콘텐츠 래퍼는 기존의 태그 규칙을 컬렉션의 할당 가능한 값에 대한 XAML의 개념으로 마이그레이션하는 데 유용합니다. 예를 들어 텍스트 관련 콘텐츠 모델을 쉽게 마이그레이션할 수 있습니다.  
  
 둘 이상의 콘텐츠 래퍼 형식을 지정하려면 특성을 여러 번 적용합니다.  
  
### DependsOnAttribute  
 **참조 설명서:**  <xref:System.Windows.Markup.DependsOnAttribute>  
  
 **적용 대상:** 속성  
  
 **인수:** 특성을 사용하는 형식의 다른 멤버 이름을 지정하는 문자열  
  
 <xref:System.Windows.Markup.DependsOnAttribute>는 특성을 사용하는 속성이 다른 속성의 값에 종속되었음을 나타냅니다.  이 특성을 속성 정의에 적용하면 종속 속성이 XAML 개체 작성에서 가장 먼저 처리됩니다.  <xref:System.Windows.Markup.DependsOnAttribute>의 사용은 유효한 개체 생성을 위해 구문 분석의 특정 순서를 따라야 하는 형식에 대한 속성의 예외적인 경우를 지정합니다.  
  
 여러 <xref:System.Windows.Markup.DependsOnAttribute> 경우를 속성 정의에 적용할 수 있습니다.  
  
### MarkupExtensionReturnTypeAttribute  
 **참조 설명서:**  <xref:System.Windows.Markup.MarkupExtensionReturnTypeAttribute>  
  
 **적용 대상:** <xref:System.Windows.Markup.MarkupExtension> 파생 형식이어야 하는 클래스  
  
 **인수:** 특성을 사용하는 <xref:System.Windows.Markup.MarkupExtension>의 `ProvideValue` 결과로 예상되는 가장 정확한 형식을 지정하는 <xref:System.Type>  
  
 자세한 내용은 [Markup Extensions for XAML Overview](../../../docs/framework/xaml-services/markup-extensions-for-xaml-overview.md)를 참조하십시오.  
  
### NameScopePropertyAttribute  
 **참조 설명서:**  <xref:System.Windows.Markup.NameScopePropertyAttribute>  
  
 **적용 대상:** 클래스  
  
 **인수:** 다음 두 가지 형식의 특성 지원:  
  
-   특성 사용 형식에 대한 속성 이름을 지정하는 문자열  
  
-   속성의 이름을 지정하는 문자열 및 명명된 속성을 정의하는 형식의 <xref:System.Type>.  이 형식은 연결 가능한 멤버를 XAML 이름 범위 속성으로 지정하는 데 사용됩니다.  
  
 <xref:System.Windows.Markup.NameScopePropertyAttribute>는 특성 사용 클래스에 대한 XAML 이름 범위 값을 제공하는 속성을 지정합니다.  XAML 이름 범위 속성은 <xref:System.Windows.Markup.INameScope>를 구현하고 실제 XAML 이름 범위, 해당 저장소 및 동작을 포함하는 개체를 참조합니다.  
  
### RuntimeNamePropertyAttribute  
 **참조 설명서:**  <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>  
  
 **적용 대상:** 클래스  
  
 **인수:** 특성을 사용하는 형식에 대한 런타임 이름 속성의 이름을 지정하는 문자열  
  
 <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>는 XAML [x:Name Directive](../../../docs/framework/xaml-services/x-name-directive.md)에 매핑되는 특성 사용 형식의 속성을 보고합니다.  이 속성은 <xref:System.String> 형식이어야 하며 읽기\/쓰기 속성이어야 합니다.  
  
 정의는 정의 형식에 할당 가능한 모든 파생 형식에 상속합니다.  특정 파생 형식에서 <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>를 적용하여 해당 형식에서 정의를 재정의할 수 있습니다.  
  
### TrimSurroundingWhitespaceAttribute  
 **참조 설명서:**  <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>  
  
 **적용 대상:** 형식  
  
 **인수:** 없음  
  
 <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>는 공백이 유효한 콘텐츠\(<xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>가 있는 컬렉션에 포함된 콘텐츠\)에서 자식 요소로 나타날 수 있는 특정 형식에 적용됩니다.  <xref:System.Windows.Markup.TrimSurroundingWhitespaceAttribute>는 주로 저장 경로와 관련이 있지만 <xref:System.Xaml.XamlType.TrimSurroundingWhitespace%2A?displayProperty=fullName>를 검사하여 로드 경로의 XAML 형식 시스템에서 사용할 수 있습니다.  자세한 내용은 [Whitespace Processing in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md)를 참조하십시오.  
  
### TypeConverterAttribute  
 **참조 설명서:**  <xref:System.ComponentModel.TypeConverterAttribute>  
  
 **적용 대상:** 클래스, 속성, 메서드\(XAML에 사용할 수 있는 유일한 메서드는 연결 가능한 멤버를 지원하는 `get` 접근자임\)  
  
 **인수:** <xref:System.ComponentModel.TypeConverter>의 <xref:System.Type>  
  
 XAML 컨텍스트의 <xref:System.ComponentModel.TypeConverterAttribute>는 사용자 지정 <xref:System.ComponentModel.TypeConverter>를 참조합니다.  이 <xref:System.ComponentModel.TypeConverter>는 사용자 지정 형식 또는 해당 형식의 멤버에 대한 형식 변환 동작을 제공합니다.  
  
 <xref:System.ComponentModel.TypeConverterAttribute> 특성을 형식에 적용하여 형식 변환기 구현을 참조합니다.  클래스, 구조체 또는 인터페이스에 대한 XAML의 형식 변환기를 정의할 수 있습니다.  열거형에 대한 형식 변환은 제공할 필요가 없습니다. 이 변환은 기본적으로 사용하도록 설정되어 있습니다.  
  
 형식 변환기는 태그의 특성이나 초기화 텍스트에 사용되는 문자열에서 원하는 대상 형식으로 변환할 수 있어야 합니다.  자세한 내용은 [TypeConverter 및 XAML](../../../docs/framework/wpf/advanced/typeconverters-and-xaml.md)을 참조하십시오.  
  
 형식의 모든 값에 적용하는 대신 XAML에 대한 형식 변환기 동작을 특정 속성에서 설정할 수도 있습니다.  이 경우 <xref:System.ComponentModel.TypeConverterAttribute>를 속성 정의\(특정 `get` 및 `set` 정의가 아닌 외부 정의\)에 적용합니다.  
  
 연결 가능한 사용자 지정 멤버의 XAML 사용에 대한 형식 변환기 동작은 XAML 사용을 지원하는 `get` 메서드 접근자에 <xref:System.ComponentModel.TypeConverterAttribute>를 적용하여 할당할 수 있습니다.  
  
 <xref:System.ComponentModel.TypeConverter>와 유사한 <xref:System.ComponentModel.TypeConverterAttribute>가 XAML이 존재하기 전에 .NET Framework에 있었으며 형식 변환기 모델은 다른 목적으로 사용되었습니다.  <xref:System.ComponentModel.TypeConverterAttribute>를 참조하고 사용하려면 정규화하거나 <xref:System.ComponentModel>에 대한 `using` 문을 제공해야 합니다.  또한 프로젝트에 System 어셈블리도 포함해야 합니다.  
  
### UidPropertyAttribute  
 **참조 설명서:**  <xref:System.Windows.Markup.UidPropertyAttribute>  
  
 **적용 대상:** 클래스  
  
 **인수:** 이름으로 관련 속성을 참조하는 문자열  
  
 [x:Uid Directive](../../../docs/framework/xaml-services/x-uid-directive.md)의 별칭을 지정하는 클래스의 CLR 속성을 나타냅니다.  
  
### UsableDuringInitializationAttribute  
 **참조 설명서:**  <xref:System.Windows.Markup.UsableDuringInitializationAttribute>  
  
 **적용 대상:** 클래스  
  
 **인수:** 부울 값.  특성의 원하는 목적을 위해 사용되는 경우 항상 `true`로 지정되어야 합니다.  
  
 XAML 개체 그래프를 만드는 동안 이 형식이 하향식으로 빌드되는지 여부를 나타냅니다.  이는 고급 개념이며 프로그래밍 모델의 정의와 밀접한 관련이 있을 수 있습니다.  자세한 내용은 <xref:System.Windows.Markup.UsableDuringInitializationAttribute>를 참조하십시오.  
  
### ValueSerializerAttribute  
 **참조 설명서:**  <xref:System.Windows.Markup.ValueSerializerAttribute>  
  
 **적용 대상:** 클래스, 속성, 메서드\(XAML에 사용할 수 있는 유일한 메서드는 연결 가능한 멤버를 지원하는 `get` 접근자임\)  
  
 **인수:** 특성 사용 형식의 모든 속성이나 특정 특성 사용 속성을 serialize할 때 사용할 값 serializer 지원 클래스를 지정하는 <xref:System.Type>  
  
 <xref:System.Windows.Markup.ValueSerializer>는 <xref:System.ComponentModel.TypeConverter>보다 많은 상태와 컨텍스트가 필요한 값 serialization 클래스를 지정합니다.  연결 가능한 멤버의 정적 `get` 접근자 메서드에 <xref:System.Windows.Markup.ValueSerializerAttribute> 특성을 적용하여 연결 가능한 멤버와 <xref:System.Windows.Markup.ValueSerializer>를 연결할 수 있습니다.  값 serialization은 열거형, 인터페이스 및 구조체에도 적용 가능하지만 대리자에는 적용할 수 없습니다.  
  
### WhitespaceSignificantCollectionAttribute  
 **참조 설명서:**  <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>  
  
 **적용 대상:** 클래스, 특히 혼합 콘텐츠를 호스팅할 컬렉션 형식. 개체 요소 주위의 공백은 UI 표현에 의미가 있는 것으로 처리될 수 있습니다.  
  
 **인수:** 없음  
  
 <xref:System.Windows.Markup.WhitespaceSignificantCollectionAttribute>는 XAML 프로세서에서 공백을 의미 있는 것으로 간주하도록 컬렉션 형식을 처리해야 함을 나타냅니다. 이는 컬렉션 내에 XAML 노드 스트림의 값 노드를 생성하는 데 영향을 줍니다.  자세한 내용은 [Whitespace Processing in XAML](../../../docs/framework/xaml-services/whitespace-processing-in-xaml.md)를 참조하십시오.  
  
### XamlDeferLoadAttribute  
 **참조 설명서:**  <xref:System.Windows.Markup.XamlDeferLoadAttribute>  
  
 **적용 대상:** 클래스, 속성  
  
 **인수:** 두 가지 특성 형식, 즉, 문자열로 나타낸 형식이나 <xref:System.Type>으로 나타낸 형식을 지원합니다.  <xref:System.Windows.Markup.XamlDeferLoadAttribute>를 참조하십시오.  
  
 클래스 또는 속성에 XAML에 대한 지연된 로드 사용\(예: 템플릿 동작\)이 있음을 나타내고 지연 동작 및 해당 대상\/콘텐츠 형식을 사용하도록 설정하는 클래스를 보고합니다.  
  
### XamlSetMarkupExtensionAttribute  
 **참조 설명서:**  <xref:System.Windows.Markup.XamlSetMarkupExtensionAttribute>  
  
 **적용 대상:** 클래스  
  
 **인수:** 콜백의 이름을 지정합니다.  
  
 클래스에서 태그 확장을 사용하여 하나 이상의 속성에 대한 값을 제공할 수 있음을 나타내며, XAML 작성기가 클래스의 속성에 대해 태그 확장 설정 작업을 수행하기 전에 호출해야 하는 처리기를 참조합니다.  
  
### XamlSetTypeConverterAttribute  
 **참조 설명서:**  <xref:System.Windows.Markup.XamlSetTypeConverterAttribute>  
  
 **적용 대상:** 클래스  
  
 **인수:** 콜백의 이름을 지정합니다.  
  
 클래스에서 형식 변환기를 사용하여 하나 이상의 속성에 대한 값을 제공할 수 있음을 나타내며, XAML 작성기가 클래스의 속성에 대해 형식 변환기 설정 작업을 수행하기 전에 호출해야 하는 처리기를 참조합니다.  
  
### XmlLangPropertyAttribute  
 **참조 설명서:**  <xref:System.Windows.Markup.XmlLangPropertyAttribute>  
  
 **적용 대상:** 클래스  
  
 **인수:** 특성 사용 형식에서 `xml:lang`에 대한 별칭으로 속성의 이름을 지정하는 문자열  
  
 <xref:System.Windows.Markup.XmlLangPropertyAttribute>는 XML `lang` 지시문에 매핑되는 특성 사용 형식의 속성을 보고합니다.  속성은 <xref:System.String> 형식일 필요는 없지만 문자열에서 할당 가능해야 합니다. 이는 형식 변환기를 속성의 형식이나 특정 속성과 연결하면 가능합니다.  속성은 읽기\/쓰기 속성이어야 합니다.  
  
 `xml:lang` 매핑 시나리오는 런타임 개체 모델에서 XMLDOM을 사용하여 특별하게 처리하지 않고도 XML에서 지정한 언어 정보에 액세스할 수 있도록 하는 경우입니다.  
  
 정의는 정의 형식에 할당 가능한 모든 파생 형식에 상속합니다.  드문 경우이긴 하지만, 특정 파생 형식에서 <xref:System.Windows.Markup.XmlLangPropertyAttribute>를 적용하여 해당 형식에서 정의를 재정의할 수 있습니다.  
  
## 어셈블리 수준의 XAML 관련 CLR 특성  
 다음 단원에서는 형식 또는 멤버 정의에 적용되지 않지만 어셈블리에는 적용되는 XAML 관련 특성에 대해 설명합니다.  이러한 특성은 XAML에서 사용할 사용자 지정 형식이 포함된 라이브러리를 정의하는 전체적인 목표와 관련이 있습니다.  이러한 특성 중 일부는 반드시 XAML 노드 스트림에 직접 영향을 미치지는 않지만 다른 소비자가 사용할 수 있도록 노드 스트림에서 전달됩니다.  정보의 소비자는 XAML 네임스페이스 정보와 관련 접두사 정보가 필요한 serialization 프로세스나 디자인 환경을 포함합니다.  XAML 스키마 컨텍스트\(.NET Framework XAML 서비스 기본값 포함\)에서도 이 정보를 사용합니다.  
  
### XmlnsCompatibleWithAttribute  
 **참조 설명서:**  <xref:System.Windows.Markup.XmlnsCompatibleWithAttribute>  
  
 **인수:**  
  
-   포함할 XAML 네임스페이스의 식별자를 지정하는 문자열  
  
-   이전 인수의 XAML 네임스페이스를 포함할 수 있는 XAML 네임스페이스의 식별자를 지정하는 문자열  
  
 <xref:System.Windows.Markup.XmlnsCompatibleWithAttribute>는 XAML 네임스페이스가 다른 XAML 네임스페이스에 의해 포함될 수 있음을 지정합니다.  일반적으로 포함하는 XAML 네임스페이스는 이전에 정의된 <xref:System.Windows.Markup.XmlnsDefinitionAttribute>에 지정됩니다.  이 기법을 사용하여 라이브러리에서 XAML 어휘의 버전을 관리하고 XAML 어휘가 이전 버전의 어휘에 대해 이전에 정의된 태그와 호환되게 할 수 있습니다.  
  
### XmlnsDefinitionAttribute  
 **참조 설명서:**  <xref:System.Windows.Markup.XmlnsDefinitionAttribute>  
  
 **인수:**  
  
-   정의할 XAML 네임스페이스의 식별자를 지정하는 문자열  
  
-   CLR 네임스페이스의 이름을 지정하는 문자열.  CLR 네임스페이스에서는 어셈블리의 public 형식을 정의해야 하며, 적어도 하나의 CLR 네임스페이스 형식은 XAML용이어야 합니다.  
  
 <xref:System.Windows.Markup.XmlnsDefinitionAttribute>는 XAML 네임스페이스와 CLR 네임스페이스 사이의 어셈블리별 매핑을 지정합니다. 이 매핑은 XAML 개체 작성기나 XAML 스키마 컨텍스트에서 형식 확인에 사용됩니다.  
  
 둘 이상의 <xref:System.Windows.Markup.XmlnsDefinitionAttribute>를 어셈블리에 적용할 수 있습니다.  이 작업은 다음과 같은 이유로 수행될 수 있습니다.  
  
-   라이브러리 디자인에 런타임 API 액세스의 논리적 구성에 대한 여러 CLR 네임스페이스가 포함되어 있지만 동일한 XAML 네임스페이스를 참조하여 이러한 네임스페이스의 모든 형식을 XAML에서 사용할 수 있게 하려고 합니다.  이 경우 <xref:System.Windows.Markup.XmlnsDefinitionAttribute.XmlNamespace%2A> 값이 동일하지만 <xref:System.Windows.Markup.XmlnsDefinitionAttribute.ClrNamespace%2A> 값은 서로 다른 여러 개의 <xref:System.Windows.Markup.XmlnsDefinitionAttribute> 특성을 적용합니다.  이 방법은 특히 프레임워크나 응용 프로그램에서 일반적으로 기본 XAML 네임스페이스로 사용할 XAML 네임스페이스에 대한 매핑을 정의하는 경우에 유용합니다.  
  
-   라이브러리 디자인에 여러 CLR 네임스페이스가 포함되어 있으며 이러한 CLR 네임스페이스의 형식 사용 간에 XAML 네임스페이스를 의도적으로 분리하려고 합니다.  
  
-   어셈블리에 CLR 네임스페이스를 정의하고 둘 이상의 XAML 네임스페이스를 통해 액세스할 수 있게 하려고 합니다.  동일한 코드베이스를 사용하여 여러 어휘를 지원하려는 경우가 이에 해당합니다.  
  
-   하나 이상의 CLR 네임스페이스에서 XAML 언어 지원을 정의합니다.  이를 위해 <xref:System.Windows.Markup.XmlnsDefinitionAttribute.XmlNamespace%2A> 값은 `http://schemas.microsoft.com/winfx/2006/xaml`이어야 합니다.  
  
### XmlnsPrefixAttribute  
 **참조 설명서:**  <xref:System.Windows.Markup.XmlnsPrefixAttribute>  
  
 **인수:**  
  
-   XAML 네임스페이스의 식별자를 지정하는 문자열  
  
-   권장되는 접두사를 지정하는 문자열  
  
 <xref:System.Windows.Markup.XmlnsDefinitionAttribute>는 XAML 네임스페이스에 사용할 권장되는 접두사를 지정합니다.  이 접두사는 .NET Framework XAML 서비스 <xref:System.Xaml.XamlXmlWriter>에 의해 serialize되는 XAML 파일에서 요소와 특성을 작성할 때나 XAML에서 구현하는 라이브러리가 XAML 편집 기능이 있는 디자인 환경과 상호 작용할 때 유용합니다.  
  
 둘 이상의 <xref:System.Windows.Markup.XmlnsPrefixAttribute>를 한 어셈블리에 적용할 수 있습니다.  이 작업은 다음과 같은 이유로 수행될 수 있습니다.  
  
-   어셈블리에서 둘 이상의 XAML 네임스페이스에 대한 형식을 정의합니다.  이 경우 XAML 네임스페이스마다 다른 접두사 값을 정의해야 합니다.  
  
-   여러 어휘를 지원하고 어휘와 XAML 네임스페이스마다 서로 다른 접두사를 사용합니다.  
  
-   어셈블리에서 XAML 언어 지원을 정의하고 `http://schemas.microsoft.com/winfx/2006/xaml`에 대한 <xref:System.Windows.Markup.XmlnsDefinitionAttribute>가 있습니다.  이 경우 일반적으로 접두사 `x`를 승격해야 합니다.  
  
> [!NOTE]
>  .NET Framework XAML 서비스에서는 XAML 관련 특성인 <xref:System.Windows.Markup.RootNamespaceAttribute>도 정의합니다.  이 특성은 프로젝트 시스템 지원에 대한 어셈블리 수준 특성이며 XAML 사용자 지정 형식과 관련이 없습니다.  
  
## 참고 항목  
 <xref:System.Attribute>   
 [Defining Custom Types for Use with .NET Framework XAML Services](../../../docs/framework/xaml-services/defining-custom-types-for-use-with-net-framework-xaml-services.md)