---
title: 1013 - CompleteExecuteActivityWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 31fc57b3-ef2f-48f0-a5de-b4e2c5c9ded7
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: de9add3f537c1d8ff97c92892197598bcc7a4fe7
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="1013---completeexecuteactivityworkitem"></a><span data-ttu-id="f40c5-102">1013 - CompleteExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="f40c5-102">1013 - CompleteExecuteActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="f40c5-103">속성</span><span class="sxs-lookup"><span data-stu-id="f40c5-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f40c5-104">ID</span><span class="sxs-lookup"><span data-stu-id="f40c5-104">ID</span></span>|<span data-ttu-id="f40c5-105">1013</span><span class="sxs-lookup"><span data-stu-id="f40c5-105">1013</span></span>|  
|<span data-ttu-id="f40c5-106">키워드</span><span class="sxs-lookup"><span data-stu-id="f40c5-106">Keywords</span></span>|<span data-ttu-id="f40c5-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="f40c5-107">WFRuntime</span></span>|  
|<span data-ttu-id="f40c5-108">수준</span><span class="sxs-lookup"><span data-stu-id="f40c5-108">Level</span></span>|<span data-ttu-id="f40c5-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="f40c5-109">Verbose</span></span>|  
|<span data-ttu-id="f40c5-110">채널</span><span class="sxs-lookup"><span data-stu-id="f40c5-110">Channel</span></span>|<span data-ttu-id="f40c5-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="f40c5-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f40c5-112">설명</span><span class="sxs-lookup"><span data-stu-id="f40c5-112">Description</span></span>  
 <span data-ttu-id="f40c5-113">ExecuteActivityWorkItem이 완료되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f40c5-113">Indicates an ExecuteActivityWorkItem has completed</span></span>  
  
## <a name="message"></a><span data-ttu-id="f40c5-114">메시지</span><span class="sxs-lookup"><span data-stu-id="f40c5-114">Message</span></span>  
 <span data-ttu-id="f40c5-115">작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 ExecuteActivityWorkItem이 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f40c5-115">An ExecuteActivityWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f40c5-116">설명</span><span class="sxs-lookup"><span data-stu-id="f40c5-116">Details</span></span>  
  
|<span data-ttu-id="f40c5-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="f40c5-117">Data Item Name</span></span>|<span data-ttu-id="f40c5-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="f40c5-118">Data Item Type</span></span>|<span data-ttu-id="f40c5-119">설명</span><span class="sxs-lookup"><span data-stu-id="f40c5-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f40c5-120">동작</span><span class="sxs-lookup"><span data-stu-id="f40c5-120">Activity</span></span>|<span data-ttu-id="f40c5-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="f40c5-121">xs:string</span></span>|<span data-ttu-id="f40c5-122">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f40c5-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="f40c5-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="f40c5-123">DisplayName</span></span>|<span data-ttu-id="f40c5-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="f40c5-124">xs:string</span></span>|<span data-ttu-id="f40c5-125">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f40c5-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="f40c5-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="f40c5-126">InstanceId</span></span>|<span data-ttu-id="f40c5-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="f40c5-127">xs:string</span></span>|<span data-ttu-id="f40c5-128">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="f40c5-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="f40c5-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f40c5-129">AppDomain</span></span>|<span data-ttu-id="f40c5-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="f40c5-130">xs:string</span></span>|<span data-ttu-id="f40c5-131">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="f40c5-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
