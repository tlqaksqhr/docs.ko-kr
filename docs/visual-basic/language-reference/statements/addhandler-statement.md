---
title: "AddHandler Statement | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.AddHandlerMethod"
  - "addhandler"
  - "vb.addhandler"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "AddHandler statement"
ms.assetid: cfe69799-2a0f-42c0-a99e-09fed954da01
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# AddHandler Statement
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

런타임에 이벤트를 이벤트 처리기에 연결합니다.  
  
## 구문  
  
```  
AddHandler event, AddressOf eventhandler  
```  
  
## 요소  
 `event`  
 처리할 이벤트 이름입니다.  
  
 `eventhandler`  
 이벤트를 처리하는 프로시저 이름입니다.  
  
## 설명  
 `AddHandler` 및 `RemoveHandler` 문을 사용하면 프로그램을 실행하는 동안 언제든지 이벤트 처리를 시작하고 중지할 수 있습니다.  
  
 `eventhandler` 프로시저의 시그니처는 `event` 이벤트의 시그니처와 일치해야 합니다.  
  
 `Handles` 키워드 및 `AddHandler` 문을 사용하여 특정 프로시저가 특정 이벤트를 처리하도록 지정할 수 있지만 둘 사이에는 차이점이 있습니다.  `AddHandler` 문은 런타임에 프로시저를 이벤트에 연결합니다.  `Handles` 키워드는 특정 이벤트를 처리하는 프로시저를 정의할 때 사용됩니다.  자세한 내용은 [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)를 참조하십시오.  
  
> [!NOTE]
>  사용자 지정 이벤트의 경우 `AddHandler` 문은 이벤트의 `AddHandler` 접근자를 호출합니다.  사용자 지정 이벤트에 대한 자세한 내용은 [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md)을 참조하십시오.  
  
## 예제  
 [!code-vb[VbVbalrEvents#17](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/addhandler-statement_1.vb)]  
  
## 참고 항목  
 [RemoveHandler Statement](../../../visual-basic/language-reference/statements/removehandler-statement.md)   
 [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)   
 [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md)   
 [Events](../../../visual-basic/programming-guide/language-features/events/events.md)