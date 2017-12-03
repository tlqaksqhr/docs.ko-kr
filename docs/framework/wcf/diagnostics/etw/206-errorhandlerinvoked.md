---
title: 206 - ErrorHandlerInvoked
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 97340f4d-4e09-4e42-a17a-982b3868dbcf
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4ff48217b1430002e1590ec3fdb1707d65075ffe
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="206---errorhandlerinvoked"></a><span data-ttu-id="d6e8d-102">206 - ErrorHandlerInvoked</span><span class="sxs-lookup"><span data-stu-id="d6e8d-102">206 - ErrorHandlerInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="d6e8d-103">속성</span><span class="sxs-lookup"><span data-stu-id="d6e8d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d6e8d-104">ID</span><span class="sxs-lookup"><span data-stu-id="d6e8d-104">ID</span></span>|<span data-ttu-id="d6e8d-105">206</span><span class="sxs-lookup"><span data-stu-id="d6e8d-105">206</span></span>|  
|<span data-ttu-id="d6e8d-106">키워드가</span><span class="sxs-lookup"><span data-stu-id="d6e8d-106">Keywords</span></span>|<span data-ttu-id="d6e8d-107">문제 해결, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="d6e8d-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="d6e8d-108">수준</span><span class="sxs-lookup"><span data-stu-id="d6e8d-108">Level</span></span>|<span data-ttu-id="d6e8d-109">정보</span><span class="sxs-lookup"><span data-stu-id="d6e8d-109">Information</span></span>|  
|<span data-ttu-id="d6e8d-110">채널</span><span class="sxs-lookup"><span data-stu-id="d6e8d-110">Channel</span></span>|<span data-ttu-id="d6e8d-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/분석</span><span class="sxs-lookup"><span data-stu-id="d6e8d-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d6e8d-112">설명</span><span class="sxs-lookup"><span data-stu-id="d6e8d-112">Description</span></span>  
 <span data-ttu-id="d6e8d-113">이 이벤트는 서비스 작업에서 발생한 예외를 처리할 수 있는 기회가 `ErrorHandler`에 제공된 후에 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="d6e8d-113">This event is emitted after an `ErrorHandler` has had an opportunity to handle an exception that occurred in a service operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d6e8d-114">메시지</span><span class="sxs-lookup"><span data-stu-id="d6e8d-114">Message</span></span>  
 <span data-ttu-id="d6e8d-115">디스패처가 '%3' 형식의 예외와 함께 '%1' 형식의 ErrorHandler를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e8d-115">The Dispatcher invoked an ErrorHandler of type '%1' with an exception of type '%3'.</span></span> <span data-ttu-id="d6e8d-116">ErrorHandled == '%2'.</span><span class="sxs-lookup"><span data-stu-id="d6e8d-116">ErrorHandled == '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d6e8d-117">세부 정보</span><span class="sxs-lookup"><span data-stu-id="d6e8d-117">Details</span></span>  
  
|<span data-ttu-id="d6e8d-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="d6e8d-118">Data Item Name</span></span>|<span data-ttu-id="d6e8d-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="d6e8d-119">Data Item Type</span></span>|<span data-ttu-id="d6e8d-120">설명</span><span class="sxs-lookup"><span data-stu-id="d6e8d-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d6e8d-121">TypeName</span><span class="sxs-lookup"><span data-stu-id="d6e8d-121">TypeName</span></span>|`xs:string`|<span data-ttu-id="d6e8d-122">호출된 `ErrorHandler` 형식의 CLR FullName입니다.</span><span class="sxs-lookup"><span data-stu-id="d6e8d-122">The CLR FullName of the type of the invoked `ErrorHandler`.</span></span>|  
|<span data-ttu-id="d6e8d-123">Handled</span><span class="sxs-lookup"><span data-stu-id="d6e8d-123">Handled</span></span>|`xs:unsignedByte`|<span data-ttu-id="d6e8d-124">오류 처리기가 오류를 처리했으면 `true`이고, 그렇지 않으면 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="d6e8d-124">`true` if the error handler handled the error, otherwise `false`.</span></span>|  
|<span data-ttu-id="d6e8d-125">ExceptionTypeName</span><span class="sxs-lookup"><span data-stu-id="d6e8d-125">ExceptionTypeName</span></span>|`xs:string`|<span data-ttu-id="d6e8d-126">처리된 예외의 CLR FullName입니다.</span><span class="sxs-lookup"><span data-stu-id="d6e8d-126">The CLR FullName of the exception that was being handled.</span></span>|  
|<span data-ttu-id="d6e8d-127">HostReference</span><span class="sxs-lookup"><span data-stu-id="d6e8d-127">HostReference</span></span>|`xs:string`|<span data-ttu-id="d6e8d-128">웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e8d-128">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="d6e8d-129">해당 형식으로 정의 됩니다 ' 웹 Site Name Application Virtual Path &#124; 서비스의 가상 경로 &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="d6e8d-129">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="d6e8d-130">예: ' 기본 웹 사이트/CalculatorApplication #124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="d6e8d-130">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="d6e8d-131">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d6e8d-131">AppDomain</span></span>|`xs:string`|<span data-ttu-id="d6e8d-132">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="d6e8d-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
