---
title: 3503 - DuplicateCorrelationQuery
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b857f8e6-ce4d-4da4-bc9d-6cd63fa558a4
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 997bdf4423364e9b5361635820849a6bde9e8960
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="3503---duplicatecorrelationquery"></a><span data-ttu-id="a58e0-102">3503 - DuplicateCorrelationQuery</span><span class="sxs-lookup"><span data-stu-id="a58e0-102">3503 - DuplicateCorrelationQuery</span></span>
## <a name="properties"></a><span data-ttu-id="a58e0-103">속성</span><span class="sxs-lookup"><span data-stu-id="a58e0-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a58e0-104">ID</span><span class="sxs-lookup"><span data-stu-id="a58e0-104">ID</span></span>|<span data-ttu-id="a58e0-105">3503</span><span class="sxs-lookup"><span data-stu-id="a58e0-105">3503</span></span>|  
|<span data-ttu-id="a58e0-106">키워드</span><span class="sxs-lookup"><span data-stu-id="a58e0-106">Keywords</span></span>|<span data-ttu-id="a58e0-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="a58e0-107">WFServices</span></span>|  
|<span data-ttu-id="a58e0-108">수준</span><span class="sxs-lookup"><span data-stu-id="a58e0-108">Level</span></span>|<span data-ttu-id="a58e0-109">경고</span><span class="sxs-lookup"><span data-stu-id="a58e0-109">Warning</span></span>|  
|<span data-ttu-id="a58e0-110">채널</span><span class="sxs-lookup"><span data-stu-id="a58e0-110">Channel</span></span>|<span data-ttu-id="a58e0-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/분석</span><span class="sxs-lookup"><span data-stu-id="a58e0-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a58e0-112">설명</span><span class="sxs-lookup"><span data-stu-id="a58e0-112">Description</span></span>  
 <span data-ttu-id="a58e0-113">중복 CorrelationQuery를 찾았음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a58e0-113">Indicates a duplicate CorrelationQuery was found.</span></span> <span data-ttu-id="a58e0-114">중복 쿼리는 상관 관계를 계산할 때 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a58e0-114">The duplicate query will not be used when calculating correlation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a58e0-115">메시지</span><span class="sxs-lookup"><span data-stu-id="a58e0-115">Message</span></span>  
 <span data-ttu-id="a58e0-116">Where='%1'인 중복 CorrelationQuery가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a58e0-116">A duplicate CorrelationQuery was found with Where='%1'.</span></span> <span data-ttu-id="a58e0-117">이 중복 쿼리는 상관 관계를 계산할 때 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a58e0-117">This duplicate query will not be used when calculating correlation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a58e0-118">설명</span><span class="sxs-lookup"><span data-stu-id="a58e0-118">Details</span></span>  
  
|<span data-ttu-id="a58e0-119">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="a58e0-119">Data Item Name</span></span>|<span data-ttu-id="a58e0-120">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="a58e0-120">Data Item Type</span></span>|<span data-ttu-id="a58e0-121">설명</span><span class="sxs-lookup"><span data-stu-id="a58e0-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a58e0-122">Where</span><span class="sxs-lookup"><span data-stu-id="a58e0-122">Where</span></span>|<span data-ttu-id="a58e0-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="a58e0-123">xs:string</span></span>|<span data-ttu-id="a58e0-124">상관 관계 쿼리의 Where 부분입니다.</span><span class="sxs-lookup"><span data-stu-id="a58e0-124">The Where portion of the correlation query.</span></span>|  
|<span data-ttu-id="a58e0-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="a58e0-125">AppDomain</span></span>|<span data-ttu-id="a58e0-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="a58e0-126">xs:string</span></span>|<span data-ttu-id="a58e0-127">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="a58e0-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
