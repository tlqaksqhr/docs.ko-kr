---
title: '방법: 응용 프로그램에 대해 시간 기반 캐시 정책 설정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time-based cache policies
- cache [.NET Framework], time-based policies
- default time-based cache policy
ms.assetid: 6bfce066-a2e7-4add-a05e-85c12ec9f07f
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 021a13b9124cf54712643e33cbf0ca77ec828b27
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33396674"
---
# <a name="how-to-set-the-default-time-based-cache-policy-for-an-application"></a><span data-ttu-id="ebd33-102">방법: 응용 프로그램에 대해 시간 기반 캐시 정책 설정</span><span class="sxs-lookup"><span data-stu-id="ebd33-102">How to: Set the Default Time-Based Cache Policy for an Application</span></span>
<span data-ttu-id="ebd33-103">기본 시간 기반 캐시 정책을 사용하면 [http://www.ietf.org](http://www.ietf.org/)에서 제공되는 RFC 2616의 섹션 13 및 14에 정의된 캐시 동작 및 캐시된 리소스와 함께 전송된 헤더를 통해 정의된 캐시 동작이 응용 프로그램에 나타날 수 있습니다. 이것은 대부분의 응용 프로그램에서 적절한 캐시 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="ebd33-103">The default time-based cache policy allows an application to have its cache behavior defined by the headers sent with the cached resource and the cache behavior defined in sections 13 and 14 of RFC 2616, available at [http://www.ietf.org](http://www.ietf.org/). This is the appropriate cache behavior for most applications.</span></span>  
  
### <a name="to-set-the-default-automatic-policy-for-an-application"></a><span data-ttu-id="ebd33-104">응용 프로그램에 대한 기본 자동 정책을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="ebd33-104">To set the default automatic policy for an application</span></span>  
  
1.  <span data-ttu-id="ebd33-105">기본 시간 기반 정책 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ebd33-105">Create a default time-based policy object.</span></span>  
  
2.  <span data-ttu-id="ebd33-106">정책 개체를 응용 프로그램 도메인의 기본값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ebd33-106">Set the policy object as the default for the application domain.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ebd33-107">예</span><span class="sxs-lookup"><span data-stu-id="ebd33-107">Example</span></span>  
 <span data-ttu-id="ebd33-108">이 섹션의 두 가지 예제는 동일한 정책을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ebd33-108">The two examples in this section produce identical policies.</span></span>  
  
 <span data-ttu-id="ebd33-109">다음 예제에서는 기본 시간 기반 정책을 만들고 이 정책을 응용 프로그램 도메인의 기본값으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ebd33-109">The following example creates a default time-based policy and sets it as the default for the application domain.</span></span>  
  
```csharp  
public static void SetDefaultTimeBasedPolicy ()  
{  
    HttpRequestCachePolicy policy = new HttpRequestCachePolicy ();  
    HttpWebRequest.DefaultCachePolicy = policy ;  
}  
```  
  
```vb  
Public Shared Sub SetDefaultTimeBasedPolicy ()  
    Dim policy = New HttpRequestCachePolicy ()  
    HttpWebRequest.DefaultCachePolicy = policy  
End Sub  
```  
  
 <span data-ttu-id="ebd33-110">다음 예제와 같이 <xref:System.Net.Cache.RequestCachePolicy> 클래스를 사용하여 기본 시간 기반 캐시 정책을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebd33-110">You can also create the default time-based cache policy using the <xref:System.Net.Cache.RequestCachePolicy> class as shown in the following example:</span></span>  
  
```csharp  
public static void SetDefaultTimeBasedPolicy2()  
{  
    RequestCachePolicy policy = new RequestCachePolicy ();  
    HttpWebRequest.DefaultCachePolicy = policy ;  
}  
```  
  
```vb  
Public Shared Sub SetDefaultTimeBasedPolicy2()  
    Dim policy As New RequestCachePolicy()  
    HttpWebRequest.DefaultCachePolicy = policy  
End Sub  
```  
  
## <a name="see-also"></a><span data-ttu-id="ebd33-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ebd33-111">See Also</span></span>  
 [<span data-ttu-id="ebd33-112">네트워크 응용 프로그램에 대한 캐시 관리</span><span class="sxs-lookup"><span data-stu-id="ebd33-112">Cache Management for Network Applications</span></span>](../../../docs/framework/network-programming/cache-management-for-network-applications.md)  
 [<span data-ttu-id="ebd33-113">캐시 정책</span><span class="sxs-lookup"><span data-stu-id="ebd33-113">Cache Policy</span></span>](../../../docs/framework/network-programming/cache-policy.md)  
 [<span data-ttu-id="ebd33-114">위치 기반 캐시 정책</span><span class="sxs-lookup"><span data-stu-id="ebd33-114">Location-Based Cache Policies</span></span>](../../../docs/framework/network-programming/location-based-cache-policies.md)  
 [<span data-ttu-id="ebd33-115">시간 기반 캐시 정책</span><span class="sxs-lookup"><span data-stu-id="ebd33-115">Time-Based Cache Policies</span></span>](../../../docs/framework/network-programming/time-based-cache-policies.md)  
 [<span data-ttu-id="ebd33-116">\<requestCaching> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="ebd33-116">\<requestCaching> Element (Network Settings)</span></span>](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)
