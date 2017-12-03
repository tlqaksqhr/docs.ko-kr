---
title: 4211 - QueuingSqlRetry
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: df569f88-c86b-4503-840d-1399b67f4df7
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 349a91f5b4708d829aee8d7f055871ac7dcc8914
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="4211---queuingsqlretry"></a><span data-ttu-id="0a4e2-102">4211 - QueuingSqlRetry</span><span class="sxs-lookup"><span data-stu-id="0a4e2-102">4211 - QueuingSqlRetry</span></span>
## <a name="properties"></a><span data-ttu-id="0a4e2-103">속성</span><span class="sxs-lookup"><span data-stu-id="0a4e2-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0a4e2-104">ID</span><span class="sxs-lookup"><span data-stu-id="0a4e2-104">ID</span></span>|<span data-ttu-id="0a4e2-105">4211</span><span class="sxs-lookup"><span data-stu-id="0a4e2-105">4211</span></span>|  
|<span data-ttu-id="0a4e2-106">키워드</span><span class="sxs-lookup"><span data-stu-id="0a4e2-106">Keywords</span></span>|<span data-ttu-id="0a4e2-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="0a4e2-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="0a4e2-108">수준</span><span class="sxs-lookup"><span data-stu-id="0a4e2-108">Level</span></span>|<span data-ttu-id="0a4e2-109">경고</span><span class="sxs-lookup"><span data-stu-id="0a4e2-109">Warning</span></span>|  
|<span data-ttu-id="0a4e2-110">채널</span><span class="sxs-lookup"><span data-stu-id="0a4e2-110">Channel</span></span>|<span data-ttu-id="0a4e2-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="0a4e2-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0a4e2-112">설명</span><span class="sxs-lookup"><span data-stu-id="0a4e2-112">Description</span></span>  
 <span data-ttu-id="0a4e2-113">SQL 재시도를 큐에 넣고 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0a4e2-113">Indicates queuing SQL retry.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0a4e2-114">메시지</span><span class="sxs-lookup"><span data-stu-id="0a4e2-114">Message</span></span>  
 <span data-ttu-id="0a4e2-115">%1밀리초의 지연으로 SQL 재시도를 큐에 넣고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a4e2-115">Queuing SQL retry with delay %1 milliseconds.</span></span>  
  
## <a name="details"></a><span data-ttu-id="0a4e2-116">설명</span><span class="sxs-lookup"><span data-stu-id="0a4e2-116">Details</span></span>  
  
|<span data-ttu-id="0a4e2-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="0a4e2-117">Data Item Name</span></span>|<span data-ttu-id="0a4e2-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="0a4e2-118">Data Item Type</span></span>|<span data-ttu-id="0a4e2-119">설명</span><span class="sxs-lookup"><span data-stu-id="0a4e2-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0a4e2-120">Delay</span><span class="sxs-lookup"><span data-stu-id="0a4e2-120">Delay</span></span>|<span data-ttu-id="0a4e2-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="0a4e2-121">xs:string</span></span>|<span data-ttu-id="0a4e2-122">재시도 사이의 지연입니다.</span><span class="sxs-lookup"><span data-stu-id="0a4e2-122">The delay between retries.</span></span>|  
|<span data-ttu-id="0a4e2-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="0a4e2-123">AppDomain</span></span>|<span data-ttu-id="0a4e2-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="0a4e2-124">xs:string</span></span>|<span data-ttu-id="0a4e2-125">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="0a4e2-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
