---
title: 1014 - ScheduleCompletionWorkItem
ms.date: 03/30/2017
ms.assetid: 84203735-478d-42d8-a320-c175dbddcb38
ms.openlocfilehash: 50b00a49ea73dcbe09e8f4c4195cbce8c1cbf615
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510369"
---
# <a name="1014---schedulecompletionworkitem"></a><span data-ttu-id="60d2c-102">1014 - ScheduleCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="60d2c-102">1014 - ScheduleCompletionWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="60d2c-103">속성</span><span class="sxs-lookup"><span data-stu-id="60d2c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="60d2c-104">ID</span><span class="sxs-lookup"><span data-stu-id="60d2c-104">ID</span></span>|<span data-ttu-id="60d2c-105">1014</span><span class="sxs-lookup"><span data-stu-id="60d2c-105">1014</span></span>|  
|<span data-ttu-id="60d2c-106">키워드</span><span class="sxs-lookup"><span data-stu-id="60d2c-106">Keywords</span></span>|<span data-ttu-id="60d2c-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="60d2c-107">WFRuntime</span></span>|  
|<span data-ttu-id="60d2c-108">수준</span><span class="sxs-lookup"><span data-stu-id="60d2c-108">Level</span></span>|<span data-ttu-id="60d2c-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="60d2c-109">Verbose</span></span>|  
|<span data-ttu-id="60d2c-110">채널</span><span class="sxs-lookup"><span data-stu-id="60d2c-110">Channel</span></span>|<span data-ttu-id="60d2c-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="60d2c-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="60d2c-112">설명</span><span class="sxs-lookup"><span data-stu-id="60d2c-112">Description</span></span>  
 <span data-ttu-id="60d2c-113">CompletionWorkItem이 예약되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="60d2c-113">Indicates a CompletionWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="60d2c-114">메시지</span><span class="sxs-lookup"><span data-stu-id="60d2c-114">Message</span></span>  
 <span data-ttu-id="60d2c-115">부모 작업 '%1', DisplayName에 대해 CompletionWorkItem이 예약 되었습니다: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="60d2c-115">A CompletionWorkItem has been scheduled for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="60d2c-116">작업 '%4', DisplayName: '%5', InstanceId: '%6'이(가) 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="60d2c-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="60d2c-117">설명</span><span class="sxs-lookup"><span data-stu-id="60d2c-117">Details</span></span>  
  
|<span data-ttu-id="60d2c-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="60d2c-118">Data Item Name</span></span>|<span data-ttu-id="60d2c-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="60d2c-119">Data Item Type</span></span>|<span data-ttu-id="60d2c-120">설명</span><span class="sxs-lookup"><span data-stu-id="60d2c-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="60d2c-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="60d2c-121">ParentActivity</span></span>|<span data-ttu-id="60d2c-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="60d2c-122">xs:string</span></span>|<span data-ttu-id="60d2c-123">부모 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="60d2c-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="60d2c-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="60d2c-124">ParentDisplayName</span></span>|<span data-ttu-id="60d2c-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="60d2c-125">xs:string</span></span>|<span data-ttu-id="60d2c-126">부모 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="60d2c-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="60d2c-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="60d2c-127">ParentInstanceId</span></span>|<span data-ttu-id="60d2c-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="60d2c-128">xs:string</span></span>|<span data-ttu-id="60d2c-129">부모 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="60d2c-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="60d2c-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="60d2c-130">CompletedActivity</span></span>|<span data-ttu-id="60d2c-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="60d2c-131">xs:string</span></span>|<span data-ttu-id="60d2c-132">완료된 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="60d2c-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="60d2c-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="60d2c-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="60d2c-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="60d2c-134">xs:string</span></span>|<span data-ttu-id="60d2c-135">완료된 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="60d2c-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="60d2c-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="60d2c-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="60d2c-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="60d2c-137">xs:string</span></span>|<span data-ttu-id="60d2c-138">완료된 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="60d2c-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="60d2c-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="60d2c-139">AppDomain</span></span>|<span data-ttu-id="60d2c-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="60d2c-140">xs:string</span></span>|<span data-ttu-id="60d2c-141">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="60d2c-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
