---
title: 214 - OperationCompleted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a6287eef-023f-4816-813c-1802c82366df
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c6ef1eb398a0146e619cbcb85fe2761306aba4fc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="214---operationcompleted"></a><span data-ttu-id="b1f72-102">214 - OperationCompleted</span><span class="sxs-lookup"><span data-stu-id="b1f72-102">214 - OperationCompleted</span></span>
## <a name="properties"></a><span data-ttu-id="b1f72-103">속성</span><span class="sxs-lookup"><span data-stu-id="b1f72-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b1f72-104">ID</span><span class="sxs-lookup"><span data-stu-id="b1f72-104">ID</span></span>|<span data-ttu-id="b1f72-105">214</span><span class="sxs-lookup"><span data-stu-id="b1f72-105">214</span></span>|  
|<span data-ttu-id="b1f72-106">키워드가</span><span class="sxs-lookup"><span data-stu-id="b1f72-106">Keywords</span></span>|<span data-ttu-id="b1f72-107">HealthMonitoring, EndToEndMonitoring, 문제 해결, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="b1f72-107">HealthMonitoring, EndToEndMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="b1f72-108">수준</span><span class="sxs-lookup"><span data-stu-id="b1f72-108">Level</span></span>|<span data-ttu-id="b1f72-109">정보</span><span class="sxs-lookup"><span data-stu-id="b1f72-109">Information</span></span>|  
|<span data-ttu-id="b1f72-110">채널</span><span class="sxs-lookup"><span data-stu-id="b1f72-110">Channel</span></span>|<span data-ttu-id="b1f72-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/분석</span><span class="sxs-lookup"><span data-stu-id="b1f72-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b1f72-112">설명</span><span class="sxs-lookup"><span data-stu-id="b1f72-112">Description</span></span>  
 <span data-ttu-id="b1f72-113">이 이벤트는 서비스 모델의 기본 `OperationInvoker`가 메서드에서 예외를 throw하지 않고 메서드에 대한 호출을 완료하면 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="b1f72-113">This event is emitted when the Service Model's default `OperationInvoker` has completed a call to a method without that method throwing an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b1f72-114">메시지</span><span class="sxs-lookup"><span data-stu-id="b1f72-114">Message</span></span>  
 <span data-ttu-id="b1f72-115">OperationInvoker가 '%1' 메서드에 대한 호출을 완료했습니다.</span><span class="sxs-lookup"><span data-stu-id="b1f72-115">An OperationInvoker completed the call to the '%1' method.</span></span> <span data-ttu-id="b1f72-116">메서드 호출 기간은 '%2'밀리초입니다.</span><span class="sxs-lookup"><span data-stu-id="b1f72-116">The method call duration was '%2' ms.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b1f72-117">세부 정보</span><span class="sxs-lookup"><span data-stu-id="b1f72-117">Details</span></span>  
  
|<span data-ttu-id="b1f72-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="b1f72-118">Data Item Name</span></span>|<span data-ttu-id="b1f72-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="b1f72-119">Data Item Type</span></span>|<span data-ttu-id="b1f72-120">설명</span><span class="sxs-lookup"><span data-stu-id="b1f72-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b1f72-121">메서드 이름</span><span class="sxs-lookup"><span data-stu-id="b1f72-121">Method Name</span></span>|`xs:string`|<span data-ttu-id="b1f72-122">`OperationInvoker`의 호출을 받은 메서드의 CLR 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b1f72-122">The CLR name of the method that was invoked by the `OperationInvoker`.</span></span>|  
|<span data-ttu-id="b1f72-123">기간</span><span class="sxs-lookup"><span data-stu-id="b1f72-123">Duration</span></span>|`xs:long`|<span data-ttu-id="b1f72-124">`OperationInvoker`가 메서드를 호출하는 데 걸린 시간(밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="b1f72-124">The time, in milliseconds, that it took the `OperationInvoker` to invoke the method.</span></span>|  
|<span data-ttu-id="b1f72-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="b1f72-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="b1f72-126">웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="b1f72-126">For web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="b1f72-127">해당 형식으로 정의 됩니다 ' 웹 Site Name Application Virtual Path &#124; 서비스의 가상 경로 &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="b1f72-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="b1f72-128">예: ' 기본 웹 사이트/CalculatorApplication #124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="b1f72-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="b1f72-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b1f72-129">AppDomain</span></span>|`xs:string`|<span data-ttu-id="b1f72-130">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="b1f72-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
