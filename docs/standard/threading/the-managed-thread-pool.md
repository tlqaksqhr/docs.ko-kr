---
title: "관리되는 스레드 풀"
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
- cpp
helpviewer_keywords:
- thread pooling [.NET Framework]
- thread pools [.NET Framework]
- threading [.NET Framework], thread pool
- threading [.NET Framework], pooling
ms.assetid: 2be05b06-a42e-4c9d-a739-96c21d673927
caps.latest.revision: "24"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 38032fccce1a8f6f7cbcb3bbd3d3f9d008a74141
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="the-managed-thread-pool"></a>관리되는 스레드 풀
<xref:System.Threading.ThreadPool> 클래스는 시스템에서 관리하는 작업자 스레드 풀을 응용 프로그램에 제공하여 스레드 관리 대신 응용 프로그램 작업에 집중할 수 있게 해줍니다. 후순위 처리가 필요한 간단한 작업이 있는 경우 관리되는 스레드 풀을 통해 쉽게 여러 스레드를 활용할 수 있습니다. 예를 들어 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]부터는 스레드 풀 스레드에서 비동기 작업을 수행하는 <xref:System.Threading.Tasks.Task> 및 <xref:System.Threading.Tasks.Task%601> 개체를 만들 수 있습니다.  
  
> [!NOTE]
>  [!INCLUDE[net_v20SP1_long](../../../includes/net-v20sp1-long-md.md)]부터 스레드 풀의 처리량이 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]의 이전 릴리스에서 병목으로 식별된 세 가지 주요 영역(큐에 작업 대기, 스레드 풀 스레드 디스패치 및 I/O 완료 스레드 디스패치)에서 크게 향상되었습니다. 이 기능을 사용하려면 응용 프로그램이 [!INCLUDE[net_v35_long](../../../includes/net-v35-long-md.md)] 이상을 대상으로 해야 합니다.  
  
 .NET Framework version 2.0에서는 사용자 인터페이스와 상호 작용하는 백그라운드 작업을 위해 사용자 인터페이스 스레드에서 발생한 이벤트를 통해 통신하는 <xref:System.ComponentModel.BackgroundWorker> 클래스도 제공합니다.  
  
 .NET Framework는 비동기 I/O 완료, 타이머 콜백, 등록된 대기 작업, 대리자를 사용한 비동기 메서드 호출 및 <xref:System.Net> 소켓 연결을 비롯한 다양한 용도로 스레드 풀 스레드를 사용합니다.  
  
## <a name="when-not-to-use-thread-pool-threads"></a>스레드 풀 스레드를 사용하지 않아야 하는 경우  
 스레드 풀 스레드를 사용하는 대신 고유한 스레드를 만들고 관리하는 것이 적절한 여러 가지 시나리오가 있습니다.  
  
-   포그라운드 스레드가 필요합니다.  
  
-   스레드가 특정 우선 순위를 가져야 합니다.  
  
-   스레드가 오랜 시간 동안 차단되게 하는 작업이 있습니다. 스레드 풀에 최대 개수의 스레드가 있으므로 차단된 스레드 풀 스레드 수가 많으면 작업이 시작되지 않을 수 있습니다.  
  
-   단일 스레드 아파트에 스레드를 배치해야 합니다. 모든 <xref:System.Threading.ThreadPool> 스레드는 다중 스레드 아파트에 있습니다.  
  
-   스레드와 연결된 안정적인 ID가 있거나 스레드를 작업 전용으로 사용해야 합니다.  
  
## <a name="thread-pool-characteristics"></a>스레드 풀 특징  
 스레드 풀 스레드는 백그라운드 스레드입니다. 참조 [포그라운드 및 백그라운드 스레드](../../../docs/standard/threading/foreground-and-background-threads.md)합니다. 각 스레드는 기본 스택 크기를 사용하고, 기본 우선 순위로 실행되며, 다중 스레드 아파트에 있습니다.  
  
 프로세스당 하나의 스레드 풀만 있습니다.  
  
