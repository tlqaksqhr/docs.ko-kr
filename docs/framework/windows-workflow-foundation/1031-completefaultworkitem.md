---
title: 1031 - CompleteFaultWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 95f4ccb0-6be4-41f3-9330-fae43165828f
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5173e61b2479d02dc35c5fcf9ae55634cc8dc7ba
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="1031---completefaultworkitem"></a><span data-ttu-id="fbec2-102">1031 - CompleteFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="fbec2-102">1031 - CompleteFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="fbec2-103">속성</span><span class="sxs-lookup"><span data-stu-id="fbec2-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fbec2-104">ID</span><span class="sxs-lookup"><span data-stu-id="fbec2-104">ID</span></span>|<span data-ttu-id="fbec2-105">1031</span><span class="sxs-lookup"><span data-stu-id="fbec2-105">1031</span></span>|  
|<span data-ttu-id="fbec2-106">키워드</span><span class="sxs-lookup"><span data-stu-id="fbec2-106">Keywords</span></span>|<span data-ttu-id="fbec2-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="fbec2-107">WFRuntime</span></span>|  
|<span data-ttu-id="fbec2-108">수준</span><span class="sxs-lookup"><span data-stu-id="fbec2-108">Level</span></span>|<span data-ttu-id="fbec2-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="fbec2-109">Verbose</span></span>|  
|<span data-ttu-id="fbec2-110">채널</span><span class="sxs-lookup"><span data-stu-id="fbec2-110">Channel</span></span>|<span data-ttu-id="fbec2-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="fbec2-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="fbec2-112">설명</span><span class="sxs-lookup"><span data-stu-id="fbec2-112">Description</span></span>  
 <span data-ttu-id="fbec2-113">FaultWorkItem이 완료되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fbec2-113">Indicates a FaultWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="fbec2-114">메시지</span><span class="sxs-lookup"><span data-stu-id="fbec2-114">Message</span></span>  
 <span data-ttu-id="fbec2-115">작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 FaultWorkItem이 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fbec2-115">A FaultWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="fbec2-116">작업 '%4', DisplayName: '%5', InstanceId: '%6'에서 예외가 전파되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fbec2-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="fbec2-117">설명</span><span class="sxs-lookup"><span data-stu-id="fbec2-117">Details</span></span>  
  
|<span data-ttu-id="fbec2-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="fbec2-118">Data Item Name</span></span>|<span data-ttu-id="fbec2-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="fbec2-119">Data Item Type</span></span>|<span data-ttu-id="fbec2-120">설명</span><span class="sxs-lookup"><span data-stu-id="fbec2-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="fbec2-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="fbec2-121">FaultActivity</span></span>|<span data-ttu-id="fbec2-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="fbec2-122">xs:string</span></span>|<span data-ttu-id="fbec2-123">오류 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="fbec2-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="fbec2-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="fbec2-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="fbec2-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="fbec2-125">xs:string</span></span>|<span data-ttu-id="fbec2-126">오류 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="fbec2-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="fbec2-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="fbec2-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="fbec2-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="fbec2-128">xs:string</span></span>|<span data-ttu-id="fbec2-129">오류 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="fbec2-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="fbec2-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="fbec2-130">ExceptionActivity</span></span>|<span data-ttu-id="fbec2-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="fbec2-131">xs:string</span></span>|<span data-ttu-id="fbec2-132">예외를 throw한 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="fbec2-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="fbec2-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="fbec2-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="fbec2-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="fbec2-134">xs:string</span></span>|<span data-ttu-id="fbec2-135">예외를 throw한 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="fbec2-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="fbec2-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="fbec2-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="fbec2-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="fbec2-137">xs:string</span></span>|<span data-ttu-id="fbec2-138">예외를 throw한 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="fbec2-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="fbec2-139">예외</span><span class="sxs-lookup"><span data-stu-id="fbec2-139">Exception</span></span>|<span data-ttu-id="fbec2-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="fbec2-140">xs:string</span></span>|<span data-ttu-id="fbec2-141">예외에 대한 예외 정보</span><span class="sxs-lookup"><span data-stu-id="fbec2-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="fbec2-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="fbec2-142">AppDomain</span></span>|<span data-ttu-id="fbec2-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="fbec2-143">xs:string</span></span>|<span data-ttu-id="fbec2-144">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="fbec2-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
