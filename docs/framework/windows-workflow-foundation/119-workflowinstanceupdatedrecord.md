---
title: 119 - WorkflowInstanceUpdatedRecord
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 32485d0a-dcdb-45bc-b1e3-79fa9ad9439b
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2b838f764b1f86b0477dc797620dca5f99bb13d8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="119---workflowinstanceupdatedrecord"></a><span data-ttu-id="4ab70-102">119 - WorkflowInstanceUpdatedRecord</span><span class="sxs-lookup"><span data-stu-id="4ab70-102">119 - WorkflowInstanceUpdatedRecord</span></span>
## <a name="properties"></a><span data-ttu-id="4ab70-103">속성</span><span class="sxs-lookup"><span data-stu-id="4ab70-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4ab70-104">ID</span><span class="sxs-lookup"><span data-stu-id="4ab70-104">ID</span></span>|<span data-ttu-id="4ab70-105">119</span><span class="sxs-lookup"><span data-stu-id="4ab70-105">119</span></span>|  
|<span data-ttu-id="4ab70-106">키워드</span><span class="sxs-lookup"><span data-stu-id="4ab70-106">Keywords</span></span>|<span data-ttu-id="4ab70-107">HealthMonitoring, WFTracking</span><span class="sxs-lookup"><span data-stu-id="4ab70-107">HealthMonitoring, WFTracking</span></span>|  
|<span data-ttu-id="4ab70-108">수준</span><span class="sxs-lookup"><span data-stu-id="4ab70-108">Level</span></span>|<span data-ttu-id="4ab70-109">정보</span><span class="sxs-lookup"><span data-stu-id="4ab70-109">Information</span></span>|  
|<span data-ttu-id="4ab70-110">채널</span><span class="sxs-lookup"><span data-stu-id="4ab70-110">Channel</span></span>|<span data-ttu-id="4ab70-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/분석</span><span class="sxs-lookup"><span data-stu-id="4ab70-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="4ab70-112">설명</span><span class="sxs-lookup"><span data-stu-id="4ab70-112">Description</span></span>  
 <span data-ttu-id="4ab70-113">워크플로 인스턴스가 업데이트되면 ETW 추적 참가자가 이 이벤트를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="4ab70-113">This event is emitted by the ETW tracking participant when a workflow instance is updated.</span></span>  
  
## <a name="message"></a><span data-ttu-id="4ab70-114">메시지</span><span class="sxs-lookup"><span data-stu-id="4ab70-114">Message</span></span>  
 <span data-ttu-id="4ab70-115">TrackRecord= WorkflowInstanceUpdatedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, State = %5, OriginalDefinitionIdentity = %6, UpdatedDefinitionIdentity = %7, Annotations = %8, ProfileName = %9</span><span class="sxs-lookup"><span data-stu-id="4ab70-115">TrackRecord= WorkflowInstanceUpdatedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, State = %5, OriginalDefinitionIdentity = %6, UpdatedDefinitionIdentity = %7, Annotations = %8, ProfileName = %9</span></span>  
  
## <a name="details"></a><span data-ttu-id="4ab70-116">설명</span><span class="sxs-lookup"><span data-stu-id="4ab70-116">Details</span></span>  
  
