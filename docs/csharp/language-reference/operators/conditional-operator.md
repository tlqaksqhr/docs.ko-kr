---
title: '?: 연산자(C# 참조)'
ms.date: 07/20/2015
f1_keywords:
- ?:_CSharpKeyword
- ?_CSharpKeyword
- :_CSharpKeyword
helpviewer_keywords:
- '?: operator [C#]'
- conditional operator (?:) [C#]
ms.assetid: e83a17f1-7500-48ba-8bee-2fbc4c847af4
ms.openlocfilehash: 1bfbe5257123438751592695f23fe24aeb7ccc2b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="-operator-c-reference"></a>?: 연산자(C# 참조)
일반적으로 3개로 구성된 조건 연산자로 알려진 조건 연산자(`?:`)는 부울 식의 값에 따라 두 값 중 하나를 반환합니다. 다음은 조건 연산자의 구문입니다.  
  
```  
condition ? first_expression : second_expression;  
```  
  
## <a name="remarks"></a>설명  
 `condition`은 `true` 또는 `false`이어야 합니다. `condition`이 `true`인 경우 `first_expression`이 평가되고 결과가 됩니다. `condition`이 `false`인 경우 `second_expression`이 평가되고 결과가 됩니다. 두 식 중 하나만 계산됩니다.  
  
 `first_expression` 및 `second_expression`의 형식이 동일하거나 한 형식에서 다른 형식으로 암시적 변환이 있어야 합니다.  
  
 조건 연산자를 사용하면 `if-else` 구성이 필요할 수 있는 계산을 더 간결하게 표현할 수 있습니다. 예를 들어, 다음 코드는 처음에 `if` 문을 사용한 다음 조건부 연산자를 사용하여 정수를 양 또는 음으로 분류합니다.  
  
```csharp
int input = Convert.ToInt32(Console.ReadLine());  
string classify;  
  
// if-else construction.  
if (input > 0)  
    classify = "positive";  
else  
    classify = "negative";  
  
// ?: conditional operator.  
classify = (input > 0) ? "positive" : "negative";  
```  
  
 조건 연산자에는 오른쪽 결합성이 있습니다. `a ? b : c ? d : e` 식은 `a ? b : (c ? d : e)`가 아닌 `(a ? b : c) ? d : e`로 평가됩니다.  
  
 조건 연산자는 오버로드할 수 없습니다.  
  
## <a name="example"></a>예  
 [!code-csharp[csRefOperators#41](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-operator_1.cs)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [C# 연산자](../../../csharp/language-reference/operators/index.md)  
 [if-else](../../../csharp/language-reference/keywords/if-else.md)  
 [?. 및 ? 연산자](../../../csharp/language-reference/operators/null-conditional-operators.md)  
 [?? 연산자](../../../csharp/language-reference/operators/null-conditional-operator.md)
