---
title: "SyncLock Statement | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.SyncLock"
  - "SyncLock"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "threading [Visual Basic], locks"
  - "SyncLock statement"
  - "locks, threads"
ms.assetid: 14501703-298f-4d43-b139-c4b6366af176
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# SyncLock Statement
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

블록을 실행하기 전에 문 블록에 대한 단독 잠금을 가져옵니다.  
  
## 구문  
  
```  
SyncLock lockobject  
    [ block ]  
End SyncLock  
```  
  
## 요소  
 `lockobject`  
 필수 요소.  개체 참조로 계산되는 식입니다.  
  
 `block`  
 선택 사항입니다.  잠금을 가져온 경우 실행할 문 블록입니다.  
  
 `End SyncLock`  
 `SyncLock` 블록을 끝냅니다.  
  
## 설명  
 `SyncLock` 문은 여러 스레드가 동시에 문 블록을 실행하지 않도록 합니다.  `SyncLock`는 각 스레드가 다른 스레드에서 블록을 실행 중이지 않을 때까지 블록을 입력하는 것을 방지합니다.  
  
 `SyncLock`는 데이터를 여러 스레드에서 동시에 업데이트하지 못하게 하는 데 가장 일반적으로 사용됩니다.  데이터를 조작하는 문을 중단 없이 완료하려면 해당 문을 `SyncLock` 블록에 넣어야 합니다.  
  
 단독 잠금으로 보호된 문 블록을 *임계 영역*이라고도 합니다.  
  
## 규칙  
  
-   분기.  블록 외부에서 `SyncLock` 블록으로 분기할 수 없습니다.  
  
-   잠금 개체 값.  `Nothing`은 `lockobject`의 값이 될 수 없습니다.  `SyncLock` 문에서 잠금 개체를 사용하려면 해당 개체를 만들어야 합니다.  
  
     `SyncLock` 블록을 실행하는 동안에는 `lockobject` 값을 변경할 수 없습니다.  이 메커니즘에서는 잠금 개체가 변경되지 않은 상태로 유지되어야 합니다.  
  
-   사용할 수 없습니다는  [Await](../../../visual-basic/language-reference/operators/await-operator.md) 연산자는 `SyncLock` 블록.  
  
## 동작  
  
-   메커니즘.  스레드는 `SyncLock` 문에 도달하면 `lockobject` 식을 계산하고 식에서 반환된 개체에 대한 단독 잠금을 가져올 때까지 실행을 중단합니다.  다른 스레드는 `SyncLock` 문에 도달하더라도 첫 번째 스레드가 `End SyncLock` 문을 실행할 때까지는 잠금을 가져오지 않습니다.  
  
-   보호된 데이터.  `lockobject`가 `Shared` 변수인 경우 단독 잠금은 클래스 인스턴스의 스레드가 다른 스레드에서는 실행 중인 `SyncLock` 블록을 실행하지 못하게 합니다.  그러면 모든 인스턴스 간에 공유되는 데이터가 보호됩니다.  
  
     `lockobject`가 `Shared`가 아니라 인스턴스 변수인 경우 잠금은 현재 인스턴스에서 실행 중인 스레드와 동일 인스턴스의 다른 스레드가 모두 `SyncLock` 블록을 실행하지 못하게 합니다.  그러면 개별 인스턴스에서 관리되는 데이터가 보호됩니다.  
  
-   획득 및 해제.  `SyncLock` 블록은 `Try` 블록이 `lockobject`에 대한 단독 잠금을 획득하고 `Finally` 블록이 잠금을 해제하는 `Try...Finally` 구문처럼 동작합니다.  따라서 `SyncLock` 블록은 사용자가 블록을 종료하는 방법에 관계없이 잠금을 해제합니다.  이는 처리되지 않은 예외의 경우에도 해당됩니다.  
  
-   Framework 호출.  `SyncLock` 블록은 <xref:System.Threading> 네임스페이스에서 `Monitor` 클래스의 `Enter` 및 `Exit` 메서드를 호출하여 단독 잠금을 획득하고 해제합니다.  
  
## 프로그래밍 방법  
 `lockobject` 식은 클래스에 단독으로 포함되는 개체를 항상 계산해야 합니다.  `Private` 개체 변수를 선언하여 현재 인스턴스에 속하는 데이터를 보호하거나 `Private Shared` 개체 변수를 선언하여 모든 인스턴스에 공통된 데이터를 보호해야 합니다.  
  
 인스턴스 데이터에 잠금 개체를 제공할 때 `Me` 키워드는 사용하지 마십시오.  클래스 외부 코드에 클래스 인스턴스에 대한 참조가 있는 경우 해당 참조를 사용자와 관련 없는 `SyncLock` 블록에 대한 잠금 개체로 사용하여 다른 데이터를 보호할 수 있습니다.  이 방법에서는 클래스와 다른 클래스가 관련 없는 `SyncLock` 블록을 실행하지 못하도록 서로 차단할 수 있습니다.  문자열 하나만 잠그는 경우에는 프로세스에서 해당 문자열을 사용하는 다른 코드에서 이 잠금을 공유하기 때문에 문제가 발생할 수 있습니다.  
  
 공유 데이터에 잠금 개체를 제공할 때 `Me.GetType` 메서드는 사용하지 마십시오.  `GetType`은 지정된 클래스 이름에 대해 항상 동일한 `Type` 개체를 반환합니다.  외부 코드가 사용자 클래스에서 `GetType`을 호출하여 사용자가 사용하고 있는 것과 동일한 잠금 개체를 얻을 수 있습니다.  그러면 두 클래스가 해당 `SyncLock` 블록에서 서로 차단하게 됩니다.  
  
## 예제  
  
### 설명  
 다음 예제에서는 간단한 메시지 목록을 유지 관리하는 클래스를 보여 줍니다.  여기서는 메시지를 배열에 저장하고 해당 배열에서 마지막으로 사용된 요소를 변수로 저장합니다.  `addAnotherMessage` 프로시저는 마지막 요소를 늘리고 새 메시지를 저장합니다.  마지막 요소가 증가되면 다른 스레드에서 마지막 요소를 다시 늘리기 전에 새 메시지를 저장해야 하기 때문에 이러한 두 작업은 `SyncLock` 및 `End SyncLock` 문에 의해 보호됩니다.  
  
 `simpleMessageList` 클래스에서 모든 해당 인스턴스 간의 단일 메시지 목록을 공유하는 경우 `messagesList` 및 `messagesLast` 변수가 `Shared`로 선언됩니다.  이 경우 모든 인스턴스에서 단일 잠금 개체가 사용되기 때문에 `messagesLock` 변수도 `Shared`로 선언되어야 합니다.  
  
### 코드  
 [!code-vb[VbVbalrThreading#1](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/synclock-statement_1.vb)]  
  
### 설명  
 다음 예제에서는 스레드와 `SyncLock`를 사용합니다.  `SyncLock` 문이 있으면 문 블록이 임계 영역이 되고 `balance`는 음수가 되지 않습니다.  `SyncLock` 및 `End SyncLock` 문을 주석 처리하여 `SyncLock` 키워드를 생략하는 효과를 볼 수 있습니다.  
  
### 코드  
 [!code-vb[VbVbalrThreading#21](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/synclock-statement_2.vb)]  
  
### 설명  
  
## 참고 항목  
 <xref:System.Threading>   
 <xref:System.Threading.Monitor>   
 [스레드 동기화](../Topic/Thread%20Synchronization%20\(C%23%20and%20Visual%20Basic\).md)   
 [스레딩](../Topic/Threading%20\(C%23%20and%20Visual%20Basic\).md)