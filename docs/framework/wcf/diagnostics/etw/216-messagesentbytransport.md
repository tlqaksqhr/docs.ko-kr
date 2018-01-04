---
title: 216 - MessageSentByTransport
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 150c3167-4154-4225-8d94-57cc94341233
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1ad2b32b8d1386f6cc0754070cba2b1a556219b5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="216---messagesentbytransport"></a><span data-ttu-id="beaad-102">216 - MessageSentByTransport</span><span class="sxs-lookup"><span data-stu-id="beaad-102">216 - MessageSentByTransport</span></span>
## <a name="properties"></a><span data-ttu-id="beaad-103">속성</span><span class="sxs-lookup"><span data-stu-id="beaad-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="beaad-104">ID</span><span class="sxs-lookup"><span data-stu-id="beaad-104">ID</span></span>|<span data-ttu-id="beaad-105">216</span><span class="sxs-lookup"><span data-stu-id="beaad-105">216</span></span>|  
|<span data-ttu-id="beaad-106">키워드가</span><span class="sxs-lookup"><span data-stu-id="beaad-106">Keywords</span></span>|<span data-ttu-id="beaad-107">문제 해결, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="beaad-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="beaad-108">수준</span><span class="sxs-lookup"><span data-stu-id="beaad-108">Level</span></span>|<span data-ttu-id="beaad-109">정보</span><span class="sxs-lookup"><span data-stu-id="beaad-109">Information</span></span>|  
|<span data-ttu-id="beaad-110">채널</span><span class="sxs-lookup"><span data-stu-id="beaad-110">Channel</span></span>|<span data-ttu-id="beaad-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/분석</span><span class="sxs-lookup"><span data-stu-id="beaad-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="beaad-112">설명</span><span class="sxs-lookup"><span data-stu-id="beaad-112">Description</span></span>  
 <span data-ttu-id="beaad-113">이 이벤트는 TCP 기반 전송이 메시지를 보낼 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="beaad-113">This event occurs when a TCP-based transport sends a message.</span></span> <span data-ttu-id="beaad-114">전송 수준에서는 단일 작업에 대해 클라이언트와 서비스 간에 여러 메시지가 교환될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="beaad-114">Note that at the transport level multiple messages can be exchanged between clients and services for a single operation.</span></span> <span data-ttu-id="beaad-115">이는 보안과 같은 인프라 동작 때문일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="beaad-115">This may be due to infrastructure behavior, security being a good example.</span></span> <span data-ttu-id="beaad-116">따라서 수 **MessageSentByTransport** 발생 하는 이벤트는 서비스의 바인딩과 해당 구성에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="beaad-116">Therefore, the number of **MessageSentByTransport** events that are emitted vary based on your service's binding and its configuration.</span></span>  
  
## <a name="message"></a><span data-ttu-id="beaad-117">메시지</span><span class="sxs-lookup"><span data-stu-id="beaad-117">Message</span></span>  
 <span data-ttu-id="beaad-118">전송이 '%1'에 메시지를 보냈습니다.</span><span class="sxs-lookup"><span data-stu-id="beaad-118">The transport sent a message to '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="beaad-119">설명</span><span class="sxs-lookup"><span data-stu-id="beaad-119">Details</span></span>  
  
|<span data-ttu-id="beaad-120">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="beaad-120">Data Item Name</span></span>|<span data-ttu-id="beaad-121">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="beaad-121">Data Item Type</span></span>|<span data-ttu-id="beaad-122">설명</span><span class="sxs-lookup"><span data-stu-id="beaad-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="beaad-123">DestinationAddress</span><span class="sxs-lookup"><span data-stu-id="beaad-123">DestinationAddress</span></span>|`xs:string`|<span data-ttu-id="beaad-124">요청 메시지가 전달된 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="beaad-124">The address that the request message was sent to.</span></span>|  
|<span data-ttu-id="beaad-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="beaad-125">HostReference</span></span>|<span data-ttu-id="beaad-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="beaad-126">xs:string</span></span>|<span data-ttu-id="beaad-127">웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="beaad-127">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="beaad-128">해당 형식으로 정의 됩니다 ' 웹 Site Name Application Virtual Path &#124; 서비스의 가상 경로 &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="beaad-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="beaad-129">예: ' 기본 웹 사이트/CalculatorApplication #124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="beaad-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="beaad-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="beaad-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="beaad-131">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="beaad-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
