---
title: 210 - MessageThrottleExceeded
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 24ca08ea-c11c-4753-946e-98aa820f8711
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c39c454e3a9bb70840b47271432d555d24fb167a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="210---messagethrottleexceeded"></a><span data-ttu-id="a8832-102">210 - MessageThrottleExceeded</span><span class="sxs-lookup"><span data-stu-id="a8832-102">210 - MessageThrottleExceeded</span></span>
## <a name="properties"></a><span data-ttu-id="a8832-103">속성</span><span class="sxs-lookup"><span data-stu-id="a8832-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a8832-104">ID</span><span class="sxs-lookup"><span data-stu-id="a8832-104">ID</span></span>|<span data-ttu-id="a8832-105">210</span><span class="sxs-lookup"><span data-stu-id="a8832-105">210</span></span>|  
|<span data-ttu-id="a8832-106">키워드가</span><span class="sxs-lookup"><span data-stu-id="a8832-106">Keywords</span></span>|<span data-ttu-id="a8832-107">EndToEndMonitoring, HealthMonitoring, 문제 해결, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="a8832-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="a8832-108">수준</span><span class="sxs-lookup"><span data-stu-id="a8832-108">Level</span></span>|<span data-ttu-id="a8832-109">경고</span><span class="sxs-lookup"><span data-stu-id="a8832-109">Warning</span></span>|  
|<span data-ttu-id="a8832-110">채널</span><span class="sxs-lookup"><span data-stu-id="a8832-110">Channel</span></span>|<span data-ttu-id="a8832-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/분석</span><span class="sxs-lookup"><span data-stu-id="a8832-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a8832-112">설명</span><span class="sxs-lookup"><span data-stu-id="a8832-112">Description</span></span>  
 <span data-ttu-id="a8832-113">이 이벤트는 세 개의 기본 서비스 스로틀 중 하나가 초과되었을 때 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="a8832-113">This event is emitted when one of the three main service throttles have been exceeded.</span></span> <span data-ttu-id="a8832-114">이 이벤트는 스로틀 한계가 처음 초과되는 경우에만 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="a8832-114">Note that this event is only emitted when the throttle limit is initially exceeded.</span></span> <span data-ttu-id="a8832-115">예를 들어 동시 호출의 스로틀 한계가 10인 경우 11번째 동시 호출을 수행하면 `MessageThrottleExceeded` 이벤트가 내보내지지만</span><span class="sxs-lookup"><span data-stu-id="a8832-115">For example, if the throttle limit for concurrent calls is 10, the 11th concurrent call results in a `MessageThrottleExceeded` event.</span></span> <span data-ttu-id="a8832-116">12번째 호출부터는 이 이벤트가 내보내지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a8832-116">The 12th call does not result in another event.</span></span> <span data-ttu-id="a8832-117">또한 불필요한 이벤트 스트림을 방지하기 위해 스로틀 한계를 넘나드는 작업을 수행하는 경우에도 이 이벤트가 내보내지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a8832-117">Additionally, to avoid a noisy event stream, activity that hovers around the limit does not result in another event.</span></span> <span data-ttu-id="a8832-118">이 예제에서는 두 개의 호출이 완료되면 동시 호출 수가 9가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8832-118">In this example, if a couple of calls complete then there are 9 concurrent calls.</span></span> <span data-ttu-id="a8832-119">나중에 두 개의 호출이 더 완료되면 현재 값은 다시 11이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8832-119">If subsequently two more calls come in, the current value is again 11.</span></span> <span data-ttu-id="a8832-120">이 경우 이 이벤트가 내보내지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a8832-120">This does not result in another event.</span></span> <span data-ttu-id="a8832-121">현재 값이 스로틀 한계의 70%에 도달하면 작업이 더디게 진행됨을 나타내는 다른 이벤트가 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="a8832-121">When the current value falls to 70 percent of the throttle limit a different event is emitted that indicates that the activity has slowed.</span></span> <span data-ttu-id="a8832-122">스로틀 한계를 초과하는 추가 작업을 수행하면 다른 `MessageThrottleExceeded` 이벤트가 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="a8832-122">Future activity that exceeds the limit results in another `MessageThrottleExceeded` event being emitted.</span></span> <span data-ttu-id="a8832-123">이 예제에서는 동시 호출 수가 7에서 11이 되면 다른 `MessageThrottleExceeded` 이벤트가 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="a8832-123">In this example, if the amount of concurrent calls falls to 7 and then again reaches 11 and another `MessageThrottleExceeded` event is emitted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a8832-124">메시지</span><span class="sxs-lookup"><span data-stu-id="a8832-124">Message</span></span>  
 <span data-ttu-id="a8832-125">'%1'의 스로틀 한계 '%2'에 도달했습니다.</span><span class="sxs-lookup"><span data-stu-id="a8832-125">The '%1' throttle limit of '%2' was hit.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a8832-126">세부 정보</span><span class="sxs-lookup"><span data-stu-id="a8832-126">Details</span></span>  
  
|<span data-ttu-id="a8832-127">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="a8832-127">Data Item Name</span></span>|<span data-ttu-id="a8832-128">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="a8832-128">Data Item Type</span></span>|<span data-ttu-id="a8832-129">설명</span><span class="sxs-lookup"><span data-stu-id="a8832-129">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a8832-130">Throttle Name</span><span class="sxs-lookup"><span data-stu-id="a8832-130">Throttle Name</span></span>|`xs:string`|<span data-ttu-id="a8832-131">초과한 스로틀의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a8832-131">The name of the throttle that has been exceeded.</span></span> <span data-ttu-id="a8832-132">`MaxConcurrentCalls`, `MaxConcurrentInstances` 또는 `MaxConcurrentSessions` 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="a8832-132">Either `MaxConcurrentCalls`, `MaxConcurrentInstances`, or `MaxConcurrentSessions`,</span></span>|  
|<span data-ttu-id="a8832-133">Limit</span><span class="sxs-lookup"><span data-stu-id="a8832-133">Limit</span></span>|`xs:long`|<span data-ttu-id="a8832-134">현재 구성된 스로틀 한계입니다.</span><span class="sxs-lookup"><span data-stu-id="a8832-134">The currently configured limit of the throttle.</span></span>|  
|<span data-ttu-id="a8832-135">HostReference</span><span class="sxs-lookup"><span data-stu-id="a8832-135">HostReference</span></span>|`xs:string`|<span data-ttu-id="a8832-136">웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="a8832-136">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="a8832-137">해당 형식으로 정의 됩니다 ' 웹 Site Name Application Virtual Path &#124; 서비스의 가상 경로 &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="a8832-137">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="a8832-138">예: ' 기본 웹 사이트/CalculatorApplication #124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="a8832-138">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="a8832-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="a8832-139">AppDomain</span></span>|`xs:string`|<span data-ttu-id="a8832-140">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="a8832-140">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
