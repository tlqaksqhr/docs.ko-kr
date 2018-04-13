---
title: 가비지 수집 알림
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- garbage collection, notifications
ms.assetid: e12d8e74-31e3-4035-a87d-f3e66f0a9b89
caps.latest.revision: 23
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: ac951ad1f89d058b06280bc176ca7928a1dc65bf
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="garbage-collection-notifications"></a><span data-ttu-id="3d3b3-102">가비지 수집 알림</span><span class="sxs-lookup"><span data-stu-id="3d3b3-102">Garbage Collection Notifications</span></span>
<span data-ttu-id="3d3b3-103">공용 언어 런타임에서 전체 가비지 수집(즉, 2세대 컬렉션)을 실행하면 성능이 저하될 수 있는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d3b3-103">There are situations in which a full garbage collection (that is, a generation 2 collection) by the common language runtime may adversely affect performance.</span></span> <span data-ttu-id="3d3b3-104">이는 대량의 요청을 처리하는 서버에서 특히 문제가 될 수 있습니다. 이 경우 장기적인 가비지 수집으로 인해 요청 시간이 초과될 수 있습니다. 중요 기간에 전체 수집이 발생하지 않도록 하기 위해 전체 가비지 수집에 근접하고 있다는 알림을 받을 수 있습니다. 그러면 워크로드를 다른 서버 인스턴스로 리디렉션하는 조치를 취할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d3b3-104">This can be an issue particularly with servers that process large volumes of requests; in this case, a long garbage collection can cause a request time-out. To prevent a full collection from occurring during a critical period, you can be notified that a full garbage collection is approaching and then take action to redirect the workload to another server instance.</span></span> <span data-ttu-id="3d3b3-105">또한 현재 서버 인스턴스가 요청을 처리하지 않아도 되는 경우 직접 수집을 유도할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d3b3-105">You can also induce a collection yourself, provided that the current server instance does not need to process requests.</span></span>  
  
 <span data-ttu-id="3d3b3-106"><xref:System.GC.RegisterForFullGCNotification%2A> 메서드는 런타임에서 전체 가비지 수집에 근접하고 있음을 감지할 때 발생되는 알림에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="3d3b3-106">The <xref:System.GC.RegisterForFullGCNotification%2A> method registers for a notification to be raised when the runtime senses that a full garbage collection is approaching.</span></span> <span data-ttu-id="3d3b3-107">이 알림에는 두 부분이 있습니다. 즉, 알림은 전체 가비지 수집에 근접하고 있을 때와 전체 가비지 수집이 완료되었을 때 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d3b3-107">There are two parts to this notification: when the full garbage collection is approaching and when the full garbage collection has completed.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="3d3b3-108">차단 가비지 수집만 알림을 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="3d3b3-108">Only blocking garbage collections raise notifications.</span></span> <span data-ttu-id="3d3b3-109">[\<gcConcurrent>](../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) 구성 요소를 사용하면 백그라운드 가비지 수집은 알림을 발생시키지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3d3b3-109">When the [\<gcConcurrent>](../../../docs/framework/configure-apps/file-schema/runtime/gcconcurrent-element.md) configuration element is enabled, background garbage collections will not raise notifications.</span></span>  
  
 <span data-ttu-id="3d3b3-110">알림이 발생한 시기를 확인하려면 <xref:System.GC.WaitForFullGCApproach%2A> 및 <xref:System.GC.WaitForFullGCComplete%2A> 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3d3b3-110">To determine when a notification has been raised, use the <xref:System.GC.WaitForFullGCApproach%2A> and <xref:System.GC.WaitForFullGCComplete%2A> methods.</span></span> <span data-ttu-id="3d3b3-111">일반적으로 `while` 루프에 이러한 메서드를 사용하면 알림 상태를 표시하는 <xref:System.GCNotificationStatus> 열거형을 계속해서 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d3b3-111">Typically, you use these methods in a `while` loop to continually obtain a <xref:System.GCNotificationStatus> enumeration that shows the status of the notification.</span></span> <span data-ttu-id="3d3b3-112">해당 값이 <xref:System.GCNotificationStatus.Succeeded>인 경우 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d3b3-112">If that value is <xref:System.GCNotificationStatus.Succeeded>, you can do the following:</span></span>  
  
