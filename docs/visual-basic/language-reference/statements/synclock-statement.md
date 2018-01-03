---
title: "SyncLock 문"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.SyncLock
- SyncLock
helpviewer_keywords:
- threading [Visual Basic], locks
- SyncLock statement [Visual Basic]
- locks, threads
ms.assetid: 14501703-298f-4d43-b139-c4b6366af176
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c363b41bb7a409c490a6e07d4a1a4f1bb44c1438
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="synclock-statement"></a>SyncLock 문
블록을 실행 하기 전에 문 블록에 대 한 단독 잠금을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
SyncLock lockobject  
    [ block ]  
End SyncLock  
```  
  
## <a name="parts"></a>요소  
 `lockobject`  
 필수. 개체 참조를 가리키는 식입니다.  
  
 `block`  
 선택 사항입니다. 잠금을 획득 하는 경우 실행할 문 블록.  
  
 `End SyncLock`  
 종료는 `SyncLock` 블록입니다.  
  
## <a name="remarks"></a>설명  
 `SyncLock` 문을 여러 스레드가 동시에 문 블록을 실행 하지 않도록 보장 합니다. `SyncLock`각 스레드가 다른 스레드에서 실행 될 때까지 블록을 입력 하지 않습니다.  
  
 가장 일반적인 용도 `SyncLock` 에서 둘 이상의 스레드에서 동시에 업데이트 되 고 데이터를 보호 하는 것입니다. 데이터를 조작 하는 문이 중단 없이 완료도 이동 해야 하는 경우 내에 배치 된 `SyncLock` 블록입니다.  
  
 배타적 잠금에 의해 보호 되는 문 블록 라고도 *임계 영역*합니다.  
  
## <a name="rules"></a>규칙  
  
-   분기입니다. 으로 분기할 수 없습니다는 `SyncLock` 블록 외부에서 차단 합니다.  
  
-   잠금 개체 값입니다. 값 `lockobject` 안 `Nothing`합니다. 사용 하기 전에 잠금 개체를 만들어야는 `SyncLock` 문.  
  
     값을 변경할 수 없습니다 `lockobject` 실행 하는 동안 한 `SyncLock` 블록입니다. 메커니즘은 잠금 개체 변경 되지 필요 합니다.  
  
-   사용할 수 없습니다는 [Await](../../../visual-basic/language-reference/operators/await-operator.md) 연산자에는 `SyncLock` 블록입니다.  
  
## <a name="behavior"></a>동작  
  
-   메커니즘입니다. 스레드에 도달 하면는 `SyncLock` 문을 평가 `lockobject` 식을 식에 의해 반환 된 개체에 대 한 단독 잠금을 가져올 때까지 실행을 일시 중단 합니다. 다른 스레드가 도달 하면는 `SyncLock` 문, 가져오지 않습니다 잠금을 첫 번째 스레드가 실행 될 때까지 `End SyncLock` 문.  
  
-   보호 된 데이터. 경우 `lockobject` 는 `Shared` 변수는 배타적 잠금을 설정 하면 클래스의 모든 인스턴스에서 스레드를 실행할 수 없도록는 `SyncLock` 다른 스레드가 실행 되는 동안 차단 합니다. 모든 인스턴스 간에 공유 되는 데이터를 보호 합니다.  
  
     경우 `lockobject` 인스턴스 변수 (하지 `Shared`), 잠금을 방지 실행 되는 현재 인스턴스에서 실행 하는 스레드는 `SyncLock` 동일한 인스턴스에 있는 다른 스레드가 동시에 블록입니다. 개별 인스턴스에 의해 유지 관리 하는 데이터를 보호 합니다.  
  
-   획득 및 해제 합니다. A `SyncLock` 블록 처럼 동작는 `Try...Finally` 구문은 `Try` 블록에서 배타적 잠금을 획득 `lockobject` 및 `Finally` 차단 해제 합니다. 이 인해는 `SyncLock` 블록은 블록을 종료 하는 방법에 관계 없이 잠금 해제 합니다. 예외가 처리 되지 않은 경우에 마찬가지입니다.  
  
-   프레임 워크 호출 합니다. `SyncLock` 획득 하 고 호출 하 여 단독 잠금을 해제 하는 블록의 `Enter` 및 `Exit` 의 메서드는 `Monitor` 클래스에 <xref:System.Threading> 네임 스페이스입니다.  
  
## <a name="programming-practices"></a>프로그래밍 방법  
 `lockobject` 식은 단독으로 클래스에 속하는 개체는 항상 계산 되어야 합니다. 선언 해야 합니다는 `Private` 현재 인스턴스에 속한 데이터를 보호 하기 위해 개체 변수 또는 `Private Shared` 모든 인스턴스에 공통 되는 데이터를 보호 하는 개체 변수입니다.  
  
 사용 하지 않아야는 `Me` 키워드를 잠금을 제공 하는 예를 들어 개체 데이터입니다. 에 대 한 잠금 개체와 해당 참조를 사용할 수를 클래스 외부의 코드에 클래스의 인스턴스에 대 한 참조를는 `SyncLock` 블록을, 다른 데이터를 보호 합니다. 이러한 방식으로 다른 클래스와 클래스 서로 차단할 수에서 관련 없는 실행 `SyncLock` 블록입니다. 잠그는 경우 문자열에 동일한 문자열을 사용 하는 프로세스의 다른 코드는 동일한 잠금을 공유 하므로 문제가 될 수 있습니다.  
  
 또한 사용해 서는 안는 `Me.GetType` 에 대 한 잠금 개체를 제공 하려면 메서드 데이터를 공유 합니다. 때문에 이것이 `GetType` 항상 동일한 반환 `Type` 지정된 된 클래스 이름에 대 한 개체입니다. 외부 코드에서 호출할 수 `GetType` 클래스에 가져오고, 사용 하는 동일한 잠금 개체인 합니다. 이 두 클래스에서 서로 차단 결과로 해당 `SyncLock` 블록입니다.  
  
## <a name="examples"></a>예제  
  
### <a name="description"></a>설명  
 다음 예제에서는 메시지의 단순 목록을 유지 관리 하는 클래스를 보여 줍니다. 배열에서 메시지를 보유 하 고 마지막 변수에 해당 배열의 요소를 사용 합니다. `addAnotherMessage` 프로시저 마지막 요소를 증가 시키고 새 메시지를 저장 합니다. 이러한 두 작업에 의해 보호 되는 `SyncLock` 및 `End SyncLock` 문, 마지막 요소 증가 된 후에 다른 스레드가 마지막 요소를 다시 증가 수 전에 새 메시지를 저장 해야 하기 때문에 있습니다.  
  
 경우는 `simpleMessageList` 클래스 공유 모든 인스턴스에서 해당 변수는 메시지 목록은 한 `messagesList` 및 `messagesLast` 로 선언 됩니다 `Shared`합니다. 이 경우 변수 `messagesLock` 이어야 `Shared`모든 인스턴스에 사용 되는 단일 잠금 개체가 있을 수 있도록 합니다.  
  
### <a name="code"></a>코드  
 [!code-vb[VbVbalrThreading#1](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/synclock-statement_1.vb)]  
  
### <a name="description"></a>설명  
 다음 예제에서는 스레드를 사용 하 고 `SyncLock`합니다. 으로 `SyncLock` 문이 있으면 문 블록은 임계 영역 및 `balance` 음수 되지 됩니다. 주석으로 처리는 `SyncLock` 및 `End SyncLock` 문을 맞추고 나머지의 영향을 확인할 수는 `SyncLock` 키워드입니다.  
  
### <a name="code"></a>코드  
 [!code-vb[VbVbalrThreading#21](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/synclock-statement_2.vb)]  
  
### <a name="comments"></a>설명  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Threading>  
 <xref:System.Threading.Monitor>  
 [스레드 동기화](../../programming-guide/concepts/threading/thread-synchronization.md)  
 [스레딩](../../programming-guide/concepts/threading/index.md)
