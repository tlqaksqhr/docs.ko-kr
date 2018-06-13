---
title: 205 - OperationInvoked
ms.date: 03/30/2017
ms.assetid: 9c8d6c90-dfa5-4ae0-a589-96679a8fb3ba
ms.openlocfilehash: e95b6923d21307b2ef68d4a5369b3cee86540239
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33458351"
---
# <a name="205---operationinvoked"></a><span data-ttu-id="31b02-102">205 - OperationInvoked</span><span class="sxs-lookup"><span data-stu-id="31b02-102">205 - OperationInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="31b02-103">속성</span><span class="sxs-lookup"><span data-stu-id="31b02-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="31b02-104">ID</span><span class="sxs-lookup"><span data-stu-id="31b02-104">ID</span></span>|<span data-ttu-id="31b02-105">205</span><span class="sxs-lookup"><span data-stu-id="31b02-105">205</span></span>|  
|<span data-ttu-id="31b02-106">키워드</span><span class="sxs-lookup"><span data-stu-id="31b02-106">Keywords</span></span>|<span data-ttu-id="31b02-107">문제 해결, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="31b02-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="31b02-108">수준</span><span class="sxs-lookup"><span data-stu-id="31b02-108">Level</span></span>|<span data-ttu-id="31b02-109">정보</span><span class="sxs-lookup"><span data-stu-id="31b02-109">Information</span></span>|  
|<span data-ttu-id="31b02-110">채널</span><span class="sxs-lookup"><span data-stu-id="31b02-110">Channel</span></span>|<span data-ttu-id="31b02-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/분석</span><span class="sxs-lookup"><span data-stu-id="31b02-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="31b02-112">설명</span><span class="sxs-lookup"><span data-stu-id="31b02-112">Description</span></span>  
 <span data-ttu-id="31b02-113">이 이벤트는 서비스 모델의 기본 `OperationInvoker`가 메서드에 대한 호출을 시작하기 바로 전에 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="31b02-113">This event is emitted just before the Service Model's default `OperationInvoker` begins a call to a method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="31b02-114">메시지</span><span class="sxs-lookup"><span data-stu-id="31b02-114">Message</span></span>  
 <span data-ttu-id="31b02-115">OperationInvoker가 '%1' 메서드를 호출했습니다.</span><span class="sxs-lookup"><span data-stu-id="31b02-115">An OperationInvoker invoked the '%1' method.</span></span> <span data-ttu-id="31b02-116">호출자 정보: '%2'.</span><span class="sxs-lookup"><span data-stu-id="31b02-116">Caller information: '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="31b02-117">설명</span><span class="sxs-lookup"><span data-stu-id="31b02-117">Details</span></span>  
  
|<span data-ttu-id="31b02-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="31b02-118">Data Item Name</span></span>|<span data-ttu-id="31b02-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="31b02-119">Data Item Type</span></span>|<span data-ttu-id="31b02-120">설명</span><span class="sxs-lookup"><span data-stu-id="31b02-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="31b02-121">메서드 이름</span><span class="sxs-lookup"><span data-stu-id="31b02-121">Method Name</span></span>|`xs:string`|<span data-ttu-id="31b02-122">`OperationInvoker`의 호출을 받은 메서드의 CLR 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="31b02-122">The CLR name of the method that was invoked by the `OperationInvoker`.</span></span>|  
|<span data-ttu-id="31b02-123">호출자 정보</span><span class="sxs-lookup"><span data-stu-id="31b02-123">Caller Information</span></span>|`xs:string`|<span data-ttu-id="31b02-124">'IPAddress:PortNumber' 형식으로 된 클라이언트의 IP 주소와 포트 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="31b02-124">The IP address and port number of the client in the format 'IPAddress:PortNumber'.</span></span> <span data-ttu-id="31b02-125">이 두 값은 작업 컨텍스트 내의 'System.ServiceModel.Channels.RemoteEndpointMessageProperty' 메시지 속성에서 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="31b02-125">The two values are retrieved from the 'System.ServiceModel.Channels.RemoteEndpointMessageProperty' message property within the operation context.</span></span> <span data-ttu-id="31b02-126">비 TCP 바인딩의 경우 이 값은 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="31b02-126">Note that for non-TCP bindings this value `null`.</span></span>|  
|<span data-ttu-id="31b02-127">HostReference</span><span class="sxs-lookup"><span data-stu-id="31b02-127">HostReference</span></span>|`xs:string`|<span data-ttu-id="31b02-128">웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="31b02-128">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="31b02-129">해당 형식으로 정의 됩니다 ' 웹 Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="31b02-129">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="31b02-130">예: ' 기본 웹 사이트/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="31b02-130">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="31b02-131">AppDomain</span><span class="sxs-lookup"><span data-stu-id="31b02-131">AppDomain</span></span>|`xs:string`|<span data-ttu-id="31b02-132">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="31b02-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
