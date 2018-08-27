---
title: '|| 연산자(C# 참조)'
ms.date: 07/20/2015
f1_keywords:
- '||_CSharpKeyword'
helpviewer_keywords:
- logical OR operator [C#]
- conditional-OR operator (||) [C#]
- '|| operator [C#]'
ms.assetid: 7d442d8e-400d-421f-b4d2-034bf82bcbdc
ms.openlocfilehash: 58e5fd72a3748e7af0894093fc461c4efb543608
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/25/2018
ms.locfileid: "42925542"
---
# <a name="-operator-c-reference"></a>|| 연산자(C# 참조)
조건부 OR 연산자(`||`)는 해당 `bool` 피연산자의 논리적 OR을 수행합니다. 첫 번째 피연산자가 `true`이면 두 번째 피연산자는 계산되지 않습니다. 첫 번째 피연산자가 `false`이면 두 번째 피연산자에 의해 OR 식 전체가 `true` 또는 `false`인지가 결정됩니다.  
  
## <a name="remarks"></a>설명  
 이 작업은  
  
```csharp  
x || y  
```  
  
 연산에 해당합니다.  
  
```csharp  
x | y  
```  
  
 단, `x`가 `true`이면 `y`는 평가되지 않습니다. `y` 값과 관계없이 OR 연산이 `true`이기 때문입니다. 이 개념을 “단락” 평가라고 합니다.  
  
 조건부 OR 연산자는 오버로드될 수 없지만 일반 논리 연산자와 [true](../../../csharp/language-reference/keywords/true.md) 및 [false](../../../csharp/language-reference/keywords/false.md) 연산자의 오버로드는 조건부 논리 연산자의 오버로드로 간주합니다(특정 제한 사항 있음).  
  
## <a name="example"></a>예  
 다음 예제에서 `||`를 사용하는 식은 첫 번째 피연산자만 계산합니다. `|`를 사용하는 식은 두 피연산자를 모두 계산합니다. 두 번째 예제에서 두 피연산자가 모두 계산되면 런타임 예외가 발생합니다.  
  
 [!code-csharp[csRefOperators#52](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-or-operator_1.cs)]  
  
## <a name="see-also"></a>참고 항목

- [C# 참조](../../../csharp/language-reference/index.md)  
- [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
- [C# 연산자](../../../csharp/language-reference/operators/index.md)
