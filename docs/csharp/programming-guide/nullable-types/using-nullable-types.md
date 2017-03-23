---
title: "Nullable 형식 사용(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "nullable 형식[C#], nullable 형식 정보"
ms.assetid: 0bacbe72-ce15-4b14-83e1-9c14e6380c28
caps.latest.revision: 31
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 31
---
# Nullable 형식 사용(C# 프로그래밍 가이드)
nullable 형식을 사용하면 내부 형식의 값을 모두 나타낼 수 있을 뿐만 아니라 [null](../../../csharp/language-reference/keywords/null.md) 값을 추가로 나타낼 수 있습니다.  nullable 형식은 다음과 같은 두 가지 방법 중 하나로 선언됩니다.  
  
 `System.Nullable<T> variable`  
  
 또는  
  
 `T?  variable`  
  
 `T`는 nullable 형식의 기본 형식입니다.  `T`는 `struct`를 포함한 모든 값 형식이 될 수 있으며 참조 형식은 될 수 없습니다.  
  
 nullable 형식이 필요한 경우를 예로 들면, true와 false라는 두 가지 값만 갖는 일반적인 부울 변수를 생각해 볼 수 있습니다.  이런 변수에는 "정의되지 않은 상태"를 의미하는 값이 없습니다.  여러 프로그래밍 응용 프로그램에서 변수는 정의되지 않은 상태로 나타날 수 있으며, 데이터베이스 상호 작용이 가장 대표적인 예입니다.  예를 들어, 데이터베이스의 필드는 true나 false 값을 포함할 수 있지만 값을 전혀 포함하지 않을 수 있습니다.  마찬가지로, 참조 형식이 초기화되지 않았음을 나타내기 위해 이를 `null`로 설정할 수 있습니다.  
  
 이러한 차이를 처리하기 위해서는 상태 정보를 저장하기 위한 추가 변수 사용, 특수 값 사용 등 별도의 프로그래밍 작업이 필요할 수 있습니다.  C\#에서 nullable 형식 한정자를 사용하면 정의되지 않은 값을 나타내는 값 형식 변수를 만들 수 있습니다.  
  
## nullable 형식의 예제  
 nullable 형식의 기준으로는 모든 값 형식을 사용할 수 있습니다.  예를 들면 다음과 같습니다.  
  
 [!code-cs[csProgGuideTypes#4](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_1.cs)]  
  
## nullable 형식의 멤버  
 nullable 형식의 각 인스턴스에는 읽기 전용인 공용 속성이 두 개 있습니다.  
  
-   `HasValue`  
  
     `HasValue`는 `bool` 형식이며,  변수에 null이 아닌 값이 포함되어 있으면 `true`로 설정됩니다.  
  
-   `Value`  
  
     `Value`는 내부 형식과 동일한 형식입니다.  `HasValue`가 `true`이면 `Value`에는 의미 있는 값이 포함됩니다.  `HasValue`가 `false`인 경우에 `Value`에 액세스하려고 하면 <xref:System.InvalidOperationException>이 throw됩니다.  
  
 이 예제에서는 변수의 값을 표시하기 전에 `HasValue` 멤버를 사용하여 변수에 값이 포함되어 있는지 테스트합니다.  
  
 [!code-cs[csProgGuideTypes#5](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_2.cs)]  
  
 값은 다음 예제와 같은 방법으로도 테스트할 수 있습니다.  
  
 [!code-cs[csProgGuideTypes#6](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_3.cs)]  
  
## 명시적 변환  
 nullable 형식은 `Value` 속성을 사용하거나 명시적으로 캐스팅하여 일반 형식으로 캐스팅할 수 있습니다.  예를 들면 다음과 같습니다.  
  
 [!code-cs[csProgGuideTypes#7](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_4.cs)]  
  
 두 데이터 형식 사이에 사용자 정의 변환이 정의되어 있는 경우에는 이러한 데이터 형식의 null 허용 버전에 대해서도 동일한 변환을 사용할 수 있습니다.  
  
## 암시적 변환  
 nullable 형식의 변수는 다음 예제와 같이 `null` 키워드를 사용하여 null로 설정할 수 있습니다.  
  
 [!code-cs[csProgGuideTypes#8](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_5.cs)]  
  
 일반 형식에서 nullable 형식으로의 변환은 암시적입니다.  
  
 [!code-cs[csProgGuideTypes#9](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_6.cs)]  
  
## 연산자  
 값 형식에 사용되는 미리 정의된 단항 및 이항 연산자와 모든 사용자 정의 연산자는 nullable 형식에도 사용할 수 있습니다.  피연산자가 null이면 이러한 연산자는 null 값을 생성합니다. 그렇지 않으면 연산자는 포함된 값을 사용하여 결과를 계산합니다.  예를 들면 다음과 같습니다.  
  
 [!code-cs[csProgGuideTypes#10](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_7.cs)]  
  
 nullable 형식과 비교를 수행하는 경우 nullable 형식 중 하나의 값이 null이고 다른 값이 null이 아니면 `!=`\(같지 않음\)을 제외하고 모든 비교 결과가 `false`입니다.  특정 비교에서 `false`를 반환한다고 해서 그 반대 경우가 `true`를 반환한다고 가정할 수는 없습니다.  다음 예제에서 10은 null보다 크지도, 작지도, 같지도 않습니다.  `num1 != num2`만 `true`입니다.  
  
 [!code-cs[csProgGuideTypes#11](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_8.cs)]  
  
 둘 다 null인 두 nullable 형식의 같음 비교는 `true`입니다.  
  
## ??Operator  
 `??` 연산자는 null이 허용되지 않는 형식에 nullable 형식을 대입할 때 반환되는 기본값을 정의합니다.  
  
 [!code-cs[csProgGuideTypes#12](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_9.cs)]  
  
 이 연산자는 여러 개의 nullable 형식과 함께 사용할 수도 있습니다.  예를 들면 다음과 같습니다.  
  
 [!code-cs[csProgGuideTypes#13](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/using-nullable-types_10.cs)]  
  
## bool?type  
 `bool?` nullable 형식에는 [true](../../../csharp/language-reference/keywords/true.md), [false](../../../csharp/language-reference/keywords/false.md) 및 [null](../../../csharp/language-reference/keywords/null.md)의 세 가지 값이 포함될 수 있습니다.  bool?에서 bool로 캐스팅하는 방법에 대한 자세한 내용은  [방법: bool?에서 bool로 안전하게 캐스팅](../../../csharp/programming-guide/nullable-types/how-to-safely-cast-from-bool-to-bool.md)을 참조하십시오.  
  
 nullable 부울은 SQL에 사용되는 부울 변수 형식과 비슷합니다.  `&`에 의해 생성되는 결과를 보장하려면  `|` 연산자가 값이 세 개인 SQL 부울 형식과 일관성을 유지할 수 있도록 다음과 같은 미리 정의된 연산자가 제공됩니다.  
  
 `bool?  operator &(bool?  x, bool?  y)`  
  
 `bool?  operator |(bool?  x, bool?  y)`  
  
 다음 표에서는 이러한 연산자의 결과를 보여 줍니다.  
  
|X|y|x&y|x&#124;y|  
|-------|-------|---------|--------------|  
|true|true|true|true|  
|true|false|false|true|  
|true|null|null|true|  
|false|true|false|true|  
|false|false|false|false|  
|false|null|false|null|  
|null|true|null|true|  
|null|false|false|null|  
|null|null|null|null|  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [nullable 형식](../../../csharp/programming-guide/nullable-types/index.md)   
 [Nullable 형식 boxing](../../../csharp/programming-guide/nullable-types/boxing-nullable-types.md)   
 [Nullable Value Types](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)