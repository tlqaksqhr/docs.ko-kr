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
ms.workload: dotnet
ms.openlocfilehash: 4d12549d201ac621361bd6a517df6c6b53ab7aec
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="39458---trackingrecordtruncated"></a><span data-ttu-id="363e0-102">39458 - TrackingRecordTruncated</span><span class="sxs-lookup"><span data-stu-id="363e0-102">39458 - TrackingRecordTruncated</span></span>
## <a name="properties"></a><span data-ttu-id="363e0-103">속성</span><span class="sxs-lookup"><span data-stu-id="363e0-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="363e0-104">ID</span><span class="sxs-lookup"><span data-stu-id="363e0-104">ID</span></span>|<span data-ttu-id="363e0-105">39458</span><span class="sxs-lookup"><span data-stu-id="363e0-105">39458</span></span>|  
|<span data-ttu-id="363e0-106">키워드</span><span class="sxs-lookup"><span data-stu-id="363e0-106">Keywords</span></span>|<span data-ttu-id="363e0-107">WFTracking</span><span class="sxs-lookup"><span data-stu-id="363e0-107">WFTracking</span></span>|  
|<span data-ttu-id="363e0-108">수준</span><span class="sxs-lookup"><span data-stu-id="363e0-108">Level</span></span>|<span data-ttu-id="363e0-109">경고</span><span class="sxs-lookup"><span data-stu-id="363e0-109">Warning</span></span>|  
|<span data-ttu-id="363e0-110">채널</span><span class="sxs-lookup"><span data-stu-id="363e0-110">Channel</span></span>|<span data-ttu-id="363e0-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="363e0-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="363e0-112">설명</span><span class="sxs-lookup"><span data-stu-id="363e0-112">Description</span></span>  
 <span data-ttu-id="363e0-113">추적 레코드가 잘렸음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="363e0-113">Indicates a tracking record has been truncated.</span></span> <span data-ttu-id="363e0-114">변수/주석/사용자 데이터가 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="363e0-114">Variables/annotations/user data have been removed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="363e0-115">메시지</span><span class="sxs-lookup"><span data-stu-id="363e0-115">Message</span></span>  
 <span data-ttu-id="363e0-116">잘린 추적 레코드 %1이(가) 공급자가 %2인 ETW 세션에 기록되었습니다.</span><span class="sxs-lookup"><span data-stu-id="363e0-116">Truncated tracking record %1 written to ETW session with provider %2.</span></span> <span data-ttu-id="363e0-117">변수/주석/사용자 데이터가 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="363e0-117">Variables/annotations/user data have been removed</span></span>  
  
## <a name="details"></a><span data-ttu-id="363e0-118">설명</span><span class="sxs-lookup"><span data-stu-id="363e0-118">Details</span></span>  
  
|<span data-ttu-id="363e0-119">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="363e0-119">Data Item Name</span></span>|<span data-ttu-id="363e0-120">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="363e0-120">Data Item Type</span></span>|<span data-ttu-id="363e0-121">설명</span><span class="sxs-lookup"><span data-stu-id="363e0-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="363e0-122">RecordNumber</span><span class="sxs-lookup"><span data-stu-id="363e0-122">RecordNumber</span></span>|<span data-ttu-id="363e0-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="363e0-123">xs:string</span></span>|<span data-ttu-id="363e0-124">추적 레코드 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="363e0-124">The tracking record number.</span></span>|  
|<span data-ttu-id="363e0-125">ProviderId</span><span class="sxs-lookup"><span data-stu-id="363e0-125">ProviderId</span></span>|<span data-ttu-id="363e0-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="363e0-126">xs:string</span></span>|<span data-ttu-id="363e0-127">ETW 공급자 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="363e0-127">The ETW provider id.</span></span>|  
|<span data-ttu-id="363e0-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="363e0-128">AppDomain</span></span>|<span data-ttu-id="363e0-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="363e0-129">xs:string</span></span>|<span data-ttu-id="363e0-130">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="363e0-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
