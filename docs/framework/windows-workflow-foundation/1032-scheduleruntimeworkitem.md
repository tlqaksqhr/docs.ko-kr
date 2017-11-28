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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4de69b1fc2647d7723db8aebb02942938db7478f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="1032---scheduleruntimeworkitem"></a><span data-ttu-id="85a06-102">1032 - ScheduleRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="85a06-102">1032 - ScheduleRuntimeWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="85a06-103">속성</span><span class="sxs-lookup"><span data-stu-id="85a06-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="85a06-104">ID</span><span class="sxs-lookup"><span data-stu-id="85a06-104">ID</span></span>|<span data-ttu-id="85a06-105">1032</span><span class="sxs-lookup"><span data-stu-id="85a06-105">1032</span></span>|  
|<span data-ttu-id="85a06-106">키워드</span><span class="sxs-lookup"><span data-stu-id="85a06-106">Keywords</span></span>|<span data-ttu-id="85a06-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="85a06-107">WFRuntime</span></span>|  
|<span data-ttu-id="85a06-108">수준</span><span class="sxs-lookup"><span data-stu-id="85a06-108">Level</span></span>|<span data-ttu-id="85a06-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="85a06-109">Verbose</span></span>|  
|<span data-ttu-id="85a06-110">채널</span><span class="sxs-lookup"><span data-stu-id="85a06-110">Channel</span></span>|<span data-ttu-id="85a06-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="85a06-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="85a06-112">설명</span><span class="sxs-lookup"><span data-stu-id="85a06-112">Description</span></span>  
 <span data-ttu-id="85a06-113">RuntimeWorkItem이 예약되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="85a06-113">Indicates a RuntimeWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="85a06-114">메시지</span><span class="sxs-lookup"><span data-stu-id="85a06-114">Message</span></span>  
 <span data-ttu-id="85a06-115">작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 런타임 작업 항목이 예약되었습니다.</span><span class="sxs-lookup"><span data-stu-id="85a06-115">A runtime work item has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="85a06-116">설명</span><span class="sxs-lookup"><span data-stu-id="85a06-116">Details</span></span>  
  
|<span data-ttu-id="85a06-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="85a06-117">Data Item Name</span></span>|<span data-ttu-id="85a06-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="85a06-118">Data Item Type</span></span>|<span data-ttu-id="85a06-119">설명</span><span class="sxs-lookup"><span data-stu-id="85a06-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="85a06-120">동작</span><span class="sxs-lookup"><span data-stu-id="85a06-120">Activity</span></span>|<span data-ttu-id="85a06-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="85a06-121">xs:string</span></span>|<span data-ttu-id="85a06-122">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="85a06-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="85a06-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="85a06-123">DisplayName</span></span>|<span data-ttu-id="85a06-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="85a06-124">xs:string</span></span>|<span data-ttu-id="85a06-125">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="85a06-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="85a06-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="85a06-126">InstanceId</span></span>|<span data-ttu-id="85a06-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="85a06-127">xs:string</span></span>|<span data-ttu-id="85a06-128">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="85a06-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="85a06-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="85a06-129">AppDomain</span></span>|<span data-ttu-id="85a06-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="85a06-130">xs:string</span></span>|<span data-ttu-id="85a06-131">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="85a06-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
