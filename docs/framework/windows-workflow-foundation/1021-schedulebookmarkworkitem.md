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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3dc30100cb134740f51e6b2b38c00b2054d2ab0a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="1021---schedulebookmarkworkitem"></a><span data-ttu-id="ff142-102">1021 - ScheduleBookmarkWorkItem</span><span class="sxs-lookup"><span data-stu-id="ff142-102">1021 - ScheduleBookmarkWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="ff142-103">속성</span><span class="sxs-lookup"><span data-stu-id="ff142-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ff142-104">ID</span><span class="sxs-lookup"><span data-stu-id="ff142-104">ID</span></span>|<span data-ttu-id="ff142-105">1021</span><span class="sxs-lookup"><span data-stu-id="ff142-105">1021</span></span>|  
|<span data-ttu-id="ff142-106">키워드</span><span class="sxs-lookup"><span data-stu-id="ff142-106">Keywords</span></span>|<span data-ttu-id="ff142-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="ff142-107">WFRuntime</span></span>|  
|<span data-ttu-id="ff142-108">수준</span><span class="sxs-lookup"><span data-stu-id="ff142-108">Level</span></span>|<span data-ttu-id="ff142-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="ff142-109">Verbose</span></span>|  
|<span data-ttu-id="ff142-110">채널</span><span class="sxs-lookup"><span data-stu-id="ff142-110">Channel</span></span>|<span data-ttu-id="ff142-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="ff142-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ff142-112">설명</span><span class="sxs-lookup"><span data-stu-id="ff142-112">Description</span></span>  
 <span data-ttu-id="ff142-113">BookmarkWorkItem이 예약되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ff142-113">Indicates a BookmarkWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ff142-114">메시지</span><span class="sxs-lookup"><span data-stu-id="ff142-114">Message</span></span>  
 <span data-ttu-id="ff142-115">작업 '%1', DisplayName에 대해 BookmarkWorkItem이 예약 되었습니다: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="ff142-115">A BookmarkWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="ff142-116">BookmarkName: %4, BookmarkScope: %5.</span><span class="sxs-lookup"><span data-stu-id="ff142-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ff142-117">설명</span><span class="sxs-lookup"><span data-stu-id="ff142-117">Details</span></span>  
  
|<span data-ttu-id="ff142-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="ff142-118">Data Item Name</span></span>|<span data-ttu-id="ff142-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="ff142-119">Data Item Type</span></span>|<span data-ttu-id="ff142-120">설명</span><span class="sxs-lookup"><span data-stu-id="ff142-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ff142-121">동작</span><span class="sxs-lookup"><span data-stu-id="ff142-121">Activity</span></span>|<span data-ttu-id="ff142-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="ff142-122">xs:string</span></span>|<span data-ttu-id="ff142-123">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ff142-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="ff142-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="ff142-124">DisplayName</span></span>|<span data-ttu-id="ff142-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="ff142-125">xs:string</span></span>|<span data-ttu-id="ff142-126">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ff142-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="ff142-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="ff142-127">InstanceId</span></span>|<span data-ttu-id="ff142-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="ff142-128">xs:string</span></span>|<span data-ttu-id="ff142-129">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ff142-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="ff142-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="ff142-130">BookmarkName</span></span>|<span data-ttu-id="ff142-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="ff142-131">xs:string</span></span>|<span data-ttu-id="ff142-132">책갈피 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ff142-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="ff142-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="ff142-133">BookmarkScope</span></span>|<span data-ttu-id="ff142-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="ff142-134">xs:string</span></span>|<span data-ttu-id="ff142-135">책갈피의 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="ff142-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="ff142-136">AppDomain</span><span class="sxs-lookup"><span data-stu-id="ff142-136">AppDomain</span></span>|<span data-ttu-id="ff142-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="ff142-137">xs:string</span></span>|<span data-ttu-id="ff142-138">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="ff142-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
