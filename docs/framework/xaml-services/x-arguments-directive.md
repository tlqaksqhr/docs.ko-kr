---
title: x:Arguments 지시문
ms.date: 03/30/2017
helpviewer_keywords:
- x:Arguments directive [XAML Services]
- Arguments directive in XAML [XAML Services]
- XAML [XAML Services], x:Arguments directive
ms.assetid: 87cc10b0-b610-4025-b6b0-ab27ca27c92e
ms.openlocfilehash: e0e7f380ec176e80d2422878a2e676d64985d660
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33564880"
---
# <a name="xarguments-directive"></a>x:Arguments 지시문
패키지 생성 인수 XAML에서 기본값이 아닌 생성자 개체 요소 선언에 대 한 또는 팩터리 메서드 개체 선언에 대 한 합니다.  
  
## <a name="xaml-element-usage-nondefault-constructor"></a>XAML 요소 사용 (기본이 아닌 생성자)  
  
```  
<object ...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-element-usage-factory-method"></a>XAML 요소 사용 (factory method)  
  
```  
<object x:FactoryMethod="methodName"...>  
  <x:Arguments>  
    oneOrMoreObjectElements  
  </x:Arguments>  
</object>  
```  
  
## <a name="xaml-values"></a>XAML 값  
  
|||  
|-|-|  
|`oneOrMoreObjectElements`|백업 기본이 아닌 생성자 또는 팩터리 메서드에 전달 될 인수를 지정 하는 하나 이상의 개체 요소입니다.<br /><br /> 일반적인 사용법 실제 인수 값을 지정 하려면 개체 요소 내의 초기화 텍스트를 사용 하는 것입니다. 예 섹션을 참조 하십시오.<br /><br /> 요소의 순서는 중요 합니다. 순서로 XAML 형식과 형식과 일치 하 고 지원 생성자 또는 팩터리 메서드 오버 로드의 순서를 입력 해야 합니다.|  
|`methodName`|처리 해야 하는 팩터리 메서드 이름 `x:Arguments` 인수입니다.|  
  
## <a name="dependencies"></a>종속성  
 `x:FactoryMethod` 범위 및 동작을 수정할 수 있는 `x:Arguments` 적용 됩니다.  
  
 없는 경우 `x:FactoryMethod` 지정 된 `x:Arguments` 지원 생성자의 대체 (비기본) 시그니처에 적용 됩니다.  
  
 경우 `x:FactoryMethod` 지정 된 `x:Arguments` 명명 된 메서드의 오버 로드에 적용 됩니다.  
  
## <a name="remarks"></a>설명  
 XAML 2006 기본이 아닌 초기화 초기화 텍스트를 통해 지원할 수 있습니다. 하지만 실용적인 응용 프로그램의 초기화 텍스트 생성 방법이 제한 됩니다. 초기화 텍스트를 단일 텍스트 문자열로 취급 됩니다. 따라서만 사용자 지정 정보 항목 및 사용자 지정 구분 기호 문자열에서을 구문 분석할 수 있는 구성 동작에 대 한 형식 변환기를 정의 하지 않으면 단일 매개 변수 초기화에 대 한 기능을 추가 합니다. 또한 개체 논리에 텍스트 문자열은 잠재적으로 실제 문자열 이외의 기본 형식을 처리 하기 위한 특정된 XAML 파서에 네이티브 기본 형식 변환기입니다.  
  
 `x:Arguments` 지시문 태그가 포함 된 개체 요소 형식을 참조 하지 않기 때문에 XAML 사용은 일반적으로 속성 요소 사용 되지 않습니다. 와 같은 기타 지시문과 더 비슷합니다는 `x:Code` 요소는 자식 내용에 대 한 기본값 이외의 다른 태그를 해석 하는 범위 기본값과입니다. 각 개체 요소의 XAML 형식을 특정 생성자 팩터리 메서드 서명을 확인 하려면 XAML 파서가에 사용 되는 인수 형식에 대 한 정보를 전달 하는 경우에 `x:Arguments` 사용은 참조 하려고 합니다.  
  
 `x:Arguments` 개체 요소에 대해 생성 되 고 앞에 야 다른 속성 요소, 콘텐츠, 내부 텍스트 또는 object 요소의 초기화 문자열입니다. 내에서 개체 요소 `x:Arguments` XAML 형식 및 해당 지원 생성자 또는 팩터리 메서드에에 허용 된 대로 특성 및 초기화 문자열을 포함할 수 있습니다. 개체 또는 인수에 대 한 사용자 지정 XAML 형식 또는 벗어나는 기본 XAML 네임 스페이스 설정 된 접두사 매핑을 참조 하 여 XAML 형식을 지정할 수 있습니다.  
  
 인수에 지정 하는 방법을 확인 하려면 다음 지침을 사용 하는 XAML 프로세서 `x:Arguments` 개체를 생성 하는 데 사용 해야 합니다. 경우 `x:FactoryMethod` 정보를 비교 하는 지정 된 지정 된 `x:FactoryMethod` (사항에 유의 값 `x:FactoryMethod` 메서드 이름 및 명명 된 메서드 오버 로드를 가질 수 있습니다. 경우 `x:FactoryMethod` 를 지정 하지 않으면 정보 개체의 모든 public 생성자 오버 로드 집합이 비교 합니다. 다음 XAML 처리 논리 매개 변수 개수를 비교 하 고 일치 하는 인자 수를 갖는 오버 로드를 선택 합니다. 둘 이상의 일치 하는 XAML 프로세서는 유형의 제공 된 개체 요소의 XAML 유형을 기반으로 하는 매개 변수를 비교 해야 합니다. 여전히 둘 이상의 일치 하는 XAML 프로세서 동작이 정의 되지 않습니다. 경우는 `x:FactoryMethod` 지정는 메서드를 확인할 수 있지만, XAML 프로세서에서 예외를 throw 해야 합니다.  
  
 XAML 특성 사용 `<x:Arguments>string</x:Arguments>` 은 기술적으로 가능 합니다. 그러나 그렇지 않은 경우 초기화 텍스트 및 형식 변환기를 통해 수행할 수 초과 기능은 제공 하 고이 구문을 사용 하 여는 XAML 2009 팩터리 메서드 기능의 디자인 의도 되지 않습니다.  
  
## <a name="examples"></a>예제  
 다음 예제에서는 시그니처를 다음의 XAML 사용에 기본이 아닌 생성자를 보여 줍니다 `x:Arguments` 서명에 액세스 하는 합니다.  
  
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
  
```xaml  
<my:Food>  
    <x:Arguments>  
        <x:String>Apple</x:String>  
        <x:Int32>150</x:Int32>  
    </x:Arguments>  
</my:Food>  
```  
  
 다음 예제에서는 대상 팩터리 메서드 시그니처를 다음의 XAML 사용 `x:Arguments` 서명에 액세스 하는 합니다.  
  
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
  
```xaml  
<my:Food x:FactoryMethod="TryLookupFood">  
    <x:Arguments>  
        <x:String>Apple</x:String>  
    </x:Arguments>  
</my:Food>  
```  
  
## <a name="see-also"></a>참고 항목  
 [.NET Framework XAML 서비스에서 사용할 사용자 지정 형식 정의](../../../docs/framework/xaml-services/defining-custom-types-for-use-with-net-framework-xaml-services.md)  
 [XAML 개요(WPF)](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
