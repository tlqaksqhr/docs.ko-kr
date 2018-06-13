---
title: 1015 - StartCompletionWorkItem
ms.date: 03/30/2017
ms.assetid: 96fd1d4e-c5d0-46ad-8a71-4b4b49ac7262
ms.openlocfilehash: 6a2d4c866ec7d43e8ae40b5616a97c3b7adf1843
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509636"
---
# <a name="1015---startcompletionworkitem"></a><span data-ttu-id="b732c-102">1015 - StartCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="b732c-102">1015 - StartCompletionWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="b732c-103">속성</span><span class="sxs-lookup"><span data-stu-id="b732c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b732c-104">ID</span><span class="sxs-lookup"><span data-stu-id="b732c-104">ID</span></span>|<span data-ttu-id="b732c-105">1015</span><span class="sxs-lookup"><span data-stu-id="b732c-105">1015</span></span>|  
|<span data-ttu-id="b732c-106">키워드</span><span class="sxs-lookup"><span data-stu-id="b732c-106">Keywords</span></span>|<span data-ttu-id="b732c-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="b732c-107">WFRuntime</span></span>|  
|<span data-ttu-id="b732c-108">수준</span><span class="sxs-lookup"><span data-stu-id="b732c-108">Level</span></span>|<span data-ttu-id="b732c-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="b732c-109">Verbose</span></span>|  
|<span data-ttu-id="b732c-110">채널</span><span class="sxs-lookup"><span data-stu-id="b732c-110">Channel</span></span>|<span data-ttu-id="b732c-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="b732c-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b732c-112">설명</span><span class="sxs-lookup"><span data-stu-id="b732c-112">Description</span></span>  
 <span data-ttu-id="b732c-113">CompletionWorkItem이 실행을 시작했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b732c-113">Indicates a CompletionWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b732c-114">메시지</span><span class="sxs-lookup"><span data-stu-id="b732c-114">Message</span></span>  
 <span data-ttu-id="b732c-115">부모 작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 CompletionWorkItem의 실행을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="b732c-115">Starting execution of a CompletionWorkItem for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="b732c-116">작업 '%4', DisplayName: '%5', InstanceId: '%6'이(가) 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b732c-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b732c-117">설명</span><span class="sxs-lookup"><span data-stu-id="b732c-117">Details</span></span>  
  
|<span data-ttu-id="b732c-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="b732c-118">Data Item Name</span></span>|<span data-ttu-id="b732c-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="b732c-119">Data Item Type</span></span>|<span data-ttu-id="b732c-120">설명</span><span class="sxs-lookup"><span data-stu-id="b732c-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b732c-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="b732c-121">ParentActivity</span></span>|<span data-ttu-id="b732c-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="b732c-122">xs:string</span></span>|<span data-ttu-id="b732c-123">부모 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b732c-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="b732c-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="b732c-124">ParentDisplayName</span></span>|<span data-ttu-id="b732c-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="b732c-125">xs:string</span></span>|<span data-ttu-id="b732c-126">부모 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b732c-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="b732c-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="b732c-127">ParentInstanceId</span></span>|<span data-ttu-id="b732c-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="b732c-128">xs:string</span></span>|<span data-ttu-id="b732c-129">부모 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b732c-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="b732c-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="b732c-130">CompletedActivity</span></span>|<span data-ttu-id="b732c-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="b732c-131">xs:string</span></span>|<span data-ttu-id="b732c-132">완료된 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b732c-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="b732c-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="b732c-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="b732c-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="b732c-134">xs:string</span></span>|<span data-ttu-id="b732c-135">완료된 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b732c-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="b732c-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="b732c-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="b732c-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="b732c-137">xs:string</span></span>|<span data-ttu-id="b732c-138">완료된 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b732c-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="b732c-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b732c-139">AppDomain</span></span>|<span data-ttu-id="b732c-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="b732c-140">xs:string</span></span>|<span data-ttu-id="b732c-141">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="b732c-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
