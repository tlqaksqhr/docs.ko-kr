---
title: 1022 - StartBookmarkWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4415fbdb-0329-4019-803f-aea66e75f3da
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cdb6af10c45e7a93e9a68e6150e5d239002cce04
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="1022---startbookmarkworkitem"></a><span data-ttu-id="76f40-102">1022 - StartBookmarkWorkItem</span><span class="sxs-lookup"><span data-stu-id="76f40-102">1022 - StartBookmarkWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="76f40-103">속성</span><span class="sxs-lookup"><span data-stu-id="76f40-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="76f40-104">ID</span><span class="sxs-lookup"><span data-stu-id="76f40-104">ID</span></span>|<span data-ttu-id="76f40-105">1022</span><span class="sxs-lookup"><span data-stu-id="76f40-105">1022</span></span>|  
|<span data-ttu-id="76f40-106">키워드</span><span class="sxs-lookup"><span data-stu-id="76f40-106">Keywords</span></span>|<span data-ttu-id="76f40-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="76f40-107">WFRuntime</span></span>|  
|<span data-ttu-id="76f40-108">수준</span><span class="sxs-lookup"><span data-stu-id="76f40-108">Level</span></span>|<span data-ttu-id="76f40-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="76f40-109">Verbose</span></span>|  
|<span data-ttu-id="76f40-110">채널</span><span class="sxs-lookup"><span data-stu-id="76f40-110">Channel</span></span>|<span data-ttu-id="76f40-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="76f40-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="76f40-112">설명</span><span class="sxs-lookup"><span data-stu-id="76f40-112">Description</span></span>  
 <span data-ttu-id="76f40-113">BookmarkWorkItem이 실행을 시작했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="76f40-113">Indicates a BookmarkWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="76f40-114">메시지</span><span class="sxs-lookup"><span data-stu-id="76f40-114">Message</span></span>  
 <span data-ttu-id="76f40-115">작업 '%1', DisplayName에 BookmarkWorkItem의 실행 시작: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="76f40-115">Starting execution of a BookmarkWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="76f40-116">BookmarkName: %4, BookmarkScope: %5.</span><span class="sxs-lookup"><span data-stu-id="76f40-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="76f40-117">설명</span><span class="sxs-lookup"><span data-stu-id="76f40-117">Details</span></span>  
  
|<span data-ttu-id="76f40-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="76f40-118">Data Item Name</span></span>|<span data-ttu-id="76f40-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="76f40-119">Data Item Type</span></span>|<span data-ttu-id="76f40-120">설명</span><span class="sxs-lookup"><span data-stu-id="76f40-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="76f40-121">동작</span><span class="sxs-lookup"><span data-stu-id="76f40-121">Activity</span></span>|<span data-ttu-id="76f40-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="76f40-122">xs:string</span></span>|<span data-ttu-id="76f40-123">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="76f40-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="76f40-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="76f40-124">DisplayName</span></span>|<span data-ttu-id="76f40-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="76f40-125">xs:string</span></span>|<span data-ttu-id="76f40-126">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="76f40-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="76f40-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="76f40-127">InstanceId</span></span>|<span data-ttu-id="76f40-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="76f40-128">xs:string</span></span>|<span data-ttu-id="76f40-129">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="76f40-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="76f40-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="76f40-130">BookmarkName</span></span>|<span data-ttu-id="76f40-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="76f40-131">xs:string</span></span>|<span data-ttu-id="76f40-132">책갈피 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="76f40-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="76f40-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="76f40-133">BookmarkScope</span></span>|<span data-ttu-id="76f40-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="76f40-134">xs:string</span></span>|<span data-ttu-id="76f40-135">책갈피의 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="76f40-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="76f40-136">AppDomain</span><span class="sxs-lookup"><span data-stu-id="76f40-136">AppDomain</span></span>|<span data-ttu-id="76f40-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="76f40-137">xs:string</span></span>|<span data-ttu-id="76f40-138">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="76f40-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
