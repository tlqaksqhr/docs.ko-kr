---
title: 499 - TransferEmitted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 07a26434-a7a0-40fc-b5d0-3520a04328ae
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 1a0bbe31095a59be4b091de6974ae0173753e240
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="499---transferemitted"></a><span data-ttu-id="74145-102">499 - TransferEmitted</span><span class="sxs-lookup"><span data-stu-id="74145-102">499 - TransferEmitted</span></span>
## <a name="properties"></a><span data-ttu-id="74145-103">속성</span><span class="sxs-lookup"><span data-stu-id="74145-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="74145-104">ID</span><span class="sxs-lookup"><span data-stu-id="74145-104">ID</span></span>|<span data-ttu-id="74145-105">499</span><span class="sxs-lookup"><span data-stu-id="74145-105">499</span></span>|  
|<span data-ttu-id="74145-106">키워드가</span><span class="sxs-lookup"><span data-stu-id="74145-106">Keywords</span></span>|<span data-ttu-id="74145-107">문제 해결, UserEvents, EndToEndMonitoring, ServiceModel, WFTracking, ServiceHost, WCFMessageLogging</span><span class="sxs-lookup"><span data-stu-id="74145-107">Troubleshooting, UserEvents, EndToEndMonitoring, ServiceModel, WFTracking, ServiceHost, WCFMessageLogging</span></span>|  
|<span data-ttu-id="74145-108">수준</span><span class="sxs-lookup"><span data-stu-id="74145-108">Level</span></span>|<span data-ttu-id="74145-109">LogAlways</span><span class="sxs-lookup"><span data-stu-id="74145-109">LogAlways</span></span>|  
|<span data-ttu-id="74145-110">채널</span><span class="sxs-lookup"><span data-stu-id="74145-110">Channel</span></span>|<span data-ttu-id="74145-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/분석</span><span class="sxs-lookup"><span data-stu-id="74145-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="74145-112">설명</span><span class="sxs-lookup"><span data-stu-id="74145-112">Description</span></span>  
 <span data-ttu-id="74145-113">전송 이벤트가 발생하는 경우 이 이벤트를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="74145-113">This event is emitted when the transfer event takes place.</span></span>  
  
## <a name="message"></a><span data-ttu-id="74145-114">메시지</span><span class="sxs-lookup"><span data-stu-id="74145-114">Message</span></span>  
 <span data-ttu-id="74145-115">전송 이벤트를 내보냈습니다.</span><span class="sxs-lookup"><span data-stu-id="74145-115">Transfer event emitted.</span></span>  
  
## <a name="details"></a><span data-ttu-id="74145-116">세부 정보</span><span class="sxs-lookup"><span data-stu-id="74145-116">Details</span></span>  
  
|<span data-ttu-id="74145-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="74145-117">Data Item Name</span></span>|<span data-ttu-id="74145-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="74145-118">Data Item Type</span></span>|<span data-ttu-id="74145-119">설명</span><span class="sxs-lookup"><span data-stu-id="74145-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="74145-120">HostReference</span><span class="sxs-lookup"><span data-stu-id="74145-120">HostReference</span></span>|`xs:string`|<span data-ttu-id="74145-121">웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="74145-121">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="74145-122">해당 형식으로 정의 됩니다 ' 웹 Site Name Application Virtual Path &#124; 서비스의 가상 경로 &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="74145-122">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="74145-123">예: ' 기본 웹 사이트/CalculatorApplication #124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="74145-123">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="74145-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="74145-124">AppDomain</span></span>|`xs:string`|<span data-ttu-id="74145-125">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="74145-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
