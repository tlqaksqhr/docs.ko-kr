---
title: 4209 - TimeoutOpeningSqlConnection
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f0e56518-9758-41dc-a760-50d1a10fba6e
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7528c967cbd88f00af448d6163c10e807f603bc6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="4209---timeoutopeningsqlconnection"></a><span data-ttu-id="88f85-102">4209 - TimeoutOpeningSqlConnection</span><span class="sxs-lookup"><span data-stu-id="88f85-102">4209 - TimeoutOpeningSqlConnection</span></span>
## <a name="properties"></a><span data-ttu-id="88f85-103">속성</span><span class="sxs-lookup"><span data-stu-id="88f85-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="88f85-104">ID</span><span class="sxs-lookup"><span data-stu-id="88f85-104">ID</span></span>|<span data-ttu-id="88f85-105">4209</span><span class="sxs-lookup"><span data-stu-id="88f85-105">4209</span></span>|  
|<span data-ttu-id="88f85-106">키워드</span><span class="sxs-lookup"><span data-stu-id="88f85-106">Keywords</span></span>|<span data-ttu-id="88f85-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="88f85-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="88f85-108">수준</span><span class="sxs-lookup"><span data-stu-id="88f85-108">Level</span></span>|<span data-ttu-id="88f85-109">오류</span><span class="sxs-lookup"><span data-stu-id="88f85-109">Error</span></span>|  
|<span data-ttu-id="88f85-110">채널</span><span class="sxs-lookup"><span data-stu-id="88f85-110">Channel</span></span>|<span data-ttu-id="88f85-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="88f85-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="88f85-112">설명</span><span class="sxs-lookup"><span data-stu-id="88f85-112">Description</span></span>  
 <span data-ttu-id="88f85-113">SQL 연결을 여는 동안 시간 초과가 발생했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="88f85-113">Indicates a timeout was encountered when trying to open a SQL connection.</span></span>  
  
## <a name="message"></a><span data-ttu-id="88f85-114">메시지</span><span class="sxs-lookup"><span data-stu-id="88f85-114">Message</span></span>  
 <span data-ttu-id="88f85-115">SQL 연결을 열려는 중 시간이 초과했습니다.</span><span class="sxs-lookup"><span data-stu-id="88f85-115">Timeout trying to open a SQL connection.</span></span> <span data-ttu-id="88f85-116">할당된 시간 제한인 %1 내에 작업을 완료하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="88f85-116">The operation did not complete within the allotted timeout of %1.</span></span> <span data-ttu-id="88f85-117">이 작업에 할당된 시간은 더 긴 시간 제한의 일부였을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88f85-117">The time allotted to this operation may have been a portion of a longer timeout.</span></span>  
  
## <a name="details"></a><span data-ttu-id="88f85-118">설명</span><span class="sxs-lookup"><span data-stu-id="88f85-118">Details</span></span>  
  
|<span data-ttu-id="88f85-119">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="88f85-119">Data Item Name</span></span>|<span data-ttu-id="88f85-120">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="88f85-120">Data Item Type</span></span>|<span data-ttu-id="88f85-121">설명</span><span class="sxs-lookup"><span data-stu-id="88f85-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="88f85-122">시간 제한</span><span class="sxs-lookup"><span data-stu-id="88f85-122">Timeout</span></span>|<span data-ttu-id="88f85-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="88f85-123">xs:string</span></span>|<span data-ttu-id="88f85-124">SQL 연결을 열기 위한 시간 제한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="88f85-124">The timeout value for opening the SQL connection.</span></span>|  
|<span data-ttu-id="88f85-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="88f85-125">AppDomain</span></span>|<span data-ttu-id="88f85-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="88f85-126">xs:string</span></span>|<span data-ttu-id="88f85-127">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="88f85-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
