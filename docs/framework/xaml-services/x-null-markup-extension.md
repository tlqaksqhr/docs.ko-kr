---
title: "x:Null Markup Extension | Microsoft Docs"
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
  - "NullExtension"
  - "x:NullExtension"
  - "x:Null"
  - "Null"
  - "xNull"
helpviewer_keywords: 
  - "Null markup extension in XAML [XAML Services]"
  - "x:Null markup extension [XAML Services]"
  - "XAML [XAML Services], x:Null markup extension"
ms.assetid: 2e3ccc21-4996-481d-91b5-3910d8b3bfa3
caps.latest.revision: 20
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 20
---
# x:Null Markup Extension
`null`은 XAML 멤버의 값으로 지정합니다.  
  
## XAML 특성 사용  
  
```  
<object property="{x:Null}" .../>  
```  
  
## 설명  
 [!INCLUDE[TLA#tla_cshrp](../../../includes/tlasharptla-cshrp-md.md)] 및 [!INCLUDE[TLA#tla_cpp](../../../includes/tlasharptla-cpp-md.md)]의 null 참조를 위한 키워드는 null입니다.  null 참조에 대한 [!INCLUDE[TLA#tla_visualb](../../../includes/tlasharptla-visualb-md.md)] 키워드는 `Nothing`이지만 코드 숨김 언어가 XAML과 연결되는지에 관계 없이 항상 XAML로 `{x:Null}`을 사용합니다.  
  
 `x:Null` 태그 확장에는 설정 가능한 속성이 없습니다.  
  
 널 사용은 CLR <xref:System.Nullable%601> 값의 XAML 멤버 노출과 관련된 경우가 많습니다.  
  
 모든 XAML 태그 확장과 같은 `x:Null` 태그 확장에서는 특성 값을 처리할 때 리터럴 또는 이벤트 처리기 참조가 아닌 다른 값이 되도록 이스케이프하기 위해 중괄호\(`{,}`\)를 사용합니다.  특성 구문은 이러한 태그 확장에 가장 많이 사용되는 구문입니다.  개체 요소 `<x:Null />`은 기술적으로 가능하지만 `x:Null` 태그 확장이 위치 매개 변수 또는 생성 인수를 갖지 않기 때문에 거의 사용되지 않습니다.  
  
 태그 확장에 대한 자세한 내용은 [태그 확장 및 WPF XAML](../../../ocs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)를 참조하십시오.  
  
 .NET Framework XAML 서비스에서 이 태그 확장에 대한 처리는 <xref:System.Windows.Markup.NullExtension> 클래스를 통해 정의됩니다.  
  
## WPF 사용 정보  
 참조 형식 종속성 속성에서 설정되지 않은 초기 값이 `null`일 필요는 없습니다.  초기 기본값은 각 종속성 속성마다 다양할 수 있으며 속성 관련 메타데이터를 기반으로 할 수 있습니다.  많은 종속성 속성이 유효성 검사 콜백 구현 때문에 태그나 코드를 통해 `null`을 값으로 받을 수 없습니다.  종속성 속성에 대한 자세한 내용은 [종속성 속성 개요](../../../ocs/framework/wpf/advanced/dependency-properties-overview.md)를 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.DependencyProperty.UnsetValue>   
 [XAML 개요\(WPF\)](../../../ocs/framework/wpf/advanced/xaml-overview-wpf.md)   
 [태그 확장 및 WPF XAML](../../../ocs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)