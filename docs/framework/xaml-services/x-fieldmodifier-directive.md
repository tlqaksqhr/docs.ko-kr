---
title: "x:FieldModifier Directive | Microsoft Docs"
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
  - "FieldModifier attribute in XAML [XAML Services]"
  - "x:FieldModifier attribute [XAML Services]"
  - "XAML [XAML Services], x:FieldModifier attribute"
ms.assetid: ed427cd4-2f35-4d24-bd2f-0fa7b71ec248
caps.latest.revision: 15
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 14
---
# x:FieldModifier Directive
명명된 개체 참조에 대한 필드가 기본 동작인 <xref:System.Reflection.TypeAttributes?displayProperty=fullName>이 아니라 <xref:System.Reflection.TypeAttributes?displayProperty=fullName> 액세스를 사용하여 정의되도록 XAML 컴파일 동작을 수정합니다.  
  
## XAML 특성 사용  
  
```  
<object x:FieldModifier="Public".../>  
```  
  
## XAML 값  
  
|||  
|-|-|  
|*Public*|<xref:System.Reflection.TypeAttributes?displayProperty=fullName> 또는 <xref:System.Reflection.TypeAttributes?displayProperty=fullName>을 지정하기 위해 전달하는 정확한 문자열은 사용하는 코드 숨김 프로그래밍 언어에 따라 다릅니다.  설명 부분을 참조하십시오.|  
  
## 종속성  
 XAML 프로덕션이 `x:FieldModifier`을 사용할 경우 해당 XAML 프로덕션의 루트 요소는 [x:Class Directive](../../../docs/framework/xaml-services/x-class-directive.md)를 선언해야 합니다.  
  
## 설명  
 `x:FieldModifier`는 클래스 또는 해당 멤버의 일반 액세스 수준 선언과 관련이 없습니다.  XAML 프로덕션의 일부인 특정 XAML 개체가 처리될 때 XAML 처리 동작에만 관련이 있으며, 응용 프로그램의 개체 그래프에서 액세스할 수 있는 개체가 됩니다.  기본적으로 이러한 개체의 필드 참조는 private으로 유지되므로, 컨트롤 소비자가 개체 그래프를 직접 수정할 수 없습니다.  대신, 컨트롤 소비자는 레이아웃 루트, 자식 요소 컬렉션, 전용 public 속성 등을 가져오는 등 프로그래밍 모델에 의해 활성화된 표준 패턴을 사용하여 개체 그래프를 수정해야 합니다.  
  
 `x:FieldModifier` 특성 값은 프로그래밍 언어에 따라 다르며 목적은 특정 프레임워크에서 다를 수 있습니다.  사용할 문자열은 각 언어에서 해당 <xref:System.CodeDom.Compiler.CodeDomProvider>를 구현하는 방법, <xref:System.Reflection.TypeAttributes?displayProperty=fullName> 및 <xref:System.Reflection.TypeAttributes?displayProperty=fullName>의 의미를 정의하기 위해 언어에서 반환하는 형식 변환기 및 해당 언어가 대\/소문자를 구분하는지 여부에 따라 달라집니다.  
  
-   [!INCLUDE[TLA2#tla_cshrp](../../../includes/tla2sharptla-cshrp-md.md)]의 경우 <xref:System.Reflection.TypeAttributes?displayProperty=fullName>을 지정하기 위해 전달할 문자열은 `public`입니다.  
  
-   [!INCLUDE[TLA2#tla_visualbnet](../../../includes/tla2sharptla-visualbnet-md.md)]의 경우 <xref:System.Reflection.TypeAttributes?displayProperty=fullName>을 지정하기 위해 전달할 문자열은 `Public`입니다.  
  
-   [!INCLUDE[TLA2#tla_cppcli](../../../includes/tla2sharptla-cppcli-md.md)]의 경우 XAML에 대한 대상이 없으므로 전달할 문자열이 정의되지 않았습니다.  
  
 <xref:System.Reflection.TypeAttributes?displayProperty=fullName>\([!INCLUDE[TLA2#tla_cshrp](../../../includes/tla2sharptla-cshrp-md.md)]의 경우 `internal`, [!INCLUDE[TLA2#tla_visualb](../../../includes/tla2sharptla-visualb-md.md)]의 경우 `Friend`\)도 지정할 수 있지만 `NotPublic` 동작은 이미 기본값이므로 <xref:System.Reflection.TypeAttributes?displayProperty=fullName>을 지정하지 않는 것이 일반적입니다.  
  
 <xref:System.Reflection.TypeAttributes?displayProperty=fullName>이 기본 동작으로 지정되는 이유는 XAML을 컴파일한 어셈블리 외부의 코드에서 XAML을 만든 요소에 액세스할 필요가 없기 때문입니다.  WPF 보안 아키텍처 및 XAML 컴파일 동작을 조합하면 사용자가 구체적으로 `x:FieldModifier`를 설정하지 않은 경우 요소 인스턴스를 저장하는 필드가 public으로 설정되지 않습니다.  
  
 `x:FieldModifier`는 [x:Name Directive](../../../docs/framework/xaml-services/x-name-directive.md)이 있는 요소와만 관련되는데, 이 이름을 사용하여 public 필드를 참조하기 때문입니다.  
  
 기본적으로 루트 요소의 partial 클래스는 public이지만 [x:ClassModifier Directive](../../../docs/framework/xaml-services/x-classmodifier-directive.md)을 사용하여 nonpublic으로 만들 수 있습니다.  [x:ClassModifier Directive](../../../docs/framework/xaml-services/x-classmodifier-directive.md)은 루트 요소 클래스 인스턴스의 액세스 수준에도 영향을 줍니다.  루트 요소에 `x:Name` 및 `x:FieldModifier`를 모두 지정할 수 있지만 이 경우 루트 요소의 public 필드 복사본이 만들어질 뿐이며 실제 루트 요소 클래스의 액세스 수준은 여전히 [x:ClassModifier Directive](../../../docs/framework/xaml-services/x-classmodifier-directive.md)을 통해 제어됩니다.  
  
## 참고 항목  
 [WPF에 대한 XAML 및 사용자 지정 클래스](../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)   
 [WPF의 코드 숨김 및 XAML](../../../docs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)   
 [x:Name Directive](../../../docs/framework/xaml-services/x-name-directive.md)   
 [WPF 응용 프로그램 만들기\(WPF\)](../../../docs/framework/wpf/app-development/building-a-wpf-application-wpf.md)   
 [x:ClassModifier Directive](../../../docs/framework/xaml-services/x-classmodifier-directive.md)