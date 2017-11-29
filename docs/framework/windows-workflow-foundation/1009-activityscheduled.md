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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d9463fbf2e7f2ac3424488dc3fca322a91d11126
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="1009---activityscheduled"></a><span data-ttu-id="7472a-102">1009 - ActivityScheduled</span><span class="sxs-lookup"><span data-stu-id="7472a-102">1009 - ActivityScheduled</span></span>
## <a name="properties"></a><span data-ttu-id="7472a-103">속성</span><span class="sxs-lookup"><span data-stu-id="7472a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7472a-104">ID</span><span class="sxs-lookup"><span data-stu-id="7472a-104">ID</span></span>|<span data-ttu-id="7472a-105">1009</span><span class="sxs-lookup"><span data-stu-id="7472a-105">1009</span></span>|  
|<span data-ttu-id="7472a-106">키워드</span><span class="sxs-lookup"><span data-stu-id="7472a-106">Keywords</span></span>|<span data-ttu-id="7472a-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="7472a-107">WFRuntime</span></span>|  
|<span data-ttu-id="7472a-108">수준</span><span class="sxs-lookup"><span data-stu-id="7472a-108">Level</span></span>|<span data-ttu-id="7472a-109">정보</span><span class="sxs-lookup"><span data-stu-id="7472a-109">Information</span></span>|  
|<span data-ttu-id="7472a-110">채널</span><span class="sxs-lookup"><span data-stu-id="7472a-110">Channel</span></span>|<span data-ttu-id="7472a-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="7472a-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="7472a-112">설명</span><span class="sxs-lookup"><span data-stu-id="7472a-112">Description</span></span>  
 <span data-ttu-id="7472a-113">실행 예약되는 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7472a-113">Indicates an activity is being scheduled for execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="7472a-114">메시지</span><span class="sxs-lookup"><span data-stu-id="7472a-114">Message</span></span>  
 <span data-ttu-id="7472a-115">Parent Activity '%1', DisplayName: '%2', InstanceId: '%3' scheduled child Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="7472a-115">Parent Activity '%1', DisplayName: '%2', InstanceId: '%3' scheduled child Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="7472a-116">설명</span><span class="sxs-lookup"><span data-stu-id="7472a-116">Details</span></span>  
  
|<span data-ttu-id="7472a-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="7472a-117">Data Item Name</span></span>|<span data-ttu-id="7472a-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="7472a-118">Data Item Type</span></span>|<span data-ttu-id="7472a-119">설명</span><span class="sxs-lookup"><span data-stu-id="7472a-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="7472a-120">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="7472a-120">ParentActivity</span></span>|<span data-ttu-id="7472a-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="7472a-121">xs:string</span></span>|<span data-ttu-id="7472a-122">부모 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7472a-122">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="7472a-123">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="7472a-123">ParentDisplayName</span></span>|<span data-ttu-id="7472a-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="7472a-124">xs:string</span></span>|<span data-ttu-id="7472a-125">부모 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7472a-125">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="7472a-126">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="7472a-126">ParentInstanceId</span></span>|<span data-ttu-id="7472a-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="7472a-127">xs:string</span></span>|<span data-ttu-id="7472a-128">부모 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="7472a-128">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="7472a-129">ChildActivity</span><span class="sxs-lookup"><span data-stu-id="7472a-129">ChildActivity</span></span>|<span data-ttu-id="7472a-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="7472a-130">xs:string</span></span>|<span data-ttu-id="7472a-131">예약된 자식 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7472a-131">The type name of the scheduled child activity.</span></span>|  
|<span data-ttu-id="7472a-132">ChildDisplayName</span><span class="sxs-lookup"><span data-stu-id="7472a-132">ChildDisplayName</span></span>|<span data-ttu-id="7472a-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="7472a-133">xs:string</span></span>|<span data-ttu-id="7472a-134">예약된 자식 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7472a-134">The display name of the scheduled child activity.</span></span>|  
|<span data-ttu-id="7472a-135">ChildInstanceId</span><span class="sxs-lookup"><span data-stu-id="7472a-135">ChildInstanceId</span></span>|<span data-ttu-id="7472a-136">xs:string</span><span class="sxs-lookup"><span data-stu-id="7472a-136">xs:string</span></span>|<span data-ttu-id="7472a-137">예약된 자식 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="7472a-137">The instance id of the scheduled child activity.</span></span>|  
|<span data-ttu-id="7472a-138">AppDomain</span><span class="sxs-lookup"><span data-stu-id="7472a-138">AppDomain</span></span>|<span data-ttu-id="7472a-139">xs:string</span><span class="sxs-lookup"><span data-stu-id="7472a-139">xs:string</span></span>|<span data-ttu-id="7472a-140">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="7472a-140">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
