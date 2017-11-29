---
title: 1014 - ScheduleCompletionWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 84203735-478d-42d8-a320-c175dbddcb38
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b6f58cf711a91a748d3516bdd0708cc89b02c623
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="1014---schedulecompletionworkitem"></a><span data-ttu-id="83715-102">1014 - ScheduleCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="83715-102">1014 - ScheduleCompletionWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="83715-103">속성</span><span class="sxs-lookup"><span data-stu-id="83715-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="83715-104">ID</span><span class="sxs-lookup"><span data-stu-id="83715-104">ID</span></span>|<span data-ttu-id="83715-105">1014</span><span class="sxs-lookup"><span data-stu-id="83715-105">1014</span></span>|  
|<span data-ttu-id="83715-106">키워드</span><span class="sxs-lookup"><span data-stu-id="83715-106">Keywords</span></span>|<span data-ttu-id="83715-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="83715-107">WFRuntime</span></span>|  
|<span data-ttu-id="83715-108">수준</span><span class="sxs-lookup"><span data-stu-id="83715-108">Level</span></span>|<span data-ttu-id="83715-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="83715-109">Verbose</span></span>|  
|<span data-ttu-id="83715-110">채널</span><span class="sxs-lookup"><span data-stu-id="83715-110">Channel</span></span>|<span data-ttu-id="83715-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="83715-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="83715-112">설명</span><span class="sxs-lookup"><span data-stu-id="83715-112">Description</span></span>  
 <span data-ttu-id="83715-113">CompletionWorkItem이 예약되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="83715-113">Indicates a CompletionWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="83715-114">메시지</span><span class="sxs-lookup"><span data-stu-id="83715-114">Message</span></span>  
 <span data-ttu-id="83715-115">부모 작업 '%1', DisplayName에 대해 CompletionWorkItem이 예약 되었습니다: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="83715-115">A CompletionWorkItem has been scheduled for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="83715-116">작업 '%4', DisplayName: '%5', InstanceId: '%6'이(가) 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="83715-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="83715-117">설명</span><span class="sxs-lookup"><span data-stu-id="83715-117">Details</span></span>  
  
|<span data-ttu-id="83715-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="83715-118">Data Item Name</span></span>|<span data-ttu-id="83715-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="83715-119">Data Item Type</span></span>|<span data-ttu-id="83715-120">설명</span><span class="sxs-lookup"><span data-stu-id="83715-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="83715-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="83715-121">ParentActivity</span></span>|<span data-ttu-id="83715-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="83715-122">xs:string</span></span>|<span data-ttu-id="83715-123">부모 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="83715-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="83715-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="83715-124">ParentDisplayName</span></span>|<span data-ttu-id="83715-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="83715-125">xs:string</span></span>|<span data-ttu-id="83715-126">부모 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="83715-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="83715-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="83715-127">ParentInstanceId</span></span>|<span data-ttu-id="83715-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="83715-128">xs:string</span></span>|<span data-ttu-id="83715-129">부모 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="83715-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="83715-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="83715-130">CompletedActivity</span></span>|<span data-ttu-id="83715-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="83715-131">xs:string</span></span>|<span data-ttu-id="83715-132">완료된 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="83715-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="83715-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="83715-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="83715-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="83715-134">xs:string</span></span>|<span data-ttu-id="83715-135">완료된 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="83715-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="83715-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="83715-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="83715-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="83715-137">xs:string</span></span>|<span data-ttu-id="83715-138">완료된 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="83715-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="83715-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="83715-139">AppDomain</span></span>|<span data-ttu-id="83715-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="83715-140">xs:string</span></span>|<span data-ttu-id="83715-141">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="83715-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
