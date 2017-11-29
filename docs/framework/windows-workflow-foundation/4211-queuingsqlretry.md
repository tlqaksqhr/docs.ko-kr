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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c318ee6509ce8b96a1e7e78a13f4aeb7c76dde6a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="4211---queuingsqlretry"></a><span data-ttu-id="2403d-102">4211 - QueuingSqlRetry</span><span class="sxs-lookup"><span data-stu-id="2403d-102">4211 - QueuingSqlRetry</span></span>
## <a name="properties"></a><span data-ttu-id="2403d-103">속성</span><span class="sxs-lookup"><span data-stu-id="2403d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2403d-104">ID</span><span class="sxs-lookup"><span data-stu-id="2403d-104">ID</span></span>|<span data-ttu-id="2403d-105">4211</span><span class="sxs-lookup"><span data-stu-id="2403d-105">4211</span></span>|  
|<span data-ttu-id="2403d-106">키워드</span><span class="sxs-lookup"><span data-stu-id="2403d-106">Keywords</span></span>|<span data-ttu-id="2403d-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="2403d-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="2403d-108">수준</span><span class="sxs-lookup"><span data-stu-id="2403d-108">Level</span></span>|<span data-ttu-id="2403d-109">경고</span><span class="sxs-lookup"><span data-stu-id="2403d-109">Warning</span></span>|  
|<span data-ttu-id="2403d-110">채널</span><span class="sxs-lookup"><span data-stu-id="2403d-110">Channel</span></span>|<span data-ttu-id="2403d-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="2403d-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2403d-112">설명</span><span class="sxs-lookup"><span data-stu-id="2403d-112">Description</span></span>  
 <span data-ttu-id="2403d-113">SQL 재시도를 큐에 넣고 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2403d-113">Indicates queuing SQL retry.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2403d-114">메시지</span><span class="sxs-lookup"><span data-stu-id="2403d-114">Message</span></span>  
 <span data-ttu-id="2403d-115">%1밀리초의 지연으로 SQL 재시도를 큐에 넣고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2403d-115">Queuing SQL retry with delay %1 milliseconds.</span></span>  
  
## <a name="details"></a><span data-ttu-id="2403d-116">설명</span><span class="sxs-lookup"><span data-stu-id="2403d-116">Details</span></span>  
  
|<span data-ttu-id="2403d-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="2403d-117">Data Item Name</span></span>|<span data-ttu-id="2403d-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="2403d-118">Data Item Type</span></span>|<span data-ttu-id="2403d-119">설명</span><span class="sxs-lookup"><span data-stu-id="2403d-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="2403d-120">Delay</span><span class="sxs-lookup"><span data-stu-id="2403d-120">Delay</span></span>|<span data-ttu-id="2403d-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="2403d-121">xs:string</span></span>|<span data-ttu-id="2403d-122">재시도 사이의 지연입니다.</span><span class="sxs-lookup"><span data-stu-id="2403d-122">The delay between retries.</span></span>|  
|<span data-ttu-id="2403d-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="2403d-123">AppDomain</span></span>|<span data-ttu-id="2403d-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="2403d-124">xs:string</span></span>|<span data-ttu-id="2403d-125">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="2403d-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
