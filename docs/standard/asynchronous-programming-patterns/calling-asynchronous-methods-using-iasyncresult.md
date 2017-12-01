---
title: "IAsyncResult를 사용하는 비동기 메서드 호출"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ending asynchronous operations
- waiting for asynchronous operations
- asynchronous method calling
- calling asynchronous methods
- asynchronous programming, calling asynchronous methods
- IAsyncResult interface, calling asynchronous methods
- stopping asynchronous operations
ms.assetid: 07fba116-045b-473c-a0b7-acdbeb49861f
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 81c05aeae00e79f614ef1514e54765b21e7e2dde
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="calling-asynchronous-methods-using-iasyncresult"></a>IAsyncResult를 사용하는 비동기 메서드 호출
.NET Framework 및 공급 업체 클래스 라이브러리의 형식에 기본 응용 프로그램 스레드를 제외한 스레드에서 비동기 작업을 수행 하는 동안 계속 실행 하려면 응용 프로그램을 사용할 수 있는 메서드를 제공할 수 있습니다. 다음 섹션에 설명 하 고 사용 하는 비동기 메서드를 호출 하는 여러 가지 방법을 보여 주는 코드 예제를 제공는 <xref:System.IAsyncResult> 디자인 패턴.  
  
-   [비동기 작업을 종료 하 여 응용 프로그램 실행 블로킹](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-by-ending-an-async-operation.md)합니다.  
  
-   [AsyncWaitHandle을 사용 하는 응용 프로그램 실행 블로킹](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-using-an-asyncwaithandle.md)합니다.  
  
-   [비동기 작업의 상태에 대 한 폴링](../../../docs/standard/asynchronous-programming-patterns/polling-for-the-status-of-an-asynchronous-operation.md)합니다.  
  
-   [AsyncCallback 대리자를 사용 하 여 비동기 작업을 종료 하도록](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [EAP(이벤트 기반 비동기 패턴)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 [이벤트 기반 비동기 패턴 개요](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-overview.md)
