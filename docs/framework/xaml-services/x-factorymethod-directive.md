---
title: "x:FactoryMethod Directive | Microsoft Docs"
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
  - "XAML. x:FactoryMethod directive [XAML Services]"
  - "FactoryMethod directive in XAML [XAML Services]"
  - "x:FactoryMethod directive [XAML Services]"
ms.assetid: 829bcbdf-5318-4afb-9a03-c310e0d2f23d
caps.latest.revision: 8
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 8
---
# x:FactoryMethod Directive
XAML 프로세서가 지원 형식 문제를 해결한 후 개체를 초기화하는 데 사용해야 하는 생성자 이외의 메서드를 지정합니다.  
  
## XAML 특성 사용, x:인수 없음  
  
```  
<object x:FactoryMethod="methodname"...>  
  ...  
</object>  
```  
  
## XAML 특성 사용, x:요소로서의 인수  
  
```  
<object x:FactoryMethod="methodname"...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## XAML 값  
  
|||  
|-|-|  
|`methodname`|XAML 프로세서가 `object`로 지정된 인스턴스를 초기화하기 위해 호출하는 메서드의 문자열 메서드 이름입니다.  설명 부분을 참조하십시오.|  
|`oneOrMoreObjectElements`|팩터리 메서드 매개 변수를 지정하는 개체에 대한 하나 이상의 개체 요소입니다.  순서가 중요하며 인수가 팩터리 메서드로 전달해야 하는 순서를 나타냅니다.|  
  
## 설명  
 `methodname`이 인스턴스 메서드인 경우 정규화할 수 없습니다.  
  
 팩터리 메서드로서 정적 메서드가 지원됩니다.  `methodname`이 정적 메서드인 경우 `methodname`은 *typeName*.*methodName* 조합으로 제공됩니다. 여기서 *typeName*은 정적 팩터리 메서드를 정의하는 클래스를 지정합니다.  *typeName*은 매핑된 xmlns의 형식을 참조하는 경우 접두사 한정될 수 있습니다.  *typeName*은 `typeof(``object``)`와는 다른 형식이 될 수 있습니다.  
  
 팩터리 메서드는 관련 개체 요소를 지원하는 형식의 선언된 공용 메서드가 되어야 합니다.  
  
 팩터리 메서드는 관련 개체에 할당할 수 있는 인스턴스를 반환해야 합니다.  팩터리 메서드는 null을 반환해서는 안 됩니다.  
  
 `x:Arguments`는 팩터리 메서드의 시그니처를 위해 가장 일치하는 원칙에 따라 작동합니다.  일치는 매개 변수 개수를 먼저 계산합니다.  매개 변수 개수에 대해 둘 이상의 가능한 일치가 있는 경우 평가된 가장 일치하는 것이 결정됩니다.  이 평가 단계 후에도 여전히 모호성이 있는 경우 XAML 프로세서 동작이 정의되지 않습니다.  
  
 `x:FactoryMethod` 요소 사용은 지시문 태그가 포함된 개체 요소 형식을 참조하지 않기 때문에 일반적으로는 속성 요소 사용이 아닙니다.  요소 사용이 특성 사용보다 덜 일반적인 것으로 예상됩니다.  `x:Arguments` \(특성 또는 요소 사용\)는 `x:FactoryMethod` 요소 사용과 함께 사용할 수 있지만 특히 Usage 섹션에 표시되지는 않습니다.  
  
 요소로서의 `x:FactoryMethod`는 다른 속성 요소보다 앞에 와야 하며 요소로 제공된 `x:Arguments`보다 앞에 와야 하고 내용\/내부 텍스트\/초기화 텍스트보다 앞에 와야 합니다.  
  
## 참고 항목  
 [x:Arguments Directive](../../../docs/framework/xaml-services/x-arguments-directive.md)