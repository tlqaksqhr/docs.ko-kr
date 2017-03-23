---
title: "명명된 메서드와 무명 메서드의 대리자 비교(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "대리자[C#], 명명된 메서드와 익명 메서드 비교"
  - "메서드[C#], 대리자"
ms.assetid: 98fa8c61-66b6-4146-986c-3236c4045733
caps.latest.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 18
---
# 명명된 메서드와 무명 메서드의 대리자 비교(C# 프로그래밍 가이드)
[대리자](../../../csharp/language-reference/keywords/delegate.md)를 명명된 메서드에 연결할 수 있습니다.  명명된 메서드를 사용하여 대리자를 인스턴스화하는 경우 다음과 같이 메서드를 매개 변수로 전달합니다.  
  
 [!code-cs[csProgGuideDelegates#1](../../../csharp/programming-guide/delegates/codesnippet/CSharp/delegates-with-named-vs-anonymous-methods_1.cs)]  
  
 이를 명명된 메서드 사용이라고 합니다.  명명된 메서드를 사용하여 만든 대리자에서는 [정적](../../../csharp/language-reference/keywords/static.md) 메서드나 인스턴스 메서드를 캡슐화할 수 있습니다.  이전 버전의 C\#에서 대리자를 인스턴스화하는 유일한 방법은 명명된 메서드를 사용하는 것입니다.  그러나 새 메서드를 만들어 예기치 못한 부담이 생기는 경우를 대비하여, C\#에서는 대리자를 호출할 때 처리될 코드 블록을 대리자를 인스턴스화할 때 바로 지정할 수 있도록 허용합니다.  블록에는 람다 식 또는 무명 메서드가 포함될 수 있습니다.  자세한 내용은 [익명 함수](../../../csharp/programming-guide/statements-expressions-operators/anonymous-functions.md)를 참조하십시오.  
  
## 설명  
 대리자 매개 변수로 전달하는 메서드의 시그니처는 대리자 선언의 시그니처와 동일해야 합니다.  
  
 대리자 인스턴스는 정적 또는 인스턴스 메서드를 캡슐화할 수 있습니다.  
  
 대리자에서는 [out](../../../csharp/language-reference/keywords/out.md) 매개 변수를 사용할 수 있지만, 호출될 대리자를 알 수 없으므로 멀티캐스트 이벤트 대리자에는 이 매개 변수를 사용하지 않는 것이 좋습니다.  
  
## 예제 1  
 다음은 대리자 선언 및 사용에 대한 간단한 예제입니다.  대리자 `Del`의 시그니처와 연결된 메서드 `MultiplyNumbers`의 시그니처는 동일합니다.  
  
 [!code-cs[csProgGuideDelegates#2](../../../csharp/programming-guide/delegates/codesnippet/CSharp/delegates-with-named-vs-anonymous-methods_2.cs)]  
  
## 예제 2  
 다음 예제에서는 하나의 대리자를 정적 메서드와 인스턴스 메서드 모두에 매핑하고 각 메서드에서 특정 정보를 반환합니다.  
  
 [!code-cs[csProgGuideDelegates#3](../../../csharp/programming-guide/delegates/codesnippet/CSharp/delegates-with-named-vs-anonymous-methods_3.cs)]  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [대리자](../../../csharp/programming-guide/delegates/index.md)   
 [무명 메서드](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)   
 [방법: 대리자 조합\(멀티캐스트 대리자\)](../../../csharp/programming-guide/delegates/how-to-combine-delegates-multicast-delegates.md)   
 [이벤트](../../../csharp/programming-guide/events/index.md)