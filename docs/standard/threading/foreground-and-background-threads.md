---
title: "포그라운드 및 백그라운드 스레드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], foreground
- threading [.NET Framework], background
- foreground threads
- background threads
ms.assetid: cfe0d632-dd35-47e0-91ad-f742a444005e
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 42ad427fc2c1175c0d9b333aa418aea039f11a35
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="foreground-and-background-threads"></a><span data-ttu-id="1d81f-102">포그라운드 및 백그라운드 스레드</span><span class="sxs-lookup"><span data-stu-id="1d81f-102">Foreground and Background Threads</span></span>
<span data-ttu-id="1d81f-103">관리 되는 스레드는 백그라운드 스레드 또는 포그라운드 스레드입니다.</span><span class="sxs-lookup"><span data-stu-id="1d81f-103">A managed thread is either a background thread or a foreground thread.</span></span> <span data-ttu-id="1d81f-104">백그라운드 스레드는 한 가지 예외로 포그라운드 스레드 동일: 백그라운드 스레드에서 실행 하는 관리 되는 실행 환경을 유지 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d81f-104">Background threads are identical to foreground threads with one exception: a background thread does not keep the managed execution environment running.</span></span> <span data-ttu-id="1d81f-105">관리 되는 프로세스 (.exe 파일은 관리 되는 어셈블리)에서 모든 포그라운드 스레드가 중지 된 후 시스템 모든 백그라운드 스레드를 중지 하 고 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d81f-105">Once all foreground threads have been stopped in a managed process (where the .exe file is a managed assembly), the system stops all background threads and shuts down.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1d81f-106">프로세스 종료 때문에 런타임에서 백그라운드 스레드가 중지 되 면 스레드에서 예외가 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d81f-106">When the runtime stops a background thread because the process is shutting down, no exception is thrown in the thread.</span></span> <span data-ttu-id="1d81f-107">그러나 스레드가 중단 되 면 때문에 <xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> 메서드는 응용 프로그램 도메인을 언로드합니다는 <xref:System.Threading.ThreadAbortException> 전경색과 배경색 모두 스레드에서 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d81f-107">However, when threads are stopped because the <xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> method unloads the application domain, a <xref:System.Threading.ThreadAbortException> is thrown in both foreground and background threads.</span></span>  
  
 <span data-ttu-id="1d81f-108">사용 하 여는 <xref:System.Threading.Thread.IsBackground%2A?displayProperty=nameWithType> 속성 스레드는 배경이 나 전경 스레드 되는지 확인 하려면 나 해당 상태를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d81f-108">Use the <xref:System.Threading.Thread.IsBackground%2A?displayProperty=nameWithType> property to determine whether a thread is a background or a foreground thread, or to change its status.</span></span> <span data-ttu-id="1d81f-109">스레드 수 설정 변경할 수을 백그라운드 스레드로 언제 든 지 해당 <xref:System.Threading.Thread.IsBackground%2A> 속성을 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="1d81f-109">A thread can be changed to a background thread at any time by setting its <xref:System.Threading.Thread.IsBackground%2A> property to `true`.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="1d81f-110">스레드 포그라운드 또는 백그라운드 상태 결과 스레드에서 처리 되지 않은 예외가 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d81f-110">The foreground or background status of a thread does not affect the outcome of an unhandled exception in the thread.</span></span> <span data-ttu-id="1d81f-111">.NET Framework 버전 2.0에서에서 응용 프로그램이 종료 포그라운드 또는 백그라운드 스레드에서 처리 되지 않은 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="1d81f-111">In the .NET Framework version 2.0, an unhandled exception in either foreground or background threads results in termination of the application.</span></span> <span data-ttu-id="1d81f-112">참조 [관리 되는 스레드의 예외](../../../docs/standard/threading/exceptions-in-managed-threads.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1d81f-112">See [Exceptions in Managed Threads](../../../docs/standard/threading/exceptions-in-managed-threads.md).</span></span>  
  
 <span data-ttu-id="1d81f-113">관리 되는 스레드 풀에 속해 있는 스레드 (즉, 짝수인 스레드에 <xref:System.Threading.Thread.IsThreadPoolThread%2A> 속성은 `true`)는 백그라운드 스레드입니다.</span><span class="sxs-lookup"><span data-stu-id="1d81f-113">Threads that belong to the managed thread pool (that is, threads whose <xref:System.Threading.Thread.IsThreadPoolThread%2A> property is `true`) are background threads.</span></span> <span data-ttu-id="1d81f-114">비관리 코드에서 관리 되는 실행 환경에 들어가는 모든 스레드 백그라운드 스레드도 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d81f-114">All threads that enter the managed execution environment from unmanaged code are marked as background threads.</span></span> <span data-ttu-id="1d81f-115">만들고 새 시작에 의해 생성 된 모든 스레드가 <xref:System.Threading.Thread> 기본 포그라운드 스레드에서 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="1d81f-115">All threads generated by creating and starting a new <xref:System.Threading.Thread> object are by default foreground threads.</span></span>  
  
 <span data-ttu-id="1d81f-116">스레드를 사용 하 여 소켓 연결 등의 동작을 모니터링 하는 경우 설정의 <xref:System.Threading.Thread.IsBackground%2A> 속성을 `true` 스레드가 사용 해도 프로세스의 종료 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d81f-116">If you use a thread to monitor an activity, such as a socket connection, set its <xref:System.Threading.Thread.IsBackground%2A> property to `true` so that the thread does not prevent your process from terminating.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d81f-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1d81f-117">See Also</span></span>  
 <xref:System.Threading.Thread.IsBackground%2A?displayProperty=nameWithType>  
 <xref:System.Threading.Thread>  
 <xref:System.Threading.ThreadAbortException>
