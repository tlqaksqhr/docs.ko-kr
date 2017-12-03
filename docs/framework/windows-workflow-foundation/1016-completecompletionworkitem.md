---
title: 1016 - CompleteCompletionWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 246929fb-6f14-440a-814b-cd8349350644
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b01706f6e84987ea20f52c131139e243e8184c51
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="1016---completecompletionworkitem"></a><span data-ttu-id="2c605-102">1016 - CompleteCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="2c605-102">1016 - CompleteCompletionWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="2c605-103">속성</span><span class="sxs-lookup"><span data-stu-id="2c605-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2c605-104">ID</span><span class="sxs-lookup"><span data-stu-id="2c605-104">ID</span></span>|<span data-ttu-id="2c605-105">1016</span><span class="sxs-lookup"><span data-stu-id="2c605-105">1016</span></span>|  
|<span data-ttu-id="2c605-106">키워드</span><span class="sxs-lookup"><span data-stu-id="2c605-106">Keywords</span></span>|<span data-ttu-id="2c605-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="2c605-107">WFRuntime</span></span>|  
|<span data-ttu-id="2c605-108">수준</span><span class="sxs-lookup"><span data-stu-id="2c605-108">Level</span></span>|<span data-ttu-id="2c605-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="2c605-109">Verbose</span></span>|  
|<span data-ttu-id="2c605-110">채널</span><span class="sxs-lookup"><span data-stu-id="2c605-110">Channel</span></span>|<span data-ttu-id="2c605-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="2c605-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2c605-112">설명</span><span class="sxs-lookup"><span data-stu-id="2c605-112">Description</span></span>  
 <span data-ttu-id="2c605-113">CompletionWorkItem이 완료되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2c605-113">Indicates a CompletionWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2c605-114">메시지</span><span class="sxs-lookup"><span data-stu-id="2c605-114">Message</span></span>  
 <span data-ttu-id="2c605-115">부모 작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 CompletionWorkItem이 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2c605-115">A CompletionWorkItem has completed for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="2c605-116">작업 '%4', DisplayName: '%5', InstanceId: '%6'이(가) 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2c605-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="2c605-117">설명</span><span class="sxs-lookup"><span data-stu-id="2c605-117">Details</span></span>  
  
|<span data-ttu-id="2c605-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="2c605-118">Data Item Name</span></span>|<span data-ttu-id="2c605-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="2c605-119">Data Item Type</span></span>|<span data-ttu-id="2c605-120">설명</span><span class="sxs-lookup"><span data-stu-id="2c605-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="2c605-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="2c605-121">ParentActivity</span></span>|<span data-ttu-id="2c605-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="2c605-122">xs:string</span></span>|<span data-ttu-id="2c605-123">부모 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2c605-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="2c605-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="2c605-124">ParentDisplayName</span></span>|<span data-ttu-id="2c605-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="2c605-125">xs:string</span></span>|<span data-ttu-id="2c605-126">부모 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2c605-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="2c605-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="2c605-127">ParentInstanceId</span></span>|<span data-ttu-id="2c605-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="2c605-128">xs:string</span></span>|<span data-ttu-id="2c605-129">부모 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="2c605-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="2c605-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="2c605-130">CompletedActivity</span></span>|<span data-ttu-id="2c605-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="2c605-131">xs:string</span></span>|<span data-ttu-id="2c605-132">완료된 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2c605-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="2c605-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="2c605-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="2c605-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="2c605-134">xs:string</span></span>|<span data-ttu-id="2c605-135">완료된 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2c605-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="2c605-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="2c605-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="2c605-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="2c605-137">xs:string</span></span>|<span data-ttu-id="2c605-138">완료된 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="2c605-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="2c605-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="2c605-139">AppDomain</span></span>|<span data-ttu-id="2c605-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="2c605-140">xs:string</span></span>|<span data-ttu-id="2c605-141">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="2c605-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