### <a name="exceptions-in-thread-pool-threads"></a>스레드 풀 스레드의 예외  
 스레드 풀 스레드에 처리되지 않은 예외가 있으면 프로세스가 종료됩니다. 이 규칙에는 다음 세 가지 예외 사항이 있습니다.  
  
-   <xref:System.Threading.Thread.Abort%2A>가 호출되었으므로 스레드 풀 스레드에서 <xref:System.Threading.ThreadAbortException>이 발생합니다.  
  
-   응용 프로그램 도메인이 언로드되고 있으므로 스레드 풀 스레드에서 <xref:System.AppDomainUnloadedException>이 발생합니다.  
  
-   공용 언어 런타임 또는 호스트 프로세스에서 스레드를 종료합니다.  
  
 자세한 내용은 참조 [관리 되는 스레드의 예외](../../../docs/standard/threading/exceptions-in-managed-threads.md)합니다.  
  
> [!NOTE]
>  .NET Framework 버전 1.0 및 1.1에서는 공용 언어 런타임이 스레드 풀 스레드에서 처리되지 않은 예외를 자동으로 포착합니다. 이는 손상된 응용 프로그램 상태일 수 있으며 결국 응용 프로그램이 중단되게 하여 디버그하기 어려울 수 있습니다.  
  
### <a name="maximum-number-of-thread-pool-threads"></a>스레드 풀 스레드의 최대 개수  
 스레드 풀에 대기할 수 있는 작업 수는 사용 가능한 메모리에 의해서만 제한됩니다. 그러나 스레드 풀은 동시에 프로세스에서 활성화될 수 있는 스레드 수를 제한합니다. [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]부터 프로세스에 대한 스레드 풀의 기본 크기는 가상 주소 공간의 크기와 같은 여러 요인에 따라 달라집니다. 프로세스에서 <xref:System.Threading.ThreadPool.GetMaxThreads%2A> 메서드를 호출하여 스레드 수를 확인할 수 있습니다.  
  
 <xref:System.Threading.ThreadPool.GetMaxThreads%2A> 및 <xref:System.Threading.ThreadPool.SetMaxThreads%2A> 메서드를 사용하여 최대 스레드 수를 제어할 수 있습니다.  
  
> [!NOTE]
>  .NET Framework 버전 1.0 및 1.1에서는 관리 코드에서 스레드 풀의 크기를 설정할 수 없습니다. 공용 언어 런타임을 호스트하는 코드에서 mscoree.h에 정의된 `CorSetMaxThreads`를 사용하여 크기를 설정할 수 있습니다.  
  
### <a name="thread-pool-minimums"></a>스레드 풀 최소값  
 스레드 풀은 각 범주에 대해 지정된 최소값에 도달할 때까지 요청 시 새 작업자 스레드 또는 I/O 완료 스레드를 제공합니다. <xref:System.Threading.ThreadPool.GetMinThreads%2A> 메서드를 사용하여 이러한 최소값을 가져올 수 있습니다.  
  
> [!NOTE]
>  요구가 적을 때는 실제 스레드 풀 스레드 수가 최소값보다 작을 수 있습니다.  
  
 최소값에 도달하면 스레드 풀이 추가 스레드를 만들거나 일부 작업이 완료될 때까지 기다릴 수 있습니다. [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]부터는 스레드 풀이 시간 단위당 완료되는 작업 수로 정의된 처리량을 최적화하기 위해 작업자 스레드를 만들고 소멸시킵니다. 스레드가 너무 적으면 사용 가능한 리소스가 효율적으로 사용되지 않는 반면, 너무 많으면 리소스 경합이 증가할 수 있습니다.  
  
