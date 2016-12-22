---
title: "remove(C# 참조) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "remove_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "remove 이벤트 접근자[C#]"
ms.assetid: c8223426-c17b-4fe2-8406-01564cf1dd2b
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# remove(C# 참조)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

`remove` 컨텍스트 키워드는 클라이언트 코드가 사용자의 [이벤트](../../../csharp/language-reference/keywords/event.md) 구독을 취소할 때 호출되는 사용자 지정 이벤트 접근자를 정의하는 데 사용됩니다.  사용자 지정 `remove` 접근자를 제공하는 경우에는 [add](../../../csharp/language-reference/keywords/add.md) 접근자도 제공해야 합니다.  
  
## 예제  
 다음 예제에서는 사용자 지정 [add](../../../csharp/language-reference/keywords/add.md) 및 `remove` 접근자가 있는 이벤트를 보여 줍니다.  전체 예제를 보려면 [방법: 인터페이스 이벤트 구현](../../../csharp/programming-guide/events/how-to-implement-interface-events.md)을 참조하십시오.  
  
 [!code-cs[csrefKeywordsContextual#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/remove_1.cs)]  
  
 일반적으로 자체 사용자 지정 이벤트 접근자를 제공할 필요는 없습니다.  대부분의 경우 이벤트를 선언할 때 컴파일러에서 자동으로 생성되는 접근자로도 충분합니다.  
  
## 참고 항목  
 [이벤트](../../../csharp/programming-guide/events/index.md)