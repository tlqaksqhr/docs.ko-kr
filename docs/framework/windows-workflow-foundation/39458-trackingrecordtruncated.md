---
title: 39458 - TrackingRecordTruncated
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5352f0eb-d571-454a-bab5-e2162888b218
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1d2bc07cff75fce7ddb50da9f54d161d7f235cab
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="39458---trackingrecordtruncated"></a><span data-ttu-id="506f6-102">39458 - TrackingRecordTruncated</span><span class="sxs-lookup"><span data-stu-id="506f6-102">39458 - TrackingRecordTruncated</span></span>
## <a name="properties"></a><span data-ttu-id="506f6-103">속성</span><span class="sxs-lookup"><span data-stu-id="506f6-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="506f6-104">ID</span><span class="sxs-lookup"><span data-stu-id="506f6-104">ID</span></span>|<span data-ttu-id="506f6-105">39458</span><span class="sxs-lookup"><span data-stu-id="506f6-105">39458</span></span>|  
|<span data-ttu-id="506f6-106">키워드</span><span class="sxs-lookup"><span data-stu-id="506f6-106">Keywords</span></span>|<span data-ttu-id="506f6-107">WFTracking</span><span class="sxs-lookup"><span data-stu-id="506f6-107">WFTracking</span></span>|  
|<span data-ttu-id="506f6-108">수준</span><span class="sxs-lookup"><span data-stu-id="506f6-108">Level</span></span>|<span data-ttu-id="506f6-109">경고</span><span class="sxs-lookup"><span data-stu-id="506f6-109">Warning</span></span>|  
|<span data-ttu-id="506f6-110">채널</span><span class="sxs-lookup"><span data-stu-id="506f6-110">Channel</span></span>|<span data-ttu-id="506f6-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="506f6-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="506f6-112">설명</span><span class="sxs-lookup"><span data-stu-id="506f6-112">Description</span></span>  
 <span data-ttu-id="506f6-113">추적 레코드가 잘렸음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="506f6-113">Indicates a tracking record has been truncated.</span></span> <span data-ttu-id="506f6-114">변수/주석/사용자 데이터가 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="506f6-114">Variables/annotations/user data have been removed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="506f6-115">메시지</span><span class="sxs-lookup"><span data-stu-id="506f6-115">Message</span></span>  
 <span data-ttu-id="506f6-116">잘린 추적 레코드 %1이(가) 공급자가 %2인 ETW 세션에 기록되었습니다.</span><span class="sxs-lookup"><span data-stu-id="506f6-116">Truncated tracking record %1 written to ETW session with provider %2.</span></span> <span data-ttu-id="506f6-117">변수/주석/사용자 데이터가 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="506f6-117">Variables/annotations/user data have been removed</span></span>  
  
## <a name="details"></a><span data-ttu-id="506f6-118">설명</span><span class="sxs-lookup"><span data-stu-id="506f6-118">Details</span></span>  
  
|<span data-ttu-id="506f6-119">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="506f6-119">Data Item Name</span></span>|<span data-ttu-id="506f6-120">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="506f6-120">Data Item Type</span></span>|<span data-ttu-id="506f6-121">설명</span><span class="sxs-lookup"><span data-stu-id="506f6-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="506f6-122">RecordNumber</span><span class="sxs-lookup"><span data-stu-id="506f6-122">RecordNumber</span></span>|<span data-ttu-id="506f6-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="506f6-123">xs:string</span></span>|<span data-ttu-id="506f6-124">추적 레코드 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="506f6-124">The tracking record number.</span></span>|  
|<span data-ttu-id="506f6-125">ProviderId</span><span class="sxs-lookup"><span data-stu-id="506f6-125">ProviderId</span></span>|<span data-ttu-id="506f6-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="506f6-126">xs:string</span></span>|<span data-ttu-id="506f6-127">ETW 공급자 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="506f6-127">The ETW provider id.</span></span>|  
|<span data-ttu-id="506f6-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="506f6-128">AppDomain</span></span>|<span data-ttu-id="506f6-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="506f6-129">xs:string</span></span>|<span data-ttu-id="506f6-130">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="506f6-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
