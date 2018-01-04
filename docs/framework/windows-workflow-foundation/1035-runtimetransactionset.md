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
ms.workload: dotnet
ms.openlocfilehash: a64a8a4ab6212a5e83b59fd7523df9cd875e7b87
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="1035---runtimetransactionset"></a><span data-ttu-id="1bbbb-102">1035 - RuntimeTransactionSet</span><span class="sxs-lookup"><span data-stu-id="1bbbb-102">1035 - RuntimeTransactionSet</span></span>
## <a name="properties"></a><span data-ttu-id="1bbbb-103">속성</span><span class="sxs-lookup"><span data-stu-id="1bbbb-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1bbbb-104">ID</span><span class="sxs-lookup"><span data-stu-id="1bbbb-104">ID</span></span>|<span data-ttu-id="1bbbb-105">1035</span><span class="sxs-lookup"><span data-stu-id="1bbbb-105">1035</span></span>|  
|<span data-ttu-id="1bbbb-106">키워드</span><span class="sxs-lookup"><span data-stu-id="1bbbb-106">Keywords</span></span>|<span data-ttu-id="1bbbb-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="1bbbb-107">WFRuntime</span></span>|  
|<span data-ttu-id="1bbbb-108">수준</span><span class="sxs-lookup"><span data-stu-id="1bbbb-108">Level</span></span>|<span data-ttu-id="1bbbb-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="1bbbb-109">Verbose</span></span>|  
|<span data-ttu-id="1bbbb-110">채널</span><span class="sxs-lookup"><span data-stu-id="1bbbb-110">Channel</span></span>|<span data-ttu-id="1bbbb-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="1bbbb-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="1bbbb-112">설명</span><span class="sxs-lookup"><span data-stu-id="1bbbb-112">Description</span></span>  
 <span data-ttu-id="1bbbb-113">작업이 런타임 트랜잭션으로 설정되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1bbbb-113">Indicates an activity has set the runtime transaction.</span></span>  
  
## <a name="message"></a><span data-ttu-id="1bbbb-114">메시지</span><span class="sxs-lookup"><span data-stu-id="1bbbb-114">Message</span></span>  
 <span data-ttu-id="1bbbb-115">런타임 트랜잭션이 작업 '%1', DisplayName가 설정한: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="1bbbb-115">The runtime transaction has been set by Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="1bbbb-116">실행에만 작업 '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="1bbbb-116">Execution isolated to Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="1bbbb-117">설명</span><span class="sxs-lookup"><span data-stu-id="1bbbb-117">Details</span></span>  
  
|<span data-ttu-id="1bbbb-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="1bbbb-118">Data Item Name</span></span>|<span data-ttu-id="1bbbb-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="1bbbb-119">Data Item Type</span></span>|<span data-ttu-id="1bbbb-120">설명</span><span class="sxs-lookup"><span data-stu-id="1bbbb-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="1bbbb-121">동작</span><span class="sxs-lookup"><span data-stu-id="1bbbb-121">Activity</span></span>|<span data-ttu-id="1bbbb-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="1bbbb-122">xs:string</span></span>|<span data-ttu-id="1bbbb-123">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1bbbb-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="1bbbb-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="1bbbb-124">DisplayName</span></span>|<span data-ttu-id="1bbbb-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="1bbbb-125">xs:string</span></span>|<span data-ttu-id="1bbbb-126">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1bbbb-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="1bbbb-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="1bbbb-127">InstanceId</span></span>|<span data-ttu-id="1bbbb-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="1bbbb-128">xs:string</span></span>|<span data-ttu-id="1bbbb-129">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="1bbbb-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="1bbbb-130">IsolatedActivity</span><span class="sxs-lookup"><span data-stu-id="1bbbb-130">IsolatedActivity</span></span>|<span data-ttu-id="1bbbb-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="1bbbb-131">xs:string</span></span>|<span data-ttu-id="1bbbb-132">트랜잭션이 격리된 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1bbbb-132">The type name of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="1bbbb-133">IsolatedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="1bbbb-133">IsolatedActivityDisplayName</span></span>|<span data-ttu-id="1bbbb-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="1bbbb-134">xs:string</span></span>|<span data-ttu-id="1bbbb-135">트랜잭션이 격리된 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1bbbb-135">The display name of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="1bbbb-136">IsolatedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="1bbbb-136">IsolatedActivityInstanceId</span></span>|<span data-ttu-id="1bbbb-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="1bbbb-137">xs:string</span></span>|<span data-ttu-id="1bbbb-138">트랜잭션이 격리된 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="1bbbb-138">The instance id of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="1bbbb-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="1bbbb-139">AppDomain</span></span>|<span data-ttu-id="1bbbb-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="1bbbb-140">xs:string</span></span>|<span data-ttu-id="1bbbb-141">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="1bbbb-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
