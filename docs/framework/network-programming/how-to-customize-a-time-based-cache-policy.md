---
title: "방법: 시간 기반 캐시 정책을 사용자 지정"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time-based cache policies
- customizing time-based cache policies
- cache [.NET Framework], time-based policies
ms.assetid: 8d84f936-2376-4356-9264-03162e0f9279
caps.latest.revision: "15"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 58fa5c71bc459b65d35f9a59bdddccab9a0f5e56
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-customize-a-time-based-cache-policy"></a><span data-ttu-id="da847-102">방법: 시간 기반 캐시 정책을 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="da847-102">How to: Customize a Time-Based Cache Policy</span></span>
<span data-ttu-id="da847-103">시간 기반 캐시 정책을 만들 경우 최대 기간, 최소 새로 고침, 최대 부실 또는 캐시 동기화 날짜에 대한 값을 지정하여 캐싱 동작을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da847-103">When creating a time-based cache policy, you can customize caching behavior by specifying values for maximum age, minimum freshness, maximum staleness, or cache synchronization date.</span></span> <span data-ttu-id="da847-104"><xref:System.Net.Cache.HttpRequestCachePolicy> 개체는 이러한 값의 유효한 조합을 지정할 수 있는 여러 가지 생성자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="da847-104">The <xref:System.Net.Cache.HttpRequestCachePolicy> object provides several constructors that allow you to specify valid combinations of these values.</span></span>  
  
### <a name="to-create-a-time-based-cache-policy-that-uses-a-cache-synchronization-date"></a><span data-ttu-id="da847-105">캐시 동기화 날짜를 사용하는 시간 기반 캐시 정책을 만들려면</span><span class="sxs-lookup"><span data-stu-id="da847-105">To create a time-based cache policy that uses a cache synchronization date</span></span>  
  
-   <span data-ttu-id="da847-106"><xref:System.DateTime> 개체를 <xref:System.Net.Cache.HttpRequestCachePolicy> 생성자에 전달하여 캐시 동기화 날짜를 사용하는 시간 기반 캐시 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="da847-106">Create a time-based cache policy that uses a cache synchronization date by passing a <xref:System.DateTime> object to the <xref:System.Net.Cache.HttpRequestCachePolicy> constructor.</span></span>  
  
    ```csharp  
    public static HttpRequestCachePolicy CreateLastSyncPolicy(DateTime when)  
    {  
        HttpRequestCachePolicy policy =   
            new HttpRequestCachePolicy(when);  
        Console.WriteLine("When: {0}", when);  
        Console.WriteLine(policy.ToString());  
        return policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Function CreateLastSyncPolicy([when] As DateTime) As HttpRequestCachePolicy  
        Dim policy As New HttpRequestCachePolicy([when])  
        Console.WriteLine("When: {0}", [when])  
        Console.WriteLine(policy.ToString())  
        Return policy  
    End Function  
    ```  
  
 <span data-ttu-id="da847-107">출력은 다음과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="da847-107">The output is similar to the following:</span></span>  
  
```  
When: 1/14/2004 8:07:30 AM  
Level:Default CacheSyncDate:1/14/2004 8:07:30 AM  
```  
  
### <a name="to-create-a-time-based-cache-policy-that-is-based-on-minimum-freshness"></a><span data-ttu-id="da847-108">최소 새로 고침을 기반으로 하는 시간 기반 캐시 정책을 만들려면</span><span class="sxs-lookup"><span data-stu-id="da847-108">To create a time-based cache policy that is based on minimum freshness</span></span>  
  
-   <span data-ttu-id="da847-109"><xref:System.Net.Cache.HttpCacheAgeControl.MinFresh>를 `cacheAgeControl` 매개 변수 값으로 지정하고 <xref:System.TimeSpan> 개체를 <xref:System.Net.Cache.HttpRequestCachePolicy> 생성자에 전달하여 최소 새로 고침을 기반으로 하는 시간 기반 캐시 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="da847-109">Create a time-based cache policy that is based on minimum freshness by specifying <xref:System.Net.Cache.HttpCacheAgeControl.MinFresh> as the `cacheAgeControl` parameter value and passing a <xref:System.TimeSpan> object to the <xref:System.Net.Cache.HttpRequestCachePolicy> constructor.</span></span>  
  
    ```csharp  
    public static HttpRequestCachePolicy CreateMinFreshPolicy(TimeSpan span)  
    {  
        HttpRequestCachePolicy policy =   
            new HttpRequestCachePolicy(HttpCacheAgeControl.MinFresh, span);  
        Console.WriteLine(policy.ToString());  
        return policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Function CreateMinFreshPolicy(span As TimeSpan) As HttpRequestCachePolicy  
        Dim policy As New HttpRequestCachePolicy(HttpCacheAgeControl.MinFresh, span)  
        Console.WriteLine(policy.ToString())  
        Return policy  
    End Function  
    ```  
  
 <span data-ttu-id="da847-110">다음 호출의 경우:</span><span class="sxs-lookup"><span data-stu-id="da847-110">For the following invocation:</span></span>  
  
