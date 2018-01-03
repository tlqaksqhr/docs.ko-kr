---
title: "캐시 정책 상호 작용 - 최대 보존 기간 및 최소 새로 고침"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- time-based cache policies
- Revalidate policy
- cache [.NET Framework], time-based policies
- freshness of cached resources
- maximum age policy
- minimum freshness policy
- age of cached resources
ms.assetid: 6567d451-ecec-496c-95a3-a415b99ba52a
caps.latest.revision: "9"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: 689b8b2d921731ecab2be2a1aa3dee5d1928e8cc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="cache-policy-interactionmaximum-age-and-minimum-freshness"></a><span data-ttu-id="d1a93-102">캐시 정책 상호 작용 - 최대 보존 기간 및 최소 새로 고침</span><span class="sxs-lookup"><span data-stu-id="d1a93-102">Cache Policy Interaction—Maximum Age and Minimum Freshness</span></span>
<span data-ttu-id="d1a93-103">최신 콘텐츠가 클라이언트 응용 프로그램에 반환되도록 돕기 위해 클라이언트 캐시 정책 및 서버 유효성 재검사 요구 사항의 상호 작용 결과로 항상 가장 보수적인 캐시 정책이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1a93-103">To help ensure that the freshest content is returned to the client application, the interaction of client cache policy and server revalidation requirements always results in the most conservative cache policy.</span></span> <span data-ttu-id="d1a93-104">이 항목의 모든 예제에서는 1월 1일에 캐시되었으며 1월 4일에 만료되는 리소스에 대한 캐시 정책을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d1a93-104">All the examples in this topic illustrate the cache policy for a resource that is cached on January 1 and expires on January 4.</span></span>  
  
 <span data-ttu-id="d1a93-105">다음 예제에서는 최대 사용 기간(`maxAge`) 및 최소 새로 고침(`minFresh`) 값의 상호 작용 결과로 생성되는 캐시 정책을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d1a93-105">The following examples illustrate the cache policy that results from the interaction of the maximum age (`maxAge`) and minimum freshness (`minFresh`) values.</span></span>  
  
-   <span data-ttu-id="d1a93-106">캐시 정책이 `maxAge` = 2일을 설정하고 `minFresh`를 지정하지 않을 경우 1월 3일에 콘텐츠 유효성이 재검사됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1a93-106">If the cache policy sets `maxAge` = 2 days and `minFresh` is not specified, the content is revalidated on January 3.</span></span>  
  
-   <span data-ttu-id="d1a93-107">캐시 정책이 `maxAge` = 2일, `minFresh` = 1일을 설정하는 경우 `maxAge`에 따라 1월 3일까지 콘텐츠가 최신 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="d1a93-107">If the cache policy sets `maxAge` = 2 days and `minFresh` = 1 day, according to `maxAge`, the content is fresh until January 3.</span></span> <span data-ttu-id="d1a93-108">`minFresh`에 따라 콘텐츠가 1월 3일까지 최신 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="d1a93-108">According to `minFresh`, the content is fresh until January 3.</span></span> <span data-ttu-id="d1a93-109">따라서 1월 3일에 콘텐츠 유효성을 재검사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1a93-109">Therefore, the content must be revalidated on January 3.</span></span>  
  
-   <span data-ttu-id="d1a93-110">캐시 정책이 `maxAge` = 2일, `minFresh` = 2일을 설정하는 경우 `maxAge`에 따라 1월 3일까지 콘텐츠가 최신 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="d1a93-110">If the cache policy sets `maxAge` = 2 days and `minFresh` = 2 days, according to `maxAge`, the content is fresh until January 3.</span></span> <span data-ttu-id="d1a93-111">`minFresh`에 따라 콘텐츠가 1월 2일까지 최신 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="d1a93-111">According to `minFresh` the content is fresh until January 2.</span></span> <span data-ttu-id="d1a93-112">따라서 1월 2일에 콘텐츠 유효성을 재검사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1a93-112">Therefore, the content must be revalidated on January 2.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1a93-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d1a93-113">See Also</span></span>  
 [<span data-ttu-id="d1a93-114">네트워크 응용 프로그램에 대한 캐시 관리</span><span class="sxs-lookup"><span data-stu-id="d1a93-114">Cache Management for Network Applications</span></span>](../../../docs/framework/network-programming/cache-management-for-network-applications.md)  
 [<span data-ttu-id="d1a93-115">캐시 정책</span><span class="sxs-lookup"><span data-stu-id="d1a93-115">Cache Policy</span></span>](../../../docs/framework/network-programming/cache-policy.md)  
 [<span data-ttu-id="d1a93-116">위치 기반 캐시 정책</span><span class="sxs-lookup"><span data-stu-id="d1a93-116">Location-Based Cache Policies</span></span>](../../../docs/framework/network-programming/location-based-cache-policies.md)  
 [<span data-ttu-id="d1a93-117">시간 기반 캐시 정책</span><span class="sxs-lookup"><span data-stu-id="d1a93-117">Time-Based Cache Policies</span></span>](../../../docs/framework/network-programming/time-based-cache-policies.md)  
 [<span data-ttu-id="d1a93-118">네트워크 응용 프로그램에서 캐싱 구성</span><span class="sxs-lookup"><span data-stu-id="d1a93-118">Configuring Caching in Network Applications</span></span>](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md)  
 [<span data-ttu-id="d1a93-119">캐시 정책 조작 -최대 사용 기간 및 최대 부실</span><span class="sxs-lookup"><span data-stu-id="d1a93-119">Cache Policy Interaction—Maximum Age and Maximum Staleness</span></span>](../../../docs/framework/network-programming/cache-policy-interaction-maximum-age-and-maximum-staleness.md)
