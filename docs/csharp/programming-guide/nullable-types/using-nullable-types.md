---
title: Nullable 형식 사용(C# 프로그래밍 가이드)
ms.date: 07/20/2015
helpviewer_keywords:
- nullable types [C#], about nullable types
ms.assetid: 0bacbe72-ce15-4b14-83e1-9c14e6380c28
ms.openlocfilehash: d2fe0f34c45d3de0516a71ca5ed4dc807df4bf93
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="using-nullable-types-c-programming-guide"></a>Nullable 형식 사용(C# 프로그래밍 가이드)
nullable 형식은 기본 형식의 모든 값과 추가 [null](../../../csharp/language-reference/keywords/null.md) 값을 나타낼 수 있습니다. nullable 형식은 다음과 같은 두 가지 방법 중 하나로 선언됩니다.  
  
 `System.Nullable<T> variable`  
  
 또는  
  
 `T? variable`  
  
 `T`는 nullable 형식의 기본 형식입니다. `T`는 `struct`를 비롯한 모든 값 형식일 수 있으나, 참조 형식일 수는 없습니다.  
  
 nullable 형식을 사용할 수 있는 경우의 예를 들기 위해 일반 부울 변수가 두 가지 값 true와 false를 가질 수 있는 방법을 고려합니다. “정의되지 않음”을 의미하는 값은 없습니다. 많은 프로그래밍 응용 프로그램(특히, 데이터베이스 상호 작용)에서 변수는 정의되지 않은 상태로 발생할 수 있습니다. 예를 들어 데이터베이스의 필드는 true 또는 false 값을 포함할 수 있지만, 전혀 값을 포함하지 않을 수도 있습니다. 마찬가지로, 초기화되지 않았음을 나타내기 위해 참조 형식을 `null`로 설정할 수 있습니다.  
  
 이 차이로 인해 상태 정보, 특수 값 사용 등을 저장하는 데 사용되는 추가 변수와 관련한 추가 프로그래밍 작업이 발생할 수 있습니다. C#에서는 nullable 형식 한정자를 사용하여 정의되지 않은 값을 나타내는 값 형식 변수를 만들 수 있습니다.  
  
## <a name="examples-of-nullable-types"></a>nullable 형식의 예  
 nullable 형식에 대한 기준으로 모든 값 형식을 사용할 수 있습니다. 예:  
  
 [!code-csharp[csProgGuideTypes#4](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_1.cs)]  
  
## <a name="the-members-of-nullable-types"></a>nullable 형식의 멤버  
 nullable 형식의 각 인스턴스에는 다음과 같은 두 개의 public 읽기 전용 속성이 포함됩니다.  
  
-   `HasValue`  
  
     `HasValue`는 `bool` 형식입니다. 변수가 null이 아닌 값을 포함한 경우 `true`로 설정됩니다.  
  
-   `Value`  
  
     `Value`는 기본 형식과 같은 형식입니다. `HasValue`가 `true`이면 `Value`에는 의미 있는 값이 포함됩니다. `HasValue`가 `false`이면 `Value`에서는 <xref:System.InvalidOperationException>을 throw합니다.  
  
 이 예제에서 `HasValue` 멤버는 변수를 표시하려고 하기 전에 변수가 값을 포함하는지를 테스트하는 데 사용됩니다.  
  
 [!code-csharp[csProgGuideTypes#5](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_2.cs)]  
  
 값에 대한 테스트는 다음 예제처럼 수행할 수도 있습니다.  
  
 [!code-csharp[csProgGuideTypes#6](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_3.cs)]  
  
## <a name="explicit-conversions"></a>명시적 변환  
 nullable 형식은 캐스트를 사용하여 명시적으로 또는 `Value` 속성을 사용하여 일반 형식으로 캐스팅할 수 있습니다. 예:  
  
 [!code-csharp[csProgGuideTypes#7](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_4.cs)]  
  
 두 데이터 형식 간에 사용자 정의 변환이 정의된 경우 이러한 데이터 형식의 nullable 버전에도 같은 변환을 사용할 수 있습니다.  
  
## <a name="implicit-conversions"></a>암시적 변환  
 nullable 형식의 변수는 다음 예제와 같이 `null` 키워드를 사용하여 null로 설정할 수 있습니다.  
  
 [!code-csharp[csProgGuideTypes#8](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_5.cs)]  
  
 일반 형식에서 nullable 형식으로의 변환은 암시적입니다.  
  
 [!code-csharp[csProgGuideTypes#9](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_6.cs)]  
  
## <a name="operators"></a>연산자  
 미리 정의된 단항 및 이항 연산자와 값 형식에 대해 존재하는 모든 사용자 정의 연산자는 nullable 형식에도 사용할 수 있습니다. 이러한 연산자는 피연산자가 null인 경우 null 값을 생성하고, 그렇지 않으면 연산자는 포함된 값을 사용하여 결과를 계산합니다. 예:  
  
 [!code-csharp[csProgGuideTypes#10](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_7.cs)]  
  
 nullable 형식과의 비교를 수행할 때 nullable 형식 중 하나의 값이 null이고 나머지는 null이 아닌 경우 모든 비교는 `!=`(같지 않음)을 제외하고는 `false`로 계산됩니다. 특정 비교에서는 `false`를 반환하고 그 반대의 경우에는 `true`를 반환한다고 가정하지 않는 것이 중요합니다. 다음 예제에서 10은 null보다 크지 않고, 작지 않고, 같지도 않습니다. `num1 != num2`만 `true`로 계산됩니다.  
  
 [!code-csharp[csProgGuideTypes#11](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_8.cs)]  
  
 둘 다 null인 두 nullable 형식의 같음 비교는 `true`로 계산됩니다.  
  
## <a name="the--operator"></a>?? 연산자  
 `??` 연산자는 nullable 형식이 nullable 형식이 아닌 형식에 할당된 경우 반환되는 기본값을 정의합니다.  
  
 [!code-csharp[csProgGuideTypes#12](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_9.cs)]  
  
 이 연산자는 여러 nullable 형식에도 사용할 수 있습니다. 예:  
  
 [!code-csharp[csProgGuideTypes#13](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_10.cs)]  
  
## <a name="the-bool-type"></a>bool? 형식  
 `bool?` nullable 형식은 세 가지 값 [true](../../../csharp/language-reference/keywords/true.md), [false](../../../csharp/language-reference/keywords/false.md) 및 [null](../../../csharp/language-reference/keywords/null.md)을 포함할 수 있습니다. bool?에서 bool로 캐스팅하는 방법에 대한 자세한 내용은 [방법: bool?에서 bool로 안전하게 캐스팅](../../../csharp/programming-guide/nullable-types/how-to-safely-cast-from-bool-to-bool.md)을 참조하세요.  
  
 nullable 부울은 SQL에서 사용되는 부울 변수 형식과 유사합니다. `&` 및 `|` 연산자에 의해 생성된 결과가 SQL의 삼중값 부울 형식과 일치하도록 다음과 같은 미리 정의된 연산자가 제공됩니다.  
  
 `bool? operator &(bool? x, bool? y)`  
  
 `bool? operator |(bool? x, bool? y)`  
  
 다음 표는 이러한 연산자의 결과를 보여 줍니다.  
  
|X|y|x&y|x&#124;y|  
|-------|-------|---------|--------------|  
|true|true|true|true|  
|true|False|false|true|  
|true|null|null|true|  
|False|true|False|true|  
|False|False|False|False|  
|False|null|False|null|  
|null|true|null|true|  
|null|False|False|null|  
|null|null|null|null|  
  
## <a name="see-also"></a>참고 항목  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [Nullable 형식](../../../csharp/programming-guide/nullable-types/index.md)  
 [Nullable 형식 boxing](../../../csharp/programming-guide/nullable-types/boxing-nullable-types.md)  
 [Nullable 값 형식](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
