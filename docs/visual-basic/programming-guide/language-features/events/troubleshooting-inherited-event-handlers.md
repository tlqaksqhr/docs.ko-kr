---
title: "Troubleshooting Inherited Event Handlers in Visual Basic | Microsoft Docs"
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
  - "troubleshooting events"
  - "inherited events"
  - "troubleshooting Visual Basic, event handlers"
  - "event handling, troubleshooting"
  - "event handlers, troubleshooting"
ms.assetid: e1c8759f-5370-4308-8476-8c48b73509bf
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# Troubleshooting Inherited Event Handlers in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

이 항목에서는 상속된 구성 요소의 이벤트 처리기와 관련하여 공통적으로 발생하는 문제점에 대해 설명합니다.  
  
## 절차  
  
#### 이벤트 처리기의 코드가 호출할 때마다 두 번씩 실행되는 문제  
  
-   상속된 이벤트 처리기에는 [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) 절을 사용할 수 없습니다.  기본 클래스의 메서드가 이미 해당 이벤트에 연결되어 있고 그에 따라 실행됩니다.  상속된 메서드에서 `Handles` 절을 제거하십시오.  
  
     [!code-vb[VbVbalrEvents#32](../../../../visual-basic/language-reference/statements/codesnippet/visualbasic/VbVbalrEvents/Class1.vb#32)]  
  
-   상속된 메서드에 `Handles` 키워드가 없는 경우에는 코드에 [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md) 또는 동일한 이벤트를 처리하는 추가 메서드가 있는지 확인하십시오.  
  
## 참고 항목  
 [Events](../../../../visual-basic/programming-guide/language-features/events/events.md)