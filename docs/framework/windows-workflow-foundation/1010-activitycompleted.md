---
title: 1010 - ActivityCompleted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d256284e-3fd2-4c33-82f4-abb617575706
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1378ddd1550db614c9eddc44f79b19ff94ed585c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="1010---activitycompleted"></a><span data-ttu-id="ef682-102">1010 - ActivityCompleted</span><span class="sxs-lookup"><span data-stu-id="ef682-102">1010 - ActivityCompleted</span></span>
## <a name="properties"></a><span data-ttu-id="ef682-103">속성</span><span class="sxs-lookup"><span data-stu-id="ef682-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ef682-104">ID</span><span class="sxs-lookup"><span data-stu-id="ef682-104">ID</span></span>|<span data-ttu-id="ef682-105">1010</span><span class="sxs-lookup"><span data-stu-id="ef682-105">1010</span></span>|  
|<span data-ttu-id="ef682-106">키워드</span><span class="sxs-lookup"><span data-stu-id="ef682-106">Keywords</span></span>|<span data-ttu-id="ef682-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="ef682-107">WFRuntime</span></span>|  
|<span data-ttu-id="ef682-108">수준</span><span class="sxs-lookup"><span data-stu-id="ef682-108">Level</span></span>|<span data-ttu-id="ef682-109">정보</span><span class="sxs-lookup"><span data-stu-id="ef682-109">Information</span></span>|  
|<span data-ttu-id="ef682-110">채널</span><span class="sxs-lookup"><span data-stu-id="ef682-110">Channel</span></span>|<span data-ttu-id="ef682-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="ef682-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ef682-112">설명</span><span class="sxs-lookup"><span data-stu-id="ef682-112">Description</span></span>  
 <span data-ttu-id="ef682-113">작업의 실행이 완료되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ef682-113">Indicates an activity has completed execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ef682-114">메시지</span><span class="sxs-lookup"><span data-stu-id="ef682-114">Message</span></span>  
 <span data-ttu-id="ef682-115">Activity '%1', DisplayName: '%2', InstanceId: '%3'이(가) '%4' 상태로 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ef682-115">Activity '%1', DisplayName: '%2', InstanceId: '%3' has completed in the '%4' state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ef682-116">설명</span><span class="sxs-lookup"><span data-stu-id="ef682-116">Details</span></span>  
  
|<span data-ttu-id="ef682-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="ef682-117">Data Item Name</span></span>|<span data-ttu-id="ef682-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="ef682-118">Data Item Type</span></span>|<span data-ttu-id="ef682-119">설명</span><span class="sxs-lookup"><span data-stu-id="ef682-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ef682-120">동작</span><span class="sxs-lookup"><span data-stu-id="ef682-120">Activity</span></span>|<span data-ttu-id="ef682-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="ef682-121">xs:string</span></span>|<span data-ttu-id="ef682-122">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ef682-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="ef682-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="ef682-123">DisplayName</span></span>|<span data-ttu-id="ef682-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="ef682-124">xs:string</span></span>|<span data-ttu-id="ef682-125">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ef682-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="ef682-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="ef682-126">InstanceId</span></span>|<span data-ttu-id="ef682-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="ef682-127">xs:string</span></span>|<span data-ttu-id="ef682-128">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ef682-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="ef682-129">상태</span><span class="sxs-lookup"><span data-stu-id="ef682-129">State</span></span>|<span data-ttu-id="ef682-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="ef682-130">xs:string</span></span>|<span data-ttu-id="ef682-131">작업의 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="ef682-131">The state of the activity.</span></span>|  
|<span data-ttu-id="ef682-132">AppDomain</span><span class="sxs-lookup"><span data-stu-id="ef682-132">AppDomain</span></span>|<span data-ttu-id="ef682-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="ef682-133">xs:string</span></span>|<span data-ttu-id="ef682-134">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="ef682-134">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
