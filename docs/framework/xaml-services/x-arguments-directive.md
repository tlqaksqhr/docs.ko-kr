---
title: "x:Arguments Directive | Microsoft Docs"
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
  - "x:Arguments directive [XAML Services]"
  - "Arguments directive in XAML [XAML Services]"
  - "XAML [XAML Services], x:Arguments directive"
ms.assetid: 87cc10b0-b610-4025-b6b0-ab27ca27c92e
caps.latest.revision: 12
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 12
---
# x:Arguments Directive
XAML에서 기본이 아닌 생성자 개체 요소 선언 또는  팩터리 메서드 개체에 대한 생성 인수를 패키지합니다.  
  
## XAML 요소 사용\(기본값이 아닌 생성자\)  
  
```  
<object ...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## XAML 요소 사용\(팩터리 메서드\)  
  
```  
<object x:FactoryMethod="methodName"...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## XAML 값  
  
|||  
|-|-|  
|`oneOrMoreObjectElements`|기본이 아닌 백업 생성자 또는 팩터리 메서드에 전달할 인수를 지정하는 하나 이상의 개체 요소입니다.<br /><br /> 일반적인 용도는 개체 요소 내의 초기화 텍스트를 사용하여 실제 인수 값을 지정하는 것입니다.  예제 섹션을 참조하십시오.<br /><br /> 요소의 순서는 중요합니다.  순서에서 XAML 형식은 지원 생성자 또는 팩터리 메서드 오버로드의 형식 순서와 일치해야 합니다.|  
|`methodName`|임의의 `x:Arguments` 인수를 처리해야 하는 팩터리 메서드의 이름입니다.|  
  
## 종속성  
 `x:FactoryMethod`는 `x:Arguments`가 적용되는 동작과 범위를 수정합니다.  
  
 `x:FactoryMethod`가 지정되지 않은 경우 `x:Arguments`가 지원 생성자의 대체\(기본값이 아님\) 서명에 적용됩니다.  
  
 `x:FactoryMethod`가 지정된 경우 `x:Arguments`가 명명된 메서드의 오버로드에 적용됩니다.  
  
## 설명  
 XAML 2006은 초기화 텍스트를 통해 기본이 아닌 초기화를 지원할 수 있습니다.  그러나 초기화 텍스트 생성 기법의 실용적인 응용 프로그램은 제한됩니다.  단일 텍스트 문자열로 처리되는 초기화 텍스트입니다. 따라서 형식 변환기가 문자열에서 사용자 지정 정보 항목과 사용자 지정 구분 기호를 구문 분석할 수 있는 구성 동작에 대해 정의되지 않는 한 단일 매개 변수 초기화에 대한 기능만 추가합니다.  또한 개체 논리에 대한 텍스트 문자열은 실제 문자열 이외의 기본 형식 처리를 위해 지정된 XAML 파서의 네이티브 기본 형식 변환기일 수 있습니다.  
  
 `x:Arguments` XAML 사용은 지시문 태그가 포함된 개체 요소 형식을 참조하지 않기 때문에 일반적으로는 속성 요소 사용이 아닙니다.  이것은 하위 내용의 기본값과 다르게 태그가 해석되어야 하는 범위를 요소에서 표시 해제하는 `x:Code` 같은 다른 지시문과 더 비슷합니다.  이 경우 각 개체 요소의 XAML 형식은 인수 형식에 대한 정보와 통신합니다. 이 형식은 XAML 파서에서 사용되며 `x:Arguments` 사용 시 참조하려는 특정 생성자 팩터리 메서드 서명 유형을 결정합니다.  
  
 생성 중인 개체 요소의 `x:Arguments`는 개체 요소의 다른 모든 속성 요소, 내용, 내부 텍스트 또는 초기화 설정의 앞에 와야 합니다.  `x:Arguments` 내의 개체 요소에는 XAML 형식 및 지원 생성자 또는 팩터리 메서드에서 허용된 것처럼 특성 및 초기화 문자열이 있습니다.  개체 또는 인수의 경우 설정된 접두사 매핑을 참조하여 기본 XAML 네임스페이스를 벗어나는 사용자 지정 XAML 형식 또는 XAML 형식을 지정할 수 있습니다.  
  
 XAML 프로세서는 다음 지침을 통해 개체를 생성하는 데 `x:Arguments`에서 지정한 인수를 사용하는 방법을 확인합니다.  `x:FactoryMethod`가 지정된 경우 정보를 지정한 `x:FactoryMethod`와 비교할 수 있습니다. `x:FactoryMethod`의 값은 메서드 이름이고 이름이 지정된 메서드에 오버로드가 있을 수 있습니다.  `x:FactoryMethod`가 지정되지 않은 경우 정보를 개체의 모든 공용 생성자 오버로드 집합과 비교할 수 있습니다.  XAML 처리 논리는 매개 변수 수를 비교하고 일치하는 인자 수를 사용하여 오버로드를 선택합니다.  둘 이상의 일치가 있는 경우 XAML 프로세서는 제공된 프로젝트 요소의 XAML 형식을 기반으로 매개 변수 형식을 비교해야 합니다.  여전히 둘 이상 일치하는 경우 XAML 프로세서 동작이 정의되지 않습니다.  `x:FactoryMethod`가 지정되었으나 메서드를 확인할 수 없으면 XAML 프로세서는 예외를 throw해야 합니다.  
  
 XAML 특성 사용 `<x:Arguments>string</x:Arguments>`는 기술적으로 가능 합니다.  그러나 여기서는 초기화 텍스트 및 형식 컨버터를 통해 수행할 수 있는 범위를 넘어서는 기능은 제공하지 않으며, 이 구문을 사용하는 것은 XAML 2009 팩터리 메서드 기능의 디자인을 위한 용도가 아닙니다.  
  
## 예제  
 다음 예제에서는 기본이 아닌 생성자 서명을 보여준 다음 이 서명에 액세스하는 `x:Arguments`의 XAML 사용법에 대해 보여줍니다.  
  
```csharp  
public class Food {  
    private string _name;  
    private Int32 _calories;  
    public Food(string name, Int32 calories) {  
        _name=name;  
        _calories=calories;  
    }  
}  
```  
  
```  
<my:Food>  
    <x:Arguments>  
        <x:String>Apple</x:String>  
        <x:Int32>150</x:Int32>  
    </x:Arguments>  
</my:Food>  
```  
  
 다음 예제에서는 대상 팩터리 메서드 서명을 표시한 후 해당 서명에 액세스하는 `x:Arguments`의 XAML 사용에 대해 표시합니다.  
  
```csharp  
public Food TryLookupFood(string name)  
{  
  switch (name) {  
    case "Apple": return new Food("Apple",150);  
    case "Chocolate": return new Food("Chocolate",200);  
    case "Cheese": return new Food("Cheese", 450);  
    default: {return new Food(name,0);  
  }  
}  
```  
  
```  
<my:Food x:FactoryMethod="TryLookupFood">  
    <x:Arguments>  
        <x:String>Apple</x:String>  
    </x:Arguments>  
</my:Food>  
```  
  
## 참고 항목  
 [Defining Custom Types for Use with .NET Framework XAML Services](../../../docs/framework/xaml-services/defining-custom-types-for-use-with-net-framework-xaml-services.md)   
 [XAML 개요\(WPF\)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)