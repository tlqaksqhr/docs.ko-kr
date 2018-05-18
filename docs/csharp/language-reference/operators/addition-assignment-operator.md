---
title: += 연산자(C# 참조)
ms.date: 07/20/2015
f1_keywords:
- +=_CSharpKeyword
helpviewer_keywords:
- += operator [C#]
- addition assignment operator (+=) [C#]
ms.assetid: 9cdf97e6-331d-492b-85e1-3ec3171484e9
ms.openlocfilehash: 90967dcdccfb71995ac83e0dd52ea7bd86f136be
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="-operator-c-reference"></a>+= 연산자(C# 참조)
더하기 대입 연산자.  
  
## <a name="remarks"></a>설명  
 다음과 같은 `+=` 대입 연산자를 사용하는 식의 경우  
  
```  
x += y  
```  
  
 위의 식은 아래의 식과 동일합니다.  
  
```  
x = x + y  
```  
  
 단, `x`가 한 번만 계산됩니다. [+ 연산자](../../../csharp/language-reference/operators/addition-operator.md)의 의미는 `x`와 `y`의 형식에 따라 달라집니다(숫자 피연산자의 경우 더하기, 문자열 피연산자의 경우 연결 등).  
  
 `+=` 연산자를 직접 오버로드할 수는 없지만 사용자 정의 형식은 [+ 연산자](../../../csharp/language-reference/operators/addition-operator.md)를 오버로드할 수 있습니다([operator](../../../csharp/language-reference/keywords/operator.md) 참조).  
  
 `+=` 연산자는 이벤트에 대한 응답으로 호출될 메서드를 지정하는 데에도 사용됩니다. 이러한 메서드를 이벤트 처리기라고 합니다. 이 컨텍스트에서 `+=` 연산자를 사용하는 것을 *이벤트 구독*이라고 합니다. 자세한 내용은 [방법: 이벤트 구독 및 구독 취소](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md) 및 [대리자](../../../csharp/programming-guide/delegates/index.md)를 참조하세요.  
  
## <a name="example"></a>예  
 [!code-csharp[csRefOperators#35](../../../csharp/language-reference/operators/codesnippet/CSharp/addition-assignment-operator_1.cs)]  
  
## <a name="see-also"></a>참고 항목  
 [C# 참조](../../../csharp/language-reference/index.md)  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)  
 [C# 연산자](../../../csharp/language-reference/operators/index.md)
