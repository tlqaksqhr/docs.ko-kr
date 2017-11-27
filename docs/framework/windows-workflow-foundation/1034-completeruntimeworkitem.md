---
title: 1034 - CompleteRuntimeWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 45620011-8b04-4f87-ab5a-65b24145e17d
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 63ab145b8a0688a7f7bbf7dbcbe8dfe612eab294
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="1034---completeruntimeworkitem"></a><span data-ttu-id="466e6-102">1034 - CompleteRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="466e6-102">1034 - CompleteRuntimeWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="466e6-103">속성</span><span class="sxs-lookup"><span data-stu-id="466e6-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="466e6-104">ID</span><span class="sxs-lookup"><span data-stu-id="466e6-104">ID</span></span>|<span data-ttu-id="466e6-105">1034</span><span class="sxs-lookup"><span data-stu-id="466e6-105">1034</span></span>|  
|<span data-ttu-id="466e6-106">키워드</span><span class="sxs-lookup"><span data-stu-id="466e6-106">Keywords</span></span>|<span data-ttu-id="466e6-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="466e6-107">WFRuntime</span></span>|  
|<span data-ttu-id="466e6-108">수준</span><span class="sxs-lookup"><span data-stu-id="466e6-108">Level</span></span>|<span data-ttu-id="466e6-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="466e6-109">Verbose</span></span>|  
|<span data-ttu-id="466e6-110">채널</span><span class="sxs-lookup"><span data-stu-id="466e6-110">Channel</span></span>|<span data-ttu-id="466e6-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="466e6-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="466e6-112">설명</span><span class="sxs-lookup"><span data-stu-id="466e6-112">Description</span></span>  
 <span data-ttu-id="466e6-113">RuntimeWorkItem이 완료되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="466e6-113">Indicates a RuntimeWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="466e6-114">메시지</span><span class="sxs-lookup"><span data-stu-id="466e6-114">Message</span></span>  
 <span data-ttu-id="466e6-115">작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 런타임 작업 항목이 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="466e6-115">A runtime work item has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="466e6-116">설명</span><span class="sxs-lookup"><span data-stu-id="466e6-116">Details</span></span>  
  
|<span data-ttu-id="466e6-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="466e6-117">Data Item Name</span></span>|<span data-ttu-id="466e6-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="466e6-118">Data Item Type</span></span>|<span data-ttu-id="466e6-119">설명</span><span class="sxs-lookup"><span data-stu-id="466e6-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="466e6-120">동작</span><span class="sxs-lookup"><span data-stu-id="466e6-120">Activity</span></span>|<span data-ttu-id="466e6-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="466e6-121">xs:string</span></span>|<span data-ttu-id="466e6-122">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="466e6-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="466e6-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="466e6-123">DisplayName</span></span>|<span data-ttu-id="466e6-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="466e6-124">xs:string</span></span>|<span data-ttu-id="466e6-125">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="466e6-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="466e6-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="466e6-126">InstanceId</span></span>|<span data-ttu-id="466e6-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="466e6-127">xs:string</span></span>|<span data-ttu-id="466e6-128">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="466e6-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="466e6-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="466e6-129">AppDomain</span></span>|<span data-ttu-id="466e6-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="466e6-130">xs:string</span></span>|<span data-ttu-id="466e6-131">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="466e6-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
