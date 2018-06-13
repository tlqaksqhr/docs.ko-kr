---
title: 303 - UserDefinedInformationEventOccured
ms.date: 03/30/2017
ms.assetid: 5ed5acaf-3755-4417-92c4-4ebc8e854ca1
ms.openlocfilehash: 0b782b5ac0527b5acb3ebf0bf11c117563042495
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33459142"
---
# <a name="303---userdefinedinformationeventoccured"></a><span data-ttu-id="bbf78-102">303 - UserDefinedInformationEventOccured</span><span class="sxs-lookup"><span data-stu-id="bbf78-102">303 - UserDefinedInformationEventOccured</span></span>
## <a name="properties"></a><span data-ttu-id="bbf78-103">속성</span><span class="sxs-lookup"><span data-stu-id="bbf78-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="bbf78-104">ID</span><span class="sxs-lookup"><span data-stu-id="bbf78-104">ID</span></span>|<span data-ttu-id="bbf78-105">303</span><span class="sxs-lookup"><span data-stu-id="bbf78-105">303</span></span>|  
|<span data-ttu-id="bbf78-106">키워드가</span><span class="sxs-lookup"><span data-stu-id="bbf78-106">Keywords</span></span>|<span data-ttu-id="bbf78-107">문제 해결, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span><span class="sxs-lookup"><span data-stu-id="bbf78-107">Troubleshooting, HealthMonitoring, UserEvents, ServiceModel, EndToEndMonitoring</span></span>|  
|<span data-ttu-id="bbf78-108">수준</span><span class="sxs-lookup"><span data-stu-id="bbf78-108">Level</span></span>|<span data-ttu-id="bbf78-109">정보</span><span class="sxs-lookup"><span data-stu-id="bbf78-109">Information</span></span>|  
|<span data-ttu-id="bbf78-110">채널</span><span class="sxs-lookup"><span data-stu-id="bbf78-110">Channel</span></span>|<span data-ttu-id="bbf78-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/분석</span><span class="sxs-lookup"><span data-stu-id="bbf78-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="bbf78-112">설명</span><span class="sxs-lookup"><span data-stu-id="bbf78-112">Description</span></span>  
 <span data-ttu-id="bbf78-113">이 이벤트는 사용자 코드에서 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="bbf78-113">This event is emitted from user code.</span></span> <span data-ttu-id="bbf78-114">개발자는 자신의 서비스에서 사용자 정의 정보 이벤트가 발생할 때 이 이벤트를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf78-114">Developers can emit this event when a custom-defined informational event occurs in their service.</span></span> <span data-ttu-id="bbf78-115">이 작업은 <xref:System.Diagnostics.Eventing> API를 사용하여 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf78-115">This can be done using the <xref:System.Diagnostics.Eventing> APIs.</span></span> <span data-ttu-id="bbf78-116">이외에도 이 API를 래핑하고 이 이벤트를 적절히 내보내는 방법을 보여 주는 WCF 샘플을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bbf78-116">Additionally, there is a WCF sample that wraps that API and demonstrates how to properly emit this event.</span></span>  
  
## <a name="message"></a><span data-ttu-id="bbf78-117">메시지</span><span class="sxs-lookup"><span data-stu-id="bbf78-117">Message</span></span>  
 <span data-ttu-id="bbf78-118">이름:'%1', 참조:'%2', 페이로드:%3</span><span class="sxs-lookup"><span data-stu-id="bbf78-118">Name:'%1', Reference:'%2', Payload:%3</span></span>  
  
## <a name="details"></a><span data-ttu-id="bbf78-119">설명</span><span class="sxs-lookup"><span data-stu-id="bbf78-119">Details</span></span>  
  
|<span data-ttu-id="bbf78-120">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="bbf78-120">Data Item Name</span></span>|<span data-ttu-id="bbf78-121">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="bbf78-121">Data Item Type</span></span>|<span data-ttu-id="bbf78-122">설명</span><span class="sxs-lookup"><span data-stu-id="bbf78-122">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="bbf78-123">이름</span><span class="sxs-lookup"><span data-stu-id="bbf78-123">Name</span></span>|`xs:string`|<span data-ttu-id="bbf78-124">이벤트의 사용자 정의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="bbf78-124">The user-defined name of the event</span></span>|  
|<span data-ttu-id="bbf78-125">HostReference</span><span class="sxs-lookup"><span data-stu-id="bbf78-125">HostReference</span></span>|`xs:string`|<span data-ttu-id="bbf78-126">웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="bbf78-126">For Web hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="bbf78-127">해당 형식으로 정의 됩니다 ' 웹 Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="bbf78-127">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="bbf78-128">예: ' 기본 웹 사이트/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="bbf78-128">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="bbf78-129">Payload</span><span class="sxs-lookup"><span data-stu-id="bbf78-129">Payload</span></span>|`xs:string`|<span data-ttu-id="bbf78-130">이벤트의 사용자 정의 페이로드입니다.</span><span class="sxs-lookup"><span data-stu-id="bbf78-130">The user-defined payload of the event.</span></span>|
