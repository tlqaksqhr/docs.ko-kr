---
title: "캐시 정책 조작 -최대 사용 기간 및 최대 부실"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- maximum staleness
- freshness of cached resources
- time, cached resources
- maximum age policy
- staleness of cached resources
- age of cached resources
ms.assetid: 7f775925-89a1-4956-ba90-c869c1749a94
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: baec376501feb70e4a9ceb3f33ac66fa76b91ac1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="cache-policy-interactionmaximum-age-and-maximum-staleness"></a><span data-ttu-id="5e5cf-102">캐시 정책 조작 -최대 사용 기간 및 최대 부실</span><span class="sxs-lookup"><span data-stu-id="5e5cf-102">Cache Policy Interaction—Maximum Age and Maximum Staleness</span></span>
<span data-ttu-id="5e5cf-103">최신 콘텐츠가 클라이언트 응용 프로그램에 반환되도록 돕기 위해 클라이언트 캐시 정책 및 서버 유효성 재검사 요구 사항의 상호 작용 결과로 항상 가장 보수적인 캐시 정책이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e5cf-103">To help ensure that the freshest content is returned to the client application, the interaction of client cache policy and server revalidation requirements always results in the most conservative cache policy.</span></span> <span data-ttu-id="5e5cf-104">이 항목의 모든 예제에서는 1월 1일에 캐시되었으며 1월 4일에 만료되는 리소스에 대한 캐시 정책을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5e5cf-104">All the examples in this topic illustrate the cache policy for a resource that is cached on January 1 and expires on January 4.</span></span>  
  
 <span data-ttu-id="5e5cf-105">다음 예제에서는 최대 부실 값(`maxStale`)이 최대 사용 기간(`maxAge`)과 함께 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e5cf-105">In the following examples, the maximum staleness value (`maxStale`) is used in conjunction with a maximum age (`maxAge`):</span></span>  
  
-   <span data-ttu-id="5e5cf-106">캐시 정책이 `maxAge` = 5일을 설정하고 `maxStale` 값을 지정하지 않을 경우 `maxAge` 값에 따라 1월 6일까지 콘텐츠를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e5cf-106">If the cache policy sets `maxAge` = 5 days and does not specify a `maxStale` value, according to the `maxAge` value, the content is usable until January 6.</span></span> <span data-ttu-id="5e5cf-107">그러나 서버의 유효성 재검사 요구 사항에 따라 콘텐츠가 1월 4일에 만료됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e5cf-107">However, according to the server's revalidation requirements, the content expires on January 4.</span></span> <span data-ttu-id="5e5cf-108">콘텐츠 만료 날짜가 더 보수적이기(더 빠르기) 때문에 `maxAge` 정책보다 우선 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e5cf-108">Because the content expiration date is more conservative (sooner), it takes precedence over the `maxAge` policy.</span></span> <span data-ttu-id="5e5cf-109">따라서 콘텐츠는 1월 4일에 만료되고 최대 사용 기간에 도달하지 않았지만 유효성을 재검사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e5cf-109">Therefore, the content expires on January 4 and must be revalidated even though its maximum age has not been reached.</span></span>  
  
-   <span data-ttu-id="5e5cf-110">캐시 정책이 `maxAge` = 5일, `maxStale` = 3일을 설정하는 경우 `maxAge` 값에 따라 1월 6일까지 콘텐츠를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e5cf-110">If the cache policy sets `maxAge` = 5 days and `maxStale` = 3 days, according to the `maxAge` value, the content is usable until January 6.</span></span> <span data-ttu-id="5e5cf-111">`maxStale` 값에 따라 콘텐츠를 1월 7일까지 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e5cf-111">According to the `maxStale` value, the content is usable until January 7.</span></span> <span data-ttu-id="5e5cf-112">따라서 콘텐츠는 1월 6일에 유효성이 재검사됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e5cf-112">Therefore, the content gets revalidated on January 6.</span></span>  
  
