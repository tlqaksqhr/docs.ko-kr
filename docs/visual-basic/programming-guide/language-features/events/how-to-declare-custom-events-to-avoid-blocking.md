---
title: "How to: Declare Custom Events To Avoid Blocking (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "declaring events, custom"
  - "events [Visual Basic], custom"
  - "custom events"
ms.assetid: 998b6a90-67c5-4d2c-8b11-366d3e355505
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# How to: Declare Custom Events To Avoid Blocking (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

특정 이벤트 처리기가 후속 이벤트 처리기를 차단하지 않아야 하는 경우가 많이 있습니다.  이때 사용자 지정 이벤트를 사용하면 이벤트가 해당 이벤트 처리기를 비동기적으로 호출할 수 있습니다.  
  
 기본적으로 이벤트 선언에 대한 지원 저장소 필드는 모든 이벤트 처리기를 순차적으로 사용하는 멀티캐스트 대리자입니다.  즉, 특정 처리기가 완료하는 데 시간이 오래 걸릴 경우 해당 처리기가 완료될 때까지 다른 처리기를 차단합니다.  그러나 올바르게 동작하는 이벤트 처리기는 수행하는 데 시간이 오래 걸리는 작업이나 다른 작업을 차단하는 작업을 수행하지 않습니다.  
  
 Visual Basic에서 제공하는 기본 이벤트 구현을 사용하는 대신 사용자 지정 이벤트를 사용하여 이벤트 처리기를 비동기적으로 실행할 수 있습니다.  
  
## 예제  
 이 예제에서 `AddHandler` 접근자는 `Click` 이벤트의 각 처리기에 대한 대리자를 `EventHandlerList` 필드에 저장된 <xref:System.Collections.ArrayList>에 추가합니다.  
  
 코드가 `Click` 이벤트를 발생시키면 `RaiseEvent` 접근자는 <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A> 메서드를 사용하여 모든 이벤트 처리기 대리자를 호출합니다.  이 메서드는 작업자 스레드의 각 처리기를 호출하고 즉시 반환하므로 처리기가 서로 차단할 수 없습니다.  
  
 [!code-vb[VbVbalrEvents#27](../../../../visual-basic/language-reference/statements/codesnippet/visualbasic/VbVbalrEvents/Class1.vb#27)]  
  
## 참고 항목  
 <xref:System.Collections.ArrayList>   
 <xref:System.Web.Services.Protocols.LogicalMethodInfo.BeginInvoke%2A>   
 [Events](../../../../visual-basic/programming-guide/language-features/events/events.md)   
 [How to: Declare Custom Events To Conserve Memory](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-conserve-memory.md)