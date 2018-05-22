---
title: 위치 기반 캐시 정책
ms.date: 03/30/2017
helpviewer_keywords:
- Cache If Available policy
- reload policy
- location-based cache policies
- Cache Only policy
- local cache
- intermediate cache
- No Cache No Store policy
- cache [.NET Framework], location-based policies
- Revalidate policy
- freshness of cached resources
- Cache Or Next Cache Only policy
- Refresh policy
ms.assetid: e41d7f1a-0a6a-4dee-97d1-c6a8b6a07fc2
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: b4109cef8d527d397903854e05a2204a3e551938
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="location-based-cache-policies"></a><span data-ttu-id="7bedb-102">위치 기반 캐시 정책</span><span class="sxs-lookup"><span data-stu-id="7bedb-102">Location-Based Cache Policies</span></span>
<span data-ttu-id="7bedb-103">위치 기반 캐시 정책은 요청한 리소스를 가져올 수 있는 위치를 기반으로 캐시된 유효한 항목의 새로 고침을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7bedb-103">A location-based cache policy defines the freshness of valid cached entries based on where the requested resource can be taken from.</span></span> <span data-ttu-id="7bedb-104">캐시된 리소스를 사용해도 서버 지정 유효성 재검사 요구 사항을 위반하지 않으면 해당 리소스는 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="7bedb-104">A cached resource is valid if using it does not does not violate server-specified revalidation requirements.</span></span> <span data-ttu-id="7bedb-105">위치 기반 캐시 정책은 <xref:System.Net.Cache.RequestCachePolicy> 또는 <xref:System.Net.Cache.HttpRequestCachePolicy> 클래스 생성자를 사용하여 프로그래밍 방식으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7bedb-105">A location-based cache policy is created programmatically by using a <xref:System.Net.Cache.RequestCachePolicy> or <xref:System.Net.Cache.HttpRequestCachePolicy> class constructor.</span></span> <span data-ttu-id="7bedb-106">위치 기반 정책 형식은 <xref:System.Net.Cache.RequestCacheLevel> 또는 <xref:System.Net.Cache.HttpRequestCacheLevel> 열거형 값을 사용하여 생성자에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="7bedb-106">The type of location-based policy is passed to the constructor using a <xref:System.Net.Cache.RequestCacheLevel> or <xref:System.Net.Cache.HttpRequestCacheLevel> enumeration value.</span></span> <span data-ttu-id="7bedb-107">위치 기반 캐시 정책을 만드는 코드 예제는 [방법: 응용 프로그램에 대한 위치 기반 캐시 정책 설정](../../../docs/framework/network-programming/how-to-set-a-location-based-cache-policy-for-an-application.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7bedb-107">For code examples that create location-based cache policies, see [How to: Set a Location-Based Cache Policy for an Application](../../../docs/framework/network-programming/how-to-set-a-location-based-cache-policy-for-an-application.md).</span></span> <span data-ttu-id="7bedb-108">다음 섹션에서는 Hypertext Transfer Protocol(http 및 https) 리소스를 위한 각각의 위치 기반 캐시 정책 형식을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7bedb-108">The following sections explain each type of location-based cache policy for Hypertext Transfer Protocol (http and https) resources.</span></span>  
  
## <a name="cache-if-available-policy"></a><span data-ttu-id="7bedb-109">사용 가능한 경우 캐시 정책</span><span class="sxs-lookup"><span data-stu-id="7bedb-109">Cache If Available Policy</span></span>  
 <span data-ttu-id="7bedb-110">로컬 캐시에 요청된 유효한 리소스가 있으면 캐시된 리소스가 사용되고, 그러지 않으면 리소스 요청이 서버에 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="7bedb-110">If a valid requested resource is in the local cache, the cached resource is used; otherwise, the request for the resource is sent to the server.</span></span> <span data-ttu-id="7bedb-111">클라이언트와 서버 사이의 모든 캐시에서 요청된 리소스를 사용할 수 있으면 중간 캐시에서 요청을 만족시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bedb-111">If the requested resource is available in any cache between the client and the server, the request can be satisfied by an intermediate cache.</span></span>  
  
## <a name="cache-only-policy"></a><span data-ttu-id="7bedb-112">캐시 전용 정책</span><span class="sxs-lookup"><span data-stu-id="7bedb-112">Cache Only Policy</span></span>  
 <span data-ttu-id="7bedb-113">로컬 캐시에 요청된 유효한 리소스가 있으면 캐시된 리소스가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7bedb-113">If a valid requested resource is in the local cache, the cached resource is used.</span></span> <span data-ttu-id="7bedb-114">이 캐시 정책 수준이 지정된 경우 항목이 로컬 캐시에 없으면 <xref:System.Net.WebException> 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="7bedb-114">When this cache policy level is specified, a <xref:System.Net.WebException> exception is thrown if the item is not in the local cache.</span></span>  
  
## <a name="cache-or-next-cache-only-policy"></a><span data-ttu-id="7bedb-115">캐시 또는 다음 캐시 전용 정책</span><span class="sxs-lookup"><span data-stu-id="7bedb-115">Cache Or Next Cache Only Policy</span></span>  
 <span data-ttu-id="7bedb-116">요청된 유효한 리소스가 로컬 캐시나 Local Area Network의 중간 캐시에 있으면 캐시된 리소스가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7bedb-116">If a valid requested resource is in the local cache or an intermediate cache on the local area network, the cached resource is used.</span></span> <span data-ttu-id="7bedb-117"><xref:System.Net.WebException> 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="7bedb-117">Otherwise, a <xref:System.Net.WebException> exception is thrown.</span></span> <span data-ttu-id="7bedb-118">HTTP 캐싱 프로토콜에서 이 작업은 캐시 전용(only-if-cached) 캐시 제어 지시문을 사용하여 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7bedb-118">In the HTTP caching protocol, this is achieved using the only-if-cached cache control directive.</span></span>  
  
## <a name="no-cache-no-store-policy"></a><span data-ttu-id="7bedb-119">캐시 없이 저장 안 함 정책</span><span class="sxs-lookup"><span data-stu-id="7bedb-119">No Cache No Store Policy</span></span>  
 <span data-ttu-id="7bedb-120">요청된 리소스는 임의 캐시에서 사용되지 않으며 임의 캐시에 두지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7bedb-120">A requested resource is never used from any cache and is never placed in any cache.</span></span> <span data-ttu-id="7bedb-121">요청된 리소스가 로컬 캐시에 있으면 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="7bedb-121">If a requested resource is present in the local cache, it is removed.</span></span> <span data-ttu-id="7bedb-122">이 정책 수준은 중간 캐시에서도 리소스를 제거해야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7bedb-122">This policy level indicates to intermediate caches that they should also remove the resource.</span></span> <span data-ttu-id="7bedb-123">HTTP 캐싱 프로토콜에서 이 작업은 저장 안 함(no-store) 캐시 제어 지시문을 사용하여 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7bedb-123">In the HTTP caching protocol, this is achieved using the no-store cache control directive.</span></span>  
  
## <a name="refresh-policy"></a><span data-ttu-id="7bedb-124">새로 고침 정책</span><span class="sxs-lookup"><span data-stu-id="7bedb-124">Refresh Policy</span></span>  
 <span data-ttu-id="7bedb-125">요청된 리소스를 서버에서 얻거나 로컬 캐시 이외의 캐시에서 찾은 경우 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bedb-125">A requested resource can be used if it is obtained from the server or found in a cache other than the local cache.</span></span> <span data-ttu-id="7bedb-126">중간 캐시에서 요청을 만족시키려면 캐시에서 서버를 사용하여 해당 캐시 항목의 유효성을 다시 검증해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bedb-126">Before the request can be satisfied by an intermediate cache, that cache must revalidate its cached entry with the server.</span></span> <span data-ttu-id="7bedb-127">HTTP 캐싱 프로토콜에서 이 작업은 max-age = 0 캐시 제어 지시문과 캐시 없음(no-cache) Pragma 헤더를 사용하여 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7bedb-127">In the HTTP caching protocol, this is achieved using the max-age = 0 cache control directive and the no-cache Pragma header.</span></span>  
  
## <a name="reload-policy"></a><span data-ttu-id="7bedb-128">다시 로드 정책</span><span class="sxs-lookup"><span data-stu-id="7bedb-128">Reload Policy</span></span>  
 <span data-ttu-id="7bedb-129">요청된 리소스는 서버에서 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7bedb-129">Requested resources must be obtained from the server.</span></span> <span data-ttu-id="7bedb-130">응답은 로컬 캐시에 저장될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7bedb-130">The response might be saved in the local cache.</span></span> <span data-ttu-id="7bedb-131">HTTP 캐싱 프로토콜에서 이 작업은 캐시 없음(no-cache) 캐시 제어 지시문과 캐시 없음(no-cache) Pragma 헤더를 사용하여 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7bedb-131">In the HTTP caching protocol, this is achieved using the no-cache cache control directive and the no-cache Pragma header.</span></span>  
  
## <a name="revalidate-policy"></a><span data-ttu-id="7bedb-132">유효성 다시 검사 정책</span><span class="sxs-lookup"><span data-stu-id="7bedb-132">Revalidate Policy</span></span>  
 <span data-ttu-id="7bedb-133">서버의 복사본과 캐시에 있는 리소스의 복사본을 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="7bedb-133">Compares the copy of the resource in the cache with the copy on the server.</span></span> <span data-ttu-id="7bedb-134">서버의 복사본이 최신이면 요청을 처리하는 데 사용하고 캐시의 복사본을 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="7bedb-134">If the copy on the server is newer, it is used to satisfy the request and replaces the copy in the cache.</span></span> <span data-ttu-id="7bedb-135">캐시의 복사본이 서버의 복사본과 동일하면 캐시된 복사본을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7bedb-135">If the copy in the cache is the same as the server copy, the cached copy is used.</span></span> <span data-ttu-id="7bedb-136">HTTP 캐싱 프로토콜에서는 조건부 요청을 사용하여 이 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7bedb-136">In the HTTP caching protocol, this is achieved using a conditional request.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bedb-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7bedb-137">See Also</span></span>  
 [<span data-ttu-id="7bedb-138">네트워크 응용 프로그램에 대한 캐시 관리</span><span class="sxs-lookup"><span data-stu-id="7bedb-138">Cache Management for Network Applications</span></span>](../../../docs/framework/network-programming/cache-management-for-network-applications.md)  
 [<span data-ttu-id="7bedb-139">캐시 정책</span><span class="sxs-lookup"><span data-stu-id="7bedb-139">Cache Policy</span></span>](../../../docs/framework/network-programming/cache-policy.md)  
 [<span data-ttu-id="7bedb-140">시간 기반 캐시 정책</span><span class="sxs-lookup"><span data-stu-id="7bedb-140">Time-Based Cache Policies</span></span>](../../../docs/framework/network-programming/time-based-cache-policies.md)  
 [<span data-ttu-id="7bedb-141">네트워크 응용 프로그램에서 캐싱 구성</span><span class="sxs-lookup"><span data-stu-id="7bedb-141">Configuring Caching in Network Applications</span></span>](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md)  
 [<span data-ttu-id="7bedb-142">\<requestCaching> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="7bedb-142">\<requestCaching> Element (Network Settings)</span></span>](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)
