---
title: 1015 - StartCompletionWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 96fd1d4e-c5d0-46ad-8a71-4b4b49ac7262
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bc317157ed7658a52aa60c9b74942f9e84d47257
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="1015---startcompletionworkitem"></a><span data-ttu-id="78c52-102">1015 - StartCompletionWorkItem</span><span class="sxs-lookup"><span data-stu-id="78c52-102">1015 - StartCompletionWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="78c52-103">속성</span><span class="sxs-lookup"><span data-stu-id="78c52-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="78c52-104">ID</span><span class="sxs-lookup"><span data-stu-id="78c52-104">ID</span></span>|<span data-ttu-id="78c52-105">1015</span><span class="sxs-lookup"><span data-stu-id="78c52-105">1015</span></span>|  
|<span data-ttu-id="78c52-106">키워드</span><span class="sxs-lookup"><span data-stu-id="78c52-106">Keywords</span></span>|<span data-ttu-id="78c52-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="78c52-107">WFRuntime</span></span>|  
|<span data-ttu-id="78c52-108">수준</span><span class="sxs-lookup"><span data-stu-id="78c52-108">Level</span></span>|<span data-ttu-id="78c52-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="78c52-109">Verbose</span></span>|  
|<span data-ttu-id="78c52-110">채널</span><span class="sxs-lookup"><span data-stu-id="78c52-110">Channel</span></span>|<span data-ttu-id="78c52-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="78c52-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="78c52-112">설명</span><span class="sxs-lookup"><span data-stu-id="78c52-112">Description</span></span>  
 <span data-ttu-id="78c52-113">CompletionWorkItem이 실행을 시작했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="78c52-113">Indicates a CompletionWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="78c52-114">메시지</span><span class="sxs-lookup"><span data-stu-id="78c52-114">Message</span></span>  
 <span data-ttu-id="78c52-115">부모 작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 CompletionWorkItem의 실행을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="78c52-115">Starting execution of a CompletionWorkItem for parent Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="78c52-116">작업 '%4', DisplayName: '%5', InstanceId: '%6'이(가) 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="78c52-116">Completed Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="78c52-117">설명</span><span class="sxs-lookup"><span data-stu-id="78c52-117">Details</span></span>  
  
|<span data-ttu-id="78c52-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="78c52-118">Data Item Name</span></span>|<span data-ttu-id="78c52-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="78c52-119">Data Item Type</span></span>|<span data-ttu-id="78c52-120">설명</span><span class="sxs-lookup"><span data-stu-id="78c52-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="78c52-121">ParentActivity</span><span class="sxs-lookup"><span data-stu-id="78c52-121">ParentActivity</span></span>|<span data-ttu-id="78c52-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="78c52-122">xs:string</span></span>|<span data-ttu-id="78c52-123">부모 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="78c52-123">The type name of the parent activity.</span></span>|  
|<span data-ttu-id="78c52-124">ParentDisplayName</span><span class="sxs-lookup"><span data-stu-id="78c52-124">ParentDisplayName</span></span>|<span data-ttu-id="78c52-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="78c52-125">xs:string</span></span>|<span data-ttu-id="78c52-126">부모 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="78c52-126">The display name of the parent activity.</span></span>|  
|<span data-ttu-id="78c52-127">ParentInstanceId</span><span class="sxs-lookup"><span data-stu-id="78c52-127">ParentInstanceId</span></span>|<span data-ttu-id="78c52-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="78c52-128">xs:string</span></span>|<span data-ttu-id="78c52-129">부모 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="78c52-129">The instance id of the parent activity.</span></span>|  
|<span data-ttu-id="78c52-130">CompletedActivity</span><span class="sxs-lookup"><span data-stu-id="78c52-130">CompletedActivity</span></span>|<span data-ttu-id="78c52-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="78c52-131">xs:string</span></span>|<span data-ttu-id="78c52-132">완료된 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="78c52-132">The type name of the completed activity.</span></span>|  
|<span data-ttu-id="78c52-133">CompletedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="78c52-133">CompletedActivityDisplayName</span></span>|<span data-ttu-id="78c52-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="78c52-134">xs:string</span></span>|<span data-ttu-id="78c52-135">완료된 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="78c52-135">The display name of the completed activity.</span></span>|  
|<span data-ttu-id="78c52-136">CompletedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="78c52-136">CompletedActivityInstanceId</span></span>|<span data-ttu-id="78c52-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="78c52-137">xs:string</span></span>|<span data-ttu-id="78c52-138">완료된 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="78c52-138">The instance id of the completed activity.</span></span>|  
|<span data-ttu-id="78c52-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="78c52-139">AppDomain</span></span>|<span data-ttu-id="78c52-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="78c52-140">xs:string</span></span>|<span data-ttu-id="78c52-141">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="78c52-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
