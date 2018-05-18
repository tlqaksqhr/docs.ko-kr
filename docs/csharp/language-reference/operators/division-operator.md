---
title: / 연산자(C# 참조)
ms.date: 04/04/2018
f1_keywords:
- /_CSharpKeyword
helpviewer_keywords:
- / operator [C#]
- division operator [C#]
ms.assetid: d155e496-678f-4efa-bebe-2bd08da2c5af
ms.openlocfilehash: 9d0bbff1fd9f4ab3c93c879d12ccd5fde1187b44
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="-operator-c-reference"></a>/ 연산자(C# 참조)
나누기 연산자(`/`)는 두 번째 피연산자로 첫 번째 피연산자를 나눕니다. 모든 숫자 형식에는 미리 정의된 나누기 연산자가 있습니다.
  
## <a name="remarks"></a>설명  
 사용자 정의 형식은 `/` 연산자를 오버로드할 수 있습니다([operator](../../../csharp/language-reference/keywords/operator.md) 참조). `/` 연산자를 오버로드하면 [/= 연산자](division-assignment-operator.md)를 암시적으로 오버로드합니다.  
  
 두 정수를 나누면 결과는 항상 정수입니다. 예를 들어 7 / 3의 결과는 2입니다. 이는 `/` 연산자가 0으로 반올림되므로(-7/3=-2) 정수 나누기와 혼동하지 않기 위한 것입니다.  
  
 몫을 유리수로 구하려면 `float`, `double` 또는 `decimal` 형식을 사용합니다. [기본 제공 숫자 형식](../../../csharp/language-reference/keywords/reference-tables-for-types.md) 간에 변환하는 여러 가지 방법이 있습니다.  
  
 나머지를 확인하려면 [나머지 연산자](../../../csharp/language-reference/operators/remainder-operator.md) `%`를 사용합니다.  
  
## <a name="example"></a>예  
 [!code-csharp[csRefOperators#42](../../../csharp/language-reference/operators/codesnippet/CSharp/division-operator_1.cs)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [C# 연산자](../../../csharp/language-reference/operators/index.md)
