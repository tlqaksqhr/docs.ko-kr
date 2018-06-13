---
title: 57398 - MaxInstancesExceeded
ms.date: 03/30/2017
ms.assetid: f943d209-dfeb-43e5-b572-c9a06217936e
ms.openlocfilehash: d644c25ec2dee06eea4a5fb66c30792bb650f252
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33512553"
---
# <a name="57398---maxinstancesexceeded"></a><span data-ttu-id="202d8-102">57398 - MaxInstancesExceeded</span><span class="sxs-lookup"><span data-stu-id="202d8-102">57398 - MaxInstancesExceeded</span></span>
## <a name="properties"></a><span data-ttu-id="202d8-103">속성</span><span class="sxs-lookup"><span data-stu-id="202d8-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="202d8-104">ID</span><span class="sxs-lookup"><span data-stu-id="202d8-104">ID</span></span>|<span data-ttu-id="202d8-105">57398</span><span class="sxs-lookup"><span data-stu-id="202d8-105">57398</span></span>|  
|<span data-ttu-id="202d8-106">키워드</span><span class="sxs-lookup"><span data-stu-id="202d8-106">Keywords</span></span>|<span data-ttu-id="202d8-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="202d8-107">WFServices</span></span>|  
|<span data-ttu-id="202d8-108">수준</span><span class="sxs-lookup"><span data-stu-id="202d8-108">Level</span></span>|<span data-ttu-id="202d8-109">경고</span><span class="sxs-lookup"><span data-stu-id="202d8-109">Warning</span></span>|  
|<span data-ttu-id="202d8-110">채널</span><span class="sxs-lookup"><span data-stu-id="202d8-110">Channel</span></span>|<span data-ttu-id="202d8-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/분석</span><span class="sxs-lookup"><span data-stu-id="202d8-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="202d8-112">설명</span><span class="sxs-lookup"><span data-stu-id="202d8-112">Description</span></span>  
 <span data-ttu-id="202d8-113">시스템이 스로틀 'MaxConcurrentInstances'에 대해 설정된 한도에 도달했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="202d8-113">Indicates the system hit the limit set for throttle 'MaxConcurrentInstances'.</span></span>  
  
## <a name="message"></a><span data-ttu-id="202d8-114">메시지</span><span class="sxs-lookup"><span data-stu-id="202d8-114">Message</span></span>  
 <span data-ttu-id="202d8-115">시스템이 'MaxConcurrentInstances' 스로틀에 대해 설정된 한계에 도달했습니다.</span><span class="sxs-lookup"><span data-stu-id="202d8-115">The system hit the limit set for throttle 'MaxConcurrentInstances'.</span></span> <span data-ttu-id="202d8-116">이 스로틀에 대한 제한은 %1(으)로 설정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="202d8-116">Limit for this throttle was set to %1.</span></span> <span data-ttu-id="202d8-117">serviceThrottle 요소에서 'maxConcurrentInstances' 특성을 수정하거나 ServiceThrottlingBehavior 동작에서 'MaxConcurrentInstances' 속성을 수정하여 스로틀 값을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="202d8-117">Throttle value can be changed by modifying attribute 'maxConcurrentInstances' in serviceThrottle element or by modifying 'MaxConcurrentInstances' property on behavior ServiceThrottlingBehavior.</span></span>  
  
## <a name="details"></a><span data-ttu-id="202d8-118">설명</span><span class="sxs-lookup"><span data-stu-id="202d8-118">Details</span></span>  
  
|<span data-ttu-id="202d8-119">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="202d8-119">Data Item Name</span></span>|<span data-ttu-id="202d8-120">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="202d8-120">Data Item Type</span></span>|<span data-ttu-id="202d8-121">설명</span><span class="sxs-lookup"><span data-stu-id="202d8-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="202d8-122">이름</span><span class="sxs-lookup"><span data-stu-id="202d8-122">Name</span></span>|<span data-ttu-id="202d8-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="202d8-123">xs:string</span></span>|<span data-ttu-id="202d8-124">항목의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="202d8-124">The name of the item.</span></span>|  
|<span data-ttu-id="202d8-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="202d8-125">AppDomain</span></span>|<span data-ttu-id="202d8-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="202d8-126">xs:string</span></span>|<span data-ttu-id="202d8-127">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="202d8-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
