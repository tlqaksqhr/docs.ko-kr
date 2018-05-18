---
title: '% 연산자(C# 참조)'
ms.date: 04/04/2018
f1_keywords:
- '%_CSharpKeyword'
helpviewer_keywords:
- remainder operator [C#]
- '% operator [C#]'
ms.assetid: 3b74f4f9-fd9c-45e7-84fa-c8d71a0dfad7
ms.openlocfilehash: b906feb22aaec97e58da562b615baae01f3e0719
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="-operator-c-reference"></a>% 연산자(C# 참조)
나머지 연산자(`%`)는 첫 번째 피연산자를 두 번째 피연산자로 나눈 후 나머지를 계산합니다. 모든 숫자 형식에는 미리 정의된 나머지 연산자가 있습니다. 
  
## <a name="remarks"></a>설명  
 `a % b` 수식은 항상 `(-b, b)` 범위로만 값을 반환하고(`b` 또는 `-b`를 반환할 수 없음) 피제수의 부호를 유지합니다. 정수 나누기의 경우 나머지 연산자는 `a % b = a - (a / b) * b` 규칙을 충족합니다.
  
 이는 유사한 규칙을 충족하지만 정수 나누기를 사용하고 `[0, b)` 범위의 값을 반환하는 정식 모듈러스와 혼동하지 않기 위한 것입니다. C#에는 정식 모듈러스에 대한 연산자가 없습니다. 그러나 양의 피제수에 대한 동작은 동일합니다.
  
 사용자 정의 형식은 `%` 연산자를 오버로드할 수 있습니다([operator](../../../csharp/language-reference/keywords/operator.md) 참조). 이항 연산자가 오버로드되면 해당 대입 연산자도 암시적으로 오버로드됩니다.  
  
## <a name="example"></a>예  
 [!code-csharp[csRefOperators#9](../../../csharp/language-reference/operators/codesnippet/CSharp/remainder-operator_1.cs)]  
  
## <a name="comments"></a>설명  
 double 형식과 연결된 반올림 오류를 확인합니다.  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [C# 연산자](../../../csharp/language-reference/operators/index.md)
