---
title: 1019 - CompleteCancelActivityWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 75a4a1ab-e5a3-4f4e-88e4-d19806e671d7
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9f8af4486d4659afd4c98016a6f88719271f1a1b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="1019---completecancelactivityworkitem"></a><span data-ttu-id="1d64b-102">1019 - CompleteCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="1d64b-102">1019 - CompleteCancelActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="1d64b-103">속성</span><span class="sxs-lookup"><span data-stu-id="1d64b-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1d64b-104">ID</span><span class="sxs-lookup"><span data-stu-id="1d64b-104">ID</span></span>|<span data-ttu-id="1d64b-105">1019</span><span class="sxs-lookup"><span data-stu-id="1d64b-105">1019</span></span>|  
|<span data-ttu-id="1d64b-106">키워드</span><span class="sxs-lookup"><span data-stu-id="1d64b-106">Keywords</span></span>|<span data-ttu-id="1d64b-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="1d64b-107">WFRuntime</span></span>|  
|<span data-ttu-id="1d64b-108">수준</span><span class="sxs-lookup"><span data-stu-id="1d64b-108">Level</span></span>|<span data-ttu-id="1d64b-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="1d64b-109">Verbose</span></span>|  
|<span data-ttu-id="1d64b-110">채널</span><span class="sxs-lookup"><span data-stu-id="1d64b-110">Channel</span></span>|<span data-ttu-id="1d64b-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="1d64b-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="1d64b-112">설명</span><span class="sxs-lookup"><span data-stu-id="1d64b-112">Description</span></span>  
 <span data-ttu-id="1d64b-113">CancelActivityWorkItem이 완료되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1d64b-113">Indicates a CancelActivityWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="1d64b-114">메시지</span><span class="sxs-lookup"><span data-stu-id="1d64b-114">Message</span></span>  
 <span data-ttu-id="1d64b-115">작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 CancelActivityWorkItem이 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1d64b-115">A CancelActivityWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="1d64b-116">설명</span><span class="sxs-lookup"><span data-stu-id="1d64b-116">Details</span></span>  
  
|<span data-ttu-id="1d64b-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="1d64b-117">Data Item Name</span></span>|<span data-ttu-id="1d64b-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="1d64b-118">Data Item Type</span></span>|<span data-ttu-id="1d64b-119">설명</span><span class="sxs-lookup"><span data-stu-id="1d64b-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="1d64b-120">동작</span><span class="sxs-lookup"><span data-stu-id="1d64b-120">Activity</span></span>|<span data-ttu-id="1d64b-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="1d64b-121">xs:string</span></span>|<span data-ttu-id="1d64b-122">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1d64b-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="1d64b-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="1d64b-123">DisplayName</span></span>|<span data-ttu-id="1d64b-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="1d64b-124">xs:string</span></span>|<span data-ttu-id="1d64b-125">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1d64b-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="1d64b-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="1d64b-126">InstanceId</span></span>|<span data-ttu-id="1d64b-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="1d64b-127">xs:string</span></span>|<span data-ttu-id="1d64b-128">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="1d64b-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="1d64b-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="1d64b-129">AppDomain</span></span>|<span data-ttu-id="1d64b-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="1d64b-130">xs:string</span></span>|<span data-ttu-id="1d64b-131">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="1d64b-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
