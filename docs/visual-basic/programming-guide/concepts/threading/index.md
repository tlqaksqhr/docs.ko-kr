---
title: 스레딩(Visual Basic)
ms.date: 07/20/2015
ms.assetid: 704bb04b-ff23-471d-ab12-3cec1c2bca59
ms.openlocfilehash: fd1530a2b03c01b0a1cba0ce3ed4e18f2bf29046
ms.sourcegitcommit: 59b51cd7c95c75be85bd6ef715e9ef8c85720bac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37874835"
---
# <a name="threading-visual-basic"></a>스레딩(Visual Basic)
스레딩을 사용하면 Visual Basic 프로그램에서 동시 처리를 수행할 수 있으므로 한 번에 여러 작업을 진행할 수 있습니다. 예를 들어 스레딩을 사용하여 사용자의 입력을 모니터링하고, 백그라운드 작업을 수행하고, 동시 입력 스트림을 처리할 수 있습니다.  
  
 스레드에는 다음과 같은 속성이 있습니다.  
  
-   스레드를 사용하면 프로그램에서 동시 처리를 수행할 수 있습니다.  
  
-   .NET Framework <xref:System.Threading> 네임스페이스를 통해 스레드를 쉽게 사용할 수 있습니다.  
  
-   스레드는 응용 프로그램의 리소스를 공유합니다. 자세한 내용은 [스레드 및 스레딩 사용](../../../../standard/threading/using-threads-and-threading.md)을 참조하세요.  
  
 기본적으로 Visual Basic 프로그램에는 스레드가 하나 있습니다. 그러나 보조 스레드를 만들어 기본 스레드와 함께 코드를 실행하는 데 사용할 수 있습니다. 이러한 스레드를 일반적으로 *작업자 스레드*라고 합니다.  
  
 작업자 스레드는 기본 스레드를 묶어두지 않고서도 시간이 오래 걸리거나 시간이 중요한 작업을 수행하는 데 사용할 수 있습니다. 예를 들어 작업자 스레드는 이전 요청이 완료될 때까지 기다리지 않고서도 서버 응용 프로그램에서 들어오는 요청을 이행하는 데 종종 사용됩니다. 또한 작업자 스레드는 사용자 인터페이스 요소를 구동하는 주 스레드가 사용자 작업에 계속 응답하도록 데스크톱 응용 프로그램에서 "백그라운드" 작업을 수행하는 데 사용됩니다.  
  
 스레딩은 처리량 및 응답성 관련 문제를 해결하지만, 교착 상태 및 경합 상태 같은 리소스 공유 문제를 유발할 수도 있습니다. 여러 스레드는 파일 핸들 및 네트워크 연결 같은 다양한 리소스를 필요로 하는 작업에 적합합니다. 단일 리소스에 여러 스레드를 할당하면 동기화 문제가 발생할 수 있으며, 다른 스레드를 기다릴 때 스레드를 자주 차단하면 여러 스레드를 사용하는 목적에 어긋납니다.  
  
 일반적인 전략은 작업자 스레드를 사용하여, 다른 스레드에서 사용하는 많은 리소스를 필요로 하지 않는 시간이 오래 걸리는 작업이나 시간이 중요한 작업을 수행하는 것입니다. 당연히 여러 스레드에서 프로그램의 일부 리소스에 액세스해야 합니다. 이러한 경우에는 <xref:System.Threading> 네임스페이스에서 스레드 동기화에 대한 클래스를 제공합니다. 이러한 클래스에는 <xref:System.Threading.Mutex>, <xref:System.Threading.Monitor>, <xref:System.Threading.Interlocked>, <xref:System.Threading.AutoResetEvent> 및 <xref:System.Threading.ManualResetEvent>가 있습니다.  
  
 이러한 클래스의 일부 또는 모두를 사용하여 여러 스레드 작업을 동기화할 수 있지만, 스레딩에 대한 일부 지원이 Visual Basic 언어에서 지원됩니다. 예를 들어 [SyncLock 문](../../../../visual-basic/language-reference/statements/synclock-statement.md)은 <xref:System.Threading.Monitor>를 암시적으로 사용하여 동기화 기능을 제공합니다.  
  
> [!NOTE]
>  [!INCLUDE[net_v40_long](~/includes/net-v40-long-md.md)]부터는 <xref:System.Threading.Tasks.Parallel?displayProperty=nameWithType> 및 <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> 클래스, [PLINQ(병렬 LINQ)](https://msdn.microsoft.com/library/dd460688), <xref:System.Collections.Concurrent?displayProperty=nameWithType> 네임스페이스의 새로운 동시 컬렉션 클래스, 그리고 스레드가 아닌 작업 개념을 기반으로 하는 새로운 프로그래밍 모델로 인해 다중 스레드 프로그래밍이 매우 간소화되었습니다. 자세한 내용은 [병렬 프로그래밍](../../../../standard/parallel-programming/index.md)을 참조하세요.  
  
## <a name="related-topics"></a>관련 항목  
  
|제목|설명|  
|-----------|-----------------|  
|[다중 스레드 응용 프로그램(Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md)|스레드를 만들고 사용하는 방법을 설명합니다.|  
|[다중 스레드 프로시저의 매개 변수 및 반환 값(Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md)|다중 스레드 응용 프로그램을 사용하여 매개 변수를 전달하고 반환하는 방법을 설명합니다.|  
|[연습: BackgroundWorker 구성 요소를 사용한 다중 스레딩(Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/walkthrough-multithreading-with-the-backgroundworker-component.md)|간단한 다중 스레드 응용 프로그램을 만드는 방법을 보여 줍니다.|  
|[스레드 동기화(Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-synchronization.md)|스레드 조작을 제어하는 방법을 설명합니다.|  
|[스레드 풀링(Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/thread-pooling.md)|시스템에서 관리하는 작업자 스레드 풀을 사용하는 방법을 설명합니다.|  
|[방법: 스레드 풀 사용(Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/how-to-use-a-thread-pool.md)|스레드 풀에서 여러 스레드의 동기화된 사용을 보여 줍니다.|  
|[스레딩](../../../../standard/threading/index.md)|.NET Framework에서 스레딩을 구현하는 방법을 설명합니다.|
