---
title: 221 - MessageReceivedFromTransport
ms.date: 03/30/2017
ms.assetid: 4995f0d5-c182-4d97-981f-6951da6df1fb
ms.openlocfilehash: 98dbf2728242fa73b3e54b7cf32f9e227e5251b2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33458779"
---
# <a name="221---messagereceivedfromtransport"></a><span data-ttu-id="1c5c4-102">221 - MessageReceivedFromTransport</span><span class="sxs-lookup"><span data-stu-id="1c5c4-102">221 - MessageReceivedFromTransport</span></span>
## <a name="properties"></a><span data-ttu-id="1c5c4-103">속성</span><span class="sxs-lookup"><span data-stu-id="1c5c4-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1c5c4-104">ID</span><span class="sxs-lookup"><span data-stu-id="1c5c4-104">ID</span></span>|<span data-ttu-id="1c5c4-105">221</span><span class="sxs-lookup"><span data-stu-id="1c5c4-105">221</span></span>|  
|<span data-ttu-id="1c5c4-106">키워드</span><span class="sxs-lookup"><span data-stu-id="1c5c4-106">Keywords</span></span>|<span data-ttu-id="1c5c4-107">EndToEndMonitoring, 문제 해결, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="1c5c4-107">EndToEndMonitoring, Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="1c5c4-108">수준</span><span class="sxs-lookup"><span data-stu-id="1c5c4-108">Level</span></span>|<span data-ttu-id="1c5c4-109">정보</span><span class="sxs-lookup"><span data-stu-id="1c5c4-109">Information</span></span>|  
|<span data-ttu-id="1c5c4-110">채널</span><span class="sxs-lookup"><span data-stu-id="1c5c4-110">Channel</span></span>|<span data-ttu-id="1c5c4-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/분석</span><span class="sxs-lookup"><span data-stu-id="1c5c4-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="1c5c4-112">설명</span><span class="sxs-lookup"><span data-stu-id="1c5c4-112">Description</span></span>  
 <span data-ttu-id="1c5c4-113">이 이벤트는 서비스 모델이 전송에서 메시지를 받을 때 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="1c5c4-113">This event is emitted when the Service Model receives a message from the transport.</span></span>  
  
## <a name="message"></a><span data-ttu-id="1c5c4-114">메시지</span><span class="sxs-lookup"><span data-stu-id="1c5c4-114">Message</span></span>  
 <span data-ttu-id="1c5c4-115">디스패처가 전송에서 메시지를 받았습니다.</span><span class="sxs-lookup"><span data-stu-id="1c5c4-115">The Dispatcher received a message from the transport.</span></span> <span data-ttu-id="1c5c4-116">Correlation ID == '%1'.</span><span class="sxs-lookup"><span data-stu-id="1c5c4-116">Correlation ID == '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="1c5c4-117">설명</span><span class="sxs-lookup"><span data-stu-id="1c5c4-117">Details</span></span>  
  
|<span data-ttu-id="1c5c4-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="1c5c4-118">Data Item Name</span></span>|<span data-ttu-id="1c5c4-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="1c5c4-119">Data Item Type</span></span>|<span data-ttu-id="1c5c4-120">설명</span><span class="sxs-lookup"><span data-stu-id="1c5c4-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="1c5c4-121">Correlation ID</span><span class="sxs-lookup"><span data-stu-id="1c5c4-121">Correlation ID</span></span>|`xs:GUID`|<span data-ttu-id="1c5c4-122">서비스 또는 클라이언트의 `MessageSentToTransport` 이벤트를 다른 끝에 있는 해당 `MessageReceivedFromTransport`에 상호 연결하는 데 사용되는 동작 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="1c5c4-122">The activity ID used to correlate a `MessageSentToTransport` event from a service or client to its corresponding `MessageReceivedFromTransport` on the other end.</span></span>|  
|<span data-ttu-id="1c5c4-123">HostReference</span><span class="sxs-lookup"><span data-stu-id="1c5c4-123">HostReference</span></span>|`xs:string`|<span data-ttu-id="1c5c4-124">웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="1c5c4-124">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="1c5c4-125">해당 형식으로 정의 됩니다 ' 웹 Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="1c5c4-125">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="1c5c4-126">예: ' 기본 웹 사이트/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="1c5c4-126">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="1c5c4-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="1c5c4-127">AppDomain</span></span>|`xs:string`|<span data-ttu-id="1c5c4-128">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="1c5c4-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
