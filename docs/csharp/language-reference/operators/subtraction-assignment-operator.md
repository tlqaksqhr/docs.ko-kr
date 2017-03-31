---
title: "-= 연산자(C# 참조) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- -=_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- subtraction assignment operator (-=) [C#]
- -= operator (subtraction assignment ) [C#]
ms.assetid: 05c7d68a-423f-4de8-891b-cf24e8fb6ed7
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: d9ffcfe9b42f7ca65801a58338c8e40a37c90316
ms.lasthandoff: 03/13/2017

---
# <a name="--operator-c-reference"></a>-= 연산자(C# 참조)
빼기 대입 연산자입니다.  
  
## <a name="remarks"></a>주의  
 다음과 같은 `-=` 대입 연산자를 사용하는 식의 경우  
  
```  
x -= y  
```  
  
 위의 식은 아래의 식과 동일합니다.  
  
```  
x = x - y  
```  
  
 단, `x`가 한 번만 계산됩니다. [- 연산자](../../../csharp/language-reference/operators/subtraction-operator.md)의 의미는 `x` 및 `y`에 따라 달라집니다(숫자 피연산자의 경우 빼기, 대리자 피연산자의 경우 대리자 제거 등).  
  
 `-=` 연산자를 직접 오버로드할 수는 없지만 사용자 정의 형식은 [- 연산자](../../../csharp/language-reference/operators/subtraction-operator.md)를 오버로드할 수 있습니다([연산자](../../../csharp/language-reference/keywords/operator.md) 참조).  
  
 또한 -= 연산자는 C#에서 이벤트 구독을 취소하는 데 사용됩니다. 자세한 내용은 [방법: 이벤트 구독 및 구독 취소](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)를 참조하세요.  
  
## <a name="example"></a>예제  
 [!code-cs[csRefOperators#6](codesnippet/CSharp/subtraction-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)   
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C# 연산자](../../../csharp/language-reference/operators/index.md)

