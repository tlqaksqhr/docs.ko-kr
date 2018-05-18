---
title: '&lt; 연산자(C# 참조)'
ms.date: 07/20/2015
f1_keywords:
- <_CSharpKeyword
helpviewer_keywords:
- less than operator (<) [C#]
- < operator [C#]
ms.assetid: 38cb91e6-79a6-48ec-9c1e-7b71fd8d2b41
ms.openlocfilehash: eceb6214e4e625aa71e12788d5dd5e8324c75443
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="lt-operator-c-reference"></a>&lt; 연산자(C# 참조)
모든 숫자 형식과 열거형은 첫 번째 피연산자가 두 번째 피연산자보다 작으면 `true`를 반환하고 그렇지 않으면 `false`를 반환하는 “보다 작음” 관계 연산자(`<`)를 정의합니다.  
  
## <a name="remarks"></a>설명  
 사용자 정의 형식은 `<` 연산자를 오버로드할 수 있습니다([operator](../../../csharp/language-reference/keywords/operator.md) 참조). `<` 연산자가 오버로드되면 [>](../../../csharp/language-reference/operators/greater-than-operator.md) 또한 오버로드되어야 합니다. 이항 연산자가 오버로드되면 해당 대입 연산자도 암시적으로 오버로드됩니다.  
  
## <a name="example"></a>예  
 [!code-csharp[csRefOperators#24](../../../csharp/language-reference/operators/codesnippet/CSharp/less-than-operator_1.cs)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [C# 연산자](../../../csharp/language-reference/operators/index.md)
