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
ms.workload: dotnet
ms.openlocfilehash: ee1daab843ad0a2161d13b86bcd657b7236ddaa6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="403---suspendsignpostevent"></a><span data-ttu-id="b78b3-102">403 - SuspendSignpostEvent</span><span class="sxs-lookup"><span data-stu-id="b78b3-102">403 - SuspendSignpostEvent</span></span>
## <a name="properties"></a><span data-ttu-id="b78b3-103">속성</span><span class="sxs-lookup"><span data-stu-id="b78b3-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b78b3-104">ID</span><span class="sxs-lookup"><span data-stu-id="b78b3-104">ID</span></span>|<span data-ttu-id="b78b3-105">403</span><span class="sxs-lookup"><span data-stu-id="b78b3-105">403</span></span>|  
|<span data-ttu-id="b78b3-106">키워드</span><span class="sxs-lookup"><span data-stu-id="b78b3-106">Keywords</span></span>|<span data-ttu-id="b78b3-107">문제 해결</span><span class="sxs-lookup"><span data-stu-id="b78b3-107">Troubleshooting</span></span>|  
|<span data-ttu-id="b78b3-108">수준</span><span class="sxs-lookup"><span data-stu-id="b78b3-108">Level</span></span>|<span data-ttu-id="b78b3-109">정보</span><span class="sxs-lookup"><span data-stu-id="b78b3-109">Information</span></span>|  
|<span data-ttu-id="b78b3-110">채널</span><span class="sxs-lookup"><span data-stu-id="b78b3-110">Channel</span></span>|<span data-ttu-id="b78b3-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/분석</span><span class="sxs-lookup"><span data-stu-id="b78b3-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b78b3-112">설명</span><span class="sxs-lookup"><span data-stu-id="b78b3-112">Description</span></span>  
 <span data-ttu-id="b78b3-113">이 이벤트는 종단 간 동작의 일시 중단을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="b78b3-113">This event marks the suspension of an end-to-end activity.</span></span> <span data-ttu-id="b78b3-114">여기에는 동작의 이름이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b78b3-114">It contains the name of the activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b78b3-115">메시지</span><span class="sxs-lookup"><span data-stu-id="b78b3-115">Message</span></span>  
 <span data-ttu-id="b78b3-116">동작 경계입니다.</span><span class="sxs-lookup"><span data-stu-id="b78b3-116">Activity boundary.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b78b3-117">설명</span><span class="sxs-lookup"><span data-stu-id="b78b3-117">Details</span></span>  
  
|<span data-ttu-id="b78b3-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="b78b3-118">Data Item Name</span></span>|<span data-ttu-id="b78b3-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="b78b3-119">Data Item Type</span></span>|<span data-ttu-id="b78b3-120">설명</span><span class="sxs-lookup"><span data-stu-id="b78b3-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b78b3-121">Extended Data</span><span class="sxs-lookup"><span data-stu-id="b78b3-121">Extended Data</span></span>|`xs:string`|<span data-ttu-id="b78b3-122">작업의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b78b3-122">The name of the activity.</span></span>|  
|<span data-ttu-id="b78b3-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b78b3-123">AppDomain</span></span>|`xs:string`|<span data-ttu-id="b78b3-124">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="b78b3-124">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
