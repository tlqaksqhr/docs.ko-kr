---
title: "x:Type Markup Extension | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "x:TypeExtension"
  - "Type"
  - "x:Type"
  - "xType"
  - "TypeExtension"
helpviewer_keywords: 
  - "x:Type markup extension [XAML Services]"
  - "XAML [XAML Services], x:Type markup extension"
  - "XAML [XAML Services], TargetType attribute"
  - "TargetType attribute [XAML Services]"
  - "Type markup extension in XAML [XAML Services]"
ms.assetid: e0e0ce6f-e873-49c7-8ad7-8b840eb353ec
caps.latest.revision: 27
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 27
---
# x:Type Markup Extension
지정된 XAML 형식의 내부 형식인 CLR <xref:System.Type> 개체를 제공합니다.  
  
## XAML 특성 사용  
  
```  
<object property="{x:Type prefix:typeNameValue}" .../>  
```  
  
## XAML 개체 요소 사용  
  
```  
<x:Type TypeName="prefix:typeNameValue"/>  
```  
  
## XAML 값  
  
|||  
|-|-|  
|`prefix`|선택적 요소.  기본값이 아닌 XAML 네임스페이스를 매핑하는 접두사입니다.  접두사는 자주 지정할 필요가 없습니다.  설명 부분을 참조하십시오.|  
|`typeNameValue`|필수 요소.  현재 기본 XAML 네임스페이스 또는 지정된 매핑된 접두사\(`prefix`를 제공한 경우\)로 확인할 수 있는 형식 이름입니다.|  
  
