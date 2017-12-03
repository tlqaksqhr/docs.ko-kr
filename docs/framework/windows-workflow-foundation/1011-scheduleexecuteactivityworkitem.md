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
ms.openlocfilehash: ec89acb9d83a28ac280db7c3d536bfe63669fa97
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="1011---scheduleexecuteactivityworkitem"></a><span data-ttu-id="40af7-102">1011 - ScheduleExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="40af7-102">1011 - ScheduleExecuteActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="40af7-103">속성</span><span class="sxs-lookup"><span data-stu-id="40af7-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="40af7-104">ID</span><span class="sxs-lookup"><span data-stu-id="40af7-104">ID</span></span>|<span data-ttu-id="40af7-105">1011</span><span class="sxs-lookup"><span data-stu-id="40af7-105">1011</span></span>|  
|<span data-ttu-id="40af7-106">키워드</span><span class="sxs-lookup"><span data-stu-id="40af7-106">Keywords</span></span>|<span data-ttu-id="40af7-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="40af7-107">WFRuntime</span></span>|  
|<span data-ttu-id="40af7-108">수준</span><span class="sxs-lookup"><span data-stu-id="40af7-108">Level</span></span>|<span data-ttu-id="40af7-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="40af7-109">Verbose</span></span>|  
|<span data-ttu-id="40af7-110">채널</span><span class="sxs-lookup"><span data-stu-id="40af7-110">Channel</span></span>|<span data-ttu-id="40af7-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="40af7-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="40af7-112">설명</span><span class="sxs-lookup"><span data-stu-id="40af7-112">Description</span></span>  
 <span data-ttu-id="40af7-113">ExecuteActivityWorkItem이 예약되어 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="40af7-113">Indicates an ExecuteActivityWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="40af7-114">메시지</span><span class="sxs-lookup"><span data-stu-id="40af7-114">Message</span></span>  
 <span data-ttu-id="40af7-115">작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 ExecuteActivityWorkItem이 예약되었습니다.</span><span class="sxs-lookup"><span data-stu-id="40af7-115">An ExecuteActivityWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="40af7-116">설명</span><span class="sxs-lookup"><span data-stu-id="40af7-116">Details</span></span>  
  
|<span data-ttu-id="40af7-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="40af7-117">Data Item Name</span></span>|<span data-ttu-id="40af7-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="40af7-118">Data Item Type</span></span>|<span data-ttu-id="40af7-119">설명</span><span class="sxs-lookup"><span data-stu-id="40af7-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="40af7-120">동작</span><span class="sxs-lookup"><span data-stu-id="40af7-120">Activity</span></span>|<span data-ttu-id="40af7-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="40af7-121">xs:string</span></span>|<span data-ttu-id="40af7-122">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="40af7-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="40af7-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="40af7-123">DisplayName</span></span>|<span data-ttu-id="40af7-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="40af7-124">xs:string</span></span>|<span data-ttu-id="40af7-125">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="40af7-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="40af7-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="40af7-126">InstanceId</span></span>|<span data-ttu-id="40af7-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="40af7-127">xs:string</span></span>|<span data-ttu-id="40af7-128">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="40af7-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="40af7-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="40af7-129">AppDomain</span></span>|<span data-ttu-id="40af7-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="40af7-130">xs:string</span></span>|<span data-ttu-id="40af7-131">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="40af7-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
