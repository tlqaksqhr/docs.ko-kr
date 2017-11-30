---
title: "판독기 및 작성기 잠금"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ReaderWriterLock class, about ReaderWriterLock class
- threading [.NET Framework], ReaderWriterLock class
ms.assetid: 8c71acf2-2c18-4f4d-8cdb-0728639265fd
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: df06e83165906199774f99de4140ace9b7396cbb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="reader-writer-locks"></a><span data-ttu-id="620b3-102">판독기 및 작성기 잠금</span><span class="sxs-lookup"><span data-stu-id="620b3-102">Reader-Writer Locks</span></span>
<span data-ttu-id="620b3-103"><xref:System.Threading.ReaderWriterLockSlim> 클래스 여러 스레드가 동시에 리소스를 읽을 수 있지만 스레드를 리소스에 쓰려면 단독 잠금을 대기 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="620b3-103">The <xref:System.Threading.ReaderWriterLockSlim> class enables multiple threads to read a resource concurrently, but requires a thread to wait for an exclusive lock in order to write to the resource.</span></span>  
  
 <span data-ttu-id="620b3-104">사용할 수 있습니다는 <xref:System.Threading.ReaderWriterLockSlim> 응용 프로그램에 공유 리소스에 액세스 하는 스레드 간 공동 작업 동기화를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="620b3-104">You might use a <xref:System.Threading.ReaderWriterLockSlim> in your application to provide cooperative synchronization among threads that access a shared resource.</span></span> <span data-ttu-id="620b3-105">잠금이 수행 되는 <xref:System.Threading.ReaderWriterLockSlim> 자체입니다.</span><span class="sxs-lookup"><span data-stu-id="620b3-105">Locks are taken on the <xref:System.Threading.ReaderWriterLockSlim> itself.</span></span>  
  
 <span data-ttu-id="620b3-106">스레드가 무시 하지 않도록에서 제공 되는 잠금 확인 해야 모든 스레드 동기화 메커니즘을 사용 하 여 처럼 <xref:System.Threading.ReaderWriterLockSlim>합니다.</span><span class="sxs-lookup"><span data-stu-id="620b3-106">As with any thread synchronization mechanism, you must ensure that no threads bypass the locking that is provided by <xref:System.Threading.ReaderWriterLockSlim>.</span></span> <span data-ttu-id="620b3-107">이 보장 하는 한 가지 방법은 공유 리소스를 캡슐화 하는 클래스를 디자인 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="620b3-107">One way to ensure this is to design a class that encapsulates the shared resource.</span></span> <span data-ttu-id="620b3-108">이 클래스는 개인 공유 리소스에 액세스 하 고 개인을 사용 하는 멤버를 제공 <xref:System.Threading.ReaderWriterLockSlim> 동기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="620b3-108">This class would provide members that access the private shared resource and that use a private <xref:System.Threading.ReaderWriterLockSlim> for synchronization.</span></span> <span data-ttu-id="620b3-109">예를 들어 참조에 대 한 코드 예제는 <xref:System.Threading.ReaderWriterLockSlim> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="620b3-109">For an example, see the code example for the <xref:System.Threading.ReaderWriterLockSlim> class.</span></span> <span data-ttu-id="620b3-110"><xref:System.Threading.ReaderWriterLockSlim>개별 개체를 동기화 할 수 있을 만큼 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="620b3-110"><xref:System.Threading.ReaderWriterLockSlim> is efficient enough to be used to synchronize individual objects.</span></span>  
  
 <span data-ttu-id="620b3-111">응용 프로그램을 읽기의 지속 시간을 최소화 및 쓰기 작업을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="620b3-111">Structure your application to minimize the duration of read and write operations.</span></span> <span data-ttu-id="620b3-112">배타적 쓰기 잠금을 이므로 쓰기 작업이 오래 직접 처리량에 영향을 합니다.</span><span class="sxs-lookup"><span data-stu-id="620b3-112">Long write operations affect throughput directly because the write lock is exclusive.</span></span> <span data-ttu-id="620b3-113">긴 작업 블록 대기 기록기 읽고 쓰기 액세스를 위해 하나 이상의 스레드가 대기 하는 경우 읽기 액세스를 요청 하는 스레드도 차단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="620b3-113">Long read operations block waiting writers, and if at least one thread is waiting for write access, threads that request read access will be blocked as well.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="620b3-114">[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 는 두 개의 판독기 및 작성기 잠금 <xref:System.Threading.ReaderWriterLockSlim> 및 <xref:System.Threading.ReaderWriterLock>합니다.</span><span class="sxs-lookup"><span data-stu-id="620b3-114">The [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] has two reader-writer locks, <xref:System.Threading.ReaderWriterLockSlim> and <xref:System.Threading.ReaderWriterLock>.</span></span> <span data-ttu-id="620b3-115"><xref:System.Threading.ReaderWriterLockSlim>새로운 개발의 모든 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="620b3-115"><xref:System.Threading.ReaderWriterLockSlim> is recommended for all new development.</span></span> <span data-ttu-id="620b3-116"><xref:System.Threading.ReaderWriterLockSlim>유사한 <xref:System.Threading.ReaderWriterLock>, 재귀 및 업그레이드 및 잠금 상태를 다운 그레이드에 대 한 규칙 간소화 합니다.</span><span class="sxs-lookup"><span data-stu-id="620b3-116"><xref:System.Threading.ReaderWriterLockSlim> is similar to <xref:System.Threading.ReaderWriterLock>, but it has simplified rules for recursion and for upgrading and downgrading lock state.</span></span> <span data-ttu-id="620b3-117"><xref:System.Threading.ReaderWriterLockSlim>대부분의 경우 잠재적인 교착 상태를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="620b3-117"><xref:System.Threading.ReaderWriterLockSlim> avoids many cases of potential deadlock.</span></span> <span data-ttu-id="620b3-118">또한의 성능 <xref:System.Threading.ReaderWriterLockSlim> 보다 훨씬 더 좋습니다 <xref:System.Threading.ReaderWriterLock>합니다.</span><span class="sxs-lookup"><span data-stu-id="620b3-118">In addition, the performance of <xref:System.Threading.ReaderWriterLockSlim> is significantly better than <xref:System.Threading.ReaderWriterLock>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="620b3-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="620b3-119">See Also</span></span>  
 <xref:System.Threading.ReaderWriterLockSlim>  
 <xref:System.Threading.ReaderWriterLock>  
 [<span data-ttu-id="620b3-120">스레딩</span><span class="sxs-lookup"><span data-stu-id="620b3-120">Threading</span></span>](../../../docs/standard/threading/index.md)  
 [<span data-ttu-id="620b3-121">스레딩 개체 및 기능</span><span class="sxs-lookup"><span data-stu-id="620b3-121">Threading Objects and Features</span></span>](../../../docs/standard/threading/threading-objects-and-features.md)
