---
title: 401- StopSignPostEvent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e033d03a-510d-4300-aa65-ef02cb4807f2
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 30e796dec45035e6b68659400ebbae1357137b27
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="401--stopsignpostevent"></a><span data-ttu-id="10235-102">401- StopSignPostEvent</span><span class="sxs-lookup"><span data-stu-id="10235-102">401- StopSignPostEvent</span></span>
## <a name="properties"></a><span data-ttu-id="10235-103">속성</span><span class="sxs-lookup"><span data-stu-id="10235-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="10235-104">ID</span><span class="sxs-lookup"><span data-stu-id="10235-104">ID</span></span>|<span data-ttu-id="10235-105">401</span><span class="sxs-lookup"><span data-stu-id="10235-105">401</span></span>|  
|<span data-ttu-id="10235-106">키워드</span><span class="sxs-lookup"><span data-stu-id="10235-106">Keywords</span></span>|<span data-ttu-id="10235-107">문제 해결</span><span class="sxs-lookup"><span data-stu-id="10235-107">Troubleshooting</span></span>|  
|<span data-ttu-id="10235-108">수준</span><span class="sxs-lookup"><span data-stu-id="10235-108">Level</span></span>|<span data-ttu-id="10235-109">정보</span><span class="sxs-lookup"><span data-stu-id="10235-109">Information</span></span>|  
|<span data-ttu-id="10235-110">채널</span><span class="sxs-lookup"><span data-stu-id="10235-110">Channel</span></span>|<span data-ttu-id="10235-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/분석</span><span class="sxs-lookup"><span data-stu-id="10235-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="10235-112">설명</span><span class="sxs-lookup"><span data-stu-id="10235-112">Description</span></span>  
 <span data-ttu-id="10235-113">이 이벤트는 종단 간 동작의 끝을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="10235-113">This event marks the end of an end-to-end activity.</span></span> <span data-ttu-id="10235-114">여기에는 동작의 이름이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="10235-114">It contains the name of the activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="10235-115">메시지</span><span class="sxs-lookup"><span data-stu-id="10235-115">Message</span></span>  
 <span data-ttu-id="10235-116">동작 경계입니다.</span><span class="sxs-lookup"><span data-stu-id="10235-116">Activity boundary.</span></span>  
  
## <a name="details"></a><span data-ttu-id="10235-117">설명</span><span class="sxs-lookup"><span data-stu-id="10235-117">Details</span></span>  
  
|<span data-ttu-id="10235-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="10235-118">Data Item Name</span></span>|<span data-ttu-id="10235-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="10235-119">Data Item Type</span></span>|<span data-ttu-id="10235-120">설명</span><span class="sxs-lookup"><span data-stu-id="10235-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="10235-121">Extended Data</span><span class="sxs-lookup"><span data-stu-id="10235-121">Extended Data</span></span>|`xs:string`|<span data-ttu-id="10235-122">작업의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="10235-122">The name of the activity.</span></span>|  
|<span data-ttu-id="10235-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="10235-123">AppDomain</span></span>|`xs:string`|<span data-ttu-id="10235-124">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="10235-124">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