> [!CAUTION]
>  <xref:System.Threading.ThreadPool.SetMinThreads%2A> 메서드를 사용하여 유휴 상태 스레드의 최소 개수를 늘릴 수 있습니다. 그러나 이러한 값을 불필요하게 늘리면 성능 문제가 발생할 수 있습니다. 너무 많은 작업이 동시에 시작되는 경우 모두 속도가 느린 것처럼 나타날 수 있습니다. 대부분의 경우 스레드 풀은 고유한 스레드 할당 알고리즘에서 성능이 향상됩니다.  
  
## <a name="skipping-security-checks"></a>보안 검사 건너뛰기  
 스레드 풀은 <xref:System.Threading.ThreadPool.UnsafeQueueUserWorkItem%2A?displayProperty=nameWithType> 및 <xref:System.Threading.ThreadPool.UnsafeRegisterWaitForSingleObject%2A?displayProperty=nameWithType> 메서드도 제공합니다. 호출자 스택이 큐에 대기 중인 작업을 실행하는 동안 수행되는 보안 검사와 관련이 없는 경우에만 이러한 메서드를 사용합니다. <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A>및 <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A> 둘 다 스레드가 작업 실행을 시작할 때 스레드 풀 스레드 스택에 병합 됩니다 호출자 스택을 캡처합니다. 보안 검사가 필요한 경우 전체 스택을 검사해야 합니다. 검사를 통해 안전성이 제공되지만 성능이 저하되는 단점도 있습니다.  
  
## <a name="using-the-thread-pool"></a>스레드 풀 사용  
 부터는 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]를 사용 하는 스레드 풀을 사용 하는 가장 쉬운 방법은 [라이브러리 TPL (작업 병렬)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)합니다. 기본적으로 <xref:System.Threading.Tasks.Task> 및 <xref:System.Threading.Tasks.Task%601>과 같은 병렬 라이브러리 형식은 스레드 풀 스레드를 사용하여 작업을 실행합니다. 관리 코드에서 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType>(또는 비관리 코드에서 `CorQueueUserWorkItem`)을 호출하고 작업을 수행하는 메서드를 나타내는 <xref:System.Threading.WaitCallback> 대리자를 전달하여 스레드 풀을 사용할 수도 있습니다. 스레드 풀을 사용하는 또 다른 방법은 <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A?displayProperty=nameWithType> 메서드를 사용하고 신호를 받거나 시간 초과된 경우 <xref:System.Threading.WaitOrTimerCallback> 대리자가 나타내는 메서드를 호출하는 <xref:System.Threading.WaitHandle>을 전달하여 대기 작업과 관련된 작업 항목을 큐에 대기합니다. 스레드 풀 스레드는 콜백 메서드를 호출하는 데 사용됩니다.  
  
## <a name="threadpool-examples"></a>ThreadPool 예제  
 이 섹션의 코드 예제에서는 <xref:System.Threading.Tasks.Task> 클래스, <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A?displayProperty=nameWithType> 메서드 및 <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A?displayProperty=nameWithType> 메서드를 사용하여 스레드 풀을 보여 줍니다.  
  
