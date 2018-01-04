---
title: 1032 - ScheduleRuntimeWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 54688101-becf-42f3-80ca-f53a7b527620
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 81cc73a5ab58e90f1a0ee5bdaf9a491d20206fb3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="1032---scheduleruntimeworkitem"></a><span data-ttu-id="8a890-102">1032 - ScheduleRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="8a890-102">1032 - ScheduleRuntimeWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="8a890-103">속성</span><span class="sxs-lookup"><span data-stu-id="8a890-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8a890-104">ID</span><span class="sxs-lookup"><span data-stu-id="8a890-104">ID</span></span>|<span data-ttu-id="8a890-105">1032</span><span class="sxs-lookup"><span data-stu-id="8a890-105">1032</span></span>|  
|<span data-ttu-id="8a890-106">키워드</span><span class="sxs-lookup"><span data-stu-id="8a890-106">Keywords</span></span>|<span data-ttu-id="8a890-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="8a890-107">WFRuntime</span></span>|  
|<span data-ttu-id="8a890-108">수준</span><span class="sxs-lookup"><span data-stu-id="8a890-108">Level</span></span>|<span data-ttu-id="8a890-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="8a890-109">Verbose</span></span>|  
|<span data-ttu-id="8a890-110">채널</span><span class="sxs-lookup"><span data-stu-id="8a890-110">Channel</span></span>|<span data-ttu-id="8a890-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="8a890-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="8a890-112">설명</span><span class="sxs-lookup"><span data-stu-id="8a890-112">Description</span></span>  
 <span data-ttu-id="8a890-113">RuntimeWorkItem이 예약되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8a890-113">Indicates a RuntimeWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="8a890-114">메시지</span><span class="sxs-lookup"><span data-stu-id="8a890-114">Message</span></span>  
 <span data-ttu-id="8a890-115">작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 런타임 작업 항목이 예약되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8a890-115">A runtime work item has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="8a890-116">설명</span><span class="sxs-lookup"><span data-stu-id="8a890-116">Details</span></span>  
  
|<span data-ttu-id="8a890-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="8a890-117">Data Item Name</span></span>|<span data-ttu-id="8a890-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="8a890-118">Data Item Type</span></span>|<span data-ttu-id="8a890-119">설명</span><span class="sxs-lookup"><span data-stu-id="8a890-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="8a890-120">동작</span><span class="sxs-lookup"><span data-stu-id="8a890-120">Activity</span></span>|<span data-ttu-id="8a890-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="8a890-121">xs:string</span></span>|<span data-ttu-id="8a890-122">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8a890-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="8a890-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="8a890-123">DisplayName</span></span>|<span data-ttu-id="8a890-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="8a890-124">xs:string</span></span>|<span data-ttu-id="8a890-125">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8a890-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="8a890-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="8a890-126">InstanceId</span></span>|<span data-ttu-id="8a890-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="8a890-127">xs:string</span></span>|<span data-ttu-id="8a890-128">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="8a890-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="8a890-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="8a890-129">AppDomain</span></span>|<span data-ttu-id="8a890-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="8a890-130">xs:string</span></span>|<span data-ttu-id="8a890-131">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="8a890-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
