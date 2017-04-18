---
title: "ThemeDictionary 태그 확장 | Microsoft Docs"
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
  - "ThemeDictionaryExtension"
  - "ThemeDictionary"
helpviewer_keywords: 
  - "ThemeDictionary 태그 확장"
  - "XAML, ThemeDictionary 태그 확장"
ms.assetid: aa75e10b-13dd-4989-972d-51bab63a05e2
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# ThemeDictionary 태그 확장
타사 컨트롤을 통합하는 사용자 지정 컨트롤 제작자 또는 응용 프로그램이 컨트롤 스타일 지정에 사용하기 위해 테마별 리소스 사전을 로드할 방법을 제공합니다.  
  
## XAML 특성 사용  
  
```  
<object property="{ThemeDictionary assemblyUri}" .../>  
```  
  
## XAML 개체 요소 사용  
  
```  
<object>  
  <object.property>  
    <ThemeDictionary AssemblyName="assemblyUri"/>  
  <object.property>  
<object>  
```  
  
## XAML 값  
  
|||  
|-|-|  
|`assemblyUri`|테마 정보가 포함된 어셈블리의 [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)]입니다.  일반적으로 더 큰 패키지의 어셈블리를 참조하는 pack URI입니다.  어셈블리 리소스 및 pack URI는 배포 문제를 단순화합니다.  자세한 내용은 [WPF의 Pack URI](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md)를 참조하십시오.|  
  
## 설명  
 이 확장은 하나의 특정 속성 값, 즉 <xref:System.Windows.ResourceDictionary.Source%2A?displayProperty=fullName>에 대한 값만 채우기 위한 것입니다.  
  
 이 확장을 사용하면 [!INCLUDE[TLA#tla_aero](../../../../includes/tlasharptla-aero-md.md)] 테마가 사용자의 시스템에 적용될 때에만 사용할 스타일과 Luna 테마가 활성화될 때 사용할 다른 스타일 등이 포함된 하나의 리소스 전용 어셈블리를 지정할 수 있습니다.  이 확장을 사용하면 필요한 경우 컨트롤 특정 리소스 사전의 콘텐츠를 자동으로 무효화하고 다른 테마에 한정되도록 다시 로드할 수 있습니다.  
  
 `assemblyUri` 문자열\(<xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> 속성 값\)은 특정 테마에 적용할 사전을 구분하는 이름 지정 규칙의 기본이 됩니다.  `ThemeDictionary`에 대한 <xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A> 논리는 사전 컴파일된 리소스 어셈블리 안에 포함된 것처럼 특정 테마 사전 variant를 가리키는 [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)]를 생성하여 변환을 완료합니다.  이 변환에 대한 설명 또는 일반 컨트롤 스타일 지정 및 페이지\/응용 프로그램 수준 스타일과의 테마 상호 작용 개념에 대해서는 여기에서 자세히 다루지 않습니다.  `ThemeDictionary` 사용에 대한 기본 시나리오는 응용 프로그램 수준에서 선언되는 `ResourceDictionary`의 <xref:System.Windows.ResourceDictionary.Source%2A> 속성을 지정하는 것입니다.  직접 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] 대신 `ThemeDictionary` 확장을 통해 어셈블리에 대한 [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)]를 제공하면 확장 로직은 시스템 테마가 변경될 때마다 적용되는 무효화 논리를 제공합니다.  
  
 특성 구문은 이러한 태그 확장에 가장 많이 사용되는 구문입니다.  `ThemeDictionary` 식별자 문자열 다음에 나오는 문자열 토큰은 기본 <xref:System.Windows.ThemeDictionaryExtension> 확장 클래스의 <xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> 값으로 할당됩니다.  
  
 `ThemeDictionary`는 개체 요소 구문에도 사용할 수 있습니다.  이 경우에는 <xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> 속성의 값을 지정해야 합니다.  
  
 <xref:System.Windows.Markup.StaticExtension.Member%2A> 속성을 다음과 같이 속성\=값 쌍으로 지정하는 자세한 특성 사용 구문에도 `ThemeDictionary`를 사용할 수 있습니다.  
  
```  
<object property="{ThemeDictionary AssemblyName=assemblyUri}" .../>  
```  
  
 자세한 정보 표시는 설정 가능한 속성이 여러 개이거나 일부 속성이 선택 사항인 확장에 유용한 경우가 많습니다.  `ThemeDictionary`에는 설정 가능한 속성이 하나뿐이고 이 속성은 필수적 속성이므로 자세한 정보 표시를 사용하지 않는 것이 일반적입니다.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서 구현에서 이 태그 확장에 대한 처리는 <xref:System.Windows.ThemeDictionaryExtension> 클래스를 통해 정의됩니다.  
  
 `ThemeDictionary`은 태그 확장입니다.  태그 확장은 특성 값을 리터럴 값 또는 처리기 이름이 아닌 다른 값이 되도록 이스케이프해야 하는 요구 사항이 있는 경우 일반적으로 구현되며 이러한 요구 사항은 특정 형식 또는 속성에 형식 변환기를 배치하는 것보다 더 포괄적입니다.  [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]의 모든 태그는 태그의 특성 구문에 { 및 } 문자를 사용하며 여기서 특성 구문은 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 프로세서에 태그 확장이 특성을 처리해야 한다는 것을 인식하는 규칙입니다.  자세한 내용은 [태그 확장 및 WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)를 참조하십시오.  
  
## 참고 항목  
 [스타일 지정 및 템플릿](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [XAML 개요\(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)   
 [태그 확장 및 WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)   
 [WPF 응용 프로그램 리소스, 콘텐츠 및 데이터 파일](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md)