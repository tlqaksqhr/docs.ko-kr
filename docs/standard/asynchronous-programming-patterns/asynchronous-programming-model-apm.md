---
title: "APM(비동기 프로그래밍 모델)"
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
- starting asynchronous operations
- beginning asynchronous operations
- asynchronous programming, ending operations
- asynchronous programming
- stopping asynchronous operations
- asynchronous programming, beginning operations
ms.assetid: c9b3501e-6bc6-40f9-8efd-4b6d9e39ccf0
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b31383f8972ecf345366f90460d88b6be21eab99
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="asynchronous-programming-model-apm"></a>APM(비동기 프로그래밍 모델)
<xref:System.IAsyncResult> 디자인 패턴을 사용하는 비동기 작업은 **Begin** *OperationName* 과 **End** *OperationName* 이라는 두 가지 메서드로 구현됩니다. 이 두 메서드를 사용하면 각각 비동기 작업 *OperationName* 이 시작되고 종료됩니다. 예를 들어 <xref:System.IO.FileStream> 클래스는 파일에서 바이트를 비동기적으로 읽는 <xref:System.IO.FileStream.BeginRead%2A> 및 <xref:System.IO.FileStream.EndRead%2A> 메서드를 제공합니다. 이러한 메서드는 비동기 버전의 <xref:System.IO.FileStream.Read%2A> 메서드를 구현합니다.  
  
> [!NOTE]
>  .NET Framework 4부터는 작업 병렬 라이브러리에서 비동기 및 병렬 프로그래밍을 위한 새로운 모델을 제공합니다. 자세한 내용은 [Task Parallel Library (TPL)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md) 및 [Task-based Asynchronous Pattern (TAP)](../../../docs/standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md)을 참조하세요.  
  
 **Begin** *OperationName*을 호출한 후에는 비동기 작업이 다른 스레드에서 발생되는 동안 응용 프로그램에서 호출 스레드에 대한 명령을 계속 실행할 수 있습니다. 응용 프로그램에서 작업 결과를 확인하려면 **Begin** *OperationName*을 호출할 때마다 **End** *OperationName* 도 호출해야 합니다.  
  
## <a name="beginning-an-asynchronous-operation"></a>비동기 작업 시작  
 **Begin** *OperationName* 메서드로 비동기 작업 *OperationName* 을 시작하고 <xref:System.IAsyncResult> 인터페이스를 구현하는 개체를 반환합니다. <xref:System.IAsyncResult> 개체는 비동기 작업에 대한 정보를 저장합니다. 다음 표에서는 비동기 작업에 대한 정보를 보여 줍니다.  
  
|멤버|설명|  
|------------|-----------------|  
|<xref:System.IAsyncResult.AsyncState%2A>|비동기 작업에 대한 정보를 포함하는 응용 프로그램별 선택적 개체입니다.|  
|<xref:System.IAsyncResult.AsyncWaitHandle%2A>|비동기 작업이 완료될 때까지 응용 프로그램 실행을 차단하기 위해 사용할 수 있는 <xref:System.Threading.WaitHandle> 입니다.|  
|<xref:System.IAsyncResult.CompletedSynchronously%2A>|비동기 작업이 별도의 **스레드에서 완료되는 대신** *Begin* OperationName <xref:System.Threading.ThreadPool> 호출에 사용된 스레드에서 완료되었는지 여부를 나타내는 값입니다.|  
|<xref:System.IAsyncResult.IsCompleted%2A>|비동기 작업이 완료되었는지 여부를 나타내는 값입니다.|  
  
 **Begin** *OperationName* 메서드에는 값 또는 참조로 전달되는 동기 버전의 메서드 서명에 선언된 매개 변수가 사용됩니다. out 매개 변수는 **Begin** *OperationName* 메서드 서명의 일부가 아닙니다. **Begin** *OperationName* 메서드 서명에는 두 개의 추가 매개 변수도 포함되어 있습니다. 그중 첫 번째 매개 변수는 비동기 작업이 완료될 때 호출되는 메서드를 참조하는 <xref:System.AsyncCallback> 대리자를 정의합니다. 호출자는 작업이 완료될 때 호출되는 메서드를 원하지 않는 경우 `null` (Visual Basic에서는`Nothing` )을 지정할 수 있습니다. 두 번째 추가 매개 변수는 사용자 정의 개체입니다. 이 개체를 사용하여 비동기 작업이 완료될 때 호출되는 메서드로 응용 프로그램별 상태 정보를 전달할 수 있습니다. 파일에서 읽은 바이트를 저장하는 바이트 배열과 같이 **Begin** *OperationName* 메서드에서 작업 관련 추가 매개 변수를 사용하는 경우 <xref:System.AsyncCallback> 및 응용 프로그램 상태 개체는 **Begin** *OperationName* 메서드 서명의 마지막 매개 변수가 됩니다.  
  
 **Begin** *OperationName* 은 호출 스레드에 대한 컨트롤을 즉시 반환합니다. **Begin** *OperationName* 메서드가 예외를 throw하면 이 예외는 이 비동기 작업이 시작되기 전에 throw됩니다. **Begin** *OperationName* 메서드가 예외를 throw하면 콜백 메서드는 호출되지 않습니다.  
  