-   <span data-ttu-id="3d3b3-113"><xref:System.GC.WaitForFullGCApproach%2A> 메서드를 사용하여 받은 알림에 대한 대응으로, 워크로드를 리디렉션하고 직접 수집을 유도할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d3b3-113">In response to a notification obtained with the <xref:System.GC.WaitForFullGCApproach%2A> method, you can redirect the workload and possibly induce a collection yourself.</span></span>  
  
-   <span data-ttu-id="3d3b3-114"><xref:System.GC.WaitForFullGCComplete%2A> 메서드를 사용하여 받은 알림에 대한 대응으로, 현재 서버 인스턴스에서 요청을 다시 처리할 수 있게 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d3b3-114">In response to a notification obtained with the <xref:System.GC.WaitForFullGCComplete%2A> method, you can make the current server instance available to process requests again.</span></span> <span data-ttu-id="3d3b3-115">또한 정보도 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d3b3-115">You can also gather information.</span></span> <span data-ttu-id="3d3b3-116">예를 들어 <xref:System.GC.CollectionCount%2A> 메서드를 사용하여 컬렉션 수를 기록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d3b3-116">For example, you can use the <xref:System.GC.CollectionCount%2A> method to record the number of collections.</span></span>  
  
 <span data-ttu-id="3d3b3-117"><xref:System.GC.WaitForFullGCApproach%2A> 및 <xref:System.GC.WaitForFullGCComplete%2A> 메서드는 함께 작동하도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3d3b3-117">The <xref:System.GC.WaitForFullGCApproach%2A> and the <xref:System.GC.WaitForFullGCComplete%2A> methods are designed to work together.</span></span> <span data-ttu-id="3d3b3-118">두 메서드를 함께 사용하지 않고 하나만 사용하면 불확실한 결과를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d3b3-118">Using one without the other can produce indeterminate results.</span></span>  
  
## <a name="full-garbage-collection"></a><span data-ttu-id="3d3b3-119">전체 가비지 수집</span><span class="sxs-lookup"><span data-stu-id="3d3b3-119">Full Garbage Collection</span></span>  
 <span data-ttu-id="3d3b3-120">다음 시나리오 중 하나에 해당하는 경우 런타임은 전체 가비지 수집을 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="3d3b3-120">The runtime causes a full garbage collection when any of the following scenarios are true:</span></span>  
  
-   <span data-ttu-id="3d3b3-121">그다음 세대 2 컬렉션을 일으키기에 충분한 메모리가 세대 2로 승격된 경우.</span><span class="sxs-lookup"><span data-stu-id="3d3b3-121">Enough memory has been promoted into generation 2 to cause the next generation 2 collection.</span></span>  
  
-   <span data-ttu-id="3d3b3-122">그다음 세대 2 컬렉션을 일으키기에 충분한 메모리가 대형 개체 힙으로 승격된 경우.</span><span class="sxs-lookup"><span data-stu-id="3d3b3-122">Enough memory has been promoted into the large object heap to cause the next generation 2 collection.</span></span>  
  
-   <span data-ttu-id="3d3b3-123">세대 1의 컬렉션이 다른 요인으로 인해 세대 2의 컬렉션으로 에스컬레이션된 경우</span><span class="sxs-lookup"><span data-stu-id="3d3b3-123">A collection of generation 1 is escalated to a collection of generation 2 due to other factors.</span></span>  
  
 <span data-ttu-id="3d3b3-124"><xref:System.GC.RegisterForFullGCNotification%2A> 메서드에서 지정한 임계값은 처음 두 시나리오에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d3b3-124">The thresholds you specify in the <xref:System.GC.RegisterForFullGCNotification%2A> method apply to the first two scenarios.</span></span> <span data-ttu-id="3d3b3-125">그러나 첫 번째 시나리오에서는 다음과 같은 두 가지 이유로 지정된 임계값에 비례한 시간에 알림을 항상 받지는 못합니다.</span><span class="sxs-lookup"><span data-stu-id="3d3b3-125">However, in the first scenario you will not always receive the notification at the time proportional to the threshold values you specify for two reasons:</span></span>  
  
