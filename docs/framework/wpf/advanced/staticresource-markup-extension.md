---
title: "StaticResource 태그 확장 | Microsoft Docs"
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
  - "StaticResource"
  - "StaticResourceExtension"
helpviewer_keywords: 
  - "StaticResource 태그 확장"
  - "XAML, StaticResource 태그 확장"
ms.assetid: 97af044c-71f1-4617-9a94-9064b68185d2
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# StaticResource 태그 확장
이미 정의된 리소스에 대한 참조를 조회하여 모든 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 속성 특성에 대한 값을 제공합니다.  해당 리소스에 대한 조회 동작은 현재 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 페이지의 태그 및 기타 응용 프로그램 소스에서 이전에 로드된 리소스를 조회하고 해당 리소스 값을 런타임 개체의 속성 값으로 생성하는 로드 시 조회와 유사합니다.  
  
## XAML 특성 사용  
  
```  
<object property="{StaticResource key}" .../>  
```  
  
## XAML 개체 요소 사용  
  
```  
<object>  
  <object.property>  
<StaticResource ResourceKey="key" .../>  
  </object.property>  
</object>  
```  
  
## XAML 값  
  
|||  
|-|-|  
|`key`|요청된 리소스에 대한 키입니다.  처음에 이 키는 리소스가 태그에서 생성된 경우라면 [x:Key 지시문](../../../../docs/framework/xaml-services/x-key-directive.md)에 의해 할당되고 리소스가 코드에서 생성된 경우라면 <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=fullName>를 호출할 때 `key` 매개 변수로 제공됩니다.|  
  
## 설명  
  
> [!IMPORTANT]
>  `StaticResource`는 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 파일 내에서 구문적으로 더 정의된 리소스에 대한 전방 참조를 만들려고 시도하지 않아야 합니다.  이러한 시도는 지원되지 않으며, 이런 참조가 실패하지 않더라도 전방 참조를 시도하면 <xref:System.Windows.ResourceDictionary>를 나타내는 내부 해시 테이블을 검색할 때 로드 시 성능 저하가 발생할 수 있습니다.  최상의 결과를 위해서는 전방 참조를 피할 수 있도록 리소스 사전의 컴퍼지션을 조정해야 합니다.  전방 참조를 피할 수 없는 경우에는 [DynamicResource 태그 확장](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md)을 대신 사용하십시오.  
  
 지정된 <xref:System.Windows.StaticResourceExtension.ResourceKey%2A>는 페이지, 응용 프로그램, 사용 가능한 컨트롤 테마 및 외부 리소스 또는 시스템 리소스의 특정 수준에서 [x:Key 지시문](../../../../docs/framework/xaml-services/x-key-directive.md)으로 식별되는 기존 리소스에 해당되어야 합니다.  리소스 조회는 이러한 순서로 수행됩니다.  정적 및 동적 리소스에 대한 리소스 조회 동작에 대한 자세한 내용은 [XAML 리소스](../../../../docs/framework/wpf/advanced/xaml-resources.md)를 참조하십시오.  
  
 리소스 키는 [XamlName 문법](../../../../docs/framework/xaml-services/xamlname-grammar.md)에 정의된 모든 문자열일 수 있습니다.  리소스 키는 <xref:System.Type>과 같은 다른 개체 형식일 수도 있습니다.  <xref:System.Type> 키는 암시적 스타일 키를 통해 테마를 사용해 컨트롤에 스타일을 적용하는 방식의 기반이 됩니다.  자세한 내용은 [컨트롤 제작 개요](../../../../docs/framework/wpf/controls/control-authoring-overview.md)를 참조하십시오.  
  
 리소스 참조 대신 사용 가능한 선언적 방법은 [DynamicResource 태그 확장](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md)입니다.  
  
 특성 구문은 이러한 태그 확장에 가장 많이 사용되는 구문입니다.  `StaticResource` 식별자 문자열 다음에 나오는 문자열 토큰은 기본 <xref:System.Windows.StaticResourceExtension> 확장 클래스의 <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> 값으로 할당됩니다.  
  
 `StaticResource`은 개체 요소 구문에서 사용할 수 있습니다.  이 경우에는 <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> 속성의 값을 지정해야 합니다.  
  
 <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> 속성을 다음과 같이 속성\=값 쌍으로 지정하는 자세한 특성 사용 구문에도 `StaticResource`을 사용할 수 있습니다.  
  
```  
<object property="{StaticResource ResourceKey=key}" .../>  
```  
  
 자세한 정보 표시는 설정 가능한 속성이 여러 개이거나 일부 속성이 선택 사항인 확장에 유용한 경우가 많습니다.  `StaticResource`에는 설정 가능한 속성이 하나뿐이고 이 속성은 필수적 속성이므로 자세한 정보 표시를 사용하지 않는 것이 일반적입니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서 구현에서 이 태그 확장에 대한 처리는 <xref:System.Windows.StaticResourceExtension> 클래스를 통해 정의됩니다.  
  
 `StaticResource`은 태그 확장입니다.  태그 확장은 특성 값을 리터럴 값 또는 처리기 이름이 아닌 다른 값이 되도록 이스케이프해야 하는 요구 사항이 있는 경우 일반적으로 구현되며 이러한 요구 사항은 특정 형식 또는 속성에 형식 변환기를 배치하는 것보다 더 포괄적입니다.  [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]의 모든 태그는 태그의 특성 구문에 { 및 } 문자를 사용하며 여기서 특성 구문은 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서에 태그 확장이 특성을 처리해야 한다는 것을 인식하는 규칙입니다.  자세한 내용은 [태그 확장 및 WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)를 참조하십시오.  
  
## 참고 항목  
 [스타일 지정 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [XAML 개요\(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)   
 [태그 확장 및 WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)   
 [XAML 리소스](../../../../docs/framework/wpf/advanced/xaml-resources.md)   
 [리소스 및 코드](../../../../docs/framework/wpf/advanced/resources-and-code.md)