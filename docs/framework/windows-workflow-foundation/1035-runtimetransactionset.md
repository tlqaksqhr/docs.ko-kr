---
title: 1035 - RuntimeTransactionSet
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 03b37de9-778c-4beb-b0e3-de73ece6088e
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 0fcd6662c0f8899b6830dc8e06cee4f56b5ff906
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="1035---runtimetransactionset"></a><span data-ttu-id="4ad55-102">1035 - RuntimeTransactionSet</span><span class="sxs-lookup"><span data-stu-id="4ad55-102">1035 - RuntimeTransactionSet</span></span>
## <a name="properties"></a><span data-ttu-id="4ad55-103">속성</span><span class="sxs-lookup"><span data-stu-id="4ad55-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4ad55-104">ID</span><span class="sxs-lookup"><span data-stu-id="4ad55-104">ID</span></span>|<span data-ttu-id="4ad55-105">1035</span><span class="sxs-lookup"><span data-stu-id="4ad55-105">1035</span></span>|  
|<span data-ttu-id="4ad55-106">키워드</span><span class="sxs-lookup"><span data-stu-id="4ad55-106">Keywords</span></span>|<span data-ttu-id="4ad55-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="4ad55-107">WFRuntime</span></span>|  
|<span data-ttu-id="4ad55-108">수준</span><span class="sxs-lookup"><span data-stu-id="4ad55-108">Level</span></span>|<span data-ttu-id="4ad55-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="4ad55-109">Verbose</span></span>|  
|<span data-ttu-id="4ad55-110">채널</span><span class="sxs-lookup"><span data-stu-id="4ad55-110">Channel</span></span>|<span data-ttu-id="4ad55-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="4ad55-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="4ad55-112">설명</span><span class="sxs-lookup"><span data-stu-id="4ad55-112">Description</span></span>  
 <span data-ttu-id="4ad55-113">작업이 런타임 트랜잭션으로 설정되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4ad55-113">Indicates an activity has set the runtime transaction.</span></span>  
  
## <a name="message"></a><span data-ttu-id="4ad55-114">메시지</span><span class="sxs-lookup"><span data-stu-id="4ad55-114">Message</span></span>  
 <span data-ttu-id="4ad55-115">런타임 트랜잭션이 작업 '%1', DisplayName가 설정한: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="4ad55-115">The runtime transaction has been set by Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="4ad55-116">실행에만 작업 '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="4ad55-116">Execution isolated to Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="4ad55-117">세부 정보</span><span class="sxs-lookup"><span data-stu-id="4ad55-117">Details</span></span>  
  
|<span data-ttu-id="4ad55-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="4ad55-118">Data Item Name</span></span>|<span data-ttu-id="4ad55-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="4ad55-119">Data Item Type</span></span>|<span data-ttu-id="4ad55-120">설명</span><span class="sxs-lookup"><span data-stu-id="4ad55-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="4ad55-121">동작</span><span class="sxs-lookup"><span data-stu-id="4ad55-121">Activity</span></span>|<span data-ttu-id="4ad55-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="4ad55-122">xs:string</span></span>|<span data-ttu-id="4ad55-123">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4ad55-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="4ad55-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="4ad55-124">DisplayName</span></span>|<span data-ttu-id="4ad55-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="4ad55-125">xs:string</span></span>|<span data-ttu-id="4ad55-126">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4ad55-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="4ad55-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="4ad55-127">InstanceId</span></span>|<span data-ttu-id="4ad55-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="4ad55-128">xs:string</span></span>|<span data-ttu-id="4ad55-129">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="4ad55-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="4ad55-130">IsolatedActivity</span><span class="sxs-lookup"><span data-stu-id="4ad55-130">IsolatedActivity</span></span>|<span data-ttu-id="4ad55-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="4ad55-131">xs:string</span></span>|<span data-ttu-id="4ad55-132">트랜잭션이 격리된 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4ad55-132">The type name of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="4ad55-133">IsolatedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="4ad55-133">IsolatedActivityDisplayName</span></span>|<span data-ttu-id="4ad55-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="4ad55-134">xs:string</span></span>|<span data-ttu-id="4ad55-135">트랜잭션이 격리된 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4ad55-135">The display name of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="4ad55-136">IsolatedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="4ad55-136">IsolatedActivityInstanceId</span></span>|<span data-ttu-id="4ad55-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="4ad55-137">xs:string</span></span>|<span data-ttu-id="4ad55-138">트랜잭션이 격리된 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="4ad55-138">The instance id of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="4ad55-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="4ad55-139">AppDomain</span></span>|<span data-ttu-id="4ad55-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="4ad55-140">xs:string</span></span>|<span data-ttu-id="4ad55-141">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="4ad55-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
