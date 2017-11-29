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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c3fcd93dbc30b20f7822a54babde8277e32d8335
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="1035---runtimetransactionset"></a><span data-ttu-id="c1c13-102">1035 - RuntimeTransactionSet</span><span class="sxs-lookup"><span data-stu-id="c1c13-102">1035 - RuntimeTransactionSet</span></span>
## <a name="properties"></a><span data-ttu-id="c1c13-103">속성</span><span class="sxs-lookup"><span data-stu-id="c1c13-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c1c13-104">ID</span><span class="sxs-lookup"><span data-stu-id="c1c13-104">ID</span></span>|<span data-ttu-id="c1c13-105">1035</span><span class="sxs-lookup"><span data-stu-id="c1c13-105">1035</span></span>|  
|<span data-ttu-id="c1c13-106">키워드</span><span class="sxs-lookup"><span data-stu-id="c1c13-106">Keywords</span></span>|<span data-ttu-id="c1c13-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="c1c13-107">WFRuntime</span></span>|  
|<span data-ttu-id="c1c13-108">수준</span><span class="sxs-lookup"><span data-stu-id="c1c13-108">Level</span></span>|<span data-ttu-id="c1c13-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="c1c13-109">Verbose</span></span>|  
|<span data-ttu-id="c1c13-110">채널</span><span class="sxs-lookup"><span data-stu-id="c1c13-110">Channel</span></span>|<span data-ttu-id="c1c13-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="c1c13-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c1c13-112">설명</span><span class="sxs-lookup"><span data-stu-id="c1c13-112">Description</span></span>  
 <span data-ttu-id="c1c13-113">작업이 런타임 트랜잭션으로 설정되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-113">Indicates an activity has set the runtime transaction.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c1c13-114">메시지</span><span class="sxs-lookup"><span data-stu-id="c1c13-114">Message</span></span>  
 <span data-ttu-id="c1c13-115">런타임 트랜잭션이 작업 '%1', DisplayName가 설정한: '%2', InstanceId: '%3'.</span><span class="sxs-lookup"><span data-stu-id="c1c13-115">The runtime transaction has been set by Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  <span data-ttu-id="c1c13-116">실행에만 작업 '%4', DisplayName: '%5', InstanceId: '%6'.</span><span class="sxs-lookup"><span data-stu-id="c1c13-116">Execution isolated to Activity '%4', DisplayName: '%5', InstanceId: '%6'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="c1c13-117">세부 정보</span><span class="sxs-lookup"><span data-stu-id="c1c13-117">Details</span></span>  
  
|<span data-ttu-id="c1c13-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="c1c13-118">Data Item Name</span></span>|<span data-ttu-id="c1c13-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="c1c13-119">Data Item Type</span></span>|<span data-ttu-id="c1c13-120">설명</span><span class="sxs-lookup"><span data-stu-id="c1c13-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="c1c13-121">동작</span><span class="sxs-lookup"><span data-stu-id="c1c13-121">Activity</span></span>|<span data-ttu-id="c1c13-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="c1c13-122">xs:string</span></span>|<span data-ttu-id="c1c13-123">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-123">The type name of the activity.</span></span>|  
|<span data-ttu-id="c1c13-124">DisplayName</span><span class="sxs-lookup"><span data-stu-id="c1c13-124">DisplayName</span></span>|<span data-ttu-id="c1c13-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="c1c13-125">xs:string</span></span>|<span data-ttu-id="c1c13-126">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-126">The display name of the activity.</span></span>|  
|<span data-ttu-id="c1c13-127">InstanceId</span><span class="sxs-lookup"><span data-stu-id="c1c13-127">InstanceId</span></span>|<span data-ttu-id="c1c13-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="c1c13-128">xs:string</span></span>|<span data-ttu-id="c1c13-129">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-129">The instance id of the activity.</span></span>|  
|<span data-ttu-id="c1c13-130">IsolatedActivity</span><span class="sxs-lookup"><span data-stu-id="c1c13-130">IsolatedActivity</span></span>|<span data-ttu-id="c1c13-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="c1c13-131">xs:string</span></span>|<span data-ttu-id="c1c13-132">트랜잭션이 격리된 작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-132">The type name of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="c1c13-133">IsolatedActivityDisplayName</span><span class="sxs-lookup"><span data-stu-id="c1c13-133">IsolatedActivityDisplayName</span></span>|<span data-ttu-id="c1c13-134">xs:string</span><span class="sxs-lookup"><span data-stu-id="c1c13-134">xs:string</span></span>|<span data-ttu-id="c1c13-135">트랜잭션이 격리된 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-135">The display name of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="c1c13-136">IsolatedActivityInstanceId</span><span class="sxs-lookup"><span data-stu-id="c1c13-136">IsolatedActivityInstanceId</span></span>|<span data-ttu-id="c1c13-137">xs:string</span><span class="sxs-lookup"><span data-stu-id="c1c13-137">xs:string</span></span>|<span data-ttu-id="c1c13-138">트랜잭션이 격리된 작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-138">The instance id of the activity that the transaction is isolated to.</span></span>|  
|<span data-ttu-id="c1c13-139">AppDomain</span><span class="sxs-lookup"><span data-stu-id="c1c13-139">AppDomain</span></span>|<span data-ttu-id="c1c13-140">xs:string</span><span class="sxs-lookup"><span data-stu-id="c1c13-140">xs:string</span></span>|<span data-ttu-id="c1c13-141">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="c1c13-141">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
