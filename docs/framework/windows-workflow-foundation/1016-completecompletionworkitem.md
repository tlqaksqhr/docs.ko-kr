---
title: 1016 - CompleteCompletionWorkItem
ms.date: 03/30/2017
ms.assetid: 246929fb-6f14-440a-814b-cd8349350644
ms.openlocfilehash: 3f0904a561a242cd3be528c9707a409b6f98e0fe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510298"
---
# <a name="1016---completecompletionworkitem"></a><span data-ttu-id="5e091-102">1016 - CompleteCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="5e091-102">1016 - CompleteCompletionWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="5e091-103">속성</span><span class="sxs-lookup"><span data-stu-id="5e091-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5e091-104">ID</span><span class="sxs-lookup"><span data-stu-id="5e091-104">ID</span></span>|<span data-ttu-id="5e091-105">1016</span><span class="sxs-lookup"><span data-stu-id="5e091-105">1016</span></span>|  
|<span data-ttu-id="5e091-106">키워드</span><span class="sxs-lookup"><span data-stu-id="5e091-106">Keywords</span></span>|<span data-ttu-id="5e091-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="5e091-107">WFRuntime</span></span>|  
|<span data-ttu-id="5e091-108">수준</span><span class="sxs-lookup"><span data-stu-id="5e091-108">Level</span></span>|<span data-ttu-id="5e091-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="5e091-109">Verbose</span></span>|  
|<span data-ttu-id="5e091-110">채널</span><span class="sxs-lookup"><span data-stu-id="5e091-110">Channel</span></span>|<span data-ttu-id="5e091-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="5e091-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5e091-112">설명</span><span class="sxs-lookup"><span data-stu-id="5e091-112">Description</span></span>  
 <span data-ttu-id="5e091-113">CompletionWorkItem이 완료되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5e091-113">Indicates a CompletionWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5e091-114">메시지</span><span class="sxs-lookup"><span data-stu-id="5e091-114">Message</span></span>  
 <span data-ttu-id="5e091-115">부모 작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 CompletionWorkItem이 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5e091-115">A CompletionWorkItem has completed for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="5e091-116">작업 '%4', DisplayName: '%5', InstanceId: '%6'이(가) 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5e091-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5e091-117">설명</span><span class="sxs-lookup"><span data-stu-id="5e091-117">Details</span></span>  
  
|<span data-ttu-id="5e091-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="5e091-118">Data Item Name</span></span>|<span data-ttu-id="5e091-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="5e091-119">Data Item Type</span></span>|<span data-ttu-id="5e091-120">설명</span><span class="sxs-lookup"><span data-stu-id="5e091-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5e091-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="5e091-121">ParentActivity</span></span>|<span data-ttu-id="5e091-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="5e091-122">xs:string</span></span>|<span data-ttu-id="5e091-123">부모 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5e091-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="5e091-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="5e091-124">ParentDisplayName</span></span>|<span data-ttu-id="5e091-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="5e091-125">xs:string</span></span>|<span data-ttu-id="5e091-126">부모 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5e091-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="5e091-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="5e091-127">ParentInstanceId</span></span>|<span data-ttu-id="5e091-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="5e091-128">xs:string</span></span>|<span data-ttu-id="5e091-129">부모 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="5e091-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="5e091-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="5e091-130">CompletedActivity</span></span>|<span data-ttu-id="5e091-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="5e091-131">xs:string</span></span>|<span data-ttu-id="5e091-132">완료된 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5e091-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="5e091-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="5e091-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="5e091-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="5e091-134">xs:string</span></span>|<span data-ttu-id="5e091-135">완료된 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5e091-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="5e091-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="5e091-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="5e091-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="5e091-137">xs:string</span></span>|<span data-ttu-id="5e091-138">완료된 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="5e091-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="5e091-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="5e091-139">AppDomain</span></span>|<span data-ttu-id="5e091-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="5e091-140">xs:string</span></span>|<span data-ttu-id="5e091-141">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="5e091-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
