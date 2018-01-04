---
title: 115 - WorkflowInstanceAbortedRecordWithId
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0293dd4e-e6ae-473a-b3d6-c2d38f9bd875
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 314f880f1fc2d78efc59f73f37122d03ae30cf72
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="115---workflowinstanceabortedrecordwithid"></a><span data-ttu-id="50f70-102">115 - WorkflowInstanceAbortedRecordWithId</span><span class="sxs-lookup"><span data-stu-id="50f70-102">115 - WorkflowInstanceAbortedRecordWithId</span></span>
## <a name="properties"></a><span data-ttu-id="50f70-103">속성</span><span class="sxs-lookup"><span data-stu-id="50f70-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="50f70-104">ID</span><span class="sxs-lookup"><span data-stu-id="50f70-104">ID</span></span>|<span data-ttu-id="50f70-105">115</span><span class="sxs-lookup"><span data-stu-id="50f70-105">115</span></span>|  
|<span data-ttu-id="50f70-106">키워드</span><span class="sxs-lookup"><span data-stu-id="50f70-106">Keywords</span></span>|<span data-ttu-id="50f70-107">HealthMonitoring, WFTracking</span><span class="sxs-lookup"><span data-stu-id="50f70-107">HealthMonitoring, WFTracking</span></span>|  
|<span data-ttu-id="50f70-108">수준</span><span class="sxs-lookup"><span data-stu-id="50f70-108">Level</span></span>|<span data-ttu-id="50f70-109">경고</span><span class="sxs-lookup"><span data-stu-id="50f70-109">Warning</span></span>|  
|<span data-ttu-id="50f70-110">채널</span><span class="sxs-lookup"><span data-stu-id="50f70-110">Channel</span></span>|<span data-ttu-id="50f70-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/분석</span><span class="sxs-lookup"><span data-stu-id="50f70-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="50f70-112">설명</span><span class="sxs-lookup"><span data-stu-id="50f70-112">Description</span></span>  
 <span data-ttu-id="50f70-113">워크플로 인스턴스가 WorkflowInstanceAbortedRecord를 내보내면 ETW 추적 참가자가 이 이벤트를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="50f70-113">This event is emitted by the ETW tracking participant when a workflow instance emits WorkflowInstanceAbortedRecord.</span></span>  
  
## <a name="message"></a><span data-ttu-id="50f70-114">메시지</span><span class="sxs-lookup"><span data-stu-id="50f70-114">Message</span></span>  
 <span data-ttu-id="50f70-115">TrackRecord = WorkflowInstanceAbortedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, Reason = %5, Annotations = %6, ProfileName = %7, WorkflowDefinitionIdentity %8 =</span><span class="sxs-lookup"><span data-stu-id="50f70-115">TrackRecord = WorkflowInstanceAbortedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, Reason = %5,  Annotations = %6, ProfileName = %7, WorkflowDefinitionIdentity = %8</span></span>  
  
## <a name="details"></a><span data-ttu-id="50f70-116">설명</span><span class="sxs-lookup"><span data-stu-id="50f70-116">Details</span></span>  
  
