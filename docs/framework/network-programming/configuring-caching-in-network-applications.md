---
title: 네트워크 응용 프로그램에서 캐싱 구성
ms.date: 03/30/2017
helpviewer_keywords:
- cache [.NET Framework], configuring
ms.assetid: 3f694a1c-de5d-47cf-a6eb-cfc369fb8a9f
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 2213b5401c7b82771dcf7a1c982f1b3d0f347832
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="configuring-caching-in-network-applications"></a><span data-ttu-id="504c8-102">네트워크 응용 프로그램에서 캐싱 구성</span><span class="sxs-lookup"><span data-stu-id="504c8-102">Configuring Caching in Network Applications</span></span>
<span data-ttu-id="504c8-103">캐싱을 구성하려면 응용 프로그램 또는 <xref:System.Net.WebRequest> 수준에서 캐시 정책을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="504c8-103">To configure caching, you must specify a cache policy at the application or <xref:System.Net.WebRequest> level.</span></span> <span data-ttu-id="504c8-104">다음 항목에서는 캐싱을 사용하도록 응용 프로그램 및 요청을 구성하는 방법을 보여 주는 코드 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="504c8-104">The following topics provide code examples that demonstrate configuring applications and requests to use caching.</span></span>  
  
-   [<span data-ttu-id="504c8-105">방법: 응용 프로그램에 대해 위치 기반 캐시 정책 설정</span><span class="sxs-lookup"><span data-stu-id="504c8-105">How to: Set a Location-Based Cache Policy for an Application</span></span>](../../../docs/framework/network-programming/how-to-set-a-location-based-cache-policy-for-an-application.md)  
  
-   [<span data-ttu-id="504c8-106">방법: 응용 프로그램에 대해 시간 기반 캐시 정책 설정</span><span class="sxs-lookup"><span data-stu-id="504c8-106">How to: Set the Default Time-Based Cache Policy for an Application</span></span>](../../../docs/framework/network-programming/how-to-set-the-default-time-based-cache-policy-for-an-application.md)  
  
-   [<span data-ttu-id="504c8-107">방법: 시간 기반 캐시 정책을 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="504c8-107">How to: Customize a Time-Based Cache Policy</span></span>](../../../docs/framework/network-programming/how-to-customize-a-time-based-cache-policy.md)  
  
-   [<span data-ttu-id="504c8-108">방법: 요청에 캐시 정책 설정</span><span class="sxs-lookup"><span data-stu-id="504c8-108">How to: Set Cache Policy for a Request</span></span>](../../../docs/framework/network-programming/how-to-set-cache-policy-for-a-request.md)  
  
 <span data-ttu-id="504c8-109">응용 프로그램 또는 컴퓨터 구성 파일을 사용하여 캐시 정책을 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="504c8-109">You can also configure cache policy using application or machine configuration files.</span></span> <span data-ttu-id="504c8-110">자세한 내용은 [\<requestCaching> 요소(네트워크 설정)](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="504c8-110">For more information, see &#124; [\<requestCaching> Element (Network Settings)](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="504c8-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="504c8-111">See Also</span></span>  
 [<span data-ttu-id="504c8-112">네트워크 응용 프로그램에 대한 캐시 관리</span><span class="sxs-lookup"><span data-stu-id="504c8-112">Cache Management for Network Applications</span></span>](../../../docs/framework/network-programming/cache-management-for-network-applications.md)  
 [<span data-ttu-id="504c8-113">캐시 정책</span><span class="sxs-lookup"><span data-stu-id="504c8-113">Cache Policy</span></span>](../../../docs/framework/network-programming/cache-policy.md)  
 [<span data-ttu-id="504c8-114">위치 기반 캐시 정책</span><span class="sxs-lookup"><span data-stu-id="504c8-114">Location-Based Cache Policies</span></span>](../../../docs/framework/network-programming/location-based-cache-policies.md)  
 [<span data-ttu-id="504c8-115">시간 기반 캐시 정책</span><span class="sxs-lookup"><span data-stu-id="504c8-115">Time-Based Cache Policies</span></span>](../../../docs/framework/network-programming/time-based-cache-policies.md)
