---
title: 포그라운드 및 백그라운드 스레드
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], foreground
- threading [.NET Framework], background
- foreground threads
- background threads
ms.assetid: cfe0d632-dd35-47e0-91ad-f742a444005e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 476dc75a569224db405eb7498ecb35eb6bda24d8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33583078"
---
# <a name="foreground-and-background-threads"></a><span data-ttu-id="d091a-102">포그라운드 및 백그라운드 스레드</span><span class="sxs-lookup"><span data-stu-id="d091a-102">Foreground and Background Threads</span></span>
<span data-ttu-id="d091a-103">관리되는 스레드는 백그라운드 스레드 또는 포그라운드 스레드입니다.</span><span class="sxs-lookup"><span data-stu-id="d091a-103">A managed thread is either a background thread or a foreground thread.</span></span> <span data-ttu-id="d091a-104">백그라운드 스레드는 하나의 예외가 있는 포그라운드 스레드와 동일합니다. 백그라운드 스레드는 관리되는 실행 환경을 계속 실행하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d091a-104">Background threads are identical to foreground threads with one exception: a background thread does not keep the managed execution environment running.</span></span> <span data-ttu-id="d091a-105">모든 포그라운드 스레드가 관리되는 프로세스(.exe 파일이 관리되는 어셈블리인 프로세스)에서 중지되면 시스템이 모든 백그라운드 스레드를 중지하고 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="d091a-105">Once all foreground threads have been stopped in a managed process (where the .exe file is a managed assembly), the system stops all background threads and shuts down.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d091a-106">프로세스가 종료되고 있기 때문에 런타임이 백그라운드 스레드를 중지하면 스레드에서 예외가 throw되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d091a-106">When the runtime stops a background thread because the process is shutting down, no exception is thrown in the thread.</span></span> <span data-ttu-id="d091a-107">그러나 <xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> 메서드가 응용 프로그램 도메인을 언로드하기 때문에 스레드가 중지되면 포그라운드 및 백그라운드 스레드 모두에서 <xref:System.Threading.ThreadAbortException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="d091a-107">However, when threads are stopped because the <xref:System.AppDomain.Unload%2A?displayProperty=nameWithType> method unloads the application domain, a <xref:System.Threading.ThreadAbortException> is thrown in both foreground and background threads.</span></span>  
  
 <span data-ttu-id="d091a-108"><xref:System.Threading.Thread.IsBackground%2A?displayProperty=nameWithType> 속성을 사용하여 스레드가 백그라운드 또는 포그라운드 스레드인지 확인하거나 해당 상태를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="d091a-108">Use the <xref:System.Threading.Thread.IsBackground%2A?displayProperty=nameWithType> property to determine whether a thread is a background or a foreground thread, or to change its status.</span></span> <span data-ttu-id="d091a-109">언제든지 <xref:System.Threading.Thread.IsBackground%2A> 속성을 `true`로 설정하여 스레드를 백그라운드 스레드로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d091a-109">A thread can be changed to a background thread at any time by setting its <xref:System.Threading.Thread.IsBackground%2A> property to `true`.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d091a-110">스레드의 포그라운드 또는 백그라운드 상태는 스레드에서 처리되지 않은 예외의 결과에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d091a-110">The foreground or background status of a thread does not affect the outcome of an unhandled exception in the thread.</span></span> <span data-ttu-id="d091a-111">.NET Framework 버전 2.0에서는 포그라운드 또는 백그라운드 스레드에서 처리되지 않은 예외로 인해 응용 프로그램이 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="d091a-111">In the .NET Framework version 2.0, an unhandled exception in either foreground or background threads results in termination of the application.</span></span> <span data-ttu-id="d091a-112">[관리되는 스레드의 예외](../../../docs/standard/threading/exceptions-in-managed-threads.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d091a-112">See [Exceptions in Managed Threads](../../../docs/standard/threading/exceptions-in-managed-threads.md).</span></span>  
  
 <span data-ttu-id="d091a-113">관리되는 스레드 풀(<xref:System.Threading.Thread.IsThreadPoolThread%2A> 속성이 `true`인 스레드)에 속하는 스레드는 백그라운드 스레드입니다.</span><span class="sxs-lookup"><span data-stu-id="d091a-113">Threads that belong to the managed thread pool (that is, threads whose <xref:System.Threading.Thread.IsThreadPoolThread%2A> property is `true`) are background threads.</span></span> <span data-ttu-id="d091a-114">비관리 코드에서 관리되는 실행 환경에 들어가는 모든 스레드는 백그라운드 스레드로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d091a-114">All threads that enter the managed execution environment from unmanaged code are marked as background threads.</span></span> <span data-ttu-id="d091a-115">새 <xref:System.Threading.Thread> 개체를 만들고 시작하여 생성된 모든 스레드는 기본적으로 포그라운드 스레드입니다.</span><span class="sxs-lookup"><span data-stu-id="d091a-115">All threads generated by creating and starting a new <xref:System.Threading.Thread> object are by default foreground threads.</span></span>  
  
 <span data-ttu-id="d091a-116">스레드를 사용하여 소켓 연결과 같은 활동을 모니터링하는 경우 스레드가 프로세스 종료를 차단하지 않도록 <xref:System.Threading.Thread.IsBackground%2A> 속성을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d091a-116">If you use a thread to monitor an activity, such as a socket connection, set its <xref:System.Threading.Thread.IsBackground%2A> property to `true` so that the thread does not prevent your process from terminating.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d091a-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d091a-117">See Also</span></span>  
 <xref:System.Threading.Thread.IsBackground%2A?displayProperty=nameWithType>  
 <xref:System.Threading.Thread>  
 <xref:System.Threading.ThreadAbortException>
