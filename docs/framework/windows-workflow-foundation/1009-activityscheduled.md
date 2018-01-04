---
title: 1009 - ActivityScheduled
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 307e38b6-d47e-47a4-9708-e74d8314b1a1
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4a0d8cc3d17ecd13d9312b42554ef5347cccf213
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="1009---activityscheduled"></a><span data-ttu-id="84604-102">1009 - ActivityScheduled</span><span class="sxs-lookup"><span data-stu-id="84604-102">1009 - ActivityScheduled</span></span>
## <a name="properties"></a><span data-ttu-id="84604-103">속성</span><span class="sxs-lookup"><span data-stu-id="84604-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="84604-104">ID</span><span class="sxs-lookup"><span data-stu-id="84604-104">ID</span></span>|<span data-ttu-id="84604-105">1009</span><span class="sxs-lookup"><span data-stu-id="84604-105">1009</span></span>|  
|<span data-ttu-id="84604-106">키워드</span><span class="sxs-lookup"><span data-stu-id="84604-106">Keywords</span></span>|<span data-ttu-id="84604-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="84604-107">WFRuntime</span></span>|  
|<span data-ttu-id="84604-108">수준</span><span class="sxs-lookup"><span data-stu-id="84604-108">Level</span></span>|<span data-ttu-id="84604-109">정보</span><span class="sxs-lookup"><span data-stu-id="84604-109">Information</span></span>|  
|<span data-ttu-id="84604-110">채널</span><span class="sxs-lookup"><span data-stu-id="84604-110">Channel</span></span>|<span data-ttu-id="84604-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="84604-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="84604-112">설명</span><span class="sxs-lookup"><span data-stu-id="84604-112">Description</span></span>  
 <span data-ttu-id="84604-113">실행 예약되는 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="84604-113">Indicates an activity is being scheduled for execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="84604-114">메시지</span><span class="sxs-lookup"><span data-stu-id="84604-114">Message</span></span>  
 <span data-ttu-id="84604-115">Parent Activity '%1', DisplayName: '%2', InstanceId: '%3' scheduled child Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="84604-115">Parent Activity '%1', DisplayName: '%2', InstanceId: '%3' scheduled child Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="84604-116">설명</span><span class="sxs-lookup"><span data-stu-id="84604-116">Details</span></span>  
  
|<span data-ttu-id="84604-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="84604-117">Data Item Name</span></span>|<span data-ttu-id="84604-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="84604-118">Data Item Type</span></span>|<span data-ttu-id="84604-119">설명</span><span class="sxs-lookup"><span data-stu-id="84604-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="84604-120">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="84604-120">ParentActivity</span></span>|<span data-ttu-id="84604-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="84604-121">xs:string</span></span>|<span data-ttu-id="84604-122">부모 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="84604-122">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="84604-123">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="84604-123">ParentDisplayName</span></span>|<span data-ttu-id="84604-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="84604-124">xs:string</span></span>|<span data-ttu-id="84604-125">부모 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="84604-125">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="84604-126">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="84604-126">ParentInstanceId</span></span>|<span data-ttu-id="84604-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="84604-127">xs:string</span></span>|<span data-ttu-id="84604-128">부모 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="84604-128">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="84604-129">ChildActivity</span><span class="sxs-lookup"><span data-stu-id="84604-129">ChildActivity</span></span>|<span data-ttu-id="84604-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="84604-130">xs:string</span></span>|<span data-ttu-id="84604-131">예약된 자식 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="84604-131">The type name of the scheduled child activity.</span></span>|  
|<span data-ttu-id="84604-132">ChildDisplayName</span><span class="sxs-lookup"><span data-stu-id="84604-132">ChildDisplayName</span></span>|<span data-ttu-id="84604-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="84604-133">xs:string</span></span>|<span data-ttu-id="84604-134">예약된 자식 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="84604-134">The display name of the scheduled child activity.</span></span>|  
|<span data-ttu-id="84604-135">ChildInstanceId</span><span class="sxs-lookup"><span data-stu-id="84604-135">ChildInstanceId</span></span>|<span data-ttu-id="84604-136">xs:string</span><span class="sxs-lookup"><span data-stu-id="84604-136">xs:string</span></span>|<span data-ttu-id="84604-137">예약된 자식 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="84604-137">The instance id of the scheduled child activity.</span></span>|  
|<span data-ttu-id="84604-138">AppDomain</span><span class="sxs-lookup"><span data-stu-id="84604-138">AppDomain</span></span>|<span data-ttu-id="84604-139">xs:string</span><span class="sxs-lookup"><span data-stu-id="84604-139">xs:string</span></span>|<span data-ttu-id="84604-140">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="84604-140">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
