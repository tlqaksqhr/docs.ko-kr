---
title: "종속성 속성 보안 | Microsoft Docs"
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
  - "종속성 속성, access"
  - "종속성 속성, 보안"
  - "보안, 종속성 속성"
  - "보안, 래퍼"
  - "유효성 검사, 종속성 속성"
  - "래퍼, access"
  - "래퍼, 보안"
ms.assetid: d10150ec-90c5-4571-8d35-84bafa2429a4
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# 종속성 속성 보안
일반적으로 종속성 속성은 공용 속성으로 간주됩니다.  [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 속성 시스템에서는 기본적으로 종속성 속성 값의 보안을 유지하지 않습니다.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="AccessSecurity"></a>   
## 래퍼 및 종속성 속성에 대한 액세스 및 보안  
 일반적으로 종속성 속성은 인스턴스에서 속성을 가져오거나 설정하는 작업을 간소화하는 "래퍼" [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 속성과 함께 구현됩니다.  그러나 실제로 래퍼는 종속성 속성과 상호 작용할 때 사용되는 기본 <xref:System.Windows.DependencyObject.GetValue%2A> 및 <xref:System.Windows.DependencyObject.SetValue%2A> 정적 호출을 구현하는 편리한 방법일 뿐입니다.  다른 각도에서 보면 속성은 전용 필드 대신 종속성 속성으로 지원되는 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 속성으로 노출됩니다.  래퍼에 적용되는 보안 메커니즘은 기본 종속성 속성에 대한 속성 시스템의 동작 및 액세스와 관계없습니다.  즉, 래퍼에 보안 요구 사항을 추가하면 편의를 위해 간단하게 사용할 수만 없게 되지 <xref:System.Windows.DependencyObject.GetValue%2A> 또는 <xref:System.Windows.DependencyObject.SetValue%2A>에 대한 호출은 차단되지 않습니다.  마찬가지로 래퍼에 보호된 액세스 또는 전용 액세스 수준을 설정해도 효과적인 보안 기능을 구현할 수 없습니다.  
  
 종속성 속성을 사용자 지정하는 경우, 호출자가 해당 속성의 액세스 수준에 대한 올바른 정보를 가져올 수 있도록 래퍼와 <xref:System.Windows.DependencyProperty> 식별자 필드를 공용 멤버로 선언해야 합니다. 이는 저장소가 종속성 속성으로 구현되기 때문입니다.  
  
 사용자 지정 종속성 속성의 경우에는 속성을 읽기 전용 종속성 속성으로 등록할 수 있습니다. 이렇게 하면 속성의 <xref:System.Windows.DependencyPropertyKey>에 대한 참조를 가지고 있는 사용자만 속성을 설정할 수 있기 때문에 속성을 효과적으로 보호할 수 있습니다.  자세한 내용은 [읽기 전용 종속성 속성](../../../../docs/framework/wpf/advanced/read-only-dependency-properties.md)을 참조하십시오.  
  
> [!NOTE]
>  <xref:System.Windows.DependencyProperty> 식별자 필드를 전용 필드로 선언하여 사용자 지정 클래스의 노출되는 네임스페이스를 간단하게 줄일 수 있지만, 이러한 속성은 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 언어 정의에서 해당 액세스 수준에 대해 정의하는 "전용" 속성의 의미와는 다릅니다. 자세한 이유는 다음 단원에서 설명합니다.  
  
<a name="PropertySystemExposure"></a>   
## 속성 시스템에서 노출하는 종속성 속성  
 일반적으로 <xref:System.Windows.DependencyProperty>는 공용 이외의 액세스 수준으로 선언하지 않는 것이 좋습니다.  이 액세스 수준 설정에서는 다른 사용자가 선언하는 클래스에서 해당 인스턴스에 대한 참조를 가져오는 것만 제한됩니다.  그러나 경우에 따라 속성 시스템에서는 클래스의 인스턴스나 파생 클래스 인스턴스의 특정 속성을 식별하기 위해 <xref:System.Windows.DependencyProperty>를 반환하며, 이 식별자는 원래 정적 식별자를 비공용으로 선언한 경우에도 <xref:System.Windows.DependencyObject.SetValue%2A> 호출에 사용될 수 있습니다.  또한 <xref:System.Windows.DependencyObject.OnPropertyChanged%2A> 가상 메서드는 값이 변경된 모든 기존 종속성 속성에 대한 정보를 받습니다.  <xref:System.Windows.DependencyObject.GetLocalValueEnumerator%2A> 메서드는 값이 로컬로 설정된 인스턴스의 모든 속성에 대한 식별자를 반환합니다.  
  
### 유효성 검사 및 보안  
 <xref:System.Windows.DependencyProperty.ValidateValueCallback%2A>에 요청을 적용한 후 요청 실패 시 유효성 검사가 실패하도록 하여 속성 설정을 차단하는 방법은 효과적인 보안 메커니즘이 아닙니다.  <xref:System.Windows.DependencyProperty.ValidateValueCallback%2A>을 통해 값 설정 무효화를 적용한 경우, 악의적인 호출자가 응용 프로그램 도메인 내에서 작업하고 있으면 해당 호출자가 이를 실행되지 않도록 억제할 수도 있습니다.  
  
## 참고 항목  
 [사용자 지정 종속성 속성](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)