---
title: 212 - ParameterInspectorBeforeCallInvoked
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 063fc8d2-ceac-4c18-8368-de84f2c78035
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 64dcdb3a928d2ec05cd7dac557b6db10cb4a6511
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="212---parameterinspectorbeforecallinvoked"></a><span data-ttu-id="0b733-102">212 - ParameterInspectorBeforeCallInvoked</span><span class="sxs-lookup"><span data-stu-id="0b733-102">212 - ParameterInspectorBeforeCallInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="0b733-103">속성</span><span class="sxs-lookup"><span data-stu-id="0b733-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0b733-104">ID</span><span class="sxs-lookup"><span data-stu-id="0b733-104">ID</span></span>|<span data-ttu-id="0b733-105">212</span><span class="sxs-lookup"><span data-stu-id="0b733-105">212</span></span>|  
|<span data-ttu-id="0b733-106">키워드가</span><span class="sxs-lookup"><span data-stu-id="0b733-106">Keywords</span></span>|<span data-ttu-id="0b733-107">문제 해결, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="0b733-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="0b733-108">수준</span><span class="sxs-lookup"><span data-stu-id="0b733-108">Level</span></span>|<span data-ttu-id="0b733-109">정보</span><span class="sxs-lookup"><span data-stu-id="0b733-109">Information</span></span>|  
|<span data-ttu-id="0b733-110">채널</span><span class="sxs-lookup"><span data-stu-id="0b733-110">Channel</span></span>|<span data-ttu-id="0b733-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/분석</span><span class="sxs-lookup"><span data-stu-id="0b733-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0b733-112">설명</span><span class="sxs-lookup"><span data-stu-id="0b733-112">Description</span></span>  
 <span data-ttu-id="0b733-113">이 이벤트는 서비스 모델이 `BeforeCall`에 대해 `ParameterInspector` 메서드를 호출한 후에 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="0b733-113">This event is emitted after the Service Model has invoked the `BeforeCall` method on a `ParameterInspector`.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0b733-114">메시지</span><span class="sxs-lookup"><span data-stu-id="0b733-114">Message</span></span>  
 <span data-ttu-id="0b733-115">디스패처가 '%1' 형식의 ParameterInspector에 대해 'BeforeCall'을 호출했습니다.</span><span class="sxs-lookup"><span data-stu-id="0b733-115">The Dispatcher invoked 'BeforeCall' on a ParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="0b733-116">세부 정보</span><span class="sxs-lookup"><span data-stu-id="0b733-116">Details</span></span>  
  
|<span data-ttu-id="0b733-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="0b733-117">Data Item Name</span></span>|<span data-ttu-id="0b733-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="0b733-118">Data Item Type</span></span>|<span data-ttu-id="0b733-119">설명</span><span class="sxs-lookup"><span data-stu-id="0b733-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0b733-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="0b733-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="0b733-121">호출된 검사자 형식의 CLR FullName입니다.</span><span class="sxs-lookup"><span data-stu-id="0b733-121">The CLR FullName of the invoked inspector's type.</span></span>|  
|<span data-ttu-id="0b733-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="0b733-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="0b733-123">웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="0b733-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="0b733-124">해당 형식으로 정의 됩니다 ' 웹 Site Name Application Virtual Path &#124; 서비스의 가상 경로 &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="0b733-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="0b733-125">예: ' 기본 웹 사이트/CalculatorApplication #124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="0b733-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="0b733-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="0b733-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="0b733-127">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="0b733-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
