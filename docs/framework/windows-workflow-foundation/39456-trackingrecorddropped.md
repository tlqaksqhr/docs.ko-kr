---
title: 39456 - TrackingRecordDropped
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: da13d5bc-1736-47a4-b3fd-064ca8040326
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 592d7c0a3725dcb50f7911a198c9dc9b7199a0a8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="39456---trackingrecorddropped"></a><span data-ttu-id="52227-102">39456 - TrackingRecordDropped</span><span class="sxs-lookup"><span data-stu-id="52227-102">39456 - TrackingRecordDropped</span></span>
## <a name="properties"></a><span data-ttu-id="52227-103">속성</span><span class="sxs-lookup"><span data-stu-id="52227-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="52227-104">ID</span><span class="sxs-lookup"><span data-stu-id="52227-104">ID</span></span>|<span data-ttu-id="52227-105">39456</span><span class="sxs-lookup"><span data-stu-id="52227-105">39456</span></span>|  
|<span data-ttu-id="52227-106">키워드</span><span class="sxs-lookup"><span data-stu-id="52227-106">Keywords</span></span>|<span data-ttu-id="52227-107">WFTracking</span><span class="sxs-lookup"><span data-stu-id="52227-107">WFTracking</span></span>|  
|<span data-ttu-id="52227-108">수준</span><span class="sxs-lookup"><span data-stu-id="52227-108">Level</span></span>|<span data-ttu-id="52227-109">경고</span><span class="sxs-lookup"><span data-stu-id="52227-109">Warning</span></span>|  
|<span data-ttu-id="52227-110">채널</span><span class="sxs-lookup"><span data-stu-id="52227-110">Channel</span></span>|<span data-ttu-id="52227-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="52227-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="52227-112">설명</span><span class="sxs-lookup"><span data-stu-id="52227-112">Description</span></span>  
 <span data-ttu-id="52227-113">추적 레코드의 크기가 ETW 세션 공급자에서 허용하는 최대값을 초과하기 때문에 추적 레코드가 삭제되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="52227-113">Indicates a tracking record has been dropped because its size exceeds maximum allowed by the ETW session provider.</span></span>  
  
## <a name="message"></a><span data-ttu-id="52227-114">메시지</span><span class="sxs-lookup"><span data-stu-id="52227-114">Message</span></span>  
 <span data-ttu-id="52227-115">추적 레코드 %1의 크기가 %2 공급자의 ETW 세션에서 허용된 최대값을 초과합니다.</span><span class="sxs-lookup"><span data-stu-id="52227-115">Size of tracking record %1 exceeds maximum allowed by the ETW session for provider %2</span></span>  
  
## <a name="details"></a><span data-ttu-id="52227-116">설명</span><span class="sxs-lookup"><span data-stu-id="52227-116">Details</span></span>  
  
|<span data-ttu-id="52227-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="52227-117">Data Item Name</span></span>|<span data-ttu-id="52227-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="52227-118">Data Item Type</span></span>|<span data-ttu-id="52227-119">설명</span><span class="sxs-lookup"><span data-stu-id="52227-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="52227-120">예외</span><span class="sxs-lookup"><span data-stu-id="52227-120">Exception</span></span>|<span data-ttu-id="52227-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="52227-121">xs:string</span></span>|<span data-ttu-id="52227-122">예외에 대한 예외 정보</span><span class="sxs-lookup"><span data-stu-id="52227-122">The exception details for the exception</span></span>|  
|<span data-ttu-id="52227-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="52227-123">AppDomain</span></span>|<span data-ttu-id="52227-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="52227-124">xs:string</span></span>|<span data-ttu-id="52227-125">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="52227-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