```  
CreateMinFreshPolicy(new TimeSpan(1,0,0));  
```  
  
```  
Level:Default MinFresh:3600  
```  
  
### <a name="to-create-a-time-based-cache-policy-that-is-based-on-minimum-freshness-and-maximum-age"></a><span data-ttu-id="da847-111">최소 새로 고침 및 최대 기간을 기반으로 하는 시간 기반 캐시 정책을 만들려면</span><span class="sxs-lookup"><span data-stu-id="da847-111">To create a time-based cache policy that is based on minimum freshness and maximum age</span></span>  
  
-   <span data-ttu-id="da847-112"><xref:System.Net.Cache.HttpCacheAgeControl.MaxAgeAndMinFresh>를 `cacheAgeControl` 매개 변수 값으로 지정하고 두 개의 <xref:System.TimeSpan> 개체를 <xref:System.Net.Cache.HttpRequestCachePolicy> 생성자에 전달하여 최소 새로 고침 및 최대 기간을 기반으로 하는 시간 기반 캐시 정책을 만듭니다. 하나의 개체는 리소스의 최대 기간을 지정하고 두 번째 개체는 캐시에서 반환된 개체에 허용되는 최소 새로 고침을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="da847-112">Create a time-based cache policy that is based on minimum freshness and maximum age by specifying <xref:System.Net.Cache.HttpCacheAgeControl.MaxAgeAndMinFresh> as the `cacheAgeControl` parameter value and passing two <xref:System.TimeSpan> objects to the <xref:System.Net.Cache.HttpRequestCachePolicy> constructor, one to specify the maximum age for resources and a second to specify the minimum freshness permitted for an object returned from the cache.</span></span>  
  
    ```csharp  
    public static HttpRequestCachePolicy CreateFreshAndAgePolicy(TimeSpan freshMinimum, TimeSpan ageMaximum)  
    {  
        HttpRequestCachePolicy policy =   
        new HttpRequestCachePolicy(HttpCacheAgeControl.MaxAgeAndMinFresh, ageMaximum, freshMinimum);  
        Console.WriteLine(policy.ToString());  
        return policy;  
    }  
    ```  
  
    ```vb  
    Public Shared Function CreateFreshAndAgePolicy(freshMinimum As TimeSpan, ageMaximum As TimeSpan) As HttpRequestCachePolicy  
        Dim policy As New HttpRequestCachePolicy(HttpCacheAgeControl.MaxAgeAndMinFresh, ageMaximum, freshMinimum)  
        Console.WriteLine(policy.ToString())  
        Return policy  
    End Function  
    ```  
  
 <span data-ttu-id="da847-113">다음 호출의 경우:</span><span class="sxs-lookup"><span data-stu-id="da847-113">For the following invocation:</span></span>  
  
```  
CreateFreshAndAgePolicy(new TimeSpan(5,0,0), new TimeSpan(10,0,0));  
```  
  
```  
Level:Default MaxAge:36000 MinFresh:18000  
```  
  
## <a name="see-also"></a><span data-ttu-id="da847-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="da847-114">See Also</span></span>  
 [<span data-ttu-id="da847-115">네트워크 응용 프로그램에 대한 캐시 관리</span><span class="sxs-lookup"><span data-stu-id="da847-115">Cache Management for Network Applications</span></span>](../../../docs/framework/network-programming/cache-management-for-network-applications.md)  
 [<span data-ttu-id="da847-116">캐시 정책</span><span class="sxs-lookup"><span data-stu-id="da847-116">Cache Policy</span></span>](../../../docs/framework/network-programming/cache-policy.md)  
 [<span data-ttu-id="da847-117">위치 기반 캐시 정책</span><span class="sxs-lookup"><span data-stu-id="da847-117">Location-Based Cache Policies</span></span>](../../../docs/framework/network-programming/location-based-cache-policies.md)  
 [<span data-ttu-id="da847-118">시간 기반 캐시 정책</span><span class="sxs-lookup"><span data-stu-id="da847-118">Time-Based Cache Policies</span></span>](../../../docs/framework/network-programming/time-based-cache-policies.md)  
 [<span data-ttu-id="da847-119">\<requestCaching> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="da847-119">\<requestCaching> Element (Network Settings)</span></span>](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)