-   <span data-ttu-id="5e5cf-113">캐시 정책이 `maxAge` = 5일, `maxStale` = 1일을 설정하는 경우 `maxAge` 값에 따라 1월 6일까지 콘텐츠를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e5cf-113">If the cache policy sets `maxAge` = 5 days and `maxStale` = 1 day, according to the `maxAge` value, the content is usable until January 6.</span></span> <span data-ttu-id="5e5cf-114">`maxStale` 값에 따라 콘텐츠를 1월 5일까지 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e5cf-114">According to the `maxStale` value, the content is usable until January 5.</span></span> <span data-ttu-id="5e5cf-115">따라서 1월 5일에 콘텐츠 유효성이 재검사됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e5cf-115">Therefore, the content gets revalidated on January 5.</span></span>  
  
 <span data-ttu-id="5e5cf-116">최대 사용 기간이 콘텐츠 만료 날짜보다 이전이면 보다 보수적인 캐싱 동작이 항상 우선 적용되고 최대 부실 값은 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5e5cf-116">When the maximum age is less than the content expiration date, the more conservative caching behavior always prevails and the maximum staleness value has no effect.</span></span> <span data-ttu-id="5e5cf-117">다음 예제에서는 콘텐츠가 만료되기 전에 최대 사용 기간(`maxAge`)에 도달할 경우 최대 부실(`maxStale`) 값을 설정할 경우의 영향을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5e5cf-117">The following examples illustrate the effect of setting a maximum staleness (`maxStale`) value when the maximum age (`maxAge`) is reached before the content expires:</span></span>  
  
-   <span data-ttu-id="5e5cf-118">캐시 정책이 `maxAge` = 1일을 설정하고 `maxStale` 값을 지정하지 않을 경우 콘텐츠가 만료되지 않았어도 1월 2일에 유효성이 재검사됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e5cf-118">If the cache policy sets `maxAge` = 1 day and does not specify a value for `maxStale` value, the content is revalidated on January 2 even though it has not expired.</span></span>  
  
-   <span data-ttu-id="5e5cf-119">캐시 정책이 `maxAge` = 1일, `maxStale` = 3일을 설정하는 경우 보다 보수적인 정책 설정을 적용하기 위해 1월 2일에 콘텐츠 유효성이 재검사됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e5cf-119">If the cache policy sets `maxAge` = 1 day and `maxStale` = 3 days, the content is revalidated on January 2 to enforce the more conservative policy setting.</span></span>  
  
-   <span data-ttu-id="5e5cf-120">캐시 정책이 `maxAge` = 1일, `maxStale` = 1일을 설정하는 경우 1월 2일에 콘텐츠 유효성이 재검사됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e5cf-120">If the cache policy sets `maxAge` = 1 day and `maxStale` = 1 day, the content is revalidated on January 2.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e5cf-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5e5cf-121">See Also</span></span>  
 [<span data-ttu-id="5e5cf-122">네트워크 응용 프로그램에 대한 캐시 관리</span><span class="sxs-lookup"><span data-stu-id="5e5cf-122">Cache Management for Network Applications</span></span>](../../../docs/framework/network-programming/cache-management-for-network-applications.md)  
 [<span data-ttu-id="5e5cf-123">캐시 정책</span><span class="sxs-lookup"><span data-stu-id="5e5cf-123">Cache Policy</span></span>](../../../docs/framework/network-programming/cache-policy.md)  
 [<span data-ttu-id="5e5cf-124">위치 기반 캐시 정책</span><span class="sxs-lookup"><span data-stu-id="5e5cf-124">Location-Based Cache Policies</span></span>](../../../docs/framework/network-programming/location-based-cache-policies.md)  
 [<span data-ttu-id="5e5cf-125">시간 기반 캐시 정책</span><span class="sxs-lookup"><span data-stu-id="5e5cf-125">Time-Based Cache Policies</span></span>](../../../docs/framework/network-programming/time-based-cache-policies.md)  
 [<span data-ttu-id="5e5cf-126">네트워크 응용 프로그램에서 캐싱 구성</span><span class="sxs-lookup"><span data-stu-id="5e5cf-126">Configuring Caching in Network Applications</span></span>](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md)  
 [<span data-ttu-id="5e5cf-127">캐시 정책 상호 작용 - 최대 보존 기간 및 최소 새로 고침</span><span class="sxs-lookup"><span data-stu-id="5e5cf-127">Cache Policy Interaction—Maximum Age and Minimum Freshness</span></span>](../../../docs/framework/network-programming/cache-policy-interaction-maximum-age-and-minimum-freshness.md)
