---
title: "스레딩 (C#) | Microsoft Docs"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 236d157d-37c0-4ee8-89fc-721e6c596325
caps.latest.revision: 4
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: 31905a37f09db5f5192123f0118252fbe8b02eff
ms.openlocfilehash: e3f213b43c2f05a5afef1db7aec8b9c2695df989
ms.contentlocale: ko-kr
ms.lasthandoff: 06/12/2017

---
# <a name="threading-c"></a>스레딩(C#)
스레딩 사용 하면 C# 프로그램에서 한 번에 둘 이상의 작업을 진행할 수 있도록 동시 처리를 수행 합니다. 예를 들어 스레딩 사용자 입력을에서 모니터링, 백그라운드 작업을 수행할 및 동시 입력 스트림을 처리에 사용할 수는 있습니다.  
  
 스레드는 다음과 같은 속성이:  
  
-   동시 처리를 수행 하 여 프로그램 스레드를 사용 합니다.  
  
-   .NET Framework <xref:System.Threading> 스레드를 보다 쉽게 사용 하 여 네임 스페이스 만듭니다.  
  
-   스레드는 응용 프로그램의 리소스를 공유 합니다. 자세한 내용은 참조 [스레드 및 스레딩 사용](https://msdn.microsoft.com/library/e1dx6b2h)합니다.  
  
 기본적으로 C# 프로그램에는 하나의 스레드가 있습니다. 그러나 보조 스레드 만들고 사용할 수 있는 기본 스레드에서 동시에 코드를 실행 하는 데 사용 합니다. 이러한 스레드는 일반적으로 라고 *작업자 스레드*합니다.  
  
 기본 스레드에서 상관 없이 오래 걸리는 작업이 나 시간이 중요 한 작업을 수행 하 작업자 스레드를 사용할 수 있습니다. 예를 들어 작업자 스레드 이전 요청이 완료 될 때까지 기다리지 않고 들어오는 요청을 수행 하는 서버 응용 프로그램에서 자주 사용 됩니다. 작업자 스레드를 데스크톱 응용 프로그램에서 "백그라운드" 작업을 수행할 때도 사용 되도록 사용자 인터페이스 요소-사용자 작업에 응답성을 유지 하는 주 스레드에-합니다.  
  
 처리량 및 응답성 문제를 해결 스레딩 되지만 경합 상태와 교착 상태와 같은 리소스 공유 문제가 발생할 수 있습니다. 다중 스레드는 다양 한 파일 핸들 및 네트워크 연결 같은 리소스를 필요로 하는 작업에 가장 적합 합니다. 단일 리소스를 여러 스레드를 할당 하면 동기화 문제가 발생할 수 이며 스레드가 다른 스레드에서 기다리는 자주 차단 기다리느라는 여러 스레드를 사용 하 여 합니다.  
  
 일반적인 전략 시간이 많이 걸리는 수행 하는 작업자 스레드 또는 다른 스레드에서 사용 되는 리소스를 많이 필요로 하지 않는 시간 위험 작업을 사용 하는 것입니다. 당연히 프로그램에서 일부 리소스 여러 스레드에서 액세스 해야 합니다. 이러한 경우에는 <xref:System.Threading> 네임 스페이스 스레드를 동기화 하기 위한 클래스를 제공 합니다. 이러한 클래스에는 <xref:System.Threading.Mutex>, <xref:System.Threading.Monitor>, <xref:System.Threading.Interlocked>, <xref:System.Threading.AutoResetEvent>, 및 <xref:System.Threading.ManualResetEvent>합니다.  
  
 이러한 클래스의 일부 또는 모든 다중 스레드 작업을 동기화 하는 데 사용할 수 있지만 스레딩에 대 한 지원이 C# 언어에서 지원 됩니다. 예를 들어는 [Lock 문](../../../../csharp/language-reference/keywords/lock-statement.md) 암시적으로 사용 하 여 동기화 기능을 제공 <xref:System.Threading.Monitor>합니다.  
  
> [!NOTE]
>  부터는 [!INCLUDE[net_v40_long](~/includes/net-v40-long-md.md)], 다중 스레드 프로그래밍으로 상당히 단순화 되었지만 <xref:System.Threading.Tasks.Parallel?displayProperty=fullName> 및 <xref:System.Threading.Tasks.Task?displayProperty=fullName> 클래스, [PLINQ (병렬 LINQ)](https://msdn.microsoft.com/library/dd460688), 새 동시 컬렉션 클래스에 <xref:System.Collections.Concurrent?displayProperty=fullName> 네임 스페이스, 아닌 작업의 개념을 기반으로 하는 새로운 프로그래밍 모델. 자세한 내용은 [병렬 프로그래밍](https://msdn.microsoft.com/library/dd460693)을 참조하세요.  
  
## <a name="related-topics"></a>관련 항목  
  
|제목|설명|  
|-----------|-----------------|  
|[다중 스레드 응용 프로그램(C#)](../../../../csharp/programming-guide/concepts/threading/multithreaded-applications.md)|만들고 스레드를 사용 하는 방법을 설명 합니다.|  
|[매개 변수 및 반환 값에 대 한 다중 스레드 프로시저 (C#)](../../../../csharp/programming-guide/concepts/threading/parameters-and-return-values-for-multithreaded-procedures.md)|전달 하 고 다중 스레드 응용 프로그램 매개 변수를 반환 하는 방법에 설명 합니다.|  
|[연습: BackgroundWorker 구성 요소 (C#)를 사용한 다중 스레딩](../../../../csharp/programming-guide/concepts/threading/walkthrough-multithreading-with-the-backgroundworker-component.md)|단순한 다중 스레드 응용 프로그램을 만드는 방법을 보여 줍니다.|  
|[스레드 동기화(C#)](../../../../csharp/programming-guide/concepts/threading/thread-synchronization.md)|스레드 조작을 제어 하는 방법에 설명 합니다.|  
|[스레드 타이머 (C#)](../../../../csharp/programming-guide/concepts/threading/thread-timers.md)|일정 한 간격 별도 스레드에서 프로시저를 실행 하는 방법에 설명 합니다.|  
|[스레드 풀링 (C#)](../../../../csharp/programming-guide/concepts/threading/thread-pooling.md)|시스템에 의해 관리 되는 작업자 스레드 풀을 사용 하는 방법을 설명 합니다.|  
|[방법: 스레드 풀 (C#) 사용](../../../../csharp/programming-guide/concepts/threading/how-to-use-a-thread-pool.md)|동기화 된 스레드 풀의 다중 스레드 사용을 보여 줍니다.|  
|[스레딩](https://msdn.microsoft.com/library/3e8s7xdd)|.NET Framework에서 스레딩을 구현 하는 방법을 설명 합니다.|
