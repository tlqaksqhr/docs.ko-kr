---
title: 1029 - ScheduleFaultWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3a56b29e-f740-459d-8576-d81e58bf5a03
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dfa9553c25f607ec25fd968c2e8c6db061fb49dc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="1029---schedulefaultworkitem"></a><span data-ttu-id="b07b9-102">1029 - ScheduleFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="b07b9-102">1029 - ScheduleFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="b07b9-103">속성</span><span class="sxs-lookup"><span data-stu-id="b07b9-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b07b9-104">ID</span><span class="sxs-lookup"><span data-stu-id="b07b9-104">ID</span></span>|<span data-ttu-id="b07b9-105">1029</span><span class="sxs-lookup"><span data-stu-id="b07b9-105">1029</span></span>|  
|<span data-ttu-id="b07b9-106">키워드</span><span class="sxs-lookup"><span data-stu-id="b07b9-106">Keywords</span></span>|<span data-ttu-id="b07b9-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="b07b9-107">WFRuntime</span></span>|  
|<span data-ttu-id="b07b9-108">수준</span><span class="sxs-lookup"><span data-stu-id="b07b9-108">Level</span></span>|<span data-ttu-id="b07b9-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="b07b9-109">Verbose</span></span>|  
|<span data-ttu-id="b07b9-110">채널</span><span class="sxs-lookup"><span data-stu-id="b07b9-110">Channel</span></span>|<span data-ttu-id="b07b9-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="b07b9-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b07b9-112">설명</span><span class="sxs-lookup"><span data-stu-id="b07b9-112">Description</span></span>  
 <span data-ttu-id="b07b9-113">FaultWorkItem이 예약되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b07b9-113">Indicates a FaultWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b07b9-114">메시지</span><span class="sxs-lookup"><span data-stu-id="b07b9-114">Message</span></span>  
 <span data-ttu-id="b07b9-115">작업 '%1', DisplayName에 대해 FaultWorkItem이 예약 되었습니다: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="b07b9-115">A FaultWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="b07b9-116">작업 '%4', DisplayName: '%5', InstanceId: '%6'에서 예외가 전파되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b07b9-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b07b9-117">설명</span><span class="sxs-lookup"><span data-stu-id="b07b9-117">Details</span></span>  
  
|<span data-ttu-id="b07b9-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="b07b9-118">Data Item Name</span></span>|<span data-ttu-id="b07b9-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="b07b9-119">Data Item Type</span></span>|<span data-ttu-id="b07b9-120">설명</span><span class="sxs-lookup"><span data-stu-id="b07b9-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b07b9-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="b07b9-121">FaultActivity</span></span>|<span data-ttu-id="b07b9-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="b07b9-122">xs:string</span></span>|<span data-ttu-id="b07b9-123">오류 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b07b9-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="b07b9-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="b07b9-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="b07b9-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="b07b9-125">xs:string</span></span>|<span data-ttu-id="b07b9-126">오류 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b07b9-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="b07b9-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="b07b9-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="b07b9-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="b07b9-128">xs:string</span></span>|<span data-ttu-id="b07b9-129">오류 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b07b9-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="b07b9-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="b07b9-130">ExceptionActivity</span></span>|<span data-ttu-id="b07b9-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="b07b9-131">xs:string</span></span>|<span data-ttu-id="b07b9-132">예외를 throw한 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b07b9-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="b07b9-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="b07b9-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="b07b9-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="b07b9-134">xs:string</span></span>|<span data-ttu-id="b07b9-135">예외를 throw한 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b07b9-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="b07b9-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="b07b9-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="b07b9-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="b07b9-137">xs:string</span></span>|<span data-ttu-id="b07b9-138">예외를 throw한 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b07b9-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="b07b9-139">예외</span><span class="sxs-lookup"><span data-stu-id="b07b9-139">Exception</span></span>|<span data-ttu-id="b07b9-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="b07b9-140">xs:string</span></span>|<span data-ttu-id="b07b9-141">예외에 대한 예외 정보</span><span class="sxs-lookup"><span data-stu-id="b07b9-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="b07b9-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b07b9-142">AppDomain</span></span>|<span data-ttu-id="b07b9-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="b07b9-143">xs:string</span></span>|<span data-ttu-id="b07b9-144">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="b07b9-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
