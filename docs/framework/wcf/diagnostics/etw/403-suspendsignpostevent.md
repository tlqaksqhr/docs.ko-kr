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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 10e745ded72caa493119d7e27a5c777b2185b96e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="403---suspendsignpostevent"></a><span data-ttu-id="8d91f-102">403 - SuspendSignpostEvent</span><span class="sxs-lookup"><span data-stu-id="8d91f-102">403 - SuspendSignpostEvent</span></span>
## <a name="properties"></a><span data-ttu-id="8d91f-103">속성</span><span class="sxs-lookup"><span data-stu-id="8d91f-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8d91f-104">ID</span><span class="sxs-lookup"><span data-stu-id="8d91f-104">ID</span></span>|<span data-ttu-id="8d91f-105">403</span><span class="sxs-lookup"><span data-stu-id="8d91f-105">403</span></span>|  
|<span data-ttu-id="8d91f-106">키워드</span><span class="sxs-lookup"><span data-stu-id="8d91f-106">Keywords</span></span>|<span data-ttu-id="8d91f-107">문제 해결</span><span class="sxs-lookup"><span data-stu-id="8d91f-107">Troubleshooting</span></span>|  
|<span data-ttu-id="8d91f-108">수준</span><span class="sxs-lookup"><span data-stu-id="8d91f-108">Level</span></span>|<span data-ttu-id="8d91f-109">정보</span><span class="sxs-lookup"><span data-stu-id="8d91f-109">Information</span></span>|  
|<span data-ttu-id="8d91f-110">채널</span><span class="sxs-lookup"><span data-stu-id="8d91f-110">Channel</span></span>|<span data-ttu-id="8d91f-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/분석</span><span class="sxs-lookup"><span data-stu-id="8d91f-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="8d91f-112">설명</span><span class="sxs-lookup"><span data-stu-id="8d91f-112">Description</span></span>  
 <span data-ttu-id="8d91f-113">이 이벤트는 종단 간 동작의 일시 중단을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="8d91f-113">This event marks the suspension of an end-to-end activity.</span></span> <span data-ttu-id="8d91f-114">여기에는 동작의 이름이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d91f-114">It contains the name of the activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="8d91f-115">메시지</span><span class="sxs-lookup"><span data-stu-id="8d91f-115">Message</span></span>  
 <span data-ttu-id="8d91f-116">동작 경계입니다.</span><span class="sxs-lookup"><span data-stu-id="8d91f-116">Activity boundary.</span></span>  
  
## <a name="details"></a><span data-ttu-id="8d91f-117">설명</span><span class="sxs-lookup"><span data-stu-id="8d91f-117">Details</span></span>  
  
|<span data-ttu-id="8d91f-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="8d91f-118">Data Item Name</span></span>|<span data-ttu-id="8d91f-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="8d91f-119">Data Item Type</span></span>|<span data-ttu-id="8d91f-120">설명</span><span class="sxs-lookup"><span data-stu-id="8d91f-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="8d91f-121">Extended Data</span><span class="sxs-lookup"><span data-stu-id="8d91f-121">Extended Data</span></span>|`xs:string`|<span data-ttu-id="8d91f-122">작업의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8d91f-122">The name of the activity.</span></span>|  
|<span data-ttu-id="8d91f-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="8d91f-123">AppDomain</span></span>|`xs:string`|<span data-ttu-id="8d91f-124">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="8d91f-124">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
