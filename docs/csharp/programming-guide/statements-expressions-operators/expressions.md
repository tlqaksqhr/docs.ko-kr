---
title: "식(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "C# 언어, 식"
  - "식[C#]"
ms.assetid: c7d8feb0-0e58-4f94-8bf6-4d070550a832
caps.latest.revision: 22
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 22
---
# 식(C# 프로그래밍 가이드)
*식*은 단일 값, 개체, 메서드 또는 네임스페이스로 계산할 수 있는 하나 이상의 피연산자와 0개 이상의 연산자로 구성된 시퀀스입니다.  식은 리터럴 값, 메서드 호출, 연산자와 피연산자 또는 *단순한 이름*으로 구성될 수 있습니다.  단순한 이름은, 변수, 형식 멤버, 메서드 매개 변수, 네임스페이스 또는 형식의 이름일 수 있습니다.  
  
 식에는 다른 식을 매개 변수로 사용하는 연산자나 해당 매개 변수가 다른 메서드 호출로 사용되는 메서드 호출을 사용할 수 있으므로 식은 간단한 것부터 매우 복잡한 것까지 그 형식이 다양할 수 있습니다.  다음은 식에 대한 두 가지 예입니다.  
  
```  
((x < 10) && ( x > 5)) || ((x > 20) && (x < 25))   
System.Convert.ToInt32("35")  
```  
  