-   <span data-ttu-id="3d3b3-126">런타임이 성능상의 이유로 각각의 소형 개체 할당을 확인하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3d3b3-126">The runtime does not check each small object allocation (for performance reasons).</span></span>  
  
-   <span data-ttu-id="3d3b3-127">세대 1 컬렉션만 메모리 수준이 세대 2로 올라갑니다.</span><span class="sxs-lookup"><span data-stu-id="3d3b3-127">Only generation 1 collections promote memory into generation 2.</span></span>  
  
 <span data-ttu-id="3d3b3-128">또한 세 번째 시나리오는 알림을 받을 수 있는 시기를 불확실하게 하는 원인이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d3b3-128">The third scenario also contributes to the uncertainty of when you will receive the notification.</span></span> <span data-ttu-id="3d3b3-129">따라서 보장할 수는 없지만, 이 시간 동안 요청을 리디렉션하거나 더 잘 수용할 수 있을 때 직접 수집을 유도함으로써 부적절한 시기의 전체 가비지 수집으로 인한 영향을 완화하는 것이 유용한 방법임은 명백합니다.</span><span class="sxs-lookup"><span data-stu-id="3d3b3-129">Although this is not a guarantee, it does prove to be a useful way to mitigate the effects of an inopportune full garbage collection by redirecting the requests during this time or inducing the collection yourself when it can be better accommodated.</span></span>  
  
## <a name="notification-threshold-parameters"></a><span data-ttu-id="3d3b3-130">알림 임계값 매개 변수</span><span class="sxs-lookup"><span data-stu-id="3d3b3-130">Notification Threshold Parameters</span></span>  
 <span data-ttu-id="3d3b3-131"><xref:System.GC.RegisterForFullGCNotification%2A> 메서드에는 세대 2 개체 및 대형 개체 힙의 임계값을 지정하는 두 개의 매개 변수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d3b3-131">The <xref:System.GC.RegisterForFullGCNotification%2A> method has two parameters to specify the threshold values of the generation 2 objects and the large object heap.</span></span> <span data-ttu-id="3d3b3-132">이러한 값이 충족되면 가비지 수집 알림이 발생되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d3b3-132">When those values are met, a garbage collection notification should be raised.</span></span> <span data-ttu-id="3d3b3-133">다음 표에서는 이러한 매개 변수에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="3d3b3-133">The following table describes these parameters.</span></span>  
  
