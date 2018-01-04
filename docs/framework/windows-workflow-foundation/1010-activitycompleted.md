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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4d11bbe013c6f3370064dd8cd9f4f03a0234d6f8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="1010---activitycompleted"></a><span data-ttu-id="c74b5-102">1010 - ActivityCompleted</span><span class="sxs-lookup"><span data-stu-id="c74b5-102">1010 - ActivityCompleted</span></span>
## <a name="properties"></a><span data-ttu-id="c74b5-103">속성</span><span class="sxs-lookup"><span data-stu-id="c74b5-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c74b5-104">ID</span><span class="sxs-lookup"><span data-stu-id="c74b5-104">ID</span></span>|<span data-ttu-id="c74b5-105">1010</span><span class="sxs-lookup"><span data-stu-id="c74b5-105">1010</span></span>|  
|<span data-ttu-id="c74b5-106">키워드</span><span class="sxs-lookup"><span data-stu-id="c74b5-106">Keywords</span></span>|<span data-ttu-id="c74b5-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="c74b5-107">WFRuntime</span></span>|  
|<span data-ttu-id="c74b5-108">수준</span><span class="sxs-lookup"><span data-stu-id="c74b5-108">Level</span></span>|<span data-ttu-id="c74b5-109">정보</span><span class="sxs-lookup"><span data-stu-id="c74b5-109">Information</span></span>|  
|<span data-ttu-id="c74b5-110">채널</span><span class="sxs-lookup"><span data-stu-id="c74b5-110">Channel</span></span>|<span data-ttu-id="c74b5-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="c74b5-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c74b5-112">설명</span><span class="sxs-lookup"><span data-stu-id="c74b5-112">Description</span></span>  
 <span data-ttu-id="c74b5-113">작업의 실행이 완료되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c74b5-113">Indicates an activity has completed execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c74b5-114">메시지</span><span class="sxs-lookup"><span data-stu-id="c74b5-114">Message</span></span>  
 <span data-ttu-id="c74b5-115">Activity '%1', DisplayName: '%2', InstanceId: '%3'이(가) '%4' 상태로 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c74b5-115">Activity '%1', DisplayName: '%2', InstanceId: '%3' has completed in the '%4' state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="c74b5-116">설명</span><span class="sxs-lookup"><span data-stu-id="c74b5-116">Details</span></span>  
  
|<span data-ttu-id="c74b5-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="c74b5-117">Data Item Name</span></span>|<span data-ttu-id="c74b5-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="c74b5-118">Data Item Type</span></span>|<span data-ttu-id="c74b5-119">설명</span><span class="sxs-lookup"><span data-stu-id="c74b5-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="c74b5-120">동작</span><span class="sxs-lookup"><span data-stu-id="c74b5-120">Activity</span></span>|<span data-ttu-id="c74b5-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="c74b5-121">xs:string</span></span>|<span data-ttu-id="c74b5-122">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c74b5-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="c74b5-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="c74b5-123">DisplayName</span></span>|<span data-ttu-id="c74b5-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="c74b5-124">xs:string</span></span>|<span data-ttu-id="c74b5-125">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c74b5-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="c74b5-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="c74b5-126">InstanceId</span></span>|<span data-ttu-id="c74b5-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="c74b5-127">xs:string</span></span>|<span data-ttu-id="c74b5-128">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c74b5-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="c74b5-129">상태</span><span class="sxs-lookup"><span data-stu-id="c74b5-129">State</span></span>|<span data-ttu-id="c74b5-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="c74b5-130">xs:string</span></span>|<span data-ttu-id="c74b5-131">작업의 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="c74b5-131">The state of the activity.</span></span>|  
|<span data-ttu-id="c74b5-132">AppDomain</span><span class="sxs-lookup"><span data-stu-id="c74b5-132">AppDomain</span></span>|<span data-ttu-id="c74b5-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="c74b5-133">xs:string</span></span>|<span data-ttu-id="c74b5-134">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="c74b5-134">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
