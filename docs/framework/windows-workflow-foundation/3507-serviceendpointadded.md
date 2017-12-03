---
title: 3507 - ServiceEndpointAdded
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c068fc0e-07ee-4551-9824-ea7216e1fe37
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 68689e1694ac594467e11fabe44773b766af2b25
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="3507---serviceendpointadded"></a><span data-ttu-id="20e51-102">3507 - ServiceEndpointAdded</span><span class="sxs-lookup"><span data-stu-id="20e51-102">3507 - ServiceEndpointAdded</span></span>
## <a name="properties"></a><span data-ttu-id="20e51-103">속성</span><span class="sxs-lookup"><span data-stu-id="20e51-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="20e51-104">ID</span><span class="sxs-lookup"><span data-stu-id="20e51-104">ID</span></span>|<span data-ttu-id="20e51-105">3507</span><span class="sxs-lookup"><span data-stu-id="20e51-105">3507</span></span>|  
|<span data-ttu-id="20e51-106">키워드</span><span class="sxs-lookup"><span data-stu-id="20e51-106">Keywords</span></span>|<span data-ttu-id="20e51-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="20e51-107">WFServices</span></span>|  
|<span data-ttu-id="20e51-108">수준</span><span class="sxs-lookup"><span data-stu-id="20e51-108">Level</span></span>|<span data-ttu-id="20e51-109">정보</span><span class="sxs-lookup"><span data-stu-id="20e51-109">Information</span></span>|  
|<span data-ttu-id="20e51-110">채널</span><span class="sxs-lookup"><span data-stu-id="20e51-110">Channel</span></span>|<span data-ttu-id="20e51-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/분석</span><span class="sxs-lookup"><span data-stu-id="20e51-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="20e51-112">설명</span><span class="sxs-lookup"><span data-stu-id="20e51-112">Description</span></span>  
 <span data-ttu-id="20e51-113">서비스 끝점이 추가되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="20e51-113">Indicates a service endpoint has been added.</span></span>  
  
## <a name="message"></a><span data-ttu-id="20e51-114">메시지</span><span class="sxs-lookup"><span data-stu-id="20e51-114">Message</span></span>  
 <span data-ttu-id="20e51-115">주소 '%1', 바인딩 '%2' 및 계약 '%3'에 대해 서비스 끝점이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="20e51-115">A service endpoint has been added for address '%1', binding '%2', and contract '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="20e51-116">설명</span><span class="sxs-lookup"><span data-stu-id="20e51-116">Details</span></span>  
  
|<span data-ttu-id="20e51-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="20e51-117">Data Item Name</span></span>|<span data-ttu-id="20e51-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="20e51-118">Data Item Type</span></span>|<span data-ttu-id="20e51-119">설명</span><span class="sxs-lookup"><span data-stu-id="20e51-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="20e51-120">Address</span><span class="sxs-lookup"><span data-stu-id="20e51-120">Address</span></span>|<span data-ttu-id="20e51-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="20e51-121">xs:string</span></span>|<span data-ttu-id="20e51-122">끝점의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="20e51-122">The address of the endpoint.</span></span>|  
|<span data-ttu-id="20e51-123">바인딩</span><span class="sxs-lookup"><span data-stu-id="20e51-123">Binding</span></span>|<span data-ttu-id="20e51-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="20e51-124">xs:string</span></span>|<span data-ttu-id="20e51-125">끝점의 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="20e51-125">The binding of the endpoint.</span></span>|  
|<span data-ttu-id="20e51-126">계약</span><span class="sxs-lookup"><span data-stu-id="20e51-126">Contract</span></span>|<span data-ttu-id="20e51-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="20e51-127">xs:string</span></span>|<span data-ttu-id="20e51-128">끝점의 계약입니다.</span><span class="sxs-lookup"><span data-stu-id="20e51-128">The contract of the endpoint.</span></span>|  
|<span data-ttu-id="20e51-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="20e51-129">AppDomain</span></span>|<span data-ttu-id="20e51-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="20e51-130">xs:string</span></span>|<span data-ttu-id="20e51-131">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="20e51-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
