---
title: 39458 - TrackingRecordTruncated
ms.date: 03/30/2017
ms.assetid: 5352f0eb-d571-454a-bab5-e2162888b218
ms.openlocfilehash: 416feb4073b31178b016ae72c9cd85e15c4a68c3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33514484"
---
# <a name="39458---trackingrecordtruncated"></a><span data-ttu-id="4f973-102">39458 - TrackingRecordTruncated</span><span class="sxs-lookup"><span data-stu-id="4f973-102">39458 - TrackingRecordTruncated</span></span>
## <a name="properties"></a><span data-ttu-id="4f973-103">속성</span><span class="sxs-lookup"><span data-stu-id="4f973-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4f973-104">ID</span><span class="sxs-lookup"><span data-stu-id="4f973-104">ID</span></span>|<span data-ttu-id="4f973-105">39458</span><span class="sxs-lookup"><span data-stu-id="4f973-105">39458</span></span>|  
|<span data-ttu-id="4f973-106">키워드</span><span class="sxs-lookup"><span data-stu-id="4f973-106">Keywords</span></span>|<span data-ttu-id="4f973-107">WFTracking</span><span class="sxs-lookup"><span data-stu-id="4f973-107">WFTracking</span></span>|  
|<span data-ttu-id="4f973-108">수준</span><span class="sxs-lookup"><span data-stu-id="4f973-108">Level</span></span>|<span data-ttu-id="4f973-109">경고</span><span class="sxs-lookup"><span data-stu-id="4f973-109">Warning</span></span>|  
|<span data-ttu-id="4f973-110">채널</span><span class="sxs-lookup"><span data-stu-id="4f973-110">Channel</span></span>|<span data-ttu-id="4f973-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="4f973-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="4f973-112">설명</span><span class="sxs-lookup"><span data-stu-id="4f973-112">Description</span></span>  
 <span data-ttu-id="4f973-113">추적 레코드가 잘렸음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4f973-113">Indicates a tracking record has been truncated.</span></span> <span data-ttu-id="4f973-114">변수/주석/사용자 데이터가 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4f973-114">Variables/annotations/user data have been removed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="4f973-115">메시지</span><span class="sxs-lookup"><span data-stu-id="4f973-115">Message</span></span>  
 <span data-ttu-id="4f973-116">잘린 추적 레코드 %1이(가) 공급자가 %2인 ETW 세션에 기록되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4f973-116">Truncated tracking record %1 written to ETW session with provider %2.</span></span> <span data-ttu-id="4f973-117">변수/주석/사용자 데이터가 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4f973-117">Variables/annotations/user data have been removed</span></span>  
  
## <a name="details"></a><span data-ttu-id="4f973-118">설명</span><span class="sxs-lookup"><span data-stu-id="4f973-118">Details</span></span>  
  
|<span data-ttu-id="4f973-119">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="4f973-119">Data Item Name</span></span>|<span data-ttu-id="4f973-120">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="4f973-120">Data Item Type</span></span>|<span data-ttu-id="4f973-121">설명</span><span class="sxs-lookup"><span data-stu-id="4f973-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="4f973-122">RecordNumber</span><span class="sxs-lookup"><span data-stu-id="4f973-122">RecordNumber</span></span>|<span data-ttu-id="4f973-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="4f973-123">xs:string</span></span>|<span data-ttu-id="4f973-124">추적 레코드 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="4f973-124">The tracking record number.</span></span>|  
|<span data-ttu-id="4f973-125">ProviderId</span><span class="sxs-lookup"><span data-stu-id="4f973-125">ProviderId</span></span>|<span data-ttu-id="4f973-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="4f973-126">xs:string</span></span>|<span data-ttu-id="4f973-127">ETW 공급자 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="4f973-127">The ETW provider id.</span></span>|  
|<span data-ttu-id="4f973-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="4f973-128">AppDomain</span></span>|<span data-ttu-id="4f973-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="4f973-129">xs:string</span></span>|<span data-ttu-id="4f973-130">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="4f973-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