|<span data-ttu-id="3d3b3-134">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3d3b3-134">Parameter</span></span>|<span data-ttu-id="3d3b3-135">설명</span><span class="sxs-lookup"><span data-stu-id="3d3b3-135">Description</span></span>|  
|---------------|-----------------|  
|`maxGenerationThreshold`|<span data-ttu-id="3d3b3-136">세대 2에서 수준이 상승된 개체에 따라 알림을 발생시킬 시점을 지정하는 1에서 99 사이의 숫자입니다.</span><span class="sxs-lookup"><span data-stu-id="3d3b3-136">A number between 1 and 99 that specifies when the notification should be raised based on the objects promoted in generation 2.</span></span>|  
|`largeObjectHeapThreshold`|<span data-ttu-id="3d3b3-137">대형 개체 힙에 할당되는 개체에 따라 알림을 발생시킬 시점을 지정하는 1에서 99 사이의 숫자입니다.</span><span class="sxs-lookup"><span data-stu-id="3d3b3-137">A number between 1 and 99 that specifies when the notification should be raised based on the objects that are allocated in the large object heap.</span></span>|  
  
 <span data-ttu-id="3d3b3-138">너무 높은 값을 지정하는 경우 알림을 받을 확률은 높아지지만 런타임에서 수집을 일으킬 때까지 너무 오래 대기할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d3b3-138">If you specify a value that is too high, there is a high probability that you will receive a notification, but it could be too long a period to wait before the runtime causes a collection.</span></span> <span data-ttu-id="3d3b3-139">직접 수집을 유도하는 경우 런타임에서 수집을 일으킬 때 회수하는 것보다 더 많은 개체를 회수할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d3b3-139">If you induce a collection yourself, you may reclaim more objects than would be reclaimed if the runtime causes the collection.</span></span>  
  
 <span data-ttu-id="3d3b3-140">너무 낮은 값을 지정하는 경우 알림을 받기에 충분한 시간이 경과하기도 전에 런타임이 수집을 일으킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d3b3-140">If you specify a value that is too low, the runtime may cause the collection before you have had sufficient time to be notified.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3d3b3-141">예제</span><span class="sxs-lookup"><span data-stu-id="3d3b3-141">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="3d3b3-142">설명</span><span class="sxs-lookup"><span data-stu-id="3d3b3-142">Description</span></span>  
 <span data-ttu-id="3d3b3-143">다음 예제에서 서버 그룹이 들어오는 웹 요청을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="3d3b3-143">In the following example, a group of servers service incoming Web requests.</span></span> <span data-ttu-id="3d3b3-144">요청 처리의 워크로드를 시뮬레이트하기 위해 바이트 배열을 <xref:System.Collections.Generic.List%601> 컬렉션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3d3b3-144">To simulate the workload of processing requests, byte arrays are added to a <xref:System.Collections.Generic.List%601> collection.</span></span> <span data-ttu-id="3d3b3-145">각 서버는 가비지 수집 알림에 등록한 후 `WaitForFullGCProc` 사용자 메서드의 스레드를 시작하여 <xref:System.GC.WaitForFullGCApproach%2A> 및 <xref:System.GC.WaitForFullGCComplete%2A> 메서드에서 반환하는 <xref:System.GCNotificationStatus> 열거형을 지속적으로 모니터링합니다.</span><span class="sxs-lookup"><span data-stu-id="3d3b3-145">Each server registers for a garbage collection notification and then starts a thread on the `WaitForFullGCProc` user method to continuously monitor the <xref:System.GCNotificationStatus> enumeration that is returned by the <xref:System.GC.WaitForFullGCApproach%2A> and the <xref:System.GC.WaitForFullGCComplete%2A> methods.</span></span>  
  
 <span data-ttu-id="3d3b3-146"><xref:System.GC.WaitForFullGCApproach%2A> 및 <xref:System.GC.WaitForFullGCComplete%2A> 메서드는 알림이 발생할 때 다음과 같은 각각의 이벤트 처리 사용자 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="3d3b3-146">The <xref:System.GC.WaitForFullGCApproach%2A> and the <xref:System.GC.WaitForFullGCComplete%2A> methods call their respective event-handling user methods when a notification is raised:</span></span>  
  
-   `OnFullGCApproachNotify`  
  
     <span data-ttu-id="3d3b3-147">이 메서드는 `RedirectRequests` 사용자 메서드를 호출하여, 서버로의 요청 전송을 일시 중단하도록 요청 큐 서버에 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="3d3b3-147">This method calls the `RedirectRequests` user method, which instructs the request queuing server to suspend sending requests to the server.</span></span> <span data-ttu-id="3d3b3-148">이는 더 이상 개체가 할당되지 않도록 클래스 수준 변수 `bAllocate`를 `false`로 설정하여 시뮬레이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d3b3-148">This is simulated by setting the class-level variable `bAllocate` to `false` so that no more objects are allocated.</span></span>  
  
     <span data-ttu-id="3d3b3-149">다음으로, 보류 중인 서버 요청에 대한 처리를 완료하기 위해 `FinishExistingRequests` 사용자 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="3d3b3-149">Next, the `FinishExistingRequests` user method is called to finish processing the pending server requests.</span></span> <span data-ttu-id="3d3b3-150">이는 <xref:System.Collections.Generic.List%601> 컬렉션을 지움으로써 시뮬레이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d3b3-150">This is simulated by clearing the <xref:System.Collections.Generic.List%601> collection.</span></span>  
  
     <span data-ttu-id="3d3b3-151">마지막으로 워크로드가 가벼우므로 가비지 수집을 유도합니다.</span><span class="sxs-lookup"><span data-stu-id="3d3b3-151">Finally, a garbage collection is induced because the workload is light.</span></span>  
  
