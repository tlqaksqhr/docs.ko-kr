---
title: 3508 - TrackingProfileNotFound
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4cee3c4a-0490-4c94-aa19-ef7ce7287c02
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: fb5636057193fcfb59e5062f6f3833a62b4f3027
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="3508---trackingprofilenotfound"></a><span data-ttu-id="31cf9-102">3508 - TrackingProfileNotFound</span><span class="sxs-lookup"><span data-stu-id="31cf9-102">3508 - TrackingProfileNotFound</span></span>
## <a name="properties"></a><span data-ttu-id="31cf9-103">속성</span><span class="sxs-lookup"><span data-stu-id="31cf9-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="31cf9-104">ID</span><span class="sxs-lookup"><span data-stu-id="31cf9-104">ID</span></span>|<span data-ttu-id="31cf9-105">3508</span><span class="sxs-lookup"><span data-stu-id="31cf9-105">3508</span></span>|  
|<span data-ttu-id="31cf9-106">키워드</span><span class="sxs-lookup"><span data-stu-id="31cf9-106">Keywords</span></span>|<span data-ttu-id="31cf9-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="31cf9-107">WFServices</span></span>|  
|<span data-ttu-id="31cf9-108">수준</span><span class="sxs-lookup"><span data-stu-id="31cf9-108">Level</span></span>|<span data-ttu-id="31cf9-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="31cf9-109">Verbose</span></span>|  
|<span data-ttu-id="31cf9-110">채널</span><span class="sxs-lookup"><span data-stu-id="31cf9-110">Channel</span></span>|<span data-ttu-id="31cf9-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/분석</span><span class="sxs-lookup"><span data-stu-id="31cf9-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="31cf9-112">설명</span><span class="sxs-lookup"><span data-stu-id="31cf9-112">Description</span></span>  
 <span data-ttu-id="31cf9-113">구성 파일에 TrackingProfile이 없거나 ActivityDefinitionId가 프로필과 일치하지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="31cf9-113">Indicates either a TrackingProfile is not found in the config file or the ActivityDefinitionId does not match the profile.</span></span>  
  
## <a name="message"></a><span data-ttu-id="31cf9-114">메시지</span><span class="sxs-lookup"><span data-stu-id="31cf9-114">Message</span></span>  
 <span data-ttu-id="31cf9-115">ActivityDefinitionId '%2'에 대한 TrackingProfile '%1'을(를) 찾지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="31cf9-115">TrackingProfile '%1' for the ActivityDefinitionId '%2' not found.</span></span> <span data-ttu-id="31cf9-116">구성 파일에 TrackingProfile이 없거나 ActivityDefinitionId가 일치하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="31cf9-116">Either the TrackingProfile is not found in the config file or the ActivityDefinitionId does not match.</span></span>  
  
## <a name="details"></a><span data-ttu-id="31cf9-117">설명</span><span class="sxs-lookup"><span data-stu-id="31cf9-117">Details</span></span>  
  
|<span data-ttu-id="31cf9-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="31cf9-118">Data Item Name</span></span>|<span data-ttu-id="31cf9-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="31cf9-119">Data Item Type</span></span>|<span data-ttu-id="31cf9-120">설명</span><span class="sxs-lookup"><span data-stu-id="31cf9-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="31cf9-121">TrackingProfile</span><span class="sxs-lookup"><span data-stu-id="31cf9-121">TrackingProfile</span></span>|<span data-ttu-id="31cf9-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="31cf9-122">xs:string</span></span>|<span data-ttu-id="31cf9-123">추적 프로필의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="31cf9-123">The name of the tracking profile.</span></span>|  
|<span data-ttu-id="31cf9-124">ActivityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="31cf9-124">ActivityDefinitionId</span></span>|<span data-ttu-id="31cf9-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="31cf9-125">xs:string</span></span>|<span data-ttu-id="31cf9-126">작업 정의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="31cf9-126">The activity definition id.</span></span>|  
|<span data-ttu-id="31cf9-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="31cf9-127">AppDomain</span></span>|<span data-ttu-id="31cf9-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="31cf9-128">xs:string</span></span>|<span data-ttu-id="31cf9-129">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="31cf9-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
