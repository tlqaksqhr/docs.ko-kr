---
title: 1020 - CreateBookmark
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4bee948d-816f-4803-85cc-3883b5e23d10
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7c47a5464222d12c1dba717e24606e5614e392f1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="1020---createbookmark"></a><span data-ttu-id="3b7a7-102">1020 - CreateBookmark</span><span class="sxs-lookup"><span data-stu-id="3b7a7-102">1020 - CreateBookmark</span></span>
## <a name="properties"></a><span data-ttu-id="3b7a7-103">속성</span><span class="sxs-lookup"><span data-stu-id="3b7a7-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3b7a7-104">ID</span><span class="sxs-lookup"><span data-stu-id="3b7a7-104">ID</span></span>|<span data-ttu-id="3b7a7-105">1020</span><span class="sxs-lookup"><span data-stu-id="3b7a7-105">1020</span></span>|  
|<span data-ttu-id="3b7a7-106">키워드</span><span class="sxs-lookup"><span data-stu-id="3b7a7-106">Keywords</span></span>|<span data-ttu-id="3b7a7-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="3b7a7-107">WFRuntime</span></span>|  
|<span data-ttu-id="3b7a7-108">수준</span><span class="sxs-lookup"><span data-stu-id="3b7a7-108">Level</span></span>|<span data-ttu-id="3b7a7-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="3b7a7-109">Verbose</span></span>|  
|<span data-ttu-id="3b7a7-110">채널</span><span class="sxs-lookup"><span data-stu-id="3b7a7-110">Channel</span></span>|<span data-ttu-id="3b7a7-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="3b7a7-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3b7a7-112">설명</span><span class="sxs-lookup"><span data-stu-id="3b7a7-112">Description</span></span>  
 <span data-ttu-id="3b7a7-113">작업에 대한 책갈피가 만들어졌음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3b7a7-113">Indicates a bookmark has been created for an activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3b7a7-114">메시지</span><span class="sxs-lookup"><span data-stu-id="3b7a7-114">Message</span></span>  
 <span data-ttu-id="3b7a7-115">책갈피를 만든 작업 '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="3b7a7-115">A Bookmark has been created for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="3b7a7-116">BookmarkName: %4, BookmarkScope: %5.</span><span class="sxs-lookup"><span data-stu-id="3b7a7-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3b7a7-117">설명</span><span class="sxs-lookup"><span data-stu-id="3b7a7-117">Details</span></span>  
  
|<span data-ttu-id="3b7a7-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="3b7a7-118">Data Item Name</span></span>|<span data-ttu-id="3b7a7-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="3b7a7-119">Data Item Type</span></span>|<span data-ttu-id="3b7a7-120">설명</span><span class="sxs-lookup"><span data-stu-id="3b7a7-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3b7a7-121">동작</span><span class="sxs-lookup"><span data-stu-id="3b7a7-121">Activity</span></span>|<span data-ttu-id="3b7a7-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="3b7a7-122">xs:string</span></span>|<span data-ttu-id="3b7a7-123">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3b7a7-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="3b7a7-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="3b7a7-124">DisplayName</span></span>|<span data-ttu-id="3b7a7-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="3b7a7-125">xs:string</span></span>|<span data-ttu-id="3b7a7-126">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3b7a7-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="3b7a7-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="3b7a7-127">InstanceId</span></span>|<span data-ttu-id="3b7a7-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="3b7a7-128">xs:string</span></span>|<span data-ttu-id="3b7a7-129">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="3b7a7-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="3b7a7-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="3b7a7-130">BookmarkName</span></span>|<span data-ttu-id="3b7a7-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="3b7a7-131">xs:string</span></span>|<span data-ttu-id="3b7a7-132">책갈피 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3b7a7-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="3b7a7-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="3b7a7-133">BookmarkScope</span></span>|<span data-ttu-id="3b7a7-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="3b7a7-134">xs:string</span></span>|<span data-ttu-id="3b7a7-135">책갈피의 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="3b7a7-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="3b7a7-136">AppDomain</span><span class="sxs-lookup"><span data-stu-id="3b7a7-136">AppDomain</span></span>|<span data-ttu-id="3b7a7-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="3b7a7-137">xs:string</span></span>|<span data-ttu-id="3b7a7-138">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="3b7a7-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