## <a name="ending-an-asynchronous-operation"></a>비동기 작업 끝내기  
 **End** *OperationName* 메서드는 비동기 작업 *OperationName*을 종료합니다. **End** *OperationName* 메서드의 반환 값은 이에 상응하는 동기 항목의 반환 값과 같은 유형으로서 비동기 작업에 대해서만 사용됩니다. 예를 들어 <xref:System.IO.FileStream.EndRead%2A> 메서드는 <xref:System.IO.FileStream> 에서 읽은 바이트 수를 반환하고 <xref:System.Net.Dns.EndGetHostByName%2A> 메서드는 호스트 컴퓨터에 대한 정보를 포함하는 <xref:System.Net.IPHostEntry> 개체를 반환합니다. **End** *OperationName* 메서드는 동기 버전의 메서드 서명에 선언된 out 또는 ref 매개 변수를 사용합니다. **End** *OperationName* 메서드에는 동기 메서드의 매개 변수와 함께 <xref:System.IAsyncResult> 매개 변수도 포함되어 있습니다. 호출자는 **Begin** *OperationName*에 대한 해당 호출로 반환된 인스턴스를 전달해야 합니다.  
  
 <xref:System.IAsyncResult> End **OperationName** *이 호출되었을 때* 개체에 표시되는 비동기 작업이 완료되지 않은 경우에는 **End** *OperationName* 에서 비동기 작업이 완료될 때까지 해당 호출 스레드를 블로킹합니다. 비동기 작업이 throw한 예외는 **End** *OperationName* 메서드에서 throw됩니다. 같은 **로** *End* OperationName <xref:System.IAsyncResult> 메서드를 여러 번 호출한 데 따른 효과는 정의되어 있지 않습니다. 마찬가지로 관련된 Begin 메서드에서 반환하지 않은 **로** *End* OperationName <xref:System.IAsyncResult> 메서드를 호출하는 경우도 정의되어 있지 않습니다.  
  
> [!NOTE]
>  정의되지 않은 두 시나리오 중 하나의 경우 구현자는 <xref:System.InvalidOperationException>을 throw하는 것을 고려해야 합니다.  
  
> [!NOTE]
>  이 디자인 패턴의 구현자는 <xref:System.IAsyncResult.IsCompleted%2A> 를 true로 설정하여 비동기 콜백 메서드(지정된 경우)를 호출하고 <xref:System.IAsyncResult.AsyncWaitHandle%2A>을 신호로 보내서 비동기 작업이 완료되었다는 것을 호출자에게 알려야 합니다.  
  
 응용 프로그램 개발자는 비동기 작업의 결과에 액세스하기 위해 여러 디자인을 선택할 수 있습니다. 어떤 선택이 올바른 선택인지는 응용 프로그램에 작업이 완료되는 동안 실행할 수 있는 지침이 있는지 여부에 따라 달라집니다. 비동기 작업의 결과를 받을 때까지 응용 프로그램이 추가 작업을 수행할 수 없는 경우 결과를 사용할 수 있을 때까지 응용 프로그램을 차단해야 합니다. 비동기 작업이 완료될 때까지 차단하려면 다음 방법 중 하나를 사용하면 됩니다.  
  
-   응용 프로그램의 주 스레드에서 **End** *OperationName* 을 호출하여 작업이 완료될 때까지 응용 프로그램 실행을 블로킹합니다. 이 방법을 보여 주는 예제를 보려면 [비동기 작업을 종료 하 여 응용 프로그램 실행 블로킹](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-by-ending-an-async-operation.md)합니다.  
  
-   <xref:System.IAsyncResult.AsyncWaitHandle%2A> 을 사용하여 하나 이상의 작업이 완료될 때까지 응용 프로그램 실행을 차단할 수 있습니다. 이 방법을 설명하는 예제는 [Blocking Application Execution Using an AsyncWaitHandle](../../../docs/standard/asynchronous-programming-patterns/blocking-application-execution-using-an-asyncwaithandle.md)을 참조하세요.  
  
 비동기 작업이 완료되는 동안 차단할 필요가 없는 응용 프로그램은 다음 방법 중 하나를 사용할 수 있습니다.  
  
-   <xref:System.IAsyncResult.IsCompleted%2A> 속성을 정기적으로 점검하고 작업 완료 시 **End** *OperationName* 을 호출하는 방법으로 작업 완료 상태를 폴링합니다. 이 방법을 설명하는 예제는 [Polling for the Status of an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/polling-for-the-status-of-an-asynchronous-operation.md)을 참조하세요.  
  
-   <xref:System.AsyncCallback> 대리자를 사용하여 작업이 완료될 때 호출할 메서드를 지정합니다. 이 방법을 설명하는 예제는 [Using an AsyncCallback Delegate to End an Asynchronous Operation](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-to-end-an-asynchronous-operation.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [EAP(이벤트 기반 비동기 패턴)](../../../docs/standard/asynchronous-programming-patterns/event-based-asynchronous-pattern-eap.md)  
 [동기 메서드를 비동기 방식으로 호출](../../../docs/standard/asynchronous-programming-patterns/calling-synchronous-methods-asynchronously.md)  
 [AsyncCallback 대리자 및 상태 개체 사용](../../../docs/standard/asynchronous-programming-patterns/using-an-asynccallback-delegate-and-state-object.md)
