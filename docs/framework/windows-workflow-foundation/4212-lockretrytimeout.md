---
title: 4212 - LockRetryTimeout
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d4ad415a-9871-49fc-85b8-8ee2ea149b1d
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: abe1f560cc984551f069a75873a7e5545aec03cf
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="4212---lockretrytimeout"></a><span data-ttu-id="80a36-102">4212 - LockRetryTimeout</span><span class="sxs-lookup"><span data-stu-id="80a36-102">4212 - LockRetryTimeout</span></span>
## <a name="properties"></a><span data-ttu-id="80a36-103">속성</span><span class="sxs-lookup"><span data-stu-id="80a36-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="80a36-104">ID</span><span class="sxs-lookup"><span data-stu-id="80a36-104">ID</span></span>|<span data-ttu-id="80a36-105">4212</span><span class="sxs-lookup"><span data-stu-id="80a36-105">4212</span></span>|  
|<span data-ttu-id="80a36-106">키워드</span><span class="sxs-lookup"><span data-stu-id="80a36-106">Keywords</span></span>|<span data-ttu-id="80a36-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="80a36-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="80a36-108">수준</span><span class="sxs-lookup"><span data-stu-id="80a36-108">Level</span></span>|<span data-ttu-id="80a36-109">경고</span><span class="sxs-lookup"><span data-stu-id="80a36-109">Warning</span></span>|  
|<span data-ttu-id="80a36-110">채널</span><span class="sxs-lookup"><span data-stu-id="80a36-110">Channel</span></span>|<span data-ttu-id="80a36-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="80a36-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="80a36-112">설명</span><span class="sxs-lookup"><span data-stu-id="80a36-112">Description</span></span>  
 <span data-ttu-id="80a36-113">SQL 공급자에서 인스턴스 잠금을 얻으려는 중 시간 초과가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="80a36-113">SQL provider encountered a timeout trying to acquire the instance lock.</span></span>  
  
## <a name="message"></a><span data-ttu-id="80a36-114">메시지</span><span class="sxs-lookup"><span data-stu-id="80a36-114">Message</span></span>  
 <span data-ttu-id="80a36-115">인스턴스 잠금을 얻으려는 중 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="80a36-115">Timeout trying to acquire the instance lock.</span></span>  <span data-ttu-id="80a36-116">할당된 시간 제한인 %1 내에 작업을 완료하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="80a36-116">The operation did not complete within the allotted timeout of %1.</span></span> <span data-ttu-id="80a36-117">이 작업에 할당된 시간은 더 긴 시간 제한의 일부였을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="80a36-117">The time allotted to this operation may have been a portion of a longer timeout.</span></span>  
  
## <a name="details"></a><span data-ttu-id="80a36-118">설명</span><span class="sxs-lookup"><span data-stu-id="80a36-118">Details</span></span>  
  
|<span data-ttu-id="80a36-119">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="80a36-119">Data Item Name</span></span>|<span data-ttu-id="80a36-120">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="80a36-120">Data Item Type</span></span>|<span data-ttu-id="80a36-121">설명</span><span class="sxs-lookup"><span data-stu-id="80a36-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="80a36-122">Delay</span><span class="sxs-lookup"><span data-stu-id="80a36-122">Delay</span></span>|<span data-ttu-id="80a36-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="80a36-123">xs:string</span></span>|<span data-ttu-id="80a36-124">재시도 사이의 지연입니다.</span><span class="sxs-lookup"><span data-stu-id="80a36-124">The delay between retries.</span></span>|  
|<span data-ttu-id="80a36-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="80a36-125">AppDomain</span></span>|<span data-ttu-id="80a36-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="80a36-126">xs:string</span></span>|<span data-ttu-id="80a36-127">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="80a36-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
