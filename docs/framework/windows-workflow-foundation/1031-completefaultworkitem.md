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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 260647b56d945600afea5609f06d36385fa66014
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="1031---completefaultworkitem"></a><span data-ttu-id="7fb5d-102">1031 - CompleteFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="7fb5d-102">1031 - CompleteFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="7fb5d-103">속성</span><span class="sxs-lookup"><span data-stu-id="7fb5d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7fb5d-104">ID</span><span class="sxs-lookup"><span data-stu-id="7fb5d-104">ID</span></span>|<span data-ttu-id="7fb5d-105">1031</span><span class="sxs-lookup"><span data-stu-id="7fb5d-105">1031</span></span>|  
|<span data-ttu-id="7fb5d-106">키워드</span><span class="sxs-lookup"><span data-stu-id="7fb5d-106">Keywords</span></span>|<span data-ttu-id="7fb5d-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="7fb5d-107">WFRuntime</span></span>|  
|<span data-ttu-id="7fb5d-108">수준</span><span class="sxs-lookup"><span data-stu-id="7fb5d-108">Level</span></span>|<span data-ttu-id="7fb5d-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="7fb5d-109">Verbose</span></span>|  
|<span data-ttu-id="7fb5d-110">채널</span><span class="sxs-lookup"><span data-stu-id="7fb5d-110">Channel</span></span>|<span data-ttu-id="7fb5d-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="7fb5d-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="7fb5d-112">설명</span><span class="sxs-lookup"><span data-stu-id="7fb5d-112">Description</span></span>  
 <span data-ttu-id="7fb5d-113">FaultWorkItem이 완료되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7fb5d-113">Indicates a FaultWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="7fb5d-114">메시지</span><span class="sxs-lookup"><span data-stu-id="7fb5d-114">Message</span></span>  
 <span data-ttu-id="7fb5d-115">작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 FaultWorkItem이 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7fb5d-115">A FaultWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="7fb5d-116">작업 '%4', DisplayName: '%5', InstanceId: '%6'에서 예외가 전파되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7fb5d-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="7fb5d-117">설명</span><span class="sxs-lookup"><span data-stu-id="7fb5d-117">Details</span></span>  
  
|<span data-ttu-id="7fb5d-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="7fb5d-118">Data Item Name</span></span>|<span data-ttu-id="7fb5d-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="7fb5d-119">Data Item Type</span></span>|<span data-ttu-id="7fb5d-120">설명</span><span class="sxs-lookup"><span data-stu-id="7fb5d-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="7fb5d-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="7fb5d-121">FaultActivity</span></span>|<span data-ttu-id="7fb5d-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="7fb5d-122">xs:string</span></span>|<span data-ttu-id="7fb5d-123">오류 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7fb5d-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="7fb5d-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="7fb5d-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="7fb5d-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="7fb5d-125">xs:string</span></span>|<span data-ttu-id="7fb5d-126">오류 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7fb5d-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="7fb5d-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="7fb5d-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="7fb5d-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="7fb5d-128">xs:string</span></span>|<span data-ttu-id="7fb5d-129">오류 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="7fb5d-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="7fb5d-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="7fb5d-130">ExceptionActivity</span></span>|<span data-ttu-id="7fb5d-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="7fb5d-131">xs:string</span></span>|<span data-ttu-id="7fb5d-132">예외를 throw한 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7fb5d-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="7fb5d-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="7fb5d-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="7fb5d-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="7fb5d-134">xs:string</span></span>|<span data-ttu-id="7fb5d-135">예외를 throw한 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7fb5d-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="7fb5d-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="7fb5d-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="7fb5d-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="7fb5d-137">xs:string</span></span>|<span data-ttu-id="7fb5d-138">예외를 throw한 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="7fb5d-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="7fb5d-139">예외</span><span class="sxs-lookup"><span data-stu-id="7fb5d-139">Exception</span></span>|<span data-ttu-id="7fb5d-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="7fb5d-140">xs:string</span></span>|<span data-ttu-id="7fb5d-141">예외에 대한 예외 정보</span><span class="sxs-lookup"><span data-stu-id="7fb5d-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="7fb5d-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="7fb5d-142">AppDomain</span></span>|<span data-ttu-id="7fb5d-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="7fb5d-143">xs:string</span></span>|<span data-ttu-id="7fb5d-144">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="7fb5d-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
