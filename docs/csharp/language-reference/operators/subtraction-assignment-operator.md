---
title: -= 연산자(C# 참조)
ms.date: 07/20/2015
f1_keywords:
- -=_CSharpKeyword
helpviewer_keywords:
- subtraction assignment operator (-=) [C#]
- -= operator (subtraction assignment ) [C#]
ms.assetid: 05c7d68a-423f-4de8-891b-cf24e8fb6ed7
ms.openlocfilehash: 2f37bfa303fb523840b15e896ee3b4a967eb5b2b
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2018
ms.locfileid: "34171457"
---
# <a name="--operator-c-reference"></a>-= 연산자(C# 참조)
빼기 대입 연산자입니다.  
  
## <a name="remarks"></a>설명  
 다음과 같은 `-=` 대입 연산자를 사용하는 식의 경우  
  
```csharp  
x -= y  
```  
  
 위의 식은 아래의 식과 동일합니다.  
  
```csharp  
x = x - y  
```  
  
 단, `x`가 한 번만 계산됩니다. [- 연산자](../../../csharp/language-reference/operators/subtraction-operator.md)의 의미는 `x` 및 `y`에 따라 달라집니다(숫자 피연산자의 경우 빼기, 대리자 피연산자의 경우 대리자 제거 등).  
  
 `-=` 연산자를 직접 오버로드할 수는 없지만 사용자 정의 형식은 [- 연산자](../../../csharp/language-reference/operators/subtraction-operator.md)를 오버로드할 수 있습니다([연산자](../../../csharp/language-reference/keywords/operator.md) 참조).  
  
 또한 -= 연산자는 C#에서 이벤트 구독을 취소하는 데 사용됩니다. 자세한 내용은 [방법: 이벤트 구독 및 구독 취소](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)를 참조하세요.  
  
## <a name="example"></a>예  
 [!code-csharp[csRefOperators#6](codesnippet/CSharp/subtraction-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [C# 연산자](../../../csharp/language-reference/operators/index.md)
