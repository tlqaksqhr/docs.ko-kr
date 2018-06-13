---
title: 경합 ETW 이벤트
ms.date: 03/30/2017
helpviewer_keywords:
- contention events [.NET Framework]
- ETW, contention events (CLR)
ms.assetid: 6933e753-2f2a-425b-ae84-42138c957d76
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3487b67ea49cecfd0da2b5b3f993ea54d562145d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33397522"
---
# <a name="contention-etw-events"></a><span data-ttu-id="cca73-102">경합 ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="cca73-102">Contention ETW Events</span></span>
<span data-ttu-id="cca73-103">런타임에서 사용되는 <xref:System.Threading.Monitor?displayProperty=nameWithType> 잠금 또는 네이티브 잠금에 대한 경합이 있을 때마다 경합 이벤트가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="cca73-103">Contention events are raised whenever there is contention for <xref:System.Threading.Monitor?displayProperty=nameWithType> locks or native locks used by the runtime.</span></span> <span data-ttu-id="cca73-104">스레드가 잠금을 소유하는 동안 또 다른 스레드가 잠금을 기다리고 있으면 경합이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="cca73-104">Contention occurs when a thread is waiting for a lock while another thread possesses the lock.</span></span>  
  
 <span data-ttu-id="cca73-105">다음 표에서는 경합 이벤트가 발생하는 키워드 및 이벤트 수준을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cca73-105">The following table shows the keyword under which contention events are raised, and the level of the events.</span></span> <span data-ttu-id="cca73-106">자세한 내용은 [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cca73-106">(For more information, see [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)</span></span>  
  
|<span data-ttu-id="cca73-107">이벤트를 발생시키기 위한 키워드</span><span class="sxs-lookup"><span data-stu-id="cca73-107">Keyword for raising the event</span></span>|<span data-ttu-id="cca73-108">수준</span><span class="sxs-lookup"><span data-stu-id="cca73-108">Level</span></span>|  
|-----------------------------------|-----------|  
|<span data-ttu-id="cca73-109">`ContentionKeyword`(0x4000)</span><span class="sxs-lookup"><span data-stu-id="cca73-109">`ContentionKeyword` (0x4000)</span></span>|<span data-ttu-id="cca73-110">정보(4)</span><span class="sxs-lookup"><span data-stu-id="cca73-110">Informational (4)</span></span>|  
  
 <span data-ttu-id="cca73-111">다음 표에서는 이벤트 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cca73-111">The following table shows event information.</span></span>  
  
|<span data-ttu-id="cca73-112">이벤트(event)</span><span class="sxs-lookup"><span data-stu-id="cca73-112">Event</span></span>|<span data-ttu-id="cca73-113">이벤트 ID</span><span class="sxs-lookup"><span data-stu-id="cca73-113">Event ID</span></span>|<span data-ttu-id="cca73-114">발생 시기</span><span class="sxs-lookup"><span data-stu-id="cca73-114">Raised when</span></span>|  
|-----------|--------------|-----------------|  
|`ContentionStart_V1`|<span data-ttu-id="cca73-115">81</span><span class="sxs-lookup"><span data-stu-id="cca73-115">81</span></span>|<span data-ttu-id="cca73-116">경합이 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="cca73-116">Contention starts.</span></span> <span data-ttu-id="cca73-117">이 이벤트에는 스레드가 잠금을 획득하기 위해 대기하기 전의 회전 시간이 포함되지 않습니다. 이 이벤트는 스레드가 잠금을 획득하기 위해 대기하는 경우에만 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="cca73-117">This event does not include the amount of spinning time before a thread waits to acquire a lock; it is raised only when the thread waits to acquire a lock.</span></span>|  
|`ContentionStop`|<span data-ttu-id="cca73-118">81</span><span class="sxs-lookup"><span data-stu-id="cca73-118">81</span></span>|<span data-ttu-id="cca73-119">경합이 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="cca73-119">Contention ends.</span></span>|  
  
 <span data-ttu-id="cca73-120">다음 표에서는 이벤트 데이터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cca73-120">The following table shows event data.</span></span>  
  
|<span data-ttu-id="cca73-121">필드 이름</span><span class="sxs-lookup"><span data-stu-id="cca73-121">Field name</span></span>|<span data-ttu-id="cca73-122">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="cca73-122">Data type</span></span>|<span data-ttu-id="cca73-123">설명</span><span class="sxs-lookup"><span data-stu-id="cca73-123">Description</span></span>|  
|----------------|---------------|-----------------|  
|<span data-ttu-id="cca73-124">플래그</span><span class="sxs-lookup"><span data-stu-id="cca73-124">Flags</span></span>|<span data-ttu-id="cca73-125">win:UInt8</span><span class="sxs-lookup"><span data-stu-id="cca73-125">win:UInt8</span></span>|<span data-ttu-id="cca73-126">0(관리), 1(네이티브).</span><span class="sxs-lookup"><span data-stu-id="cca73-126">0 for managed; 1 for native.</span></span>|  
|<span data-ttu-id="cca73-127">ClrInstanceID</span><span class="sxs-lookup"><span data-stu-id="cca73-127">ClrInstanceID</span></span>|<span data-ttu-id="cca73-128">win:UInt16</span><span class="sxs-lookup"><span data-stu-id="cca73-128">win:UInt16</span></span>|<span data-ttu-id="cca73-129">CLR 인스턴스의 고유 ID.</span><span class="sxs-lookup"><span data-stu-id="cca73-129">Unique ID for the instance of CLR.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="cca73-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cca73-130">See Also</span></span>  
 [<span data-ttu-id="cca73-131">CLR ETW 이벤트</span><span class="sxs-lookup"><span data-stu-id="cca73-131">CLR ETW Events</span></span>](../../../docs/framework/performance/clr-etw-events.md)
