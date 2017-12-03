---
title: 222 - OperationFailed
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6b530ded-8f20-4d78-8bfe-1875276df6ba
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5d56766dd32acf1ef71f7c06a5c3c94cc7510070
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="222---operationfailed"></a><span data-ttu-id="f0ff0-102">222 - OperationFailed</span><span class="sxs-lookup"><span data-stu-id="f0ff0-102">222 - OperationFailed</span></span>
## <a name="properties"></a><span data-ttu-id="f0ff0-103">속성</span><span class="sxs-lookup"><span data-stu-id="f0ff0-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f0ff0-104">ID</span><span class="sxs-lookup"><span data-stu-id="f0ff0-104">ID</span></span>|<span data-ttu-id="f0ff0-105">222</span><span class="sxs-lookup"><span data-stu-id="f0ff0-105">222</span></span>|  
|<span data-ttu-id="f0ff0-106">키워드가</span><span class="sxs-lookup"><span data-stu-id="f0ff0-106">Keywords</span></span>|<span data-ttu-id="f0ff0-107">EndToEndMonitoring, HealthMonitoring, 문제 해결, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="f0ff0-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="f0ff0-108">수준</span><span class="sxs-lookup"><span data-stu-id="f0ff0-108">Level</span></span>|<span data-ttu-id="f0ff0-109">경고</span><span class="sxs-lookup"><span data-stu-id="f0ff0-109">Warning</span></span>|  
|<span data-ttu-id="f0ff0-110">채널</span><span class="sxs-lookup"><span data-stu-id="f0ff0-110">Channel</span></span>|<span data-ttu-id="f0ff0-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/분석</span><span class="sxs-lookup"><span data-stu-id="f0ff0-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f0ff0-112">설명</span><span class="sxs-lookup"><span data-stu-id="f0ff0-112">Description</span></span>  
 <span data-ttu-id="f0ff0-113">이 이벤트는 서비스 모델의 기본 `OperationInvoker`에서 해당 메서드를 호출하는 동안 예외가 발생하면 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="f0ff0-113">This event is emitted when the Service Model's default `OperationInvoker` has encountered an exception while invoking its method.</span></span> <span data-ttu-id="f0ff0-114">`FaultException`에서 파생되는 예외가 발생할 경우에는 이 이벤트가 내보내지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ff0-114">Note that exceptions that derive from `FaultException` cause this event to not be emitted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f0ff0-115">메시지</span><span class="sxs-lookup"><span data-stu-id="f0ff0-115">Message</span></span>  
 <span data-ttu-id="f0ff0-116">OperationInvoker의 호출을 받은 '%1' 메서드에서 처리되지 않은 예외가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="f0ff0-116">The '%1' method threw an unhandled exception when invoked by the OperationInvoker.</span></span> <span data-ttu-id="f0ff0-117">메서드 호출 기간은 '%2'밀리초입니다.</span><span class="sxs-lookup"><span data-stu-id="f0ff0-117">The method call duration was '%2' ms.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f0ff0-118">세부 정보</span><span class="sxs-lookup"><span data-stu-id="f0ff0-118">Details</span></span>  
  
|<span data-ttu-id="f0ff0-119">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="f0ff0-119">Data Item Name</span></span>|<span data-ttu-id="f0ff0-120">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="f0ff0-120">Data Item Type</span></span>|<span data-ttu-id="f0ff0-121">설명</span><span class="sxs-lookup"><span data-stu-id="f0ff0-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f0ff0-122">메서드 이름</span><span class="sxs-lookup"><span data-stu-id="f0ff0-122">Method Name</span></span>|`xs:string`|<span data-ttu-id="f0ff0-123">`OperationInvoker`의 호출을 받은 메서드의 CLR 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f0ff0-123">The CLR name of the method that was invoked by the `OperationInvoker`.</span></span>|  
|<span data-ttu-id="f0ff0-124">기간</span><span class="sxs-lookup"><span data-stu-id="f0ff0-124">Duration</span></span>|`xs:long`|<span data-ttu-id="f0ff0-125">`OperationInvoker`가 메서드를 호출하는 데 걸린 시간(밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="f0ff0-125">The time, in milliseconds, that it took the `OperationInvoker` to invoke the method.</span></span>|  
|<span data-ttu-id="f0ff0-126">HostReference</span><span class="sxs-lookup"><span data-stu-id="f0ff0-126">HostReference</span></span>|`xs:string`|<span data-ttu-id="f0ff0-127">웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="f0ff0-127">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="f0ff0-128">해당 형식으로 정의 됩니다 ' 웹 Site Name Application Virtual Path &#124; 서비스의 가상 경로 &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="f0ff0-128">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="f0ff0-129">예: ' 기본 웹 사이트/CalculatorApplication #124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="f0ff0-129">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="f0ff0-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f0ff0-130">AppDomain</span></span>|`xs:string`|<span data-ttu-id="f0ff0-131">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="f0ff0-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
