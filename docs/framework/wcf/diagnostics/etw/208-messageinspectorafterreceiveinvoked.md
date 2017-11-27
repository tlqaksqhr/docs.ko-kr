---
title: 208 - MessageInspectorAfterReceiveInvoked
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dfb5f7b0-4346-4949-8104-351726b1f502
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: cdb89eb9f2a50db20f6da53a2b3f527aef8c0ed1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="208---messageinspectorafterreceiveinvoked"></a><span data-ttu-id="5b936-102">208 - MessageInspectorAfterReceiveInvoked</span><span class="sxs-lookup"><span data-stu-id="5b936-102">208 - MessageInspectorAfterReceiveInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="5b936-103">속성</span><span class="sxs-lookup"><span data-stu-id="5b936-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5b936-104">ID</span><span class="sxs-lookup"><span data-stu-id="5b936-104">ID</span></span>|<span data-ttu-id="5b936-105">208</span><span class="sxs-lookup"><span data-stu-id="5b936-105">208</span></span>|  
|<span data-ttu-id="5b936-106">키워드</span><span class="sxs-lookup"><span data-stu-id="5b936-106">Keywords</span></span>|<span data-ttu-id="5b936-107">문제 해결, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="5b936-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="5b936-108">수준</span><span class="sxs-lookup"><span data-stu-id="5b936-108">Level</span></span>|<span data-ttu-id="5b936-109">정보</span><span class="sxs-lookup"><span data-stu-id="5b936-109">Information</span></span>|  
|<span data-ttu-id="5b936-110">채널</span><span class="sxs-lookup"><span data-stu-id="5b936-110">Channel</span></span>|<span data-ttu-id="5b936-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/분석</span><span class="sxs-lookup"><span data-stu-id="5b936-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5b936-112">설명</span><span class="sxs-lookup"><span data-stu-id="5b936-112">Description</span></span>  
 <span data-ttu-id="5b936-113">이 이벤트는 서비스 모델이 메시지 검사자에 대해 `AfterReceive` 메서드를 호출한 후에 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="5b936-113">This event is emitted after the Service Model has invoked the `AfterReceive` method on a message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5b936-114">메시지</span><span class="sxs-lookup"><span data-stu-id="5b936-114">Message</span></span>  
 <span data-ttu-id="5b936-115">디스패처가 '%1' 형식의 MessageInspector에 대해 'AfterReceiveReply'를 호출했습니다.</span><span class="sxs-lookup"><span data-stu-id="5b936-115">The Dispatcher invoked 'AfterReceiveReply' on a MessageInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5b936-116">설명</span><span class="sxs-lookup"><span data-stu-id="5b936-116">Details</span></span>  
  
|<span data-ttu-id="5b936-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="5b936-117">Data Item Name</span></span>|<span data-ttu-id="5b936-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="5b936-118">Data Item Type</span></span>|<span data-ttu-id="5b936-119">설명</span><span class="sxs-lookup"><span data-stu-id="5b936-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5b936-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="5b936-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="5b936-121">호출된 `MessageInspector` 형식의 CLR FullName입니다.</span><span class="sxs-lookup"><span data-stu-id="5b936-121">The CLR FullName of the type of the invoked `MessageInspector`.</span></span>|  
|<span data-ttu-id="5b936-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="5b936-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="5b936-123">웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="5b936-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="5b936-124">해당 형식으로 정의 됩니다 ' 웹 Site Name Application Virtual Path &#124; 서비스의 가상 경로 &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="5b936-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="5b936-125">예: ' 기본 웹 사이트/CalculatorApplication #124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="5b936-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="5b936-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="5b936-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="5b936-127">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="5b936-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
