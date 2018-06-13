---
title: 1031 - CompleteFaultWorkItem
ms.date: 03/30/2017
ms.assetid: 95f4ccb0-6be4-41f3-9330-fae43165828f
ms.openlocfilehash: cdcbe516fc8ba7440b3d109a5e5cadc105ecee9f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509745"
---
# <a name="1031---completefaultworkitem"></a><span data-ttu-id="b41a5-102">1031 - CompleteFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="b41a5-102">1031 - CompleteFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="b41a5-103">속성</span><span class="sxs-lookup"><span data-stu-id="b41a5-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b41a5-104">ID</span><span class="sxs-lookup"><span data-stu-id="b41a5-104">ID</span></span>|<span data-ttu-id="b41a5-105">1031</span><span class="sxs-lookup"><span data-stu-id="b41a5-105">1031</span></span>|  
|<span data-ttu-id="b41a5-106">키워드</span><span class="sxs-lookup"><span data-stu-id="b41a5-106">Keywords</span></span>|<span data-ttu-id="b41a5-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="b41a5-107">WFRuntime</span></span>|  
|<span data-ttu-id="b41a5-108">수준</span><span class="sxs-lookup"><span data-stu-id="b41a5-108">Level</span></span>|<span data-ttu-id="b41a5-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="b41a5-109">Verbose</span></span>|  
|<span data-ttu-id="b41a5-110">채널</span><span class="sxs-lookup"><span data-stu-id="b41a5-110">Channel</span></span>|<span data-ttu-id="b41a5-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="b41a5-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b41a5-112">설명</span><span class="sxs-lookup"><span data-stu-id="b41a5-112">Description</span></span>  
 <span data-ttu-id="b41a5-113">FaultWorkItem이 완료되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b41a5-113">Indicates a FaultWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b41a5-114">메시지</span><span class="sxs-lookup"><span data-stu-id="b41a5-114">Message</span></span>  
 <span data-ttu-id="b41a5-115">작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 FaultWorkItem이 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b41a5-115">A FaultWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span> <span data-ttu-id="b41a5-116">작업 '%4', DisplayName: '%5', InstanceId: '%6'에서 예외가 전파되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b41a5-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b41a5-117">설명</span><span class="sxs-lookup"><span data-stu-id="b41a5-117">Details</span></span>  
  
|<span data-ttu-id="b41a5-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="b41a5-118">Data Item Name</span></span>|<span data-ttu-id="b41a5-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="b41a5-119">Data Item Type</span></span>|<span data-ttu-id="b41a5-120">설명</span><span class="sxs-lookup"><span data-stu-id="b41a5-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b41a5-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="b41a5-121">FaultActivity</span></span>|<span data-ttu-id="b41a5-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="b41a5-122">xs:string</span></span>|<span data-ttu-id="b41a5-123">오류 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b41a5-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="b41a5-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="b41a5-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="b41a5-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="b41a5-125">xs:string</span></span>|<span data-ttu-id="b41a5-126">오류 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b41a5-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="b41a5-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="b41a5-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="b41a5-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="b41a5-128">xs:string</span></span>|<span data-ttu-id="b41a5-129">오류 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b41a5-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="b41a5-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="b41a5-130">ExceptionActivity</span></span>|<span data-ttu-id="b41a5-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="b41a5-131">xs:string</span></span>|<span data-ttu-id="b41a5-132">예외를 throw한 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b41a5-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="b41a5-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="b41a5-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="b41a5-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="b41a5-134">xs:string</span></span>|<span data-ttu-id="b41a5-135">예외를 throw한 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b41a5-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="b41a5-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="b41a5-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="b41a5-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="b41a5-137">xs:string</span></span>|<span data-ttu-id="b41a5-138">예외를 throw한 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b41a5-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="b41a5-139">예외</span><span class="sxs-lookup"><span data-stu-id="b41a5-139">Exception</span></span>|<span data-ttu-id="b41a5-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="b41a5-140">xs:string</span></span>|<span data-ttu-id="b41a5-141">예외에 대한 예외 정보</span><span class="sxs-lookup"><span data-stu-id="b41a5-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="b41a5-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b41a5-142">AppDomain</span></span>|<span data-ttu-id="b41a5-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="b41a5-143">xs:string</span></span>|<span data-ttu-id="b41a5-144">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="b41a5-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
