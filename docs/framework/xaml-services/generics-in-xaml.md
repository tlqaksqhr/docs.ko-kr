---
title: "Generics in XAML | Microsoft Docs"
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
  - "generics [XAML Services]"
ms.assetid: 835bfed7-585c-4216-ae67-b674edab8b92
caps.latest.revision: 8
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 8
---
# Generics in XAML
System.Xaml에서 구현된 .NET Framework XAML 서비스는 제네릭 CLR 형식을 사용하기 위한 지원 기능을 제공합니다.  이 지원 기능에는 제네릭의 제약 조건을 형식 인수로 지정하는 것과 제네릭 컬렉션 경우에 적절한 `Add` 메서드를 호출하여 제약 조건을 적용하는 것이 포함됩니다.  이 항목에서는 XAML에서 제네릭 형식의 사용 및 참조에 대한 측면에 대해 설명합니다.  
  
## x:TypeArguments  
 `x:TypeArguments`는 XAML 언어에서 정의된 지시문입니다.  제네릭 형식이 지원하는 XAML 형식의 멤버로 사용될 때 `x:TypeArguments`는 제네릭의 제한하는 형식 인수를 지원 생성자에 전달합니다.  구문 예제를 비롯하여 `x:TypeArguments`의 .NET Framework XAML 서비스 사용과 관련된 참조 구문은 [x:TypeArguments Directive](../../../docs/framework/xaml-services/x-typearguments-directive.md)을 참조하십시오.  
  
 `x:TypeArguments`가 문자열을 사용하고 형식 변환기 지원을 갖고 있기 때문에 일반적으로 XAML 사용에서 특성으로 선언됩니다.  
  
 XAML 노드 스트림에서 `x:TypeArguments`에 의해 선언된 정보는 노드 스트림의 `StartObject` 위치에 있는 <xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=fullName>에서 가져올 수 있습니다.  <xref:System.Xaml.XamlType.TypeArguments%2A?displayProperty=fullName>의 반환 값은 <xref:System.Xaml.XamlType> 값의 목록입니다.  XAML 형식이 제네릭 형식을 나타내는지 여부는 <xref:System.Xaml.XamlType.IsGeneric%2A?displayProperty=fullName>을 호출하여 확인할 수 있습니다.  
  
## XAML의 제네릭에 대한 규칙 및 구문 규칙  
 XAML에서 제네릭 형식은 항상 제한된 제네릭으로 표현되어야 합니다. 제한되지 않은 제네릭은 XAML 형식 시스템이나 XAML 노드 스트림에 표시되지 않으며 XAML 태그에 표현될 수 없습니다.  제네릭이 `x:TypeArguments`에 의해 참조될 제네릭의 중첩 형식 제약 조건인 경우나 `x:Type`이 제네릭 형식에 대한 CLR 형식 참조를 제공하는 경우에 제네릭은 XAML 특성 구문 내에서 참조될 수 있습니다.  이는 .NET Framework XAML 서비스에서 정의된 <xref:System.Xaml.Schema.XamlTypeTypeConverter> 클래스를 통해 지원됩니다.  
  
 <xref:System.Xaml.Schema.XamlTypeTypeConverter>를 통해 사용할 수 있게 되는 XAML 특성 구문 형태는 제네릭의 형식과 제약 조건에 꺾쇠 괄호를 사용하는 일반적인 MSIL\/CLR 구문 규칙을 변경하고 제약 조건 컨테이너에 괄호를 대신 사용합니다.  예제를 보려면 [x:TypeArguments Directive](../../../docs/framework/xaml-services/x-typearguments-directive.md)을 참조하십시오.  
  
## 제네릭 및 XAML 2009 기능  
 XAML 2009를 사용하는 경우 일반적인 언어 기본 형식에 대한 XAML 형식을 얻기 위해 CLR 기본 형식을 매핑하는 대신 [XAML 2009 기본 제공 형식](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md)을 `x:TypeArguments`의 정보 항목으로 사용할 수 있습니다.  예를 들어 다음을 선언할 수 있습니다. 여기서 접두사 매핑은 표시되지 않았지만 `x`는 XAML 2009의 XAML 언어 XAML 네임스페이스입니다.  
  
```  
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>  
```  
  
## WPF 및 기타 v3.5 프레임워크의 제네릭 지원  
 특히 WPF를 대상으로 하는 경우 XAML 2006 사용을 위해 [x:Class](../../../docs/framework/xaml-services/x-class-directive.md)는 `x:TypeArguments`와 동일한 요소에서도 제공되어야 하며 해당 요소가 XAML 문서에서 루트 요소여야 합니다.  루트 요소는 하나 이상의 형식 인수가 있는 제네릭 형식에 매핑되어야 합니다.  예를 들면 <xref:System.Windows.Navigation.PageFunction%601>과 같이 지정합니다.  
  
 제네릭 사용을 지원하는 가능한 해결 방법에는 제네릭 형식을 반환할 수 있는 사용자 지정 태그 확장을 정의하거나 제네릭 형식에서 파생되지만 자체 클래스 정의에서 제네릭 제약 조건을 노출하는 래핑 클래스 정의를 제공하는 것이 포함됩니다.  
  
 WPF와 대상 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]에서는 XAML 2009 기능을 `x:TypeArguments`와 함께 사용할 수 있지만 느슨한 XAML\(태그 컴파일되지 않은 XAML\)의 경우에만 가능합니다.  WPF에 대한 태그 컴파일된 XAML 및 BAML 형태의 XAML은 현재 XAML 2009 키워드 및 기능을 지원하지 않습니다.  
  
 [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)]에 대한 [!INCLUDE[TLA#tla_workflow](../../../includes/tlasharptla-workflow-md.md)]의 사용자 지정 워크플로는 제네릭 XAML 사용을 지원하지 않습니다.  
  
## 참고 항목  
 [x:TypeArguments Directive](../../../docs/framework/xaml-services/x-typearguments-directive.md)   
 [x:Class Directive](../../../docs/framework/xaml-services/x-class-directive.md)   
 [Built\-in Types for Common XAML Language Primitives](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md)