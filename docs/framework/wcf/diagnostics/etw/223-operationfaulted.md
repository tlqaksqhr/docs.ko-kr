---
title: 223 - OperationFaulted
ms.date: 03/30/2017
ms.assetid: 2f7d89d7-3a6a-40fe-9610-5424eb6bbf61
ms.openlocfilehash: cf4a455d80a1a0ac09e99bad967c1feba3653842
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33459421"
---
# <a name="223---operationfaulted"></a><span data-ttu-id="5ac56-102">223 - OperationFaulted</span><span class="sxs-lookup"><span data-stu-id="5ac56-102">223 - OperationFaulted</span></span>
## <a name="properties"></a><span data-ttu-id="5ac56-103">속성</span><span class="sxs-lookup"><span data-stu-id="5ac56-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5ac56-104">ID</span><span class="sxs-lookup"><span data-stu-id="5ac56-104">ID</span></span>|<span data-ttu-id="5ac56-105">223</span><span class="sxs-lookup"><span data-stu-id="5ac56-105">223</span></span>|  
|<span data-ttu-id="5ac56-106">키워드</span><span class="sxs-lookup"><span data-stu-id="5ac56-106">Keywords</span></span>|<span data-ttu-id="5ac56-107">EndToEndMonitoring, HealthMonitoring, 문제 해결, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="5ac56-107">EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="5ac56-108">수준</span><span class="sxs-lookup"><span data-stu-id="5ac56-108">Level</span></span>|<span data-ttu-id="5ac56-109">경고</span><span class="sxs-lookup"><span data-stu-id="5ac56-109">Warning</span></span>|  
|<span data-ttu-id="5ac56-110">채널</span><span class="sxs-lookup"><span data-stu-id="5ac56-110">Channel</span></span>|<span data-ttu-id="5ac56-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/분석</span><span class="sxs-lookup"><span data-stu-id="5ac56-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5ac56-112">설명</span><span class="sxs-lookup"><span data-stu-id="5ac56-112">Description</span></span>  
 <span data-ttu-id="5ac56-113">이 이벤트는 서비스 모델의 기본 `OperationInvoker`에서 해당 메서드를 호출하는 동안 `FaultException`에서 파생되는 예외가 발생하면 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="5ac56-113">This event is emitted when the Service Model's default `OperationInvoker` has encountered an exception deriving from `FaultException` while invoking its method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5ac56-114">메시지</span><span class="sxs-lookup"><span data-stu-id="5ac56-114">Message</span></span>  
 <span data-ttu-id="5ac56-115">OperationInvoker의 호출을 받은 '%1' 메서드에서 FaultException이 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="5ac56-115">The '%1' method threw a FaultException when invoked by the OperationInvoker.</span></span> <span data-ttu-id="5ac56-116">메서드 호출 기간은 '%2'밀리초입니다.</span><span class="sxs-lookup"><span data-stu-id="5ac56-116">The method call duration was '%2' ms.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5ac56-117">설명</span><span class="sxs-lookup"><span data-stu-id="5ac56-117">Details</span></span>  
  
|<span data-ttu-id="5ac56-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="5ac56-118">Data Item Name</span></span>|<span data-ttu-id="5ac56-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="5ac56-119">Data Item Type</span></span>|<span data-ttu-id="5ac56-120">설명</span><span class="sxs-lookup"><span data-stu-id="5ac56-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5ac56-121">MethodName</span><span class="sxs-lookup"><span data-stu-id="5ac56-121">MethodName</span></span>|`xs:string`|<span data-ttu-id="5ac56-122">`OperationInvoker`의 호출을 받은 메서드의 CLR 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5ac56-122">The CLR name of the method that was invoked by the `OperationInvoker`.</span></span>|  
|<span data-ttu-id="5ac56-123">기간</span><span class="sxs-lookup"><span data-stu-id="5ac56-123">Duration</span></span>|`xs:long`|<span data-ttu-id="5ac56-124">`OperationInvoker`가 메서드를 호출하는 데 걸린 시간(밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="5ac56-124">The time, in milliseconds, that it took the `OperationInvoker` to invoke the method.</span></span>|  
|<span data-ttu-id="5ac56-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="5ac56-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="5ac56-126">웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="5ac56-126">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="5ac56-127">해당 형식으로 정의 됩니다 ' 웹 Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="5ac56-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="5ac56-128">예: ' 기본 웹 사이트/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="5ac56-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="5ac56-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="5ac56-129">AppDomain</span></span>|`xs:string`|<span data-ttu-id="5ac56-130">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="5ac56-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
