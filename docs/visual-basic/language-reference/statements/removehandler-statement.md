---
title: "RemoveHandler Statement | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.RemoveHandlerMethod"
  - "vb.RemoveHandler"
  - "RemoveHandler"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "RemoveHandler keyword"
  - "RemoveHandler statement"
ms.assetid: 647cd825-e877-4910-b4f1-8d168beebe6a
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# RemoveHandler Statement
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

이벤트와 이벤트 핸들러 간의 연결을 제거합니다.  
  
## 구문  
  
```  
RemoveHandler event, AddressOf eventhandler  
```  
  
## 요소  
  
|||  
|-|-|  
|용어|정의|  
|`event`|처리 중인 이벤트 이름입니다.|  
|`eventhandler`|현재 이벤트를 처리하고 있는 프로시저 이름입니다.|  
  
## 설명  
 `AddHandler` 및 `RemoveHandler` 문을 사용하면 프로그램을 실행하는 동안 언제든지 특정 이벤트에 대한 이벤트 처리를 시작하고 중지할 수 있습니다.  
  
> [!NOTE]
>  사용자 지정 이벤트의 경우 `RemoveHandler` 문은 이벤트의 `RemoveHandler` 접근자를 호출합니다.  사용자 지정 이벤트에 대한 자세한 내용은 [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md)을 참조하십시오.  
  
## 예제  
 [!code-vb[VbVbalrEvents#17](../../../visual-basic/language-reference/statements/codesnippet/visualbasic/VbVbalrEvents/Class1.vb#17)]  
  
## 참고 항목  
 [AddHandler Statement](../../../visual-basic/language-reference/statements/addhandler-statement.md)   
 [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)   
 [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md)   
 [Events](../../../visual-basic/programming-guide/language-features/events/events.md)