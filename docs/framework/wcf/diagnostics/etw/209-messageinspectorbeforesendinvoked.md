---
title: 209 - MessageInspectorBeforeSendInvoked
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7d710875-fb77-4463-978b-bc86d59d84cd
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3341f9ae5600536a7d824034582bf232f5be90ad
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="209---messageinspectorbeforesendinvoked"></a><span data-ttu-id="50ada-102">209 - MessageInspectorBeforeSendInvoked</span><span class="sxs-lookup"><span data-stu-id="50ada-102">209 - MessageInspectorBeforeSendInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="50ada-103">속성</span><span class="sxs-lookup"><span data-stu-id="50ada-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="50ada-104">ID</span><span class="sxs-lookup"><span data-stu-id="50ada-104">ID</span></span>|<span data-ttu-id="50ada-105">209</span><span class="sxs-lookup"><span data-stu-id="50ada-105">209</span></span>|  
|<span data-ttu-id="50ada-106">키워드가</span><span class="sxs-lookup"><span data-stu-id="50ada-106">Keywords</span></span>|<span data-ttu-id="50ada-107">문제 해결, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="50ada-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="50ada-108">수준</span><span class="sxs-lookup"><span data-stu-id="50ada-108">Level</span></span>|<span data-ttu-id="50ada-109">정보</span><span class="sxs-lookup"><span data-stu-id="50ada-109">Information</span></span>|  
|<span data-ttu-id="50ada-110">채널</span><span class="sxs-lookup"><span data-stu-id="50ada-110">Channel</span></span>|<span data-ttu-id="50ada-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/분석</span><span class="sxs-lookup"><span data-stu-id="50ada-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="50ada-112">설명</span><span class="sxs-lookup"><span data-stu-id="50ada-112">Description</span></span>  
 <span data-ttu-id="50ada-113">이 이벤트는 서비스 모델이 메시지 검사자에 대해 `BeforeSend` 메서드를 호출한 후에 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="50ada-113">This event is emitted after the Service Model has invoked the `BeforeSend` method on a message inspector.</span></span>  
  
## <a name="message"></a><span data-ttu-id="50ada-114">메시지</span><span class="sxs-lookup"><span data-stu-id="50ada-114">Message</span></span>  
 <span data-ttu-id="50ada-115">디스패처가 '%1' 형식의 MessageInspector에 대해 'BeforeSendRequest'를 호출했습니다.</span><span class="sxs-lookup"><span data-stu-id="50ada-115">The Dispatcher invoked 'BeforeSendRequest' on a MessageInspector of type '%1'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="50ada-116">세부 정보</span><span class="sxs-lookup"><span data-stu-id="50ada-116">Details</span></span>  
  
|<span data-ttu-id="50ada-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="50ada-117">Data Item Name</span></span>|<span data-ttu-id="50ada-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="50ada-118">Data Item Type</span></span>|<span data-ttu-id="50ada-119">설명</span><span class="sxs-lookup"><span data-stu-id="50ada-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="50ada-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="50ada-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="50ada-121">호출된 `MessageInspector` 형식의 CLR FullName입니다.</span><span class="sxs-lookup"><span data-stu-id="50ada-121">The CLR FullName of the type of the invoked `MessageInspector`.</span></span>|  
|<span data-ttu-id="50ada-122">HostReference</span><span class="sxs-lookup"><span data-stu-id="50ada-122">HostReference</span></span>|`xs:string`|<span data-ttu-id="50ada-123">웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="50ada-123">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="50ada-124">해당 형식으로 정의 됩니다 ' 웹 Site Name Application Virtual Path &#124; 서비스의 가상 경로 &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="50ada-124">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="50ada-125">예: ' 기본 웹 사이트/CalculatorApplication #124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="50ada-125">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="50ada-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="50ada-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="50ada-127">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="50ada-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
