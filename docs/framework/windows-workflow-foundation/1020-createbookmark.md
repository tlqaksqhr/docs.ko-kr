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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d0584c6eeaf0e08e92ad94e01e1fca765616440f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="1020---createbookmark"></a><span data-ttu-id="c526c-102">1020 - CreateBookmark</span><span class="sxs-lookup"><span data-stu-id="c526c-102">1020 - CreateBookmark</span></span>
## <a name="properties"></a><span data-ttu-id="c526c-103">속성</span><span class="sxs-lookup"><span data-stu-id="c526c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c526c-104">ID</span><span class="sxs-lookup"><span data-stu-id="c526c-104">ID</span></span>|<span data-ttu-id="c526c-105">1020</span><span class="sxs-lookup"><span data-stu-id="c526c-105">1020</span></span>|  
|<span data-ttu-id="c526c-106">키워드</span><span class="sxs-lookup"><span data-stu-id="c526c-106">Keywords</span></span>|<span data-ttu-id="c526c-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="c526c-107">WFRuntime</span></span>|  
|<span data-ttu-id="c526c-108">수준</span><span class="sxs-lookup"><span data-stu-id="c526c-108">Level</span></span>|<span data-ttu-id="c526c-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="c526c-109">Verbose</span></span>|  
|<span data-ttu-id="c526c-110">채널</span><span class="sxs-lookup"><span data-stu-id="c526c-110">Channel</span></span>|<span data-ttu-id="c526c-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="c526c-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c526c-112">설명</span><span class="sxs-lookup"><span data-stu-id="c526c-112">Description</span></span>  
 <span data-ttu-id="c526c-113">작업에 대한 책갈피가 만들어졌음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c526c-113">Indicates a bookmark has been created for an activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c526c-114">메시지</span><span class="sxs-lookup"><span data-stu-id="c526c-114">Message</span></span>  
 <span data-ttu-id="c526c-115">책갈피를 만든 작업 '%1', DisplayName: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="c526c-115">A Bookmark has been created for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="c526c-116">BookmarkName: %4, BookmarkScope: %5.</span><span class="sxs-lookup"><span data-stu-id="c526c-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="c526c-117">설명</span><span class="sxs-lookup"><span data-stu-id="c526c-117">Details</span></span>  
  
|<span data-ttu-id="c526c-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="c526c-118">Data Item Name</span></span>|<span data-ttu-id="c526c-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="c526c-119">Data Item Type</span></span>|<span data-ttu-id="c526c-120">설명</span><span class="sxs-lookup"><span data-stu-id="c526c-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="c526c-121">동작</span><span class="sxs-lookup"><span data-stu-id="c526c-121">Activity</span></span>|<span data-ttu-id="c526c-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="c526c-122">xs:string</span></span>|<span data-ttu-id="c526c-123">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c526c-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="c526c-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="c526c-124">DisplayName</span></span>|<span data-ttu-id="c526c-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="c526c-125">xs:string</span></span>|<span data-ttu-id="c526c-126">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c526c-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="c526c-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="c526c-127">InstanceId</span></span>|<span data-ttu-id="c526c-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="c526c-128">xs:string</span></span>|<span data-ttu-id="c526c-129">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c526c-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="c526c-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="c526c-130">BookmarkName</span></span>|<span data-ttu-id="c526c-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="c526c-131">xs:string</span></span>|<span data-ttu-id="c526c-132">책갈피 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c526c-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="c526c-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="c526c-133">BookmarkScope</span></span>|<span data-ttu-id="c526c-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="c526c-134">xs:string</span></span>|<span data-ttu-id="c526c-135">책갈피의 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="c526c-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="c526c-136">AppDomain</span><span class="sxs-lookup"><span data-stu-id="c526c-136">AppDomain</span></span>|<span data-ttu-id="c526c-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="c526c-137">xs:string</span></span>|<span data-ttu-id="c526c-138">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="c526c-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
