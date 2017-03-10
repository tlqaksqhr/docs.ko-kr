---
title: "+= 연산자(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "+=_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "+= 연산자[C#]"
  - "더하기 대입 연산자(+=)[C#]"
ms.assetid: 9cdf97e6-331d-492b-85e1-3ec3171484e9
caps.latest.revision: 20
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 20
---
# += 연산자(C# 참조)
더하기 할당 연산자입니다.  
  
## 설명  
 다음과 같이 `+=` 대입 연산자를 사용하는 식은  
  
```  
x += y  
```  
  
 동일한 함수는  
  
```  
x = x + y  
```  
  
 그러나 `x`가 한 번만 계산된다는 점은 다릅니다.  [\+ 연산자](../../../csharp/language-reference/operators/addition-operator.md)의 의미는 `x` 및 `y`의 형식에 따라 달라집니다\(숫자 피연산자의 더하기, 문자열 피연산자의 연결 등\).  
  
 `+=` 연산자는 직접 오버로드될 수 없지만 사용자 정의 형식으로 [\+ 연산자](../../../csharp/language-reference/operators/addition-operator.md)를 오버로드할 수 있습니다\([operator](../../../csharp/language-reference/keywords/operator.md) 참조\).  
  
 `+=` 연산자를 사용하여 이벤트에 대한 응답으로 호출되는 메서드를 지정할 수도 있습니다. 이러한 메서드를 이벤트 처리기라고 합니다.  이 컨텍스트에서 `+=` 연산자 사용을 *이벤트 구독*이라고 합니다.  자세한 내용은 [방법: 이벤트 구독 및 구독 취소](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)를 참조하십시오.  및 [대리자](../../../csharp/programming-guide/delegates/index.md)를 참조하십시오.  
  
## 예제  
 [!code-cs[csRefOperators#35](../../../csharp/language-reference/operators/codesnippet/csharp/csrefOperators/csrefOperators.cs#35)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 연산자](../../../csharp/language-reference/operators/index.md)