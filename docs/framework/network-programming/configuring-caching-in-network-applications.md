---
title: "네트워크 응용 프로그램에서 캐싱 구성"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: cache [.NET Framework], configuring
ms.assetid: 3f694a1c-de5d-47cf-a6eb-cfc369fb8a9f
caps.latest.revision: "10"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: fe70c8952451f5af8ac46549919ca164816819e5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="configuring-caching-in-network-applications"></a><span data-ttu-id="cacef-102">네트워크 응용 프로그램에서 캐싱 구성</span><span class="sxs-lookup"><span data-stu-id="cacef-102">Configuring Caching in Network Applications</span></span>
<span data-ttu-id="cacef-103">캐싱을 구성하려면 응용 프로그램 또는 <xref:System.Net.WebRequest> 수준에서 캐시 정책을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cacef-103">To configure caching, you must specify a cache policy at the application or <xref:System.Net.WebRequest> level.</span></span> <span data-ttu-id="cacef-104">다음 항목에서는 캐싱을 사용하도록 응용 프로그램 및 요청을 구성하는 방법을 보여 주는 코드 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cacef-104">The following topics provide code examples that demonstrate configuring applications and requests to use caching.</span></span>  
  
-   [<span data-ttu-id="cacef-105">방법: 응용 프로그램에 대해 위치 기반 캐시 정책 설정</span><span class="sxs-lookup"><span data-stu-id="cacef-105">How to: Set a Location-Based Cache Policy for an Application</span></span>](../../../docs/framework/network-programming/how-to-set-a-location-based-cache-policy-for-an-application.md)  
  
-   [<span data-ttu-id="cacef-106">방법: 응용 프로그램에 대해 시간 기반 캐시 정책 설정</span><span class="sxs-lookup"><span data-stu-id="cacef-106">How to: Set the Default Time-Based Cache Policy for an Application</span></span>](../../../docs/framework/network-programming/how-to-set-the-default-time-based-cache-policy-for-an-application.md)  
  
-   [<span data-ttu-id="cacef-107">방법: 시간 기반 캐시 정책을 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="cacef-107">How to: Customize a Time-Based Cache Policy</span></span>](../../../docs/framework/network-programming/how-to-customize-a-time-based-cache-policy.md)  
  
-   [<span data-ttu-id="cacef-108">방법: 요청에 캐시 정책 설정</span><span class="sxs-lookup"><span data-stu-id="cacef-108">How to: Set Cache Policy for a Request</span></span>](../../../docs/framework/network-programming/how-to-set-cache-policy-for-a-request.md)  
  
 <span data-ttu-id="cacef-109">응용 프로그램 또는 컴퓨터 구성 파일을 사용하여 캐시 정책을 구성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cacef-109">You can also configure cache policy using application or machine configuration files.</span></span> <span data-ttu-id="cacef-110">자세한 내용은 [\<requestCaching> 요소(네트워크 설정)](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cacef-110">For more information, see &#124; [\<requestCaching> Element (Network Settings)](../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cacef-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cacef-111">See Also</span></span>  
 [<span data-ttu-id="cacef-112">네트워크 응용 프로그램에 대한 캐시 관리</span><span class="sxs-lookup"><span data-stu-id="cacef-112">Cache Management for Network Applications</span></span>](../../../docs/framework/network-programming/cache-management-for-network-applications.md)  
 [<span data-ttu-id="cacef-113">캐시 정책</span><span class="sxs-lookup"><span data-stu-id="cacef-113">Cache Policy</span></span>](../../../docs/framework/network-programming/cache-policy.md)  
 [<span data-ttu-id="cacef-114">위치 기반 캐시 정책</span><span class="sxs-lookup"><span data-stu-id="cacef-114">Location-Based Cache Policies</span></span>](../../../docs/framework/network-programming/location-based-cache-policies.md)  
 [<span data-ttu-id="cacef-115">시간 기반 캐시 정책</span><span class="sxs-lookup"><span data-stu-id="cacef-115">Time-Based Cache Policies</span></span>](../../../docs/framework/network-programming/time-based-cache-policies.md)
