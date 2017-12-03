---
title: 1021 - ScheduleBookmarkWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2e0da311-b219-4637-9460-90cdafcc4ecd
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 781f4b6d064ac90f762e10e03783422c64a1bf05
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="1021---schedulebookmarkworkitem"></a><span data-ttu-id="5f13c-102">1021 - ScheduleBookmarkWorkItem</span><span class="sxs-lookup"><span data-stu-id="5f13c-102">1021 - ScheduleBookmarkWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="5f13c-103">속성</span><span class="sxs-lookup"><span data-stu-id="5f13c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5f13c-104">ID</span><span class="sxs-lookup"><span data-stu-id="5f13c-104">ID</span></span>|<span data-ttu-id="5f13c-105">1021</span><span class="sxs-lookup"><span data-stu-id="5f13c-105">1021</span></span>|  
|<span data-ttu-id="5f13c-106">키워드</span><span class="sxs-lookup"><span data-stu-id="5f13c-106">Keywords</span></span>|<span data-ttu-id="5f13c-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="5f13c-107">WFRuntime</span></span>|  
|<span data-ttu-id="5f13c-108">수준</span><span class="sxs-lookup"><span data-stu-id="5f13c-108">Level</span></span>|<span data-ttu-id="5f13c-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="5f13c-109">Verbose</span></span>|  
|<span data-ttu-id="5f13c-110">채널</span><span class="sxs-lookup"><span data-stu-id="5f13c-110">Channel</span></span>|<span data-ttu-id="5f13c-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="5f13c-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5f13c-112">설명</span><span class="sxs-lookup"><span data-stu-id="5f13c-112">Description</span></span>  
 <span data-ttu-id="5f13c-113">BookmarkWorkItem이 예약되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5f13c-113">Indicates a BookmarkWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5f13c-114">메시지</span><span class="sxs-lookup"><span data-stu-id="5f13c-114">Message</span></span>  
 <span data-ttu-id="5f13c-115">작업 '%1', DisplayName에 대해 BookmarkWorkItem이 예약 되었습니다: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="5f13c-115">A BookmarkWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="5f13c-116">BookmarkName: %4, BookmarkScope: %5.</span><span class="sxs-lookup"><span data-stu-id="5f13c-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5f13c-117">설명</span><span class="sxs-lookup"><span data-stu-id="5f13c-117">Details</span></span>  
  
|<span data-ttu-id="5f13c-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="5f13c-118">Data Item Name</span></span>|<span data-ttu-id="5f13c-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="5f13c-119">Data Item Type</span></span>|<span data-ttu-id="5f13c-120">설명</span><span class="sxs-lookup"><span data-stu-id="5f13c-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5f13c-121">동작</span><span class="sxs-lookup"><span data-stu-id="5f13c-121">Activity</span></span>|<span data-ttu-id="5f13c-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="5f13c-122">xs:string</span></span>|<span data-ttu-id="5f13c-123">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5f13c-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="5f13c-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="5f13c-124">DisplayName</span></span>|<span data-ttu-id="5f13c-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="5f13c-125">xs:string</span></span>|<span data-ttu-id="5f13c-126">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5f13c-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="5f13c-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="5f13c-127">InstanceId</span></span>|<span data-ttu-id="5f13c-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="5f13c-128">xs:string</span></span>|<span data-ttu-id="5f13c-129">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="5f13c-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="5f13c-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="5f13c-130">BookmarkName</span></span>|<span data-ttu-id="5f13c-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="5f13c-131">xs:string</span></span>|<span data-ttu-id="5f13c-132">책갈피 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5f13c-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="5f13c-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="5f13c-133">BookmarkScope</span></span>|<span data-ttu-id="5f13c-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="5f13c-134">xs:string</span></span>|<span data-ttu-id="5f13c-135">책갈피의 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="5f13c-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="5f13c-136">AppDomain</span><span class="sxs-lookup"><span data-stu-id="5f13c-136">AppDomain</span></span>|<span data-ttu-id="5f13c-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="5f13c-137">xs:string</span></span>|<span data-ttu-id="5f13c-138">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="5f13c-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
