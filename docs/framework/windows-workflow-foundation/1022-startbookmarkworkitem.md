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
ms.openlocfilehash: d7df39bd0f6d6d4d309cf5c599ecd3795eb92067
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="1022---startbookmarkworkitem"></a><span data-ttu-id="23a89-102">1022 - StartBookmarkWorkItem</span><span class="sxs-lookup"><span data-stu-id="23a89-102">1022 - StartBookmarkWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="23a89-103">속성</span><span class="sxs-lookup"><span data-stu-id="23a89-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="23a89-104">ID</span><span class="sxs-lookup"><span data-stu-id="23a89-104">ID</span></span>|<span data-ttu-id="23a89-105">1022</span><span class="sxs-lookup"><span data-stu-id="23a89-105">1022</span></span>|  
|<span data-ttu-id="23a89-106">키워드</span><span class="sxs-lookup"><span data-stu-id="23a89-106">Keywords</span></span>|<span data-ttu-id="23a89-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="23a89-107">WFRuntime</span></span>|  
|<span data-ttu-id="23a89-108">수준</span><span class="sxs-lookup"><span data-stu-id="23a89-108">Level</span></span>|<span data-ttu-id="23a89-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="23a89-109">Verbose</span></span>|  
|<span data-ttu-id="23a89-110">채널</span><span class="sxs-lookup"><span data-stu-id="23a89-110">Channel</span></span>|<span data-ttu-id="23a89-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="23a89-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="23a89-112">설명</span><span class="sxs-lookup"><span data-stu-id="23a89-112">Description</span></span>  
 <span data-ttu-id="23a89-113">BookmarkWorkItem이 실행을 시작했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="23a89-113">Indicates a BookmarkWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="23a89-114">메시지</span><span class="sxs-lookup"><span data-stu-id="23a89-114">Message</span></span>  
 <span data-ttu-id="23a89-115">작업 '%1', DisplayName에 BookmarkWorkItem의 실행 시작: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="23a89-115">Starting execution of a BookmarkWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="23a89-116">BookmarkName: %4, BookmarkScope: %5.</span><span class="sxs-lookup"><span data-stu-id="23a89-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="23a89-117">설명</span><span class="sxs-lookup"><span data-stu-id="23a89-117">Details</span></span>  
  
|<span data-ttu-id="23a89-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="23a89-118">Data Item Name</span></span>|<span data-ttu-id="23a89-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="23a89-119">Data Item Type</span></span>|<span data-ttu-id="23a89-120">설명</span><span class="sxs-lookup"><span data-stu-id="23a89-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="23a89-121">동작</span><span class="sxs-lookup"><span data-stu-id="23a89-121">Activity</span></span>|<span data-ttu-id="23a89-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="23a89-122">xs:string</span></span>|<span data-ttu-id="23a89-123">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="23a89-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="23a89-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="23a89-124">DisplayName</span></span>|<span data-ttu-id="23a89-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="23a89-125">xs:string</span></span>|<span data-ttu-id="23a89-126">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="23a89-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="23a89-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="23a89-127">InstanceId</span></span>|<span data-ttu-id="23a89-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="23a89-128">xs:string</span></span>|<span data-ttu-id="23a89-129">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="23a89-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="23a89-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="23a89-130">BookmarkName</span></span>|<span data-ttu-id="23a89-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="23a89-131">xs:string</span></span>|<span data-ttu-id="23a89-132">책갈피 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="23a89-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="23a89-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="23a89-133">BookmarkScope</span></span>|<span data-ttu-id="23a89-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="23a89-134">xs:string</span></span>|<span data-ttu-id="23a89-135">책갈피의 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="23a89-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="23a89-136">AppDomain</span><span class="sxs-lookup"><span data-stu-id="23a89-136">AppDomain</span></span>|<span data-ttu-id="23a89-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="23a89-137">xs:string</span></span>|<span data-ttu-id="23a89-138">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="23a89-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
