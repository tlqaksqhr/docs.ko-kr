---
title: 220 - MessageSentToTransport
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aef4e781-240b-45bc-bff8-400053037e71
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a84aa9ccbb51f2390376fc549660ca5e027969c1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="220---messagesenttotransport"></a><span data-ttu-id="96bcb-102">220 - MessageSentToTransport</span><span class="sxs-lookup"><span data-stu-id="96bcb-102">220 - MessageSentToTransport</span></span>
## <a name="properties"></a><span data-ttu-id="96bcb-103">속성</span><span class="sxs-lookup"><span data-stu-id="96bcb-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="96bcb-104">ID</span><span class="sxs-lookup"><span data-stu-id="96bcb-104">Id</span></span>|<span data-ttu-id="96bcb-105">220</span><span class="sxs-lookup"><span data-stu-id="96bcb-105">220</span></span>|  
|<span data-ttu-id="96bcb-106">키워드가</span><span class="sxs-lookup"><span data-stu-id="96bcb-106">Keywords</span></span>|<span data-ttu-id="96bcb-107">EndToEndMonitoring, 문제 해결, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="96bcb-107">EndToEndMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="96bcb-108">수준</span><span class="sxs-lookup"><span data-stu-id="96bcb-108">Level</span></span>|<span data-ttu-id="96bcb-109">정보</span><span class="sxs-lookup"><span data-stu-id="96bcb-109">Information</span></span>|  
|<span data-ttu-id="96bcb-110">채널</span><span class="sxs-lookup"><span data-stu-id="96bcb-110">Channel</span></span>|<span data-ttu-id="96bcb-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/분석</span><span class="sxs-lookup"><span data-stu-id="96bcb-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="96bcb-112">설명</span><span class="sxs-lookup"><span data-stu-id="96bcb-112">Description</span></span>  
 <span data-ttu-id="96bcb-113">이 이벤트는 서비스 모델이 전송에 메시지를 보낼 때 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="96bcb-113">This event is emitted when the Service Model sends a message to the transport.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="96bcb-114">단방향 전송의 경우에는 이 이벤트가 내보내지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="96bcb-114">This event will not be emitted for one-way transports.</span></span>  
  
## <a name="message"></a><span data-ttu-id="96bcb-115">메시지</span><span class="sxs-lookup"><span data-stu-id="96bcb-115">Message</span></span>  
 <span data-ttu-id="96bcb-116">디스패처가 전송에 메시지를 보냈습니다.</span><span class="sxs-lookup"><span data-stu-id="96bcb-116">The Dispatcher sent a message to the transport.</span></span> <span data-ttu-id="96bcb-117">Correlation ID == '%1'.</span><span class="sxs-lookup"><span data-stu-id="96bcb-117">Correlation ID == '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="96bcb-118">세부 정보</span><span class="sxs-lookup"><span data-stu-id="96bcb-118">Details</span></span>  
  
|<span data-ttu-id="96bcb-119">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="96bcb-119">Data Item Name</span></span>|<span data-ttu-id="96bcb-120">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="96bcb-120">Data Item Type</span></span>|<span data-ttu-id="96bcb-121">설명</span><span class="sxs-lookup"><span data-stu-id="96bcb-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="96bcb-122">Correlation ID</span><span class="sxs-lookup"><span data-stu-id="96bcb-122">Correlation ID</span></span>|`xs:GUID`|<span data-ttu-id="96bcb-123">서비스 또는 클라이언트의 `MessageSentToTransport` 이벤트를 다른 끝에 있는 해당 `MessageReceivedFromTransport`에 상호 연결하는 데 사용되는 동작 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="96bcb-123">The activity ID used to correlate a `MessageSentToTransport` event from a service or client to its corresponding `MessageReceivedFromTransport` on the other end.</span></span>|  
|<span data-ttu-id="96bcb-124">HostReference</span><span class="sxs-lookup"><span data-stu-id="96bcb-124">HostReference</span></span>|`xs:string`|<span data-ttu-id="96bcb-125">웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="96bcb-125">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="96bcb-126">해당 형식으로 정의 됩니다 ' 웹 Site Name Application Virtual Path &#124; 서비스의 가상 경로 &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="96bcb-126">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="96bcb-127">예: ' 기본 웹 사이트/CalculatorApplication #124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="96bcb-127">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="96bcb-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="96bcb-128">AppDomain</span></span>|`xs:string`|<span data-ttu-id="96bcb-129">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="96bcb-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
