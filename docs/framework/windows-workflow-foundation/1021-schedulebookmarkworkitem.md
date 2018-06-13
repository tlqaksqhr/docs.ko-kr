---
title: 1021 - ScheduleBookmarkWorkItem
ms.date: 03/30/2017
ms.assetid: 2e0da311-b219-4637-9460-90cdafcc4ecd
ms.openlocfilehash: abc026165568d05faef619da28c94f27f37eea27
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509758"
---
# <a name="1021---schedulebookmarkworkitem"></a><span data-ttu-id="afb5b-102">1021 - ScheduleBookmarkWorkItem</span><span class="sxs-lookup"><span data-stu-id="afb5b-102">1021 - ScheduleBookmarkWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="afb5b-103">속성</span><span class="sxs-lookup"><span data-stu-id="afb5b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="afb5b-104">ID</span><span class="sxs-lookup"><span data-stu-id="afb5b-104">ID</span></span>|<span data-ttu-id="afb5b-105">1021</span><span class="sxs-lookup"><span data-stu-id="afb5b-105">1021</span></span>|  
|<span data-ttu-id="afb5b-106">키워드</span><span class="sxs-lookup"><span data-stu-id="afb5b-106">Keywords</span></span>|<span data-ttu-id="afb5b-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="afb5b-107">WFRuntime</span></span>|  
|<span data-ttu-id="afb5b-108">수준</span><span class="sxs-lookup"><span data-stu-id="afb5b-108">Level</span></span>|<span data-ttu-id="afb5b-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="afb5b-109">Verbose</span></span>|  
|<span data-ttu-id="afb5b-110">채널</span><span class="sxs-lookup"><span data-stu-id="afb5b-110">Channel</span></span>|<span data-ttu-id="afb5b-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="afb5b-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="afb5b-112">설명</span><span class="sxs-lookup"><span data-stu-id="afb5b-112">Description</span></span>  
 <span data-ttu-id="afb5b-113">BookmarkWorkItem이 예약되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="afb5b-113">Indicates a BookmarkWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="afb5b-114">메시지</span><span class="sxs-lookup"><span data-stu-id="afb5b-114">Message</span></span>  
 <span data-ttu-id="afb5b-115">작업 '%1', DisplayName에 대해 BookmarkWorkItem이 예약 되었습니다: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="afb5b-115">A BookmarkWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="afb5b-116">BookmarkName: %4, BookmarkScope: %5.</span><span class="sxs-lookup"><span data-stu-id="afb5b-116">BookmarkName: %4, BookmarkScope: %5.</span></span>  
  
## <a name="details"></a><span data-ttu-id="afb5b-117">설명</span><span class="sxs-lookup"><span data-stu-id="afb5b-117">Details</span></span>  
  
|<span data-ttu-id="afb5b-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="afb5b-118">Data Item Name</span></span>|<span data-ttu-id="afb5b-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="afb5b-119">Data Item Type</span></span>|<span data-ttu-id="afb5b-120">설명</span><span class="sxs-lookup"><span data-stu-id="afb5b-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="afb5b-121">동작</span><span class="sxs-lookup"><span data-stu-id="afb5b-121">Activity</span></span>|<span data-ttu-id="afb5b-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="afb5b-122">xs:string</span></span>|<span data-ttu-id="afb5b-123">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="afb5b-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="afb5b-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="afb5b-124">DisplayName</span></span>|<span data-ttu-id="afb5b-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="afb5b-125">xs:string</span></span>|<span data-ttu-id="afb5b-126">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="afb5b-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="afb5b-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="afb5b-127">InstanceId</span></span>|<span data-ttu-id="afb5b-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="afb5b-128">xs:string</span></span>|<span data-ttu-id="afb5b-129">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="afb5b-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="afb5b-130">BookmarkName</span><span class="sxs-lookup"><span data-stu-id="afb5b-130">BookmarkName</span></span>|<span data-ttu-id="afb5b-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="afb5b-131">xs:string</span></span>|<span data-ttu-id="afb5b-132">책갈피 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="afb5b-132">The name of the bookmark.</span></span>|  
|<span data-ttu-id="afb5b-133">BookmarkScope</span><span class="sxs-lookup"><span data-stu-id="afb5b-133">BookmarkScope</span></span>|<span data-ttu-id="afb5b-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="afb5b-134">xs:string</span></span>|<span data-ttu-id="afb5b-135">책갈피의 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="afb5b-135">The scope of the bookmark.</span></span>|  
|<span data-ttu-id="afb5b-136">AppDomain</span><span class="sxs-lookup"><span data-stu-id="afb5b-136">AppDomain</span></span>|<span data-ttu-id="afb5b-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="afb5b-137">xs:string</span></span>|<span data-ttu-id="afb5b-138">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="afb5b-138">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
