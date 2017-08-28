---
title: "형식 매개 변수에 대한 제약 조건(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- generics [C#], type constraints
- type constraints [C#]
- type parameters [C#], constraints
- unbound type parameter [C#]
ms.assetid: 141b003e-1ddb-4e1c-bcb2-e1c3870e6a51
caps.latest.revision: 41
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: e91ae026bd89a6dd30b4c9233da4dd897928291e
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="constraints-on-type-parameters-c-programming-guide"></a>형식 매개 변수에 대한 제약 조건(C# 프로그래밍 가이드)
제네릭 클래스를 정의하는 경우 클라이언트 코드에서 클래스를 인스턴스화할 때 형식 인수에 사용할 수 있는 형식 종류에 제한을 적용할 수 있습니다. 클라이언트 코드에서 제약 조건에 의해 허용되지 않는 형식을 사용하여 클래스를 인스턴스화하려고 하면 컴파일 시간 오류가 발생합니다. 이러한 제한을 제약 조건이라고 합니다. 제약 조건은 `where` 상황별 키워드를 사용하여 지정됩니다. 다음 표에는 6가지 유형의 제약 조건이 나와 있습니다.  
  
|제약 조건|설명|  
|----------------|-----------------|  
|where T : struct|형식 인수는 값 형식이어야 합니다. <xref:System.Nullable>를 제외한 임의의 값 형식을 지정할 수 있습니다. 자세한 내용은 [Nullable 형식 사용](../../../csharp/programming-guide/nullable-types/using-nullable-types.md)을 참조하세요.|  
|where T : class|형식 인수가 참조 형식이어야 합니다. 이 제약 조건은 클래스, 인터페이스, 대리자 또는 배열 형식에도 적용됩니다.|  
|where T : new()|형식 인수에 매개 변수가 없는 public 생성자가 있어야 합니다. 다른 제약 조건과 함께 사용할 경우 `new()` 제약 조건을 마지막에 지정해야 합니다.|  
|where T : \<기본 클래스 이름>|형식 인수가 지정된 기본 클래스이거나 지정된 기본 클래스에서 파생되어야 합니다.|  
|where T : \<인터페이스 이름>|형식 인수가 지정된 인터페이스이거나 지정된 인터페이스를 구현해야 합니다. 여러 인터페이스 제약 조건을 지정할 수 있습니다. 제약 인터페이스가 제네릭일 수도 있습니다.|  
|where T : U|T에 대해 제공되는 형식 인수는 U에 대해 제공되는 인수이거나 이 인수에서 파생되어야 합니다.|  
  
## <a name="why-use-constraints"></a>제약 조건을 사용하는 이유  
 제네릭 목록의 항목을 검사하여 유효한지 확인하거나 다른 항목과 비교하려는 경우 컴파일러에 호출해야 하는 연산자 또는 메서드가 클라이언트 코드에서 지정될 수 있는 형식 인수에 의해 지원된다는 보장이 있어야 합니다. 제네릭 클래스 정의에 하나 이상의 제약 조건을 적용하면 이러한 보장을 얻을 수 있습니다. 예를 들어 기본 클래스 제약 조건은 이 형식의 개체나 이 형식에서 파생된 개체만 형식 인수로 사용된다고 컴파일러에 알립니다. 컴파일러에 이 보장이 있으면 해당 형식의 메서드가 제네릭 클래스에서 호출되도록 허용할 수 있습니다. 제약 조건은 상황별 키워드 `where`를 사용하여 적용됩니다. 다음 코드 예제에서는 기본 클래스 제약 조건을 적용하여 `GenericList<T>` 클래스([제네릭 소개](../../../csharp/programming-guide/generics/introduction-to-generics.md))에 추가할 수 있는 기능을 보여 줍니다.  
  
 [!code-cs[csProgGuideGenerics#11](../../../csharp/programming-guide/generics/codesnippet/CSharp/constraints-on-type-parameters_1.cs)]  
  
 제약 조건을 통해 제네릭 클래스는 `Employee.Name` 속성을 사용할 수 있습니다. T 형식의 모든 항목이 `Employee` 개체이거나 `Employee`에서 상속되는 개체임이 보장되기 때문입니다.  
  
 동일한 형식 매개 변수에 여러 개의 제약 조건을 적용할 수 있으며, 제약 조건 자체가 다음과 같이 제네릭 형식일 수 있습니다.  
  
 [!code-cs[csProgGuideGenerics#12](../../../csharp/programming-guide/generics/codesnippet/CSharp/constraints-on-type-parameters_2.cs)]  
  
 형식 매개 변수 제약을 통해 허용되는 작업 및 메서드 호출 수를 제약 형식 및 해당 상속 계층 구조의 모든 형식에서 지원하는 작업 및 메서드 호출로 늘립니다. 따라서 제네릭 클래스 또는 메서드를 디자인할 때 단순한 할당 이외의 작업을 제네릭 멤버에 대해 수행하거나 `System.Object`에서 지원되지 않는 메서드를 호출하는 경우 형식 매개 변수에 제약 조건을 적용해야 합니다.  
  
 `where T : class` 제약 조건을 적용하는 경우 `==` 및 `!=` 연산자는 참조 ID만 테스트하고 값이 같은지 테스트하지 않으므로 형식 매개 변수에 사용하지 않도록 합니다. 이러한 연산자가 인수로 사용되는 형식에서 오버로드되는 경우에도 마찬가지입니다. 다음 코드는 이 내용을 보여 줍니다. <xref:System.String> 클래스가 `==` 연산자를 오버로드하지만 출력이 false입니다.  
  
 [!code-cs[csProgGuideGenerics#13](../../../csharp/programming-guide/generics/codesnippet/CSharp/constraints-on-type-parameters_3.cs)]  
  
 이렇게 동작하는 이유는 컴파일 시간에 컴파일러에서 T가 참조 형식이란 것만 알고 있으므로 모든 참조 형식에 유효한 기본 연산자를 사용해야 하기 때문입니다. 값이 같은지 테스트해야 하는 경우 권장되는 방법은 `where T : IComparable<T>` 제약 조건도 적용하여 제네릭 클래스를 생성하는 데 사용할 모든 클래스에서 해당 인터페이스를 구현하는 것입니다.  
  
## <a name="constraining-multiple-parameters"></a>여러 매개 변수 제약  
 다음 예제와 같이 여러 매개 변수에 제약 조건을 적용하고, 단일 매개 변수에 여러 제약 조건을 적용할 수 있습니다.  
  
 [!code-cs[csProgGuideGenerics#64](../../../csharp/programming-guide/generics/codesnippet/CSharp/constraints-on-type-parameters_4.cs)]  
  
## <a name="unbounded-type-parameters"></a>바인딩되지 않은 형식 매개 변수  
 공용 클래스 `SampleClass<T>{}`의 T와 같이 제약 조건이 없는 형식 매개 변수를 바인딩되지 않은 형식 매개 변수라고 합니다. 바인딩되지 않은 형식 매개 변수에는 다음 규칙이 있습니다.  
  
-   `!=` 및 `==` 연산자는 구체적인 형식 인수가 이러한 연산자를 지원한다는 보장이 없기 때문에 사용할 수 없습니다.  
  
-   `System.Object`로/에서 변환하거나 임의의 인터페이스 형식으로 명시적으로 변환할 수 있습니다.  
  
-   [null](../../../csharp/language-reference/keywords/null.md)과 비교할 수 있습니다. 바인딩되지 않은 매개 변수를 `null`과 비교하는 경우 형식 인수가 값 형식이면 비교에서 항상 false를 반환합니다.  
  
## <a name="type-parameters-as-constraints"></a>제약 조건인 형식 매개 변수  
 다음 예제와 같이 고유한 형식 매개 변수가 있는 멤버 함수가 해당 매개 변수를 포함 형식의 형식 매개 변수로 제약해야 하는 경우 제네릭 형식 매개 변수를 제약 조건으로 사용하면 유용합니다.  
  
 [!code-cs[csProgGuideGenerics#14](../../../csharp/programming-guide/generics/codesnippet/CSharp/constraints-on-type-parameters_5.cs)]  
  
 앞의 예제에서 `T`는 `Add` 메서드 컨텍스트에서는 형식 제약 조건이고, `List` 클래스 컨텍스트에서는 바인딩되지 않은 형식 매개 변수입니다.  
  
 제네릭 클래스 정의에서 형식 매개 변수를 제약 조건으로 사용할 수도 있습니다. 다른 형식 매개 변수와 함께 꺾쇠 괄호 안에 형식 매개 변수를 선언해야 합니다.  
  
 [!code-cs[csProgGuideGenerics#15](../../../csharp/programming-guide/generics/codesnippet/CSharp/constraints-on-type-parameters_6.cs)]  
  
 제네릭 클래스에서 형식 매개 변수를 제약 조건으로 사용할 경우 컴파일러에서 형식 매개 변수가 `System.Object`에서 파생된다는 점을 제외하고 형식 매개 변수에 대해 어떠한 정보도 알 수 없으므로 유용성이 매우 제한됩니다. 두 형식 매개 변수 사이의 상속 관계를 적용하려는 시나리오에서 제네릭 클래스에 형식 매개 변수를 제약 조건으로 사용합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Collections.Generic>   
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [제네릭 소개](../../../csharp/programming-guide/generics/introduction-to-generics.md)   
 [제네릭 클래스](../../../csharp/programming-guide/generics/generic-classes.md)   
 [new 제약 조건](../../../csharp/language-reference/keywords/new-constraint.md)

