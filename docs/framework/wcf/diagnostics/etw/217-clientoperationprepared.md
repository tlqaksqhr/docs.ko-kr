---
title: 217 - ClientOperationPrepared
ms.date: 03/30/2017
ms.assetid: ad207f04-b038-4f33-95e9-27a361df8ecd
ms.openlocfilehash: 5979cd8ffe0e05b61af01d2aa98c4a2c63fd432c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33461067"
---
# <a name="217---clientoperationprepared"></a><span data-ttu-id="d7b4f-102">217 - ClientOperationPrepared</span><span class="sxs-lookup"><span data-stu-id="d7b4f-102">217 - ClientOperationPrepared</span></span>
## <a name="properties"></a><span data-ttu-id="d7b4f-103">속성</span><span class="sxs-lookup"><span data-stu-id="d7b4f-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d7b4f-104">ID</span><span class="sxs-lookup"><span data-stu-id="d7b4f-104">ID</span></span>|<span data-ttu-id="d7b4f-105">217</span><span class="sxs-lookup"><span data-stu-id="d7b4f-105">217</span></span>|  
|<span data-ttu-id="d7b4f-106">키워드가</span><span class="sxs-lookup"><span data-stu-id="d7b4f-106">Keywords</span></span>|<span data-ttu-id="d7b4f-107">문제 해결, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="d7b4f-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="d7b4f-108">수준</span><span class="sxs-lookup"><span data-stu-id="d7b4f-108">Level</span></span>|<span data-ttu-id="d7b4f-109">정보</span><span class="sxs-lookup"><span data-stu-id="d7b4f-109">Information</span></span>|  
|<span data-ttu-id="d7b4f-110">채널</span><span class="sxs-lookup"><span data-stu-id="d7b4f-110">Channel</span></span>|<span data-ttu-id="d7b4f-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/분석</span><span class="sxs-lookup"><span data-stu-id="d7b4f-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d7b4f-112">설명</span><span class="sxs-lookup"><span data-stu-id="d7b4f-112">Description</span></span>  
 <span data-ttu-id="d7b4f-113">이 이벤트는 서비스에 작업을 보내기 바로 전에 클라이언트에서 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="d7b4f-113">This event is emitted by clients just before an operation is sent to the service.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d7b4f-114">메시지</span><span class="sxs-lookup"><span data-stu-id="d7b4f-114">Message</span></span>  
 <span data-ttu-id="d7b4f-115">클라이언트가 '%2' 계약과 연결된 '%1' 작업을 실행하는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="d7b4f-115">The Client is executing Action '%1' associated with the '%2' contract.</span></span> <span data-ttu-id="d7b4f-116">메시지를 '%3'(으)로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="d7b4f-116">The message will be sent to '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d7b4f-117">설명</span><span class="sxs-lookup"><span data-stu-id="d7b4f-117">Details</span></span>  
  
|<span data-ttu-id="d7b4f-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="d7b4f-118">Data Item Name</span></span>|<span data-ttu-id="d7b4f-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="d7b4f-119">Data Item Type</span></span>|<span data-ttu-id="d7b4f-120">설명</span><span class="sxs-lookup"><span data-stu-id="d7b4f-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d7b4f-121">작업</span><span class="sxs-lookup"><span data-stu-id="d7b4f-121">Action</span></span>|`xs:string`|<span data-ttu-id="d7b4f-122">보내는 메시지의 SOAP 동작 헤더입니다.</span><span class="sxs-lookup"><span data-stu-id="d7b4f-122">The SOAP action header of the outgoing message.</span></span>|  
|<span data-ttu-id="d7b4f-123">Contract Name</span><span class="sxs-lookup"><span data-stu-id="d7b4f-123">Contract Name</span></span>|`xs:string`|<span data-ttu-id="d7b4f-124">계약 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d7b4f-124">The name of the contract.</span></span> <span data-ttu-id="d7b4f-125">예를 들면 ICalculator와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d7b4f-125">Example: ICalculator.</span></span>|  
|<span data-ttu-id="d7b4f-126">대상</span><span class="sxs-lookup"><span data-stu-id="d7b4f-126">Destination</span></span>|`xs:string`|<span data-ttu-id="d7b4f-127">메시지를 받는 서비스 끝점의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="d7b4f-127">The address of the service endpoint that the message is sent to.</span></span>|  
|<span data-ttu-id="d7b4f-128">HostReference</span><span class="sxs-lookup"><span data-stu-id="d7b4f-128">HostReference</span></span>|`xs:string`|<span data-ttu-id="d7b4f-129">웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="d7b4f-129">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="d7b4f-130">해당 형식으로 정의 됩니다 ' 웹 Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="d7b4f-130">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="d7b4f-131">예: ' 기본 웹 사이트/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="d7b4f-131">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="d7b4f-132">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d7b4f-132">AppDomain</span></span>|`xs:string`|<span data-ttu-id="d7b4f-133">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="d7b4f-133">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