|<span data-ttu-id="50f70-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="50f70-117">Data Item Name</span></span>|<span data-ttu-id="50f70-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="50f70-118">Data Item Type</span></span>|<span data-ttu-id="50f70-119">설명</span><span class="sxs-lookup"><span data-stu-id="50f70-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="50f70-120">InstanceId</span><span class="sxs-lookup"><span data-stu-id="50f70-120">InstanceId</span></span>|<span data-ttu-id="50f70-121">xs:GUID</span><span class="sxs-lookup"><span data-stu-id="50f70-121">xs:GUID</span></span>|<span data-ttu-id="50f70-122">워크플로의 인스턴스 ID</span><span class="sxs-lookup"><span data-stu-id="50f70-122">The instance id for the workflow</span></span>|  
|<span data-ttu-id="50f70-123">RecordNumber</span><span class="sxs-lookup"><span data-stu-id="50f70-123">RecordNumber</span></span>|<span data-ttu-id="50f70-124">xs:long</span><span class="sxs-lookup"><span data-stu-id="50f70-124">xs:long</span></span>|<span data-ttu-id="50f70-125">내보낸 레코드의 시퀀스 번호</span><span class="sxs-lookup"><span data-stu-id="50f70-125">The sequence number of the emitted record</span></span>|  
|<span data-ttu-id="50f70-126">EventTime</span><span class="sxs-lookup"><span data-stu-id="50f70-126">EventTime</span></span>|<span data-ttu-id="50f70-127">xs:dateTime</span><span class="sxs-lookup"><span data-stu-id="50f70-127">xs:dateTime</span></span>|<span data-ttu-id="50f70-128">이벤트를 내보낸 시간(UTC)</span><span class="sxs-lookup"><span data-stu-id="50f70-128">The time in UTC when the event was emitted</span></span>|  
|<span data-ttu-id="50f70-129">ActivityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="50f70-129">ActivityDefinitionId</span></span>|<span data-ttu-id="50f70-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="50f70-130">xs:string</span></span>|<span data-ttu-id="50f70-131">워크플로의 루트 활동 이름</span><span class="sxs-lookup"><span data-stu-id="50f70-131">The name of the root activity in the workflow</span></span>|  
|<span data-ttu-id="50f70-132">상태</span><span class="sxs-lookup"><span data-stu-id="50f70-132">State</span></span>|<span data-ttu-id="50f70-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="50f70-133">xs:string</span></span>|<span data-ttu-id="50f70-134">워크플로의 현재 상태</span><span class="sxs-lookup"><span data-stu-id="50f70-134">The current state of the Workflow.</span></span>|  
|<span data-ttu-id="50f70-135">주석</span><span class="sxs-lookup"><span data-stu-id="50f70-135">Annotations</span></span>|<span data-ttu-id="50f70-136">xs:string</span><span class="sxs-lookup"><span data-stu-id="50f70-136">xs:string</span></span>|<span data-ttu-id="50f70-137">이 이벤트에 추가된 주석입니다.</span><span class="sxs-lookup"><span data-stu-id="50f70-137">The annotations that were added to this event.</span></span> <span data-ttu-id="50f70-138">값 형식으로 xml 요소에 저장 됩니다 \<항목 >\< 항목 이름 = "annotationName" type = "> annotationValue\<항목/>\<항목/>입니다.</span><span class="sxs-lookup"><span data-stu-id="50f70-138">The values are stored in an xml element in the format \<items>\< item name = "annotationName" type="System.String">annotationValue\</item>\</items>.</span></span> <span data-ttu-id="50f70-139">주석을 지정 하지 않으면 문자열을 포함 하는 경우 \<항목 / >입니다.</span><span class="sxs-lookup"><span data-stu-id="50f70-139">If no annotations are specified then the string contains \<items/>.</span></span> <span data-ttu-id="50f70-140">ETW 이벤트 크기는 ETW 버퍼 크기 또는 ETW 이벤트의 최대 페이로드에 따라 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="50f70-140">The ETW event size is limited by the ETW buffer size or the max payload for an ETW event.</span></span> <span data-ttu-id="50f70-141">이벤트 크기가 ETW 제한을 초과 하면 주석을 삭제 하 고 주석 값으로 바꿔 이벤트 잘립니다 경우 \<항목 >... \<항목/>입니다.</span><span class="sxs-lookup"><span data-stu-id="50f70-141">If the size of the event exceeds the ETW limits, then the event is truncated by dropping the annotations and replacing the annotation value with \<items>...\</items>.</span></span>|  
|<span data-ttu-id="50f70-142">ProfileName</span><span class="sxs-lookup"><span data-stu-id="50f70-142">ProfileName</span></span>|<span data-ttu-id="50f70-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="50f70-143">xs:string</span></span>|<span data-ttu-id="50f70-144">이 이벤트를 내보낸 이름 또는 추적 프로필</span><span class="sxs-lookup"><span data-stu-id="50f70-144">The name or the tracking profile that resulted in this event being emitted</span></span>|  
|<span data-ttu-id="50f70-145">WorkflowDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="50f70-145">WorkflowDefinitionIdentity</span></span>|<span data-ttu-id="50f70-146">xs:string</span><span class="sxs-lookup"><span data-stu-id="50f70-146">xs:string</span></span>|<span data-ttu-id="50f70-147">워크플로 정의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="50f70-147">The workflow definition id</span></span>|  
|<span data-ttu-id="50f70-148">AppDomain</span><span class="sxs-lookup"><span data-stu-id="50f70-148">AppDomain</span></span>|<span data-ttu-id="50f70-149">xs:string</span><span class="sxs-lookup"><span data-stu-id="50f70-149">xs:string</span></span>|<span data-ttu-id="50f70-150">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="50f70-150">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
