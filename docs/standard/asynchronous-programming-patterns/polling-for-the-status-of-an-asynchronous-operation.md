---
title: "비동기 작업의 상태에 대한 폴링"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- asynchronous programming, status polling
- polling asynchronous operation status
- status information [.NET Framework], asynchronous operations
ms.assetid: b541af31-dacb-4e20-8847-1b1ff7c35363
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e1f7f74a8b38c06f6a042d55c0def76ddfc5da77
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="polling-for-the-status-of-an-asynchronous-operation"></a>비동기 작업의 상태에 대한 폴링
비동기 작업의 결과 기다리는 동안 다른 작업을 수행할 수 있는 응용 프로그램은 작업이 완료 될 때까지 대기 하는 것을 차단 하지 않아야 합니다. 다음 옵션 중 하나를 사용 하 여 비동기 작업이 완료 되기를 기다리는 동안 명령을 계속 실행 합니다.  
  
-   사용 하 여는 <xref:System.IAsyncResult.IsCompleted%2A> 의 속성은 <xref:System.IAsyncResult> 비동기 작업에서 반환 **시작** *OperationName* 작업이 완료 되었는지 여부를 확인 하는 메서드. 이 방법은 폴링 라고 하며이 항목에 나와 있습니다.  
  
-   사용 하 여 프로그램 <xref:System.AsyncCallback> 별도의 스레드에서 비동기 작업의 결과 처리 하는 대리자입니다. 이 방법을 보여 주는 예제를 보려면 [AsyncCallback 대리자를 사용 하 여 비동기 작업을 종료 하도록](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md)합니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는의 비동기 메서드를 사용 하 여는 <xref:System.Net.Dns> 사용자가 지정한 컴퓨터에 대 한 도메인 이름 시스템 정보를 검색할 수 있습니다. 이 예제에서는 비동기 작업을 시작 하 고 다음 마침표 (".") 작업이 완료 될 때까지 콘솔. **null** (**Nothing** Visual Basic의)에 대 한 전달 되는 <xref:System.Net.Dns.BeginGetHostByName%2A> <xref:System.AsyncCallback> 및 <xref:System.Object> 매개 변수가이 방법을 사용할 때는이 인수를 필요 하지 않으므로 합니다.  
  
 [!code-csharp[AsyncDesignPattern#3](../../../samples/snippets/csharp/VS_Snippets_CLR/AsyncDesignPattern/CS/Async_Poll.cs#3)]
 [!code-vb[AsyncDesignPattern#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AsyncDesignPattern/VB/Async_Poll.vb#3)]  
  
## <a name="see-also"></a>참고 항목  
 [EAP(이벤트 기반 비동기 패턴)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 [이벤트 기반 비동기 패턴 개요](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
