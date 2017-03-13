---
title: "add(C# 참조) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "add_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "add 이벤트 접근자[C#]"
ms.assetid: faf30b99-10e8-45cd-ab9a-57585d4d1d8d
caps.latest.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 7
---
# add(C# 참조)
`add` 컨텍스트 키워드는 클라이언트 코드가 사용자의 [이벤트](../../../csharp/language-reference/keywords/event.md)를 구독할 때 호출되는 사용자 지정 이벤트 접근자를 정의하는 데 사용됩니다.  사용자 지정 `add` 접근자를 제공하는 경우에는 [remove](../../../csharp/language-reference/keywords/remove.md) 접근자도 제공해야 합니다.  
  
## 예제  
 다음 예제에서는 사용자 지정 `add` 및 [remove](../../../csharp/language-reference/keywords/remove.md) 접근자가 있는 이벤트를 보여 줍니다.  전체 예제를 보려면 [방법: 인터페이스 이벤트 구현](../../../csharp/programming-guide/events/how-to-implement-interface-events.md)을 참조하십시오.  
  
 [!code-cs[csrefKeywordsContextual#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/add_1.cs)]  
  
 일반적으로 자체 사용자 지정 이벤트 접근자를 제공할 필요는 없습니다.  대부분의 경우 이벤트를 선언할 때 컴파일러에서 자동으로 생성되는 접근자로도 충분합니다.  
  
## 참고 항목  
 [이벤트](../../../csharp/programming-guide/events/index.md)