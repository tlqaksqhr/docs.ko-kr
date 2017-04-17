---
title: "x:ClassModifier Directive | Microsoft Docs"
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
  - "xClassModifier"
  - "x:ClassModifier"
  - "ClassModifier"
helpviewer_keywords: 
  - "XAML [XAML Services], x:ClassModifier attribute"
  - "x:ClassModifier attribute [XAML Services]"
  - "ClassModifier attribute in XAML [XAML Services]"
ms.assetid: ef30ab78-d334-4668-917d-c9f66c3b6aea
caps.latest.revision: 22
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 21
---
# x:ClassModifier Directive
`x:Class`도 제공되는 경우 XAML 컴파일 동작을 수정합니다.  특히 `Public` 액세스 수준\(기본값\)을 가지는 부분 `class`를 만드는 대신에 제공된 `x:Class`는 `NotPublic` 액세스 수준으로 생성됩니다.  이 동작은 생성된 어셈블리의 클래스에 대한 액세스 수준에 영향을 줍니다.  
  
## XAML 특성 사용  
  
```  
<object x:Class="namespace.classname" x:ClassModifier="NotPublic">  
   ...  
</object>  
```  
  
## XAML 값  
  
|||  
|-|-|  
|*NotPublic*|<xref:System.Reflection.TypeAttributes?displayProperty=fullName> 또는 <xref:System.Reflection.TypeAttributes?displayProperty=fullName>을 지정하기 위해 전달할 정확한 문자열은 사용하는 코드 숨김 프로그래밍 언어에 따라 다릅니다.  설명 부분을 참조하십시오.|  
  
## 종속성  
 [x:Class](../../../docs/framework/xaml-services/x-class-directive.md)는 동일한 요소에도 제공해야 하며 이 요소는 페이지의 루트 요소여야 합니다.  자세한 내용은 [\[MS\-XAML\] Section 4.3.1.8](http://go.microsoft.com/fwlink/?LinkId=114525)을 참조하십시오.  
  
## 설명  
 .NET Framework XAML 서비스에서 사용하는 `x:ClassModifier` 값은 프로그래밍 언어에 따라 다릅니다.  사용할 문자열은 각 언어에서 해당 <xref:System.CodeDom.Compiler.CodeDomProvider>를 구현하는 방법, <xref:System.Reflection.TypeAttributes?displayProperty=fullName> 및 <xref:System.Reflection.TypeAttributes?displayProperty=fullName>의 의미를 정의하기 위해 언어에서 반환하는 형식 변환기 및 해당 언어가 대\/소문자를 구분하는지 여부에 따라 달라집니다.  
  
-   [!INCLUDE[TLA2#tla_cshrp](../../../includes/tla2sharptla-cshrp-md.md)]의 경우 <xref:System.Reflection.TypeAttributes?displayProperty=fullName>을 지정하기 위해 전달할 문자열은 `internal`입니다.  
  
-   [!INCLUDE[TLA2#tla_visualbnet](../../../includes/tla2sharptla-visualbnet-md.md)]의 경우 <xref:System.Reflection.TypeAttributes?displayProperty=fullName>을 지정하기 위해 전달할 문자열은 `Friend`입니다.  
  
-   [!INCLUDE[TLA2#tla_cppcli](../../../includes/tla2sharptla-cppcli-md.md)]의 경우 XAML 컴파일을 지원하는 대상이 없으므로 전달할 값이 지정되지 않았습니다.  
  
 <xref:System.Reflection.TypeAttributes?displayProperty=fullName>\([!INCLUDE[TLA2#tla_cshrp](../../../includes/tla2sharptla-cshrp-md.md)]에서는 `public`, [!INCLUDE[TLA2#tla_visualb](../../../includes/tla2sharptla-visualb-md.md)]에서는 `Public`\)을 지정할 수도 있으나, <xref:System.Reflection.TypeAttributes?displayProperty=fullName>을 지정하는 작업은 <xref:System.Reflection.TypeAttributes?displayProperty=fullName>이 이미 기본 동작으로 지정되어 있으므로 자주 사용하지 않는 것이 좋습니다.  
  
 중첩된 클래스 참조는 XAML에서 지원되지 않으므로 동일한 사용자 코드 액세스 수준 제한을 가진 다른 값\(예: [!INCLUDE[TLA2#tla_cshrp](../../../includes/tla2sharptla-cshrp-md.md)]의 `private`\)은 `x:ClassModifier`와 관련이 없으며 <xref:System.Reflection.TypeAttributes?displayProperty=fullName> 한정자가 동일한 결과를 가져옵니다.  
  
## 보안 정보  
 `x:ClassModifier`에 선언된 액세스 수준은 여전히 특정 프레임워크의 해석과 그 기능의 영향을 받습니다.  WPF에는 팩 URI 참조를 통해 WPF 리소스에서 클래스를 참조하는 경우 `x:ClassModifier`가 `internal`일 때 형식을 로드하고 인스턴스화하는 기능이 포함되어 있습니다.  이 상황 및 다른 프레임워크에 의해 구현된 이와 유사한 기타 상황의 결과로 가능한 모든 인스턴스화 시도를 차단하기 위해 `x:ClassModifier`에만 의존하지 마십시오.  
  
## 참고 항목  
 [x:Class Directive](../../../docs/framework/xaml-services/x-class-directive.md)   
 [WPF의 코드 숨김 및 XAML](../../../docs/framework/wpf/advanced/code-behind-and-xaml-in-wpf.md)   
 [x:FieldModifier Directive](../../../docs/framework/xaml-services/x-fieldmodifier-directive.md)   
 [보안\(WPF\)](../../../docs/framework/wpf/security-wpf.md)   
 [Types Migrated from WPF to System.Xaml](../../../docs/framework/xaml-services/types-migrated-from-wpf-to-system-xaml.md)