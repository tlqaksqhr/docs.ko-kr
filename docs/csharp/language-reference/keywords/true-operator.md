---
title: true 연산자(C# 참조)
ms.date: 07/20/2015
helpviewer_keywords:
- true operator [C#]
ms.assetid: acaba817-5da5-4364-b3b2-2e5c75ec1839
ms.openlocfilehash: 71f522b3860f7461f5c52dd77bb424f7ba0f9bf5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33275082"
---
# <a name="true-operator-c-reference"></a>true 연산자(C# 참조)
[bool](../../../csharp/language-reference/keywords/bool.md) 값 `true`를 반환하여 피연산자가 true임을 나타내고, true가 아니면 `false`를 반환합니다.  
  
 C# 2.0 이전에는 `true` 및 `false` 연산자를 사용하여 `SqlBool` 등의 형식과 호환되는 사용자 정의 nullable 값 형식을 만들었습니다. 그러나 이제 언어에서 nullable 값 형식에 대한 기본 제공 지원을 제공하며, 가능한 한 `true` 및 `false` 연산자를 오버로드하는 대신 이러한 형식을 사용해야 합니다. 자세한 내용은 [Nullable 형식](../../../csharp/programming-guide/nullable-types/index.md)을 참조하세요.  
  
 nullable 부울을 사용하는 경우 하나 또는 두 값이 모두 null일 수 있기 때문에 `a != b` 식이 `!(a == b)`와 다를 수 있습니다. 식에서 null 값을 올바르게 식별하려면 `true` 및 `false` 연산자를 별도로 둘 다 오버로드해야 합니다. 다음 예제에서는 `true` 및 `false` 연산자를 오버로드하고 사용하는 방법을 보여 줍니다.  
  
 [!code-csharp[csrefKeywordsOperator#16](../../../csharp/language-reference/keywords/codesnippet/CSharp/true-operator_1.cs)]  
  
 [if](../../../csharp/language-reference/keywords/if-else.md), [do](../../../csharp/language-reference/keywords/do.md), [while](../../../csharp/language-reference/keywords/while.md) 및 [for](../../../csharp/language-reference/keywords/for.md) 문의 제어 식과 [조건식](../../../csharp/language-reference/operators/conditional-operator.md)에서 `true` 및 `false` 연산자를 오버로드하는 형식을 사용할 수 있습니다.  
  
 형식이 `true` 연산자를 정의하는 경우 [false](../../../csharp/language-reference/keywords/false.md) 연산자도 정의해야 합니다.  
  
 형식에서 직접 조건부 논리 연산자([&&](../../../csharp/language-reference/operators/conditional-and-operator.md) 및 [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md))를 오버로드할 수는 없지만 일반 논리 연산자와 `true` 및 `false` 연산자를 오버로드하면 동일한 효과를 얻을 수 있습니다.  
  
## <a name="c-language-specification"></a>C# 언어 사양  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [C# 키워드](../../../csharp/language-reference/keywords/index.md)  
 [C# 연산자](../../../csharp/language-reference/operators/index.md)  
 [false](../../../csharp/language-reference/keywords/false.md)
