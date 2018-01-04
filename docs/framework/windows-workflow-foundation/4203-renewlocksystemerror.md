---
title: 4203 - RenewLockSystemError
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6ec9ec6f-4ae2-45cf-b99b-02cdb9dc9ec9
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8fabe6f2c023bf9b997d2a4e19b4a3755c93f408
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="4203---renewlocksystemerror"></a><span data-ttu-id="56ca1-102">4203 - RenewLockSystemError</span><span class="sxs-lookup"><span data-stu-id="56ca1-102">4203 - RenewLockSystemError</span></span>
## <a name="properties"></a><span data-ttu-id="56ca1-103">속성</span><span class="sxs-lookup"><span data-stu-id="56ca1-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="56ca1-104">ID</span><span class="sxs-lookup"><span data-stu-id="56ca1-104">ID</span></span>|<span data-ttu-id="56ca1-105">4203</span><span class="sxs-lookup"><span data-stu-id="56ca1-105">4203</span></span>|  
|<span data-ttu-id="56ca1-106">키워드</span><span class="sxs-lookup"><span data-stu-id="56ca1-106">Keywords</span></span>|<span data-ttu-id="56ca1-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="56ca1-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="56ca1-108">수준</span><span class="sxs-lookup"><span data-stu-id="56ca1-108">Level</span></span>|<span data-ttu-id="56ca1-109">오류</span><span class="sxs-lookup"><span data-stu-id="56ca1-109">Error</span></span>|  
|<span data-ttu-id="56ca1-110">채널</span><span class="sxs-lookup"><span data-stu-id="56ca1-110">Channel</span></span>|<span data-ttu-id="56ca1-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="56ca1-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="56ca1-112">설명</span><span class="sxs-lookup"><span data-stu-id="56ca1-112">Description</span></span>  
 <span data-ttu-id="56ca1-113">잠금 만료가 이미 지났거나 잠금 소유자가 삭제되었기 때문에 SQL 공급자가 잠금 만료를 연장하지 못했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="56ca1-113">Indicates SQL provider has failed to extend lock expiration due to either lock expiration already passed or the lock owner was deleted.</span></span> <span data-ttu-id="56ca1-114">SqlWorkflowInstanceStore가 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="56ca1-114">The SqlWorkflowInstanceStore will be aborted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="56ca1-115">메시지</span><span class="sxs-lookup"><span data-stu-id="56ca1-115">Message</span></span>  
 <span data-ttu-id="56ca1-116">잠금 만료를 연장하지 못했습니다. 잠금 만료가 이미 지났거나 잠금 소유자가 삭제되었습니다.</span><span class="sxs-lookup"><span data-stu-id="56ca1-116">Failed to extend lock expiration, lock expiration already passed or the lock owner was deleted.</span></span> <span data-ttu-id="56ca1-117">SqlWorkflowInstanceStore를 중단하는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="56ca1-117">Aborting SqlWorkflowInstanceStore.</span></span>  
  
## <a name="details"></a><span data-ttu-id="56ca1-118">설명</span><span class="sxs-lookup"><span data-stu-id="56ca1-118">Details</span></span>  
  
|<span data-ttu-id="56ca1-119">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="56ca1-119">Data Item Name</span></span>|<span data-ttu-id="56ca1-120">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="56ca1-120">Data Item Type</span></span>|<span data-ttu-id="56ca1-121">설명</span><span class="sxs-lookup"><span data-stu-id="56ca1-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="56ca1-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="56ca1-122">AppDomain</span></span>|<span data-ttu-id="56ca1-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="56ca1-123">xs:string</span></span>|<span data-ttu-id="56ca1-124">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="56ca1-124">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
