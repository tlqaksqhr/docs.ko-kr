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
ms.openlocfilehash: d2a150b9e9c78a9ce1f5e20b962a58ef2d5dde9d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="1032---scheduleruntimeworkitem"></a><span data-ttu-id="190ac-102">1032 - ScheduleRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="190ac-102">1032 - ScheduleRuntimeWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="190ac-103">속성</span><span class="sxs-lookup"><span data-stu-id="190ac-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="190ac-104">ID</span><span class="sxs-lookup"><span data-stu-id="190ac-104">ID</span></span>|<span data-ttu-id="190ac-105">1032</span><span class="sxs-lookup"><span data-stu-id="190ac-105">1032</span></span>|  
|<span data-ttu-id="190ac-106">키워드</span><span class="sxs-lookup"><span data-stu-id="190ac-106">Keywords</span></span>|<span data-ttu-id="190ac-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="190ac-107">WFRuntime</span></span>|  
|<span data-ttu-id="190ac-108">수준</span><span class="sxs-lookup"><span data-stu-id="190ac-108">Level</span></span>|<span data-ttu-id="190ac-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="190ac-109">Verbose</span></span>|  
|<span data-ttu-id="190ac-110">채널</span><span class="sxs-lookup"><span data-stu-id="190ac-110">Channel</span></span>|<span data-ttu-id="190ac-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="190ac-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="190ac-112">설명</span><span class="sxs-lookup"><span data-stu-id="190ac-112">Description</span></span>  
 <span data-ttu-id="190ac-113">RuntimeWorkItem이 예약되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="190ac-113">Indicates a RuntimeWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="190ac-114">메시지</span><span class="sxs-lookup"><span data-stu-id="190ac-114">Message</span></span>  
 <span data-ttu-id="190ac-115">작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 런타임 작업 항목이 예약되었습니다.</span><span class="sxs-lookup"><span data-stu-id="190ac-115">A runtime work item has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="190ac-116">설명</span><span class="sxs-lookup"><span data-stu-id="190ac-116">Details</span></span>  
  
|<span data-ttu-id="190ac-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="190ac-117">Data Item Name</span></span>|<span data-ttu-id="190ac-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="190ac-118">Data Item Type</span></span>|<span data-ttu-id="190ac-119">설명</span><span class="sxs-lookup"><span data-stu-id="190ac-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="190ac-120">동작</span><span class="sxs-lookup"><span data-stu-id="190ac-120">Activity</span></span>|<span data-ttu-id="190ac-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="190ac-121">xs:string</span></span>|<span data-ttu-id="190ac-122">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="190ac-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="190ac-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="190ac-123">DisplayName</span></span>|<span data-ttu-id="190ac-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="190ac-124">xs:string</span></span>|<span data-ttu-id="190ac-125">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="190ac-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="190ac-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="190ac-126">InstanceId</span></span>|<span data-ttu-id="190ac-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="190ac-127">xs:string</span></span>|<span data-ttu-id="190ac-128">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="190ac-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="190ac-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="190ac-129">AppDomain</span></span>|<span data-ttu-id="190ac-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="190ac-130">xs:string</span></span>|<span data-ttu-id="190ac-131">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="190ac-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
