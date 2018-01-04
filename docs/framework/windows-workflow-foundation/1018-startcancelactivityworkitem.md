---
title: 1018 - StartCancelActivityWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 68b4fa1d-eee6-4a2a-8c16-7e9d89f08ab9
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2d64d18474ff867ee5679e07c18a288f07185f60
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="1018---startcancelactivityworkitem"></a><span data-ttu-id="4bac5-102">1018 - StartCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="4bac5-102">1018 - StartCancelActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="4bac5-103">속성</span><span class="sxs-lookup"><span data-stu-id="4bac5-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4bac5-104">ID</span><span class="sxs-lookup"><span data-stu-id="4bac5-104">ID</span></span>|<span data-ttu-id="4bac5-105">1018</span><span class="sxs-lookup"><span data-stu-id="4bac5-105">1018</span></span>|  
|<span data-ttu-id="4bac5-106">키워드</span><span class="sxs-lookup"><span data-stu-id="4bac5-106">Keywords</span></span>|<span data-ttu-id="4bac5-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="4bac5-107">WFRuntime</span></span>|  
|<span data-ttu-id="4bac5-108">수준</span><span class="sxs-lookup"><span data-stu-id="4bac5-108">Level</span></span>|<span data-ttu-id="4bac5-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="4bac5-109">Verbose</span></span>|  
|<span data-ttu-id="4bac5-110">채널</span><span class="sxs-lookup"><span data-stu-id="4bac5-110">Channel</span></span>|<span data-ttu-id="4bac5-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="4bac5-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="4bac5-112">설명</span><span class="sxs-lookup"><span data-stu-id="4bac5-112">Description</span></span>  
 <span data-ttu-id="4bac5-113">CancelActivityWorkItem이 실행을 시작했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4bac5-113">Indicates a CancelActivityWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="4bac5-114">메시지</span><span class="sxs-lookup"><span data-stu-id="4bac5-114">Message</span></span>  
 <span data-ttu-id="4bac5-115">작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 CancelActivityWorkItem의 실행을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="4bac5-115">Starting execution of a CancelActivityWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="4bac5-116">설명</span><span class="sxs-lookup"><span data-stu-id="4bac5-116">Details</span></span>  
  
|<span data-ttu-id="4bac5-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="4bac5-117">Data Item Name</span></span>|<span data-ttu-id="4bac5-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="4bac5-118">Data Item Type</span></span>|<span data-ttu-id="4bac5-119">설명</span><span class="sxs-lookup"><span data-stu-id="4bac5-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="4bac5-120">동작</span><span class="sxs-lookup"><span data-stu-id="4bac5-120">Activity</span></span>|<span data-ttu-id="4bac5-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="4bac5-121">xs:string</span></span>|<span data-ttu-id="4bac5-122">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4bac5-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="4bac5-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="4bac5-123">DisplayName</span></span>|<span data-ttu-id="4bac5-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="4bac5-124">xs:string</span></span>|<span data-ttu-id="4bac5-125">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4bac5-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="4bac5-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="4bac5-126">InstanceId</span></span>|<span data-ttu-id="4bac5-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="4bac5-127">xs:string</span></span>|<span data-ttu-id="4bac5-128">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="4bac5-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="4bac5-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="4bac5-129">AppDomain</span></span>|<span data-ttu-id="4bac5-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="4bac5-130">xs:string</span></span>|<span data-ttu-id="4bac5-131">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="4bac5-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
