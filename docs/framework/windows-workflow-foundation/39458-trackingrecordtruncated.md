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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ecf18d6d751edd47dbeca7d2e5f4491892e41e6d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="39458---trackingrecordtruncated"></a><span data-ttu-id="7f262-102">39458 - TrackingRecordTruncated</span><span class="sxs-lookup"><span data-stu-id="7f262-102">39458 - TrackingRecordTruncated</span></span>
## <a name="properties"></a><span data-ttu-id="7f262-103">속성</span><span class="sxs-lookup"><span data-stu-id="7f262-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7f262-104">ID</span><span class="sxs-lookup"><span data-stu-id="7f262-104">ID</span></span>|<span data-ttu-id="7f262-105">39458</span><span class="sxs-lookup"><span data-stu-id="7f262-105">39458</span></span>|  
|<span data-ttu-id="7f262-106">키워드</span><span class="sxs-lookup"><span data-stu-id="7f262-106">Keywords</span></span>|<span data-ttu-id="7f262-107">WFTracking</span><span class="sxs-lookup"><span data-stu-id="7f262-107">WFTracking</span></span>|  
|<span data-ttu-id="7f262-108">수준</span><span class="sxs-lookup"><span data-stu-id="7f262-108">Level</span></span>|<span data-ttu-id="7f262-109">경고</span><span class="sxs-lookup"><span data-stu-id="7f262-109">Warning</span></span>|  
|<span data-ttu-id="7f262-110">채널</span><span class="sxs-lookup"><span data-stu-id="7f262-110">Channel</span></span>|<span data-ttu-id="7f262-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="7f262-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="7f262-112">설명</span><span class="sxs-lookup"><span data-stu-id="7f262-112">Description</span></span>  
 <span data-ttu-id="7f262-113">추적 레코드가 잘렸음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7f262-113">Indicates a tracking record has been truncated.</span></span> <span data-ttu-id="7f262-114">변수/주석/사용자 데이터가 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7f262-114">Variables/annotations/user data have been removed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="7f262-115">메시지</span><span class="sxs-lookup"><span data-stu-id="7f262-115">Message</span></span>  
 <span data-ttu-id="7f262-116">잘린 추적 레코드 %1이(가) 공급자가 %2인 ETW 세션에 기록되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7f262-116">Truncated tracking record %1 written to ETW session with provider %2.</span></span> <span data-ttu-id="7f262-117">변수/주석/사용자 데이터가 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7f262-117">Variables/annotations/user data have been removed</span></span>  
  
## <a name="details"></a><span data-ttu-id="7f262-118">설명</span><span class="sxs-lookup"><span data-stu-id="7f262-118">Details</span></span>  
  
|<span data-ttu-id="7f262-119">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="7f262-119">Data Item Name</span></span>|<span data-ttu-id="7f262-120">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="7f262-120">Data Item Type</span></span>|<span data-ttu-id="7f262-121">설명</span><span class="sxs-lookup"><span data-stu-id="7f262-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="7f262-122">RecordNumber</span><span class="sxs-lookup"><span data-stu-id="7f262-122">RecordNumber</span></span>|<span data-ttu-id="7f262-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="7f262-123">xs:string</span></span>|<span data-ttu-id="7f262-124">추적 레코드 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="7f262-124">The tracking record number.</span></span>|  
|<span data-ttu-id="7f262-125">ProviderId</span><span class="sxs-lookup"><span data-stu-id="7f262-125">ProviderId</span></span>|<span data-ttu-id="7f262-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="7f262-126">xs:string</span></span>|<span data-ttu-id="7f262-127">ETW 공급자 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="7f262-127">The ETW provider id.</span></span>|  
|<span data-ttu-id="7f262-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="7f262-128">AppDomain</span></span>|<span data-ttu-id="7f262-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="7f262-129">xs:string</span></span>|<span data-ttu-id="7f262-130">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="7f262-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