|<span data-ttu-id="4ab70-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="4ab70-117">Data Item Name</span></span>|<span data-ttu-id="4ab70-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="4ab70-118">Data Item Type</span></span>|<span data-ttu-id="4ab70-119">설명</span><span class="sxs-lookup"><span data-stu-id="4ab70-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="4ab70-120">InstanceId</span><span class="sxs-lookup"><span data-stu-id="4ab70-120">InstanceId</span></span>|<span data-ttu-id="4ab70-121">xs:GUID</span><span class="sxs-lookup"><span data-stu-id="4ab70-121">xs:GUID</span></span>|<span data-ttu-id="4ab70-122">워크플로의 인스턴스 ID</span><span class="sxs-lookup"><span data-stu-id="4ab70-122">The instance id for the workflow</span></span>|  
|<span data-ttu-id="4ab70-123">RecordNumber</span><span class="sxs-lookup"><span data-stu-id="4ab70-123">RecordNumber</span></span>|<span data-ttu-id="4ab70-124">xs:long</span><span class="sxs-lookup"><span data-stu-id="4ab70-124">xs:long</span></span>|<span data-ttu-id="4ab70-125">내보낸 레코드의 시퀀스 번호</span><span class="sxs-lookup"><span data-stu-id="4ab70-125">The sequence number of the emitted record</span></span>|  
|<span data-ttu-id="4ab70-126">EventTime</span><span class="sxs-lookup"><span data-stu-id="4ab70-126">EventTime</span></span>|<span data-ttu-id="4ab70-127">xs:dateTime</span><span class="sxs-lookup"><span data-stu-id="4ab70-127">xs:dateTime</span></span>|<span data-ttu-id="4ab70-128">이벤트를 내보낸 시간(UTC)</span><span class="sxs-lookup"><span data-stu-id="4ab70-128">The time in UTC when the event was emitted</span></span>|  
|<span data-ttu-id="4ab70-129">ActivityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="4ab70-129">ActivityDefinitionId</span></span>|<span data-ttu-id="4ab70-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="4ab70-130">xs:string</span></span>|<span data-ttu-id="4ab70-131">워크플로의 루트 활동 이름</span><span class="sxs-lookup"><span data-stu-id="4ab70-131">The name of the root activity in the workflow</span></span>|  
|<span data-ttu-id="4ab70-132">상태</span><span class="sxs-lookup"><span data-stu-id="4ab70-132">State</span></span>|<span data-ttu-id="4ab70-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="4ab70-133">xs:string</span></span>|<span data-ttu-id="4ab70-134">워크플로의 현재 상태</span><span class="sxs-lookup"><span data-stu-id="4ab70-134">The current state of the Workflow.</span></span>|  
|<span data-ttu-id="4ab70-135">OriginalDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="4ab70-135">OriginalDefinitionIdentity</span></span>|<span data-ttu-id="4ab70-136">xs:string</span><span class="sxs-lookup"><span data-stu-id="4ab70-136">xs:string</span></span>|<span data-ttu-id="4ab70-137">원래 워크플로 정의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="4ab70-137">The original workflow definition id</span></span>|  
|<span data-ttu-id="4ab70-138">UpdatedDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="4ab70-138">UpdatedDefinitionIdentity</span></span>|<span data-ttu-id="4ab70-139">xs:string</span><span class="sxs-lookup"><span data-stu-id="4ab70-139">xs:string</span></span>|<span data-ttu-id="4ab70-140">업로드된 워크플로 정의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="4ab70-140">The updated workflow definition id</span></span>|  
|<span data-ttu-id="4ab70-141">주석</span><span class="sxs-lookup"><span data-stu-id="4ab70-141">Annotations</span></span>|<span data-ttu-id="4ab70-142">xs:string</span><span class="sxs-lookup"><span data-stu-id="4ab70-142">xs:string</span></span>|<span data-ttu-id="4ab70-143">이 이벤트에 추가된 주석입니다.</span><span class="sxs-lookup"><span data-stu-id="4ab70-143">The annotations that were added to this event.</span></span> <span data-ttu-id="4ab70-144">값 형식으로 xml 요소에 저장 됩니다 \<항목 >\< 항목 이름 = "annotationName" type = "> annotationValue\<항목/>\<항목/>입니다.</span><span class="sxs-lookup"><span data-stu-id="4ab70-144">The values are stored in an xml element in the format \<items>\< item name = "annotationName" type="System.String">annotationValue\</item>\</items>.</span></span> <span data-ttu-id="4ab70-145">주석을 지정 하지 않으면 문자열을 포함 하는 경우 \<항목 / >입니다.</span><span class="sxs-lookup"><span data-stu-id="4ab70-145">If no annotations are specified then the string contains \<items/>.</span></span> <span data-ttu-id="4ab70-146">ETW 이벤트 크기는 ETW 버퍼 크기 또는 ETW 이벤트의 최대 페이로드에 따라 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ab70-146">The ETW event size is limited by the ETW buffer size or the max payload for an ETW event.</span></span> <span data-ttu-id="4ab70-147">이벤트 크기가 ETW 제한을 초과 하면 주석을 삭제 하 고 주석 값으로 바꿔 이벤트 잘립니다 경우 \<항목 >... \<항목/>입니다.</span><span class="sxs-lookup"><span data-stu-id="4ab70-147">If the size of the event exceeds the ETW limits, then the event is truncated by dropping the annotations and replacing the annotation value with \<items>...\</items>.</span></span>|  
|<span data-ttu-id="4ab70-148">ProfileName</span><span class="sxs-lookup"><span data-stu-id="4ab70-148">ProfileName</span></span>|<span data-ttu-id="4ab70-149">xs:string</span><span class="sxs-lookup"><span data-stu-id="4ab70-149">xs:string</span></span>|<span data-ttu-id="4ab70-150">이 이벤트를 내보낸 이름 또는 추적 프로필</span><span class="sxs-lookup"><span data-stu-id="4ab70-150">The name or the tracking profile that resulted in this event being emitted</span></span>|  
|<span data-ttu-id="4ab70-151">WorkflowDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="4ab70-151">WorkflowDefinitionIdentity</span></span>|<span data-ttu-id="4ab70-152">xs:string</span><span class="sxs-lookup"><span data-stu-id="4ab70-152">xs:string</span></span>|<span data-ttu-id="4ab70-153">워크플로 정의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="4ab70-153">The workflow definition id</span></span>|  
|<span data-ttu-id="4ab70-154">AppDomain</span><span class="sxs-lookup"><span data-stu-id="4ab70-154">AppDomain</span></span>|<span data-ttu-id="4ab70-155">xs:string</span><span class="sxs-lookup"><span data-stu-id="4ab70-155">xs:string</span></span>|<span data-ttu-id="4ab70-156">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="4ab70-156">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