## 식 값  
 문 또는 메서드 매개 변수와 같이 식이 사용되는 대부분의 컨텍스트에서 식은 특정 값으로 계산될 것으로 예상됩니다.  x와 y가 정수이면 식 `x + y`는 숫자 값으로 계산됩니다.  식 `new MyClass()`는 `MyClass` 개체의 새 인스턴스에 대한 참조로 계산됩니다.  식 `myClass.ToString()`은 메서드의 반환 형식인 문자열로 계산됩니다.  그러나 네임스페이스 이름은 식으로 분류되지만 값으로 계산되지 않으므로 식의 최종 결과가 될 수 없습니다.  네임스페이스 이름을 메서드 매개 변수에 전달하거나 새 식에 사용하거나 변수에 할당할 수 없습니다.  네임스페이스 이름은 더 큰 식의 하위 식으로만 사용할 수 있습니다.  형식\(<xref:System.Type?displayProperty=fullName> 개체와 다름\), 메서드 그룹 이름\(특정 메서드와 다름\) 및 이벤트 [add](../../../csharp/language-reference/keywords/add.md)와 [remove](../../../csharp/language-reference/keywords/remove.md) 접근자의 경우도 이와 동일합니다.  
  
 모든 값에는 연결된 형식이 있습니다.  예를 들어 x와 y가 모두 `int` 형식의 변수이면 식 `x + y`의 값도 `int` 형식이 됩니다.  값이 다른 형식의 변수에 할당되거나 x와 y가 다른 형식이면 형식 변환 규칙이 적용됩니다.  변환이 수행되는 방법에 대한 자세한 내용은 [캐스팅 및 형식 변환\(C\#\)](../../../csharp/programming-guide/types/casting-and-type-conversions.md)을 참조하십시오.  
  
## 오버플로  
 값이 값 형식의 최대값보다 큰 경우 숫자 식에서 오버플로가 발생합니다.  자세한 내용은 [Checked 및 Unchecked](../../../csharp/language-reference/keywords/checked-and-unchecked.md) 및 [명시적 숫자 변환 표](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)을 참조하십시오.  
  
## 연산자 우선 순위 및 결합성  
 식이 계산되는 방식은 결합성 규칙 및 연산자 우선 순위에 의해 결정됩니다.  자세한 내용은 [연산자](../../../csharp/programming-guide/statements-expressions-operators/operators.md)를 참조하십시오.  
  
 할당 식과 메서드 호출 식을 제외한 대부분의 식은 문에 포함되어야 합니다.  자세한 내용은 [문](../../../csharp/programming-guide/statements-expressions-operators/statements.md)를 참조하십시오.  
  
## 리터럴 및 단순한 이름  
 식에서 가장 간단한 두 가지 형식은 리터럴과 단순한 이름입니다.  리터럴은 이름이 없는 상수 값입니다.  예를 들어 다음 코드 예제에서 `5`와 `"Hello World"`는 모두 리터럴 값입니다.  
  
 [!code-cs[csProgGuideStatements#2](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/expressions_1.cs)]  
  
 리터럴에 대한 자세한 내용은 [형식](../../../csharp/language-reference/keywords/types.md)을 참조하십시오.  
  
 앞의 예제에서 `i`와 `s`는 모두 지역 변수를 식별하는 단순한 이름입니다.  이러한 변수가 식에서 사용될 때 변수 이름은 현재 메모리의 변수 위치에 저장되어 있는 값으로 계산됩니다.  다음 예제에서 이를 확인할 수 있습니다.  
  
 [!code-cs[csProgGuideStatements#3](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/expressions_2.cs)]  
  
## 호출 식  
 다음 코드 예제에서 `DoWork`에 대한 호출이 호출 식입니다.  
  
```  
DoWork();  
```  
  
 메서드 호출에는 메서드의 이름\(이전 예제의 이름 또는 다른 식의 결과\) 뒤에 괄호 및 메서드 매개 변수가 필요합니다.  자세한 내용은 [메서드](../../../csharp/programming-guide/classes-and-structs/methods.md)를 참조하십시오.  대리자 호출에서는 대리자 이름과 메서드 매개 변수를 괄호 안에 사용합니다.  자세한 내용은 [대리자](../../../csharp/programming-guide/delegates/index.md)를 참조하십시오.  메서드 호출 및 대리자 호출의 결과 값은 메서드가 값을 반환하는 경우 해당 반환 값입니다.  void를 반환하는 메서드는 식에서 값 대신 사용할 수 없습니다.  
  
## 쿼리 식  
 일반적으로 식에 대한 동일한 규칙이 쿼리 식에 적용됩니다.  자세한 내용은 [LINQ 쿼리 식](../../../csharp/programming-guide/linq-query-expressions/index.md)을 참조하십시오.  
  
## 람다 식  
 람다 식은 이름이 없지만 입력 매개 변수와 여러 문을 포함할 수 있는 "인라인 메서드"를 나타냅니다.  LINQ에서 람다 식을 광범위하게 사용하여 인수를 메서드에 전달합니다.  람다 식은 사용 중인 컨텍스트에 따라 대리자 또는 식 트리로 컴파일됩니다.  자세한 내용은 [람다 식](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)을 참조하십시오.  
  
## 식 트리  
 식 트리에서는 식을 데이터 구조로 나타낼 수 있습니다.  식 트리는 LINQ 제공자에 의해 광범위하게 사용되어 SQL 데이터베이스와 같은 다른 컨텍스트에서 의미가 있는 코드로 쿼리 식을 변환합니다.  자세한 내용은 [식 트리](../Topic/Expression%20Trees%20\(C%23%20and%20Visual%20Basic\).md)를 참조하십시오.  
  
## 설명  
 식에서 변수, 개체 속성 또는 개체 인덱서에 액세스하면 해당 항목의 값이 식의 값으로 사용됩니다.  식의 최종 계산 결과가 필요한 형식이면 C\#에서 값이나 개체가 필요한 모든 위치에 식을 사용할 수 있습니다.  
  
## 중요 설명서 장  
 [변수 및 식을](란?LinkId%20=%20221228) 에서 [처음 Visual C\# 2010](란?LinkId%20=%20221214)  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [메서드](../../../csharp/programming-guide/classes-and-structs/methods.md)   
 [대리자](../../../csharp/programming-guide/delegates/index.md)   
 [연산자](../../../csharp/programming-guide/statements-expressions-operators/operators.md)   
 [형식](../../../csharp/programming-guide/types/index.md)   
 [LINQ 쿼리 식](../../../csharp/programming-guide/linq-query-expressions/index.md)