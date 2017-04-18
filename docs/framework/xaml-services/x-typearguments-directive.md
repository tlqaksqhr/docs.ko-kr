---
title: "x:TypeArguments Directive | Microsoft Docs"
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
  - "x:TypeArguments"
  - "xTypeArguments"
  - "TypeArguments"
helpviewer_keywords: 
  - "x:TypeArguments attribute [XAML Services]"
  - "TypeArguments attribute in XAML [XAML Services]"
  - "XAML [XAML Services], x:TypeArguments attribute"
ms.assetid: 86561058-d393-4a44-b5c3-993a4513ea74
caps.latest.revision: 18
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 18
---
# x:TypeArguments Directive
제네릭의 포함 형식 인수를 제네릭 형식의 생성자에 전달합니다.  
  
## XAML 특성 사용  
  
```  
<object x:TypeArguments="typeString" .../>  
```  
  
## XAML 값  
  
|||  
|-|-|  
|`object`|XAML 형식의 개체 요소 선언은 CLR 제네릭 형식에 의해 지원됩니다.  `object`가 기본 XAML 네임스페이스에서 가져오지 않은 XAML 형식을 나타내는 경우 `object`에는 `object`가 존재하는 XAML 네임스페이스를 나타내는 접두사가 필요합니다.|  
|`typeString`|하나 이상의 XAML 형식 이름을 문자열로 선언하는 문자열로, CLR 제네릭 형식의 형식 인수를 제공합니다.  자세한 구문 정보는 설명을 참조하십시오.|  
  
## 설명  
 대부분의 경우 `typeString` 문자열의 정보 항목 중 하나로 사용되는 XAML 형식은 접두사로 지정됩니다.  일반적인 형식의 CLR 제네릭 제약 조건\(예: <xref:System.Int32> and <xref:System.String>\)은 CLR 기본 클래스 라이브러리에서 제공됩니다.  이러한 라이브러리는 일반적인 프레임워크 특정 기본 XAML 네임스페이스에 매핑되지 않으므로 XAML 사용의 경우 접두사를 매핑해야 합니다.  
  
 쉼표 구분 기호를 사용하여 둘 이상의 XAML 형식 이름을 지정할 수 있습니다.  
  
 제네릭 제약 조건이 제네릭 형식을 사용하는 경우 중첩된 제약 조건 형식 인수는 괄호\(\) 안에 포함될 수 있습니다.  
  
 `x:TypeArguments`의 이 정의가 .NET Framework XAML 서비스에 특정하고 CLR 지원을 사용한다는 점에 유의하십시오.  언어 수준 정의는 [\[MS\-XAML\] Section 5.3.11](http://go.microsoft.com/fwlink/?LinkId=114525)에서 볼 수 있습니다.  
  
## 사용 예제  
 이 예제에서는 다음 XAML 네임스페이스 정의가 선언되었다고 가정하십시오.  
  
```  
xmlns:sys="clr-namespace:System;assembly=mscorlib"  
xmlns:scg="clr-namespace:System.Collections.Generic;assembly=mscorlib"  
```  
  
### 목록\<String\>  
 `<scg:List x:TypeArguments="sys:String" ...>`은 <xref:System.String> 형식 인수가 하나 있는 새 <xref:System.Collections.Generic.List%601>를 인스턴스화합니다.  
  
### 사전\<문자열,문자열\>  
 `<scg:Dictionary x:TypeArguments="sys:String,sys:String" ...>`은 <xref:System.String> 형식 인수가 두 개 있는 새 <xref:System.Collections.Generic.Dictionary%602>를 인스턴스화합니다.  
  
### 큐\<KeyValuePair\<String,String\>\>  
 `<scg:Queue x:TypeArguments="scg:KeyValuePair(sys:String,sys:String)" ...>`는 내부 제약 조건 형식 인수 <xref:System.String> 및 <xref:System.String>을 사용하여 및 <xref:System.Collections.Generic.KeyValuePair%602>의 제약 조건을 갖고 있는 새 <xref:System.Collections.Generic.Queue%601>를 인스턴스화합니다.  
  
## XAML 2006 및 WPF 제네릭 XAML 사용  
 XAML 2006 사용 및 WPF 응용 프로그램에 사용되는 XAML의 경우 `x:TypeArguments` 및 일반적으로 XAML의 제네릭 형식 사용에 대해 다음과 같은 제한 사항이 있습니다.  
  
-   XAML 파일의 루트 요소만 제네릭 형식을 참조하는 제네릭 XAML 사용을 지원할 수 있습니다.  
  
-   루트 요소는 하나 이상의 형식 인수가 있는 제네릭 형식에 매핑되어야 합니다.  예를 들면 <xref:System.Windows.Navigation.PageFunction%601>과 같이 지정합니다.  페이지 함수는 WPF에서 XAML 제네릭 사용 지원을 위한 기본 시나리오입니다.  
  
-   제네릭에 대한 루트 요소에 XAML 개체는 `x:Class`를 사용하여 partial 클래스도 선언해야 합니다.  이는 WPF 빌드 작업을 정의하는 경우에도 마찬가지입니다.  
  
-   `x:TypeArguments`는 중첩된 제네릭 제약 조건을 참조할 수 없습니다.  
  
## WPF 3.0 또는 WPF 3.5 종속성이 없는 XAML 2009 또는 XAML 2006  
 XAML 2006 또는 XAML 2009에 대한 .NET Framework XAM에서 일반 XAML 사용에 대한 WPF 관련 제한이 완화되었습니다.  지원 형식 시스템과 개체 모델이 지원할 수 있는 XAML 태그에 있는 모든 위치에서 제네릭 개체 요소를 인스턴스화할 수 있습니다.  
  
 CLR 기본 형식을 매핑하는 대신 XAML 2009를 사용하여 일반적인 언어 기본 형식에 대한 XAML 형식을 가져오면 [공용 XAML 언어 기본 형식에 대한 기본 제공 형식](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md)을 `typeString`의 정보 항목으로 사용할 수 있습니다.  예를 들어 다음을 선언할 수 있습니다. 여기서 접두사 매핑은 표시되지 않았지만 x는 XAML 2009의 XAML 언어 XAML 네임스페이스입니다.  
  
```  
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>  
```  
  
 WPF에서와 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]을 대상으로 할 때 XAML 2009 기능을 `x:TypeArguments`와 함께 사용할 수 있지만 태그 컴파일되지 않은 느슨한 XAML의 경우에만 가능합니다.  WPF에 대한 태그 컴파일된 XAML 및 BAML 형태의 XAML은 현재 XAML 2009 키워드 및 기능을 지원하지 않습니다.  XAML을 태그 컴파일해야 하는 경우 "XAML 2006 및 WPF 제네릭 XAML 사용" 섹션에서 설명한 제한 사항 하에서 작동해야 합니다.SECTION.  
  
## 참고 항목  
 [x:Class Directive](../../../docs/framework/xaml-services/x-class-directive.md)   
 [x:Type Markup Extension](../../../docs/framework/xaml-services/x-type-markup-extension.md)   
 [공용 XAML 언어 기본 형식에 대한 기본 제공 형식](../../../docs/framework/xaml-services/built-in-types-for-common-xaml-language-primitives.md)   
 [Generics in XAML](../../../docs/framework/xaml-services/generics-in-xaml.md)