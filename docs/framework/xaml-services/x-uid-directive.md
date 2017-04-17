---
title: "x:Uid Directive | Microsoft Docs"
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
  - "XAML [XAML Services], localizable content attribute"
  - "XAML [XAML Services], x:Uid attribute"
  - "x:Uid attribute [XAML Services]"
  - "Uid attribute [XAML Services]"
ms.assetid: 81defade-483b-4a89-b76d-9b25bba34010
caps.latest.revision: 12
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 12
---
# x:Uid Directive
태그 요소의 고유 식별자를 제공합니다.  대부분의 시나리오에서 이 고유한 식별자는 XAML 지역화 프로세스와 도구에서 사용됩니다.  
  
## XAML 특성 사용  
  
```  
<object x:Uid="identifier"... />  
```  
  
## XAML 값  
  
|||  
|-|-|  
|`identifier`|`x:Uid` 소비자에 의해 해석될 때 파일에서 고유해야 하는 문자열로, 수동으로 만들어지거나 자동으로 생성됩니다.|  
  
## 설명  
 \[MS\-XAML\]에서는 `x:Uid`가 지시문으로 정의됩니다.  자세한 내용은 [\[MS\-XAML\] Section 5.3.6](http://go.microsoft.com/fwlink/?LinkId=114525)을 참조하십시오.  
  
 `x:Uid`는 명시된 XAML 지역화 시나리오로 인해 지역화에 사용되는 식별자가 `x:Name`의 프로그래밍 모델 암시에 대한 종속성이 없도록 `x:Name`에서 분리합니다.  또한 `x:Name`은 XAML 네임스페이스의 적용을 받지만 `x:Uid`은 고유성 적용의 모든 XAML 정의 언어 정의 개념의 적용을 받지 않습니다.  일반적으로 XAML 프로세서에는\(지역화 프로세스의 일부가 아닌 프로세서\) `x:Uid` 값이 고유해야 한다는 요구 사항이 없습니다.  이 책임은 개념적으로 값의 작성기에 있습니다.  전용 전역화 프로세스 또는 도구 등과 같은 값의 소비자는 당연히 단일 XAML 소스 내에 있는 `x:Uid` 값의 고유성을 기대합니다.  일반적인 고유성 모델은 `x:Uid` 값이 XAML을 나타내는 XML로 인코딩된 파일 내에서 고유합니다.  
  
 특정 XAML 스키마에 대한 상당한 지식이 있는 도구는 텍스트 문자열 값이 태그에 있는 모든 경우보다는 실제 지역화 가능한 문자열에만 `x:Uid`을 적용하도록 선택할 수 있습니다.  
  
 프레임워크는 특성 <xref:System.Windows.Markup.UidPropertyAttribute>를 정의 형식에 적용하여 `x:Uid`에 대한 별칭이 될 개체 모델에 특정 속성을 지정할 수 있습니다.  프레임워크에서 특정 속성을 지정하면 `x:Uid`와 동일 개체에서 별칭이 지정된 멤버를 모두 지정할 수 없습니다.  두 개의 `x:Uid` 및 별칭이 지정된 멤버가 모두 지정되면 .NET Framework XAML 서비스 API는 이 경우에 일반적으로 <xref:System.Xaml.XamlDuplicateMemberException>를 throw합니다.  
  
## WPF 사용 정보  
 `x:Uid`의 WPF 지역화 프로세스의 역할과 XAML의 BAML 폼에 대한 자세한 내용은 [WPF의 전역화](../../../ocs/framework/wpf/advanced/globalization-for-wpf.md) 또는 <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>를 참조하십시오.  
  
## 참고 항목  
 <xref:System.Windows.Markup.Localizer.BamlLocalizableResourceKey.Uid%2A>   
 <xref:Microsoft.Build.Tasks.Windows.UidManager>   
 [WPF의 전역화](../../../ocs/framework/wpf/advanced/globalization-for-wpf.md)