---
title: "XAML 2009 Language Features | Microsoft Docs"
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
  - "XAML 2009 [XAML Services]"
  - "XAML [XAML Services], XAML 2009"
ms.assetid: f6bb18d8-c86a-4549-8862-323e6b32a8dd
caps.latest.revision: 11
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 11
---
# XAML 2009 Language Features
XAML 2009는 기존 XAML 언어 사양을 확장하는 새 XAML 언어 기능의 약식 용어입니다. XAML 2009에서는 여러 가지 새로운 지시문과 구문이 도입되었습니다. 여기에는 [x:Arguments Directive](../../../docs/framework/xaml-services/x-arguments-directive.md), [x:FactoryMethod Directive](../../../docs/framework/xaml-services/x-factorymethod-directive.md), [x:Reference Markup Extension](../../../docs/framework/xaml-services/x-reference-markup-extension.md), [x:TypeArguments Directive](../../../docs/framework/xaml-services/x-typearguments-directive.md), 공용 언어 기본 형식에 대한 기본 제공 형식\(예: `x:Char`\)이 포함됩니다.  
  
<a name="xaml_2009_support_in_wpf_and_visual_studio"></a>   
## WPF 및 Visual Studio의 XAML 2009 지원  
 WPF에서 XAML 2009 기능을 사용할 수 있지만 WPF 태그 컴파일된 XAML에만 사용할 수 있습니다. 태그 컴파일된 XAML 및 BAML 형식의 XAML은 현재 XAML 2009 언어 키워드 및 기능을 지원하지 않습니다.  
  
 WPF에서 느슨한 XAML을 로드하는 기존 기술은 태그 컴파일된 XAML보다 제한적인 CLR 형식 및 형식 시스템에 대해 가능한 보안 및 액세스 제한이 있을 수도 있습니다. 자세한 내용은 [보안\(WPF\)](../../../ocs/framework/wpf/security-wpf.md) 또는 [WPF 보안 전략 \- 플랫폼 보안](../../../ocs/framework/wpf/wpf-security-strategy-platform-security.md)을 참조하세요.  
  
 XAML 2009에서는 이전 XAML 2006 구문을 수정하거나 기본 태그 폼을 수정하는 추가 기능도 도입되었습니다.  
  
### 개체 요소인 x:Key  
 XAML 2009에서는 `x:Key`를 개체\(개체 요소 값을 가진 속성 요소\)로 지원할 수 있습니다. 그러나 XAML 2006에서는 `x:Key`를 특성으로만 지원했습니다.[x:Key Directive](../../../docs/framework/xaml-services/x-key-directive.md)의 “XAML 2009” 섹션을 참조하세요.  
  
### 속성 요소에 대한 xmlns  
 XAML 2009에서는 속성 요소에 대한 XAML 네임스페이스\(xmlns\) 정의를 지원할 수 있습니다. 그러나 XAML 2006에서는 개체 요소에 대한 xmlns 정의만 지원합니다.  
  
### 이벤트 특성  
 이벤트에서 지원하는 특성에 대해 XAML 2006에서는 태그 컴파일이 필요하다고 가정하고 이벤트를 태그 컴파일에 제출합니다. XAML 2009에서는 XAML의 런타임 구문 분석 및 로드 시까지 이벤트 연결을 지연하는, 태그 확장과 유사한 태그 폼을 지원합니다. 그러나 WPF UI에 대한 XAML 시나리오 및 WPF 응용 프로그램에서는 일반적으로 이 기능을 사용하지 않습니다. WPF 및 XAML 2006 구현에서는 대부분의 이벤트 특성 처리에 대해 <xref:System.Windows.UIElement> 수준에서 정의된 라우트된 이벤트에 대한 이벤트 처리기 연결 및 해당 태그 컴파일러 단계의 조합을 사용합니다. 또한 태그 컴파일러는 빌드 작업에서 태그 컴파일러가 사용됨을 선언하는 XAML에 있는 모든 이벤트 특성을 전처리합니다.  
  
## 참고 항목  
 [XAML 개요\(WPF\)](../../../ocs/framework/wpf/advanced/xaml-overview-wpf.md)