-   `OnFullGCCompleteNotify`  
  
     <span data-ttu-id="3d3b3-152">서버가 전체 가비지 수집에 더 이상 취약하지 않으므로 이 메서드는 사용자 메서드 `AcceptRequests`를 호출하여 요청 수락을 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="3d3b3-152">This method calls the user method `AcceptRequests` to resume accepting requests because the server is no longer susceptible to a full garbage collection.</span></span> <span data-ttu-id="3d3b3-153">이 작업은 개체를 <xref:System.Collections.Generic.List%601> 컬렉션에 추가하는 것을 다시 시작할 수 있도록 `bAllocate` 변수를 `true`로 설정하여 시뮬레이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d3b3-153">This action is simulated by setting the `bAllocate` variable to `true` so that objects can resume being added to the <xref:System.Collections.Generic.List%601> collection.</span></span>  
  
 <span data-ttu-id="3d3b3-154">다음 코드에는 예제의 `Main` 메서드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d3b3-154">The following code contains the `Main` method of the example.</span></span>  
  
 [!code-cpp[GCNotification#2](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#2)]
 [!code-csharp[GCNotification#2](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#2)]
 [!code-vb[GCNotification#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#2)]  
  
 <span data-ttu-id="3d3b3-155">다음 코드에는 가비지 수집 알림을 확인하기 위한 연속 while 루프가 들어 있는 `WaitForFullGCProc` 사용자 메서드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d3b3-155">The following code contains the `WaitForFullGCProc` user method, that contains a continuous while loop to check for garbage collection notifications.</span></span>  
  
 [!code-cpp[GCNotification#8](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#8)]
 [!code-csharp[GCNotification#8](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#8)]
 [!code-vb[GCNotification#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#8)]  
  
 <span data-ttu-id="3d3b3-156">다음 코드에는 다음에서 호출되는 `OnFullGCApproachNotify` 메서드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d3b3-156">The following code contains the `OnFullGCApproachNotify` method as called from the</span></span>  
  
 <span data-ttu-id="3d3b3-157">`WaitForFullGCProc` 메서드를 호출하여 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d3b3-157">`WaitForFullGCProc` method.</span></span>  
  
 [!code-cpp[GCNotification#5](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#5)]
 [!code-csharp[GCNotification#5](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#5)]
 [!code-vb[GCNotification#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#5)]  
  
 <span data-ttu-id="3d3b3-158">다음 코드에는 다음에서 호출되는 `OnFullGCApproachComplete` 메서드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d3b3-158">The following code contains the `OnFullGCApproachComplete` method as called from the</span></span>  
  
 <span data-ttu-id="3d3b3-159">`WaitForFullGCProc` 메서드를 호출하여 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="3d3b3-159">`WaitForFullGCProc` method.</span></span>  
  
 [!code-cpp[GCNotification#6](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#6)]
 [!code-csharp[GCNotification#6](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#6)]
 [!code-vb[GCNotification#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#6)]  
  
 <span data-ttu-id="3d3b3-160">다음 코드에는 `OnFullGCApproachNotify` 및 `OnFullGCCompleteNotify` 메서드에서 호출되는 사용자 메서드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3d3b3-160">The following code contains the user methods that are called from the `OnFullGCApproachNotify` and `OnFullGCCompleteNotify` methods.</span></span> <span data-ttu-id="3d3b3-161">사용자 메서드는 요청을 리디렉션하고, 기존 요청을 완료한 다음, 전체 가비지 수집이 발생한 이후에 요청을 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="3d3b3-161">The user methods redirect requests, finish existing requests, and then resume requests after a full garbage collection has occurred.</span></span>  
  
 [!code-cpp[GCNotification#9](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#9)]
 [!code-csharp[GCNotification#9](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#9)]
 [!code-vb[GCNotification#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#9)]  
  
 <span data-ttu-id="3d3b3-162">전체 코드 샘플은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3d3b3-162">The entire code sample is as follows:</span></span>  
  
 [!code-cpp[GCNotification#1](../../../samples/snippets/cpp/VS_Snippets_CLR/GCNotification/cpp/program.cpp#1)]
 [!code-csharp[GCNotification#1](../../../samples/snippets/csharp/VS_Snippets_CLR/GCNotification/cs/Program.cs#1)]
 [!code-vb[GCNotification#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/GCNotification/vb/program.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="3d3b3-163">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3d3b3-163">See Also</span></span>  
 [<span data-ttu-id="3d3b3-164">가비지 수집</span><span class="sxs-lookup"><span data-stu-id="3d3b3-164">Garbage Collection</span></span>](../../../docs/standard/garbage-collection/index.md)
