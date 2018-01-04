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
ms.workload: dotnet
ms.openlocfilehash: 61c67792f807907f58480f3bfa3d192b811766b4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="1021---schedulebookmarkworkitem"></a><span data-ttu-id="da29e-102">1021 - ScheduleBookmarkWorkItem</span><span class="sxs-lookup"><span data-stu-id="da29e-102">1021 - ScheduleBookmarkWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="da29e-103">속성</span><span class="sxs-lookup"><span data-stu-id="da29e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="da29e-104">ID</span><span class="sxs-lookup"><span data-stu-id="da29e-104">ID</span></span>|<span data-ttu-id="da29e-105">1021</span><span class="sxs-lookup"><span data-stu-id="da29e-105">1021</span></span>|  
|<span data-ttu-id="da29e-106">키워드</span><span class="sxs-lookup"><span data-stu-id="da29e-106">Keywords</span></span>|<span data-ttu-id="da29e-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="da29e-107">WFRuntime</span></span>|  
|<span data-ttu-id="da29e-108">수준</span><span class="sxs-lookup"><span data-stu-id="da29e-108">Level</span></span>|<span data-ttu-id="da29e-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="da29e-109">Verbose</span></span>|  
|<span data-ttu-id="da29e-110">채널</span><span class="sxs-lookup"><span data-stu-id="da29e-110">Channel</span></span>|<span data-ttu-id="da29e-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="da29e-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="da29e-112">설명</span><span class="sxs-lookup"><span data-stu-id="da29e-112">Description</span></span>  
 <span data-ttu-id="da29e-113">BookmarkWorkItem이 예약되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="da29e-113">Indicates a BookmarkWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="da29e-114">메시지</span><span class="sxs-lookup"><span data-stu-id="da29e-114">Message</span></span>  
 <span data-ttu-id="da29e-115">작업 '%1', DisplayName에 대해 BookmarkWorkItem이 예약 되었습니다: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="da29e-115">A BookmarkWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="da29e-116">BookmarkName: %4, BookmarkScope: %5.</span><span class="sxs-lookup"><span data-stu-id="da29e-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="da29e-117">설명</span><span class="sxs-lookup"><span data-stu-id="da29e-117">Details</span></span>  
  
|<span data-ttu-id="da29e-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="da29e-118">Data Item Name</span></span>|<span data-ttu-id="da29e-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="da29e-119">Data Item Type</span></span>|<span data-ttu-id="da29e-120">설명</span><span class="sxs-lookup"><span data-stu-id="da29e-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="da29e-121">동작</span><span class="sxs-lookup"><span data-stu-id="da29e-121">Activity</span></span>|<span data-ttu-id="da29e-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="da29e-122">xs:string</span></span>|<span data-ttu-id="da29e-123">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="da29e-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="da29e-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="da29e-124">DisplayName</span></span>|<span data-ttu-id="da29e-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="da29e-125">xs:string</span></span>|<span data-ttu-id="da29e-126">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="da29e-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="da29e-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="da29e-127">InstanceId</span></span>|<span data-ttu-id="da29e-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="da29e-128">xs:string</span></span>|<span data-ttu-id="da29e-129">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="da29e-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="da29e-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="da29e-130">BookmarkName</span></span>|<span data-ttu-id="da29e-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="da29e-131">xs:string</span></span>|<span data-ttu-id="da29e-132">책갈피 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="da29e-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="da29e-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="da29e-133">BookmarkScope</span></span>|<span data-ttu-id="da29e-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="da29e-134">xs:string</span></span>|<span data-ttu-id="da29e-135">책갈피의 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="da29e-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="da29e-136">AppDomain</span><span class="sxs-lookup"><span data-stu-id="da29e-136">AppDomain</span></span>|<span data-ttu-id="da29e-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="da29e-137">xs:string</span></span>|<span data-ttu-id="da29e-138">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="da29e-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
