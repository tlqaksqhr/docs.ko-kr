---
title: "x:Reference Markup Extension | Microsoft Docs"
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
  - "x:Reference markup extension [XAML Services]"
  - "XAML [XAML Services], x:Reference Markup Extension"
  - "Reference markup extension [XAML Services]"
ms.assetid: 2982e68b-d26b-4aa3-826a-34c57a9c5199
caps.latest.revision: 8
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 8
---
# x:Reference Markup Extension
XAML 태그에 선언된 인스턴스를 참조합니다.  참조는 요소의 `x:Name`을 참조합니다.  
  
## XAML 특성 사용  
  
```  
<object property="{x:Reference instancexName}" .../>  
```  
  
## XAML 개체 요소 사용  
  
```  
<object>  
  <object.property>  
    <x:Reference Name="instancexName"/>  
  </object.property>  
</object>  
```  
  
## XAML 값  
  
|||  
|-|-|  
|`instancexName`|참조되는 인스턴스의 `x:Name` 값\(또는 <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>\-식별된 속성 값\)입니다.|  
  
## 설명  
 `x:Reference`는 WPF 같은 특정 프레임워크에서 구현된 요소 참조 개념에 대한 XAML 언어 수준 지원을 제공합니다.  
  
## x:참조 및 WPF  
 WPF 및 XAML 2006에서 요소 참조는 <xref:System.Windows.Data.Binding.ElementName%2A> 바인딩의 프레임워크 수준 기능으로 주소 지정됩니다.  대부분의 WPF 응용 프로그램 및 시나리오의 경우 <xref:System.Windows.Data.Binding.ElementName%2A> 바인딩을 계속 사용해야 합니다.  이 일반 지침의 예외는 데이터 바인딩을 실용적이지 못하게 만드는 데이터 컨텍스트 또는 다른 범위가 있고 태그 컴파일이 포함되지 않는 경우를 포함할 수 있습니다.  
  
 `x:Reference`는 XAML 2009에 정의된 구문입니다.  WPF에서 XAML 2009 기능을 사용할 수 있지만 WPF 태그 컴파일되지 않은 XAML의 경우에만 가능합니다.  태그 컴파일된 XAML 및 BAML 형태의 XAML은 현재 XAML 2009 언어 키워드 및 기능을 지원하지 않습니다.