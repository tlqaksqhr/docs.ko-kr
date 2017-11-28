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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1ba1ae69caff2e08da58e824d35341d3781ea8ef
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="1029---schedulefaultworkitem"></a><span data-ttu-id="035e3-102">1029 - ScheduleFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="035e3-102">1029 - ScheduleFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="035e3-103">속성</span><span class="sxs-lookup"><span data-stu-id="035e3-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="035e3-104">ID</span><span class="sxs-lookup"><span data-stu-id="035e3-104">ID</span></span>|<span data-ttu-id="035e3-105">1029</span><span class="sxs-lookup"><span data-stu-id="035e3-105">1029</span></span>|  
|<span data-ttu-id="035e3-106">키워드</span><span class="sxs-lookup"><span data-stu-id="035e3-106">Keywords</span></span>|<span data-ttu-id="035e3-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="035e3-107">WFRuntime</span></span>|  
|<span data-ttu-id="035e3-108">수준</span><span class="sxs-lookup"><span data-stu-id="035e3-108">Level</span></span>|<span data-ttu-id="035e3-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="035e3-109">Verbose</span></span>|  
|<span data-ttu-id="035e3-110">채널</span><span class="sxs-lookup"><span data-stu-id="035e3-110">Channel</span></span>|<span data-ttu-id="035e3-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="035e3-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="035e3-112">설명</span><span class="sxs-lookup"><span data-stu-id="035e3-112">Description</span></span>  
 <span data-ttu-id="035e3-113">FaultWorkItem이 예약되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="035e3-113">Indicates a FaultWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="035e3-114">메시지</span><span class="sxs-lookup"><span data-stu-id="035e3-114">Message</span></span>  
 <span data-ttu-id="035e3-115">작업 '%1', DisplayName에 대해 FaultWorkItem이 예약 되었습니다: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="035e3-115">A FaultWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="035e3-116">작업 '%4', DisplayName: '%5', InstanceId: '%6'에서 예외가 전파되었습니다.</span><span class="sxs-lookup"><span data-stu-id="035e3-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="035e3-117">설명</span><span class="sxs-lookup"><span data-stu-id="035e3-117">Details</span></span>  
  
|<span data-ttu-id="035e3-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="035e3-118">Data Item Name</span></span>|<span data-ttu-id="035e3-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="035e3-119">Data Item Type</span></span>|<span data-ttu-id="035e3-120">설명</span><span class="sxs-lookup"><span data-stu-id="035e3-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="035e3-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="035e3-121">FaultActivity</span></span>|<span data-ttu-id="035e3-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="035e3-122">xs:string</span></span>|<span data-ttu-id="035e3-123">오류 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="035e3-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="035e3-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="035e3-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="035e3-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="035e3-125">xs:string</span></span>|<span data-ttu-id="035e3-126">오류 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="035e3-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="035e3-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="035e3-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="035e3-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="035e3-128">xs:string</span></span>|<span data-ttu-id="035e3-129">오류 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="035e3-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="035e3-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="035e3-130">ExceptionActivity</span></span>|<span data-ttu-id="035e3-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="035e3-131">xs:string</span></span>|<span data-ttu-id="035e3-132">예외를 throw한 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="035e3-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="035e3-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="035e3-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="035e3-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="035e3-134">xs:string</span></span>|<span data-ttu-id="035e3-135">예외를 throw한 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="035e3-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="035e3-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="035e3-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="035e3-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="035e3-137">xs:string</span></span>|<span data-ttu-id="035e3-138">예외를 throw한 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="035e3-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="035e3-139">예외</span><span class="sxs-lookup"><span data-stu-id="035e3-139">Exception</span></span>|<span data-ttu-id="035e3-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="035e3-140">xs:string</span></span>|<span data-ttu-id="035e3-141">예외에 대한 예외 정보</span><span class="sxs-lookup"><span data-stu-id="035e3-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="035e3-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="035e3-142">AppDomain</span></span>|<span data-ttu-id="035e3-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="035e3-143">xs:string</span></span>|<span data-ttu-id="035e3-144">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="035e3-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
