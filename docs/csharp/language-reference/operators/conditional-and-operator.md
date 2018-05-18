---
title: '&amp;&amp; 연산자(C# 참조)'
ms.date: 07/20/2015
f1_keywords:
- '&&_CSharpKeyword'
helpviewer_keywords:
- '&& operator [C#]'
- logical AND operator [C#]
ms.assetid: 2e4f0a1c-92a3-40f8-8e3b-17b607f20c31
ms.openlocfilehash: 86508c6eeb2998c6f202608f9204b72b60786e4a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="ampamp-operator-c-reference"></a>&amp;&amp; 연산자(C# 참조)
조건부 AND 연산자(`&&`)는 `bool` 피연산자의 논리적 AND를 수행하지만 필요할 경우 두 번째 피연산자만 계산합니다.  
  
## <a name="remarks"></a>설명  
 이 작업은  
  
```  
x && y  
```  
  
 연산에 해당합니다.  
  
```  
x & y  
```  
  
 단, `x`가 `false`일 경우 `y`는 계산되지 않습니다. `y` 값이 무엇이든지 AND 연산의 결과는 `false`이기 때문입니다. 이것을 "단락" 계산이라고 합니다.  
  
 조건부 AND 연산자는 오버로드될 수 없지만 일반 논리 연산자와 [true](../../../csharp/language-reference/keywords/true.md) 및 [false](../../../csharp/language-reference/keywords/false.md) 연산자의 오버로드는 조건부 논리 연산자의 오버로드로 간주합니다(특정 제한 사항 있음).  
  
## <a name="example"></a>예  
 다음 예제에서는 피연산자가 `false`를 반환하므로 두 번째 `if` 문의 조건식은 첫 번째 피연산자만 계산합니다.  
  
 [!code-csharp[csRefOperators#48](../../../csharp/language-reference/operators/codesnippet/CSharp/conditional-and-operator_1.cs)]  
  
## <a name="c-language-specification"></a>C# 언어 사양  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [C# 연산자](../../../csharp/language-reference/operators/index.md)
