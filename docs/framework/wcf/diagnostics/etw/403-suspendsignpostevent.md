---
title: 403 - SuspendSignpostEvent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fb2e6f29-e556-47b4-b4c1-acd6b8879702
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b9259ca71a21e36eaae06d33920adec538e36d98
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="403---suspendsignpostevent"></a><span data-ttu-id="e01c4-102">403 - SuspendSignpostEvent</span><span class="sxs-lookup"><span data-stu-id="e01c4-102">403 - SuspendSignpostEvent</span></span>
## <a name="properties"></a><span data-ttu-id="e01c4-103">속성</span><span class="sxs-lookup"><span data-stu-id="e01c4-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e01c4-104">ID</span><span class="sxs-lookup"><span data-stu-id="e01c4-104">ID</span></span>|<span data-ttu-id="e01c4-105">403</span><span class="sxs-lookup"><span data-stu-id="e01c4-105">403</span></span>|  
|<span data-ttu-id="e01c4-106">키워드</span><span class="sxs-lookup"><span data-stu-id="e01c4-106">Keywords</span></span>|<span data-ttu-id="e01c4-107">문제 해결</span><span class="sxs-lookup"><span data-stu-id="e01c4-107">Troubleshooting</span></span>|  
|<span data-ttu-id="e01c4-108">수준</span><span class="sxs-lookup"><span data-stu-id="e01c4-108">Level</span></span>|<span data-ttu-id="e01c4-109">정보</span><span class="sxs-lookup"><span data-stu-id="e01c4-109">Information</span></span>|  
|<span data-ttu-id="e01c4-110">채널</span><span class="sxs-lookup"><span data-stu-id="e01c4-110">Channel</span></span>|<span data-ttu-id="e01c4-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/분석</span><span class="sxs-lookup"><span data-stu-id="e01c4-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e01c4-112">설명</span><span class="sxs-lookup"><span data-stu-id="e01c4-112">Description</span></span>  
 <span data-ttu-id="e01c4-113">이 이벤트는 종단 간 동작의 일시 중단을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="e01c4-113">This event marks the suspension of an end-to-end activity.</span></span> <span data-ttu-id="e01c4-114">여기에는 동작의 이름이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e01c4-114">It contains the name of the activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e01c4-115">메시지</span><span class="sxs-lookup"><span data-stu-id="e01c4-115">Message</span></span>  
 <span data-ttu-id="e01c4-116">동작 경계입니다.</span><span class="sxs-lookup"><span data-stu-id="e01c4-116">Activity boundary.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e01c4-117">설명</span><span class="sxs-lookup"><span data-stu-id="e01c4-117">Details</span></span>  
  
|<span data-ttu-id="e01c4-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="e01c4-118">Data Item Name</span></span>|<span data-ttu-id="e01c4-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="e01c4-119">Data Item Type</span></span>|<span data-ttu-id="e01c4-120">설명</span><span class="sxs-lookup"><span data-stu-id="e01c4-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e01c4-121">Extended Data</span><span class="sxs-lookup"><span data-stu-id="e01c4-121">Extended Data</span></span>|`xs:string`|<span data-ttu-id="e01c4-122">작업의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e01c4-122">The name of the activity.</span></span>|  
|<span data-ttu-id="e01c4-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="e01c4-123">AppDomain</span></span>|`xs:string`|<span data-ttu-id="e01c4-124">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="e01c4-124">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
