---
title: 211 - ParameterInspectorAfterCallInvoked
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c0e21297-10b8-4456-a0e1-e019145cd5ac
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 78424b8057518f5d9f201ead33b2784ffeeb7e58
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="211---parameterinspectoraftercallinvoked"></a><span data-ttu-id="3a3d8-102">211 - ParameterInspectorAfterCallInvoked</span><span class="sxs-lookup"><span data-stu-id="3a3d8-102">211 - ParameterInspectorAfterCallInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="3a3d8-103">속성</span><span class="sxs-lookup"><span data-stu-id="3a3d8-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3a3d8-104">ID</span><span class="sxs-lookup"><span data-stu-id="3a3d8-104">ID</span></span>|<span data-ttu-id="3a3d8-105">211</span><span class="sxs-lookup"><span data-stu-id="3a3d8-105">211</span></span>|  
|<span data-ttu-id="3a3d8-106">키워드</span><span class="sxs-lookup"><span data-stu-id="3a3d8-106">Keywords</span></span>|<span data-ttu-id="3a3d8-107">문제 해결, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="3a3d8-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="3a3d8-108">수준</span><span class="sxs-lookup"><span data-stu-id="3a3d8-108">Level</span></span>|<span data-ttu-id="3a3d8-109">정보</span><span class="sxs-lookup"><span data-stu-id="3a3d8-109">Information</span></span>|  
|<span data-ttu-id="3a3d8-110">채널</span><span class="sxs-lookup"><span data-stu-id="3a3d8-110">Channel</span></span>|<span data-ttu-id="3a3d8-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/분석</span><span class="sxs-lookup"><span data-stu-id="3a3d8-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3a3d8-112">설명</span><span class="sxs-lookup"><span data-stu-id="3a3d8-112">Description</span></span>  
 <span data-ttu-id="3a3d8-113">이 이벤트는 서비스 모델이 `AfterCall`에 대해 `ParameterInspector` 메서드를 호출한 후에 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="3a3d8-113">This event is emitted after the Service Model has invoked the `AfterCall` method on a `ParameterInspector`.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3a3d8-114">메시지</span><span class="sxs-lookup"><span data-stu-id="3a3d8-114">Message</span></span>  
 <span data-ttu-id="3a3d8-115">디스패처가 '%1' 형식의 ParameterInspector에 대해 'AfterCall'을 호출했습니다.</span><span class="sxs-lookup"><span data-stu-id="3a3d8-115">The Dispatcher invoked 'AfterCall' on a ParameterInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3a3d8-116">설명</span><span class="sxs-lookup"><span data-stu-id="3a3d8-116">Details</span></span>  
  
|<span data-ttu-id="3a3d8-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="3a3d8-117">Data Item Name</span></span>|<span data-ttu-id="3a3d8-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="3a3d8-118">Data Item Type</span></span>|<span data-ttu-id="3a3d8-119">설명</span><span class="sxs-lookup"><span data-stu-id="3a3d8-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3a3d8-120">형식 이름</span><span class="sxs-lookup"><span data-stu-id="3a3d8-120">Type Name</span></span>|`xs:string`|<span data-ttu-id="3a3d8-121">호출된 `ParameterInspector` 형식의 CLR FullName입니다.</span><span class="sxs-lookup"><span data-stu-id="3a3d8-121">The CLR FullName of the type of the invoked `ParameterInspector`.</span></span>|  
|<span data-ttu-id="3a3d8-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="3a3d8-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="3a3d8-123">웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="3a3d8-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="3a3d8-124">해당 형식으로 정의 됩니다 ' 웹 Site Name Application Virtual Path &#124; 서비스의 가상 경로 &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="3a3d8-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="3a3d8-125">예: ' 기본 웹 사이트/CalculatorApplication #124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="3a3d8-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="3a3d8-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="3a3d8-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="3a3d8-127">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="3a3d8-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
