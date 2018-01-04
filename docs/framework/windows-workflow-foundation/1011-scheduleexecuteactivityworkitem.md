---
title: 1011 - ScheduleExecuteActivityWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e503ae46-ad6b-4fcb-8c0e-146d59a8eff1
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fe006534e0199888668145be9da3f964055cc464
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="1011---scheduleexecuteactivityworkitem"></a><span data-ttu-id="8cc00-102">1011 - ScheduleExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="8cc00-102">1011 - ScheduleExecuteActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="8cc00-103">속성</span><span class="sxs-lookup"><span data-stu-id="8cc00-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8cc00-104">ID</span><span class="sxs-lookup"><span data-stu-id="8cc00-104">ID</span></span>|<span data-ttu-id="8cc00-105">1011</span><span class="sxs-lookup"><span data-stu-id="8cc00-105">1011</span></span>|  
|<span data-ttu-id="8cc00-106">키워드</span><span class="sxs-lookup"><span data-stu-id="8cc00-106">Keywords</span></span>|<span data-ttu-id="8cc00-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="8cc00-107">WFRuntime</span></span>|  
|<span data-ttu-id="8cc00-108">수준</span><span class="sxs-lookup"><span data-stu-id="8cc00-108">Level</span></span>|<span data-ttu-id="8cc00-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="8cc00-109">Verbose</span></span>|  
|<span data-ttu-id="8cc00-110">채널</span><span class="sxs-lookup"><span data-stu-id="8cc00-110">Channel</span></span>|<span data-ttu-id="8cc00-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="8cc00-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="8cc00-112">설명</span><span class="sxs-lookup"><span data-stu-id="8cc00-112">Description</span></span>  
 <span data-ttu-id="8cc00-113">ExecuteActivityWorkItem이 예약되어 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8cc00-113">Indicates an ExecuteActivityWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="8cc00-114">메시지</span><span class="sxs-lookup"><span data-stu-id="8cc00-114">Message</span></span>  
 <span data-ttu-id="8cc00-115">작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 ExecuteActivityWorkItem이 예약되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8cc00-115">An ExecuteActivityWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="8cc00-116">설명</span><span class="sxs-lookup"><span data-stu-id="8cc00-116">Details</span></span>  
  
|<span data-ttu-id="8cc00-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="8cc00-117">Data Item Name</span></span>|<span data-ttu-id="8cc00-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="8cc00-118">Data Item Type</span></span>|<span data-ttu-id="8cc00-119">설명</span><span class="sxs-lookup"><span data-stu-id="8cc00-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="8cc00-120">동작</span><span class="sxs-lookup"><span data-stu-id="8cc00-120">Activity</span></span>|<span data-ttu-id="8cc00-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="8cc00-121">xs:string</span></span>|<span data-ttu-id="8cc00-122">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8cc00-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="8cc00-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="8cc00-123">DisplayName</span></span>|<span data-ttu-id="8cc00-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="8cc00-124">xs:string</span></span>|<span data-ttu-id="8cc00-125">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8cc00-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="8cc00-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="8cc00-126">InstanceId</span></span>|<span data-ttu-id="8cc00-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="8cc00-127">xs:string</span></span>|<span data-ttu-id="8cc00-128">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="8cc00-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="8cc00-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="8cc00-129">AppDomain</span></span>|<span data-ttu-id="8cc00-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="8cc00-130">xs:string</span></span>|<span data-ttu-id="8cc00-131">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="8cc00-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
