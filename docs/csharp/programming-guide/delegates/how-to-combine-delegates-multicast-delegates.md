---
title: "방법: 대리자 조합(멀티캐스트 대리자)(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "대리자[C#], 결합"
  - "멀티캐스트 대리자[C#]"
ms.assetid: 4e689450-6d0c-46de-acfd-f961018ae5dd
caps.latest.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 17
---
# 방법: 대리자 조합(멀티캐스트 대리자)(C# 프로그래밍 가이드)
이 예제에서는 멀티캐스트 대리자를 만드는 방법에 대해 설명합니다.  [대리자](../../../csharp/language-reference/keywords/delegate.md) 개체에는 `+` 연산자를 사용하여 대리자 인스턴스에 여러 개체를 할당할 수 있는 유용한 특성이 있습니다.  멀티캐스트 대리자에는 할당된 대리자 목록이 포함됩니다.  멀티캐스트 대리자를 호출하면 목록에 있는 대리자가 순서대로 호출됩니다.  같은 형식의 대리자만 조합할 수 있습니다.  
  
 `-` 연산자를 사용하면 멀티캐스트 대리자에서 구성 요소 대리자를 제거할 수 있습니다.  
  
## 예제  
 [!code-cs[csProgGuideDelegates#11](../../../csharp/programming-guide/delegates/codesnippet/CSharp/how-to-combine-delegates-multicast-delegates_1.cs)]  
  
## 참고 항목  
 <xref:System.MulticastDelegate>   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [이벤트](../../../csharp/programming-guide/events/index.md)