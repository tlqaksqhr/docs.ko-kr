---
title: "How to: Declare Custom Events To Conserve Memory (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "declaring events, custom"
  - "events [Visual Basic], custom"
  - "custom events"
ms.assetid: 87ebee87-260c-462f-979c-407874debd19
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Declare Custom Events To Conserve Memory (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

응용 프로그램에서 메모리 사용량을 적게 유지해야 하는 몇 가지 경우가 있습니다.  사용자 지정 이벤트를 사용하여 응용 프로그램에서 처리되는 이벤트만 메모리를 사용합니다.  
  
 기본적으로 클래스에서 이벤트를 선언하면 컴파일러는 필드에 이벤트 정보를 저장하는 데 사용할 메모리를 할당합니다.  클래스에 사용되지 않은 이벤트가 많이 있는 경우 해당 이벤트에서 필요 없는 메모리를 사용하게 됩니다.  
  
 Visual Basic에서 제공하는 기본 구현된 이벤트를 사용하는 대신 사용자 지정 이벤트를 사용하여 메모리 사용을 세부적으로 관리할 수 있습니다.  
  
## 예제  
 다음 예제에서는 클래스가 `Events` 필드에 저장된 <xref:System.ComponentModel.EventHandlerList> 클래스의 인스턴스 하나를 사용하여 사용 중인 이벤트에 대한 정보를 저장합니다.  <xref:System.ComponentModel.EventHandlerList> 클래스는 대리자를 보관하도록 최적화된 목록 클래스입니다.  
  
 클래스의 모든 이벤트에서는 `Events` 필드를 사용하여 각 이벤트를 처리하는 메서드를 추적합니다.  
  
 [!code-vb[VbVbalrEvents#22](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-declare-custom-events-to-conserve-memory_1.vb)]  
  
## 참고 항목  
 <xref:System.ComponentModel.EventHandlerList>   
 [Events](../../../../visual-basic/programming-guide/language-features/events/events.md)   
 [How to: Declare Custom Events To Avoid Blocking](../../../../visual-basic/programming-guide/language-features/events/how-to-declare-custom-events-to-avoid-blocking.md)