---
title: 214 - OperationCompleted
ms.date: 03/30/2017
ms.assetid: a6287eef-023f-4816-813c-1802c82366df
ms.openlocfilehash: da1021b674b555b683f8f745f5a2a0073c9567e8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33459370"
---
# <a name="214---operationcompleted"></a><span data-ttu-id="d6b05-102">214 - OperationCompleted</span><span class="sxs-lookup"><span data-stu-id="d6b05-102">214 - OperationCompleted</span></span>
## <a name="properties"></a><span data-ttu-id="d6b05-103">속성</span><span class="sxs-lookup"><span data-stu-id="d6b05-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d6b05-104">ID</span><span class="sxs-lookup"><span data-stu-id="d6b05-104">ID</span></span>|<span data-ttu-id="d6b05-105">214</span><span class="sxs-lookup"><span data-stu-id="d6b05-105">214</span></span>|  
|<span data-ttu-id="d6b05-106">키워드가</span><span class="sxs-lookup"><span data-stu-id="d6b05-106">Keywords</span></span>|<span data-ttu-id="d6b05-107">HealthMonitoring, EndToEndMonitoring, 문제 해결, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="d6b05-107">HealthMonitoring, EndToEndMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="d6b05-108">수준</span><span class="sxs-lookup"><span data-stu-id="d6b05-108">Level</span></span>|<span data-ttu-id="d6b05-109">정보</span><span class="sxs-lookup"><span data-stu-id="d6b05-109">Information</span></span>|  
|<span data-ttu-id="d6b05-110">채널</span><span class="sxs-lookup"><span data-stu-id="d6b05-110">Channel</span></span>|<span data-ttu-id="d6b05-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/분석</span><span class="sxs-lookup"><span data-stu-id="d6b05-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d6b05-112">설명</span><span class="sxs-lookup"><span data-stu-id="d6b05-112">Description</span></span>  
 <span data-ttu-id="d6b05-113">이 이벤트는 서비스 모델의 기본 `OperationInvoker`가 메서드에서 예외를 throw하지 않고 메서드에 대한 호출을 완료하면 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="d6b05-113">This event is emitted when the Service Model's default `OperationInvoker` has completed a call to a method without that method throwing an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d6b05-114">메시지</span><span class="sxs-lookup"><span data-stu-id="d6b05-114">Message</span></span>  
 <span data-ttu-id="d6b05-115">OperationInvoker가 '%1' 메서드에 대한 호출을 완료했습니다.</span><span class="sxs-lookup"><span data-stu-id="d6b05-115">An OperationInvoker completed the call to the '%1' method.</span></span> <span data-ttu-id="d6b05-116">메서드 호출 기간은 '%2'밀리초입니다.</span><span class="sxs-lookup"><span data-stu-id="d6b05-116">The method call duration was '%2' ms.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d6b05-117">설명</span><span class="sxs-lookup"><span data-stu-id="d6b05-117">Details</span></span>  
  
|<span data-ttu-id="d6b05-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="d6b05-118">Data Item Name</span></span>|<span data-ttu-id="d6b05-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="d6b05-119">Data Item Type</span></span>|<span data-ttu-id="d6b05-120">설명</span><span class="sxs-lookup"><span data-stu-id="d6b05-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d6b05-121">메서드 이름</span><span class="sxs-lookup"><span data-stu-id="d6b05-121">Method Name</span></span>|`xs:string`|<span data-ttu-id="d6b05-122">`OperationInvoker`의 호출을 받은 메서드의 CLR 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d6b05-122">The CLR name of the method that was invoked by the `OperationInvoker`.</span></span>|  
|<span data-ttu-id="d6b05-123">기간</span><span class="sxs-lookup"><span data-stu-id="d6b05-123">Duration</span></span>|`xs:long`|<span data-ttu-id="d6b05-124">`OperationInvoker`가 메서드를 호출하는 데 걸린 시간(밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="d6b05-124">The time, in milliseconds, that it took the `OperationInvoker` to invoke the method.</span></span>|  
|<span data-ttu-id="d6b05-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="d6b05-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="d6b05-126">웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="d6b05-126">For web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="d6b05-127">해당 형식으로 정의 됩니다 ' 웹 Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="d6b05-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="d6b05-128">예: ' 기본 웹 사이트/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="d6b05-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="d6b05-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d6b05-129">AppDomain</span></span>|`xs:string`|<span data-ttu-id="d6b05-130">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="d6b05-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
