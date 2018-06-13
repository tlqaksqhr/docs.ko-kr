---
title: 1022 - StartBookmarkWorkItem
ms.date: 03/30/2017
ms.assetid: 4415fbdb-0329-4019-803f-aea66e75f3da
ms.openlocfilehash: 93d906b32b51effaa709da6763f535708cd6f821
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509810"
---
# <a name="1022---startbookmarkworkitem"></a><span data-ttu-id="ea1f2-102">1022 - StartBookmarkWorkItem</span><span class="sxs-lookup"><span data-stu-id="ea1f2-102">1022 - StartBookmarkWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="ea1f2-103">속성</span><span class="sxs-lookup"><span data-stu-id="ea1f2-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ea1f2-104">ID</span><span class="sxs-lookup"><span data-stu-id="ea1f2-104">ID</span></span>|<span data-ttu-id="ea1f2-105">1022</span><span class="sxs-lookup"><span data-stu-id="ea1f2-105">1022</span></span>|  
|<span data-ttu-id="ea1f2-106">키워드</span><span class="sxs-lookup"><span data-stu-id="ea1f2-106">Keywords</span></span>|<span data-ttu-id="ea1f2-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="ea1f2-107">WFRuntime</span></span>|  
|<span data-ttu-id="ea1f2-108">수준</span><span class="sxs-lookup"><span data-stu-id="ea1f2-108">Level</span></span>|<span data-ttu-id="ea1f2-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="ea1f2-109">Verbose</span></span>|  
|<span data-ttu-id="ea1f2-110">채널</span><span class="sxs-lookup"><span data-stu-id="ea1f2-110">Channel</span></span>|<span data-ttu-id="ea1f2-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="ea1f2-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ea1f2-112">설명</span><span class="sxs-lookup"><span data-stu-id="ea1f2-112">Description</span></span>  
 <span data-ttu-id="ea1f2-113">BookmarkWorkItem이 실행을 시작했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ea1f2-113">Indicates a BookmarkWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ea1f2-114">메시지</span><span class="sxs-lookup"><span data-stu-id="ea1f2-114">Message</span></span>  
 <span data-ttu-id="ea1f2-115">작업 '%1', DisplayName에 BookmarkWorkItem의 실행 시작: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="ea1f2-115">Starting execution of a BookmarkWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="ea1f2-116">BookmarkName: %4, BookmarkScope: %5.</span><span class="sxs-lookup"><span data-stu-id="ea1f2-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ea1f2-117">설명</span><span class="sxs-lookup"><span data-stu-id="ea1f2-117">Details</span></span>  
  
|<span data-ttu-id="ea1f2-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="ea1f2-118">Data Item Name</span></span>|<span data-ttu-id="ea1f2-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="ea1f2-119">Data Item Type</span></span>|<span data-ttu-id="ea1f2-120">설명</span><span class="sxs-lookup"><span data-stu-id="ea1f2-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ea1f2-121">동작</span><span class="sxs-lookup"><span data-stu-id="ea1f2-121">Activity</span></span>|<span data-ttu-id="ea1f2-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="ea1f2-122">xs:string</span></span>|<span data-ttu-id="ea1f2-123">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ea1f2-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="ea1f2-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="ea1f2-124">DisplayName</span></span>|<span data-ttu-id="ea1f2-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="ea1f2-125">xs:string</span></span>|<span data-ttu-id="ea1f2-126">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ea1f2-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="ea1f2-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="ea1f2-127">InstanceId</span></span>|<span data-ttu-id="ea1f2-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="ea1f2-128">xs:string</span></span>|<span data-ttu-id="ea1f2-129">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ea1f2-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="ea1f2-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="ea1f2-130">BookmarkName</span></span>|<span data-ttu-id="ea1f2-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="ea1f2-131">xs:string</span></span>|<span data-ttu-id="ea1f2-132">책갈피 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ea1f2-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="ea1f2-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="ea1f2-133">BookmarkScope</span></span>|<span data-ttu-id="ea1f2-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="ea1f2-134">xs:string</span></span>|<span data-ttu-id="ea1f2-135">책갈피의 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="ea1f2-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="ea1f2-136">AppDomain</span><span class="sxs-lookup"><span data-stu-id="ea1f2-136">AppDomain</span></span>|<span data-ttu-id="ea1f2-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="ea1f2-137">xs:string</span></span>|<span data-ttu-id="ea1f2-138">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="ea1f2-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
