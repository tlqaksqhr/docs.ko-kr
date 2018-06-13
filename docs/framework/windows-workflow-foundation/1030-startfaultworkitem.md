---
title: 1030 - StartFaultWorkItem
ms.date: 03/30/2017
ms.assetid: e1601fb9-0bc6-4dbe-816f-f24914063d34
ms.openlocfilehash: 3848d644e77041a62a52eb2eae5eeef286dfe334
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509682"
---
# <a name="1030---startfaultworkitem"></a><span data-ttu-id="f97c0-102">1030 - StartFaultWorkItem</span><span class="sxs-lookup"><span data-stu-id="f97c0-102">1030 - StartFaultWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="f97c0-103">속성</span><span class="sxs-lookup"><span data-stu-id="f97c0-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f97c0-104">ID</span><span class="sxs-lookup"><span data-stu-id="f97c0-104">ID</span></span>|<span data-ttu-id="f97c0-105">1030</span><span class="sxs-lookup"><span data-stu-id="f97c0-105">1030</span></span>|  
|<span data-ttu-id="f97c0-106">키워드</span><span class="sxs-lookup"><span data-stu-id="f97c0-106">Keywords</span></span>|<span data-ttu-id="f97c0-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="f97c0-107">WFRuntime</span></span>|  
|<span data-ttu-id="f97c0-108">수준</span><span class="sxs-lookup"><span data-stu-id="f97c0-108">Level</span></span>|<span data-ttu-id="f97c0-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="f97c0-109">Verbose</span></span>|  
|<span data-ttu-id="f97c0-110">채널</span><span class="sxs-lookup"><span data-stu-id="f97c0-110">Channel</span></span>|<span data-ttu-id="f97c0-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="f97c0-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f97c0-112">설명</span><span class="sxs-lookup"><span data-stu-id="f97c0-112">Description</span></span>  
 <span data-ttu-id="f97c0-113">FaultWorkItem이 실행을 시작했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f97c0-113">Indicates a FaultWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f97c0-114">메시지</span><span class="sxs-lookup"><span data-stu-id="f97c0-114">Message</span></span>  
 <span data-ttu-id="f97c0-115">작업 '%1', DisplayName에 FaultWorkItem의 실행 시작: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="f97c0-115">Starting execution of a FaultWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="f97c0-116">작업 '%4', DisplayName: '%5', InstanceId: '%6'에서 예외가 전파되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f97c0-116">The exception was propagated from Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f97c0-117">설명</span><span class="sxs-lookup"><span data-stu-id="f97c0-117">Details</span></span>  
  
|<span data-ttu-id="f97c0-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="f97c0-118">Data Item Name</span></span>|<span data-ttu-id="f97c0-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="f97c0-119">Data Item Type</span></span>|<span data-ttu-id="f97c0-120">설명</span><span class="sxs-lookup"><span data-stu-id="f97c0-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f97c0-121">FaultActivity</span><span class="sxs-lookup"><span data-stu-id="f97c0-121">FaultActivity</span></span>|<span data-ttu-id="f97c0-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="f97c0-122">xs:string</span></span>|<span data-ttu-id="f97c0-123">오류 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f97c0-123">The type name of the fault activity.</span></span>|  
|<span data-ttu-id="f97c0-124">FaultActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="f97c0-124">FaultActivityDisplayName</span></span>|<span data-ttu-id="f97c0-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="f97c0-125">xs:string</span></span>|<span data-ttu-id="f97c0-126">오류 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f97c0-126">The display name of the fault activity.</span></span>|  
|<span data-ttu-id="f97c0-127">FaultActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="f97c0-127">FaultActivityInstanceId</span></span>|<span data-ttu-id="f97c0-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="f97c0-128">xs:string</span></span>|<span data-ttu-id="f97c0-129">오류 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="f97c0-129">The instance id of the fault activity.</span></span>|  
|<span data-ttu-id="f97c0-130">ExceptionActivity</span><span class="sxs-lookup"><span data-stu-id="f97c0-130">ExceptionActivity</span></span>|<span data-ttu-id="f97c0-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="f97c0-131">xs:string</span></span>|<span data-ttu-id="f97c0-132">예외를 throw한 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f97c0-132">The type name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="f97c0-133">ExceptionActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="f97c0-133">ExceptionActivityDisplayName</span></span>|<span data-ttu-id="f97c0-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="f97c0-134">xs:string</span></span>|<span data-ttu-id="f97c0-135">예외를 throw한 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f97c0-135">The display name of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="f97c0-136">ExceptionActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="f97c0-136">ExceptionActivityInstanceId</span></span>|<span data-ttu-id="f97c0-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="f97c0-137">xs:string</span></span>|<span data-ttu-id="f97c0-138">예외를 throw한 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="f97c0-138">The instance id of the activity that threw the exception.</span></span>|  
|<span data-ttu-id="f97c0-139">예외</span><span class="sxs-lookup"><span data-stu-id="f97c0-139">Exception</span></span>|<span data-ttu-id="f97c0-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="f97c0-140">xs:string</span></span>|<span data-ttu-id="f97c0-141">예외에 대한 예외 정보</span><span class="sxs-lookup"><span data-stu-id="f97c0-141">The exception details for the exception</span></span>|  
|<span data-ttu-id="f97c0-142">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f97c0-142">AppDomain</span></span>|<span data-ttu-id="f97c0-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="f97c0-143">xs:string</span></span>|<span data-ttu-id="f97c0-144">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="f97c0-144">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
