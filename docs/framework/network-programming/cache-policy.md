---
title: "캐시 정책"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- time-based cache policies
- location-based cache policies
- cache [.NET Framework], policies
- request cache policies
- freshness of cached resources
- content cache policies
- expired content
ms.assetid: 1a7e04ec-7872-41c2-96c6-52566dcb412b
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 375c3b44f505a9bf36ce721c5ccde9b888114309
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="cache-policy"></a><span data-ttu-id="b0bbe-102">캐시 정책</span><span class="sxs-lookup"><span data-stu-id="b0bbe-102">Cache Policy</span></span>
<span data-ttu-id="b0bbe-103">캐시 정책이 요청된 리소스의 캐시된 복사본을 통해 요청을 충족할 수 있는지 여부를 결정하는 데 사용되는 규칙을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b0bbe-103">A cache policy defines rules that are used to determine whether a request can be satisfied using a cached copy of the requested resource.</span></span> <span data-ttu-id="b0bbe-104">응용 프로그램에서 새로 고침에 대한 클라이언트 캐시 요구 사항을 지정하지만, 유효한 캐시 정책은 클라이언트 캐시 요구 사항, 서버의 콘텐츠 만료 요구 사항 및 서버의 유효성 재검사 요구 사항에 의해 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0bbe-104">Applications specify client cache requirements for freshness, but the effective cache policy is determined by the client cache requirements, the server's content expiration requirements, and the server's revalidation requirements.</span></span> <span data-ttu-id="b0bbe-105">최신 콘텐츠가 클라이언트 응용 프로그램에 반환되도록 돕기 위해 클라이언트 캐시 정책 및 서버 요구 사항의 상호 작용 결과로 항상 가장 보수적인 캐시 정책이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0bbe-105">The interaction of client cache policy and server requirements always results in the most conservative cache policy, to help ensure that the freshest content is returned to the client application.</span></span>  
  
 <span data-ttu-id="b0bbe-106">캐시 정책은 위치 기반 또는 시간 기반입니다.</span><span class="sxs-lookup"><span data-stu-id="b0bbe-106">Cache policies are either location-based or time-based.</span></span> <span data-ttu-id="b0bbe-107">위치 기반 캐시 정책은 요청한 리소스를 가져올 수 있는 위치를 기준으로 캐시된 항목의 새로 고침을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b0bbe-107">A location-based cache policy defines the freshness of cached entries based on where the requested resource can be taken from.</span></span> <span data-ttu-id="b0bbe-108">시간 기반 캐시 정책은 리소스가 검색된 시간, 리소스와 함께 반환된 헤더, 현재 시간을 사용하여 캐시된 항목의 새로 고침을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b0bbe-108">A time-based cache policy defines the freshness of cached entries using the time the resource was retrieved, headers returned with the resource, and the current time.</span></span> <span data-ttu-id="b0bbe-109">대부분의 응용 프로그램은 [http://www.ietf.org](http://www.ietf.org/)에 있는 RFC 2616에 지정된 캐싱 정책을 구현하는 기본 시간 기반 캐시 정책을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0bbe-109">Most applications can use the default time-based cache policy, which implements the caching policy specified in RFC 2616, available at [http://www.ietf.org](http://www.ietf.org/).</span></span>  
  
 <span data-ttu-id="b0bbe-110">다음 표에 설명된 클래스는 캐시 정책을 지정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0bbe-110">The classes described in the following table are used to specify cache policies.</span></span>  
  
|<span data-ttu-id="b0bbe-111">클래스 이름</span><span class="sxs-lookup"><span data-stu-id="b0bbe-111">Class name</span></span>|<span data-ttu-id="b0bbe-112">설명</span><span class="sxs-lookup"><span data-stu-id="b0bbe-112">Description</span></span>|  
|----------------|-----------------|  
|<xref:System.Net.Cache.HttpRequestCachePolicy>|<span data-ttu-id="b0bbe-113"><xref:System.Net.HttpWebRequest> 개체를 사용하여 요청된 리소스에 대한 위치 기반 및 시간 기반 캐시 정책을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b0bbe-113">Represents location-based and time-based cache policies for resources requested using <xref:System.Net.HttpWebRequest> objects.</span></span>|  
|<xref:System.Net.Cache.RequestCachePolicy>|<span data-ttu-id="b0bbe-114"><xref:System.Net.Cache.RequestCacheLevel.Default> 개체를 사용하여 요청된 리소스에 대한 위치 기반 캐시 정책 또는 <xref:System.Net.WebRequest> 시간 기반 캐시 정책을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b0bbe-114">Represents location-based cache policies or the <xref:System.Net.Cache.RequestCacheLevel.Default> time-based cache policy for resources requested using <xref:System.Net.WebRequest> objects.</span></span>|  
|<xref:System.Net.Cache.HttpCacheAgeControl>|<span data-ttu-id="b0bbe-115">시간 기반 <xref:System.Net.Cache.HttpRequestCachePolicy> 개체를 만드는 데 사용되는 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b0bbe-115">Specifies values used to create time-based <xref:System.Net.Cache.HttpRequestCachePolicy> objects.</span></span>|  
|<xref:System.Net.Cache.HttpRequestCacheLevel>|<span data-ttu-id="b0bbe-116">위치 기반 및 시간 기반 <xref:System.Net.Cache.HttpRequestCachePolicy> 개체를 만드는 데 사용되는 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b0bbe-116">Specifies values used to create location-based and time-based <xref:System.Net.Cache.HttpRequestCachePolicy> objects.</span></span>|  
|<xref:System.Net.Cache.RequestCacheLevel>|<span data-ttu-id="b0bbe-117">위치 기반 또는 <xref:System.Net.Cache.RequestCacheLevel.Default> 시간 기반 <xref:System.Net.Cache.RequestCachePolicy> 개체를 만드는 데 사용되는 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b0bbe-117">Specifies values used to create location-based or the <xref:System.Net.Cache.RequestCacheLevel.Default> time-based <xref:System.Net.Cache.RequestCachePolicy> objects.</span></span>|  
  
 <span data-ttu-id="b0bbe-118">응용 프로그램에서 만든 모든 요청 또는 개별 요청에 대한 캐시 정책을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0bbe-118">You can define a cache policy for all requests made by your application or for individual requests.</span></span> <span data-ttu-id="b0bbe-119">응용 프로그램 수준 캐시 정책과 요청 수준 캐시 정책을 둘 다 지정하는 경우 요청 수준 정책이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0bbe-119">When you specify both an application-level cache policy and a request-level cache policy, the request-level policy is used.</span></span> <span data-ttu-id="b0bbe-120">프로그래밍 방식으로 또는 응용 프로그램 또는 컴퓨터 구성 파일을 사용하여 응용 프로그램 수준 캐시 정책을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0bbe-120">You can specify an application-level cache policy programmatically or by using the application or machine configuration files.</span></span> <span data-ttu-id="b0bbe-121">자세한 내용은 [\<requestCaching> 요소(네트워크 설정)](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b0bbe-121">For more information, see [\<requestCaching> Element (Network Settings)](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md).</span></span>  
  
 <span data-ttu-id="b0bbe-122">캐시 정책을 만들려면 <xref:System.Net.Cache.RequestCachePolicy> 또는 <xref:System.Net.Cache.HttpRequestCachePolicy> 클래스 인스턴스를 만들어 정책 개체를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0bbe-122">To create a cache policy, you must create a policy object by creating an instance of the <xref:System.Net.Cache.RequestCachePolicy> or <xref:System.Net.Cache.HttpRequestCachePolicy> class.</span></span> <span data-ttu-id="b0bbe-123">요청에 정책을 지정하려면 요청의 <xref:System.Net.WebRequest.CachePolicy%2A> 속성을 정책 개체로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b0bbe-123">To specify the policy on a request, set the request's <xref:System.Net.WebRequest.CachePolicy%2A> property to the policy object.</span></span> <span data-ttu-id="b0bbe-124">프로그래밍 방식으로 응용 프로그램 수준 정책을 설정하는 경우 <xref:System.Net.HttpWebRequest.DefaultCachePolicy%2A> 속성을 정책 개체로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b0bbe-124">When setting an application-level policy programmatically, set the <xref:System.Net.HttpWebRequest.DefaultCachePolicy%2A> property to the policy object.</span></span>  
  
 <span data-ttu-id="b0bbe-125">캐시 정책을 만들고 사용하는 방법을 보여 주는 코드 예제는 [네트워크 응용 프로그램에서 캐싱 구성](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b0bbe-125">For code examples that demonstrate creating and using cache policies, see [Configuring Caching in Network Applications](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0bbe-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b0bbe-126">See Also</span></span>  
 [<span data-ttu-id="b0bbe-127">네트워크 응용 프로그램에 대한 캐시 관리</span><span class="sxs-lookup"><span data-stu-id="b0bbe-127">Cache Management for Network Applications</span></span>](../../../docs/framework/network-programming/cache-management-for-network-applications.md)  
 [<span data-ttu-id="b0bbe-128">위치 기반 캐시 정책</span><span class="sxs-lookup"><span data-stu-id="b0bbe-128">Location-Based Cache Policies</span></span>](../../../docs/framework/network-programming/location-based-cache-policies.md)  
 [<span data-ttu-id="b0bbe-129">시간 기반 캐시 정책</span><span class="sxs-lookup"><span data-stu-id="b0bbe-129">Time-Based Cache Policies</span></span>](../../../docs/framework/network-programming/time-based-cache-policies.md)  
 [<span data-ttu-id="b0bbe-130">네트워크 응용 프로그램에서 캐싱 구성</span><span class="sxs-lookup"><span data-stu-id="b0bbe-130">Configuring Caching in Network Applications</span></span>](../../../docs/framework/network-programming/configuring-caching-in-network-applications.md)