## 설명  
 `x:Type` 태그 확장에는 [!INCLUDE[TLA#tla_cshrp](../../../includes/tlasharptla-cshrp-md.md)]의 `typeof()` 연산자 또는 [!INCLUDE[TLA#tla_visualb](../../../includes/tlasharptla-visualb-md.md)]의 `GetType` 연산자와 유사한 기능이 있습니다.  
  
 `x:Type` 태그 확장은 형식 <xref:System.Type>을 설정하는 속성에 폼 문자열 변환 동작을 공급합니다.  입력은 XAML 형식입니다.  입력 XAML 형식과 출력 CLR <xref:System.Type> 간의 관계는 XAML 스키마 컨텍스트와 컨텍스트가 제공하는 <xref:System.Windows.Markup.IXamlTypeResolver> 서비스를 기반으로 필요한 <xref:System.Xaml.XamlType>를 찾은 후 출력 <xref:System.Type>이 입력 <xref:System.Xaml.XamlType>의 <xref:System.Xaml.XamlType.UnderlyingType%2A>이라는 것입니다.  
  
 .NET Framework XAML 서비스에서 이 태그 확장에 대한 처리는 <xref:System.Windows.Markup.TypeExtension> 클래스를 통해 정의됩니다.  
  
 특정 프레임워크 구현에서는 <xref:System.Type>를 값으로 사용하는 일부 속성은 형식의 이름을 직접 받아들일 수 있습니다\(형식 `Name`의 문자열 값\).  그러나 이 동작을 구현하는 것은 복잡한 시나리오입니다.  예를 들어, 아래의 "WPF 사용 정보" 섹션을 참조하십시오.  
  
 특성 구문은 이러한 태그 확장에 가장 많이 사용되는 구문입니다.  `x:Type` 식별자 문자열 다음에 나오는 문자열 토큰은 기본 <xref:System.Windows.Markup.TypeExtension> 확장 클래스의 <xref:System.Windows.Markup.TypeExtension.TypeName%2A> 값으로 할당됩니다.  CLR 형식을 기반으로 하는 .NET Framework XAML 서비스의 기본 XAML 스키마 컨텍스트에서 이 특성의 값은 원하는 형식의 <xref:System.Reflection.MemberInfo.Name%2A>이거나 <xref:System.Reflection.MemberInfo.Name%2A>이 기본값이 아닌 XAML 네임스페이스 매핑에 대한 접두사가 선행하는 포함입니다.  
  
 `x:Type` 태그 확장은 개체 요소 구문에서 사용할 수 있습니다.  이 경우 <xref:System.Windows.Markup.TypeExtension.TypeName%2A> 속성 값을 지정해야만 확장을 적절히 초기화할 수 있습니다.  
  
 `x:Type` 태그 확장은 자세한 특성으로 사용할 수도 있지만 이 사용은 일반적인 것은 아닙니다. `<``object` `property``="{x:Type TypeName=``typeNameValue``}" .../>`  
  
## WPF 사용 정보  
  
### 기본 XAML 네임스페이스 및 형식 매핑  
 WPF 프로그래밍을 위한 기본 XAML 네임스페이스에는 일반 XAML 시나리오에 필요한 대부분의 일반적인 XAML 시나리오가 포함되므로 XAML 형식 값을 참조할 때 접두사를 피할 수 있습니다.  사용자 지정 어셈블리의 형식을 참조하거나, WPF 어셈블리에 내에 있지만 기본 XAML 네임스페이스로 매핑되지 않은 CLR 네임스페이스에 포함된 형식의 경우에는 접두사를 매핑해야 할 수도 있습니다.  접두사, XAML 네임스페이스 및 CLR 네임스페이스 매핑에 대한 자세한 내용은 [WPF XAML을 위한 XAML 네임스페이스 및 네임스페이스 매핑](../../../docs/framework/wpf/advanced/xaml-namespaces-and-namespace-mapping-for-wpf-xaml.md)을 참조하십시오.  
  
### Typename\-as\-String을 지원하는 속성 입력  
 WPF는 `x:Type` 태그 확장 사용을 요구하지 않고 형식 <xref:System.Type>의 일부 속성 값을 지정할 수 있는 기술을 지원합니다.  대신, 형식 이름을 지정하는 문자열로 값을 지정할 수 있습니다.  이 예로는 <xref:System.Windows.Controls.ControlTemplate.TargetType%2A?displayProperty=fullName> 및 <xref:System.Windows.Style.TargetType%2A?displayProperty=fullName>이 있습니다.  이 동작에 대한 지원은 형식 변환기 또는 태그 확장을 통해 제공되지 않습니다.  대신, <xref:System.Windows.FrameworkElementFactory>를 통해 구현된 지연 동작입니다.  
  
 Silverlight는 비슷한 규칙을 지원합니다.  실제로 Silverlight는 현재 XAML 언어 지원에서 `{x:Type}`을\(를\) 지원하지 않으며 WPF\-Silverlight XAML의 마이그레이션을 지원하는 몇몇 환경 외부에서 `{x:Type}`의 사용을 허용하지 않습니다.  따라서 문자열로 나타낸 동작은 <xref:System.Type>이 값인 모든 Silverlight 네이티브 속성 평가에 기본으로 제공됩니다.  
  
## XAML 2009  
 XAML 2009는 제네릭 형식에 대한 추가 지원을 제공하고 이 지원을 제공하도록 `x:TypeArguments` 및 `x:Type`의 동작을 수정합니다.  
  
-   `x:TypeArguments` 및 일반 개체 인스턴스화의 관련 개체 요소는 루트 이외의 요소에 있을 수 있습니다.  자세한 내용은 [x:TypeArguments Directive](../../../docs/framework/xaml-services/x-typearguments-directive.md)의 "XAML 2009" 단원을 참조하십시오.  
  
-   XAML 2009는 태그에서 제네릭 형식의 제약 조건을 지정하는 구문을 지원합니다.  `x:TypeArguments`, `x:Type` 또는 두 가지 기능을 조합하여 사용할 수 있습니다.  
  
-   또한 로드를 위해 XAML 2009를 처리할 때 WPF XAML구현은 형식 <xref:System.Type>을 사용하는 특정 프레임워크의 암시적 형식 변환 동작에 이 기능을 추가합니다.  
  
 WPF에서 XAML 2009 기능을 사용할 수 있지만 느슨한 XAML이며 태그 컴파일되지 않은 XAML의 경우에만 가능합니다.  WPF에 대한 태그 컴파일된 XAML 및 BAML 형태의 XAML은 현재 XAML 2009 키워드 및 기능을 지원하지 않습니다.  
  
## 참고 항목  
 <xref:System.Windows.Style>   
 [스타일 지정 및 템플릿](../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [XAML 개요\(WPF\)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)   
 [태그 확장 및 WPF XAML](../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)