-   [작업 병렬 라이브러리와 비동기 작업 실행](#TaskParallelLibrary)  
  
-   [QueueUserWorkItem으로 비동기적으로 코드 실행](#ExecuteCodeWithQUWI)  
  
-   [QueueUserWorkItem에 대 한 작업 데이터 제공](#TaskDataForQUWI)  
  
-   [RegisterWaitForSingleObject 사용](#RegisterWaitForSingleObject)  
  
<a name="TaskParallelLibrary"></a>   
### <a name="executing-asynchronous-tasks-with-the-task-parallel-library"></a>작업 병렬 라이브러리를 사용하여 비동기 작업 실행  
 다음 예제에서는 <xref:System.Threading.Tasks.TaskFactory.StartNew%2A?displayProperty=nameWithType> 메서드를 호출하여 <xref:System.Threading.Tasks.Task> 개체를 만들고 사용하는 방법을 보여 줍니다. 사용 하는 예제에 대 한는 <xref:System.Threading.Tasks.Task%601> 비동기 작업에서 값을 반환 하는 클래스 [하는 방법: 작업에서 값을 반환할](../../../docs/standard/parallel-programming/how-to-return-a-value-from-a-task.md)합니다.  
  
 [!code-csharp[System.Threading.Tasks.Task#01](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.threading.tasks.task/cs/startnew.cs#01)]
 [!code-vb[System.Threading.Tasks.Task#01](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.threading.tasks.task/vb/startnew.vb#01)]  
  
<a name="ExecuteCodeWithQUWI"></a>   
### <a name="executing-code-asynchronously-with-queueuserworkitem"></a>QueueUserWorkItem을 사용하여 비동기적으로 코드 실행  
 다음 예제에서는 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> 메서드를 사용하여 `ThreadProc` 메서드가 나타내는 매우 간단한 작업을 큐에 대기합니다.  
  
 [!code-cpp[Conceptual.ThreadPool#1](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.threadpool/cpp/source1.cpp#1)]
 [!code-csharp[Conceptual.ThreadPool#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.threadpool/cs/source1.cs#1)]
 [!code-vb[Conceptual.ThreadPool#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.threadpool/vb/source1.vb#1)]  
  
<a name="TaskDataForQUWI"></a>   
### <a name="supplying-task-data-for-queueuserworkitem"></a>QueueUserWorkItem에 대한 작업 데이터 제공  
 다음 코드 예제에서는 <xref:System.Threading.ThreadPool.QueueUserWorkItem%2A> 메서드를 사용하여 작업을 큐에 대기하고 작업에 대한 데이터를 제공합니다.  
  
 [!code-cpp[Conceptual.ThreadPool#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.threadpool/cpp/source2.cpp#2)]
 [!code-csharp[Conceptual.ThreadPool#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.threadpool/cs/source2.cs#2)]
 [!code-vb[Conceptual.ThreadPool#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.threadpool/vb/source2.vb#2)]  
  
<a name="RegisterWaitForSingleObject"></a>   
### <a name="using-registerwaitforsingleobject"></a>RegisterWaitForSingleObject 사용  
 다음 예제에서는 여러 가지 스레딩 기능을 보여 줍니다.  
  
-   <xref:System.Threading.ThreadPool.RegisterWaitForSingleObject%2A> 메서드를 사용하여 <xref:System.Threading.ThreadPool> 스레드에서 실행할 작업을 큐에 대기.  
  
-   <xref:System.Threading.AutoResetEvent>를 사용하여 실행할 작업에 신호 보내기. 참조 [EventWaitHandle, AutoResetEvent, CountdownEvent, ManualResetEvent](../../../docs/standard/threading/eventwaithandle-autoresetevent-countdownevent-manualresetevent.md)합니다.  
  
-   <xref:System.Threading.WaitOrTimerCallback> 대리자를 사용하여 시간 초과 및 신호 모두 처리.  
  
-   <xref:System.Threading.RegisteredWaitHandle>을 사용하여 큐에 대기 중인 작업 취소.  
  
 [!code-cpp[Conceptual.ThreadPool#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.threadpool/cpp/source3.cpp#3)]
 [!code-csharp[Conceptual.ThreadPool#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.threadpool/cs/source3.cs#3)]
 [!code-vb[Conceptual.ThreadPool#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.threadpool/vb/source3.vb#3)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Threading.ThreadPool>  
 <xref:System.Threading.Tasks.Task>  
 <xref:System.Threading.Tasks.Task%601>  
 [TPL(작업 병렬 라이브러리)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)  
 [TPL(작업 병렬 라이브러리)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)  
 [방법: 작업에서 값 반환](../../../docs/standard/parallel-programming/how-to-return-a-value-from-a-task.md)  
 [스레딩 개체 및 기능](../../../docs/standard/threading/threading-objects-and-features.md)  
 [스레드 및 스레딩](../../../docs/standard/threading/threads-and-threading.md)  
 [비동기 파일 I/O](../../../docs/standard/io/asynchronous-file-i-o.md)  
 [타이머](../../../docs/standard/threading/timers.md)
