---
title: 207 - FaultProviderInvoked
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b730d903-01c2-4deb-85a4-da12f8a21fe4
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: fe3698653be04119c84c5f423207458e9d033dc1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="207---faultproviderinvoked"></a><span data-ttu-id="1a7fd-102">207 - FaultProviderInvoked</span><span class="sxs-lookup"><span data-stu-id="1a7fd-102">207 - FaultProviderInvoked</span></span>
## <a name="properties"></a><span data-ttu-id="1a7fd-103">속성</span><span class="sxs-lookup"><span data-stu-id="1a7fd-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1a7fd-104">ID</span><span class="sxs-lookup"><span data-stu-id="1a7fd-104">ID</span></span>|<span data-ttu-id="1a7fd-105">207</span><span class="sxs-lookup"><span data-stu-id="1a7fd-105">207</span></span>|  
|<span data-ttu-id="1a7fd-106">키워드</span><span class="sxs-lookup"><span data-stu-id="1a7fd-106">Keywords</span></span>|<span data-ttu-id="1a7fd-107">문제 해결, ServiceModel</span><span class="sxs-lookup"><span data-stu-id="1a7fd-107">Troubleshooting, ServiceModel</span></span>|  
|<span data-ttu-id="1a7fd-108">수준</span><span class="sxs-lookup"><span data-stu-id="1a7fd-108">Level</span></span>|<span data-ttu-id="1a7fd-109">정보</span><span class="sxs-lookup"><span data-stu-id="1a7fd-109">Information</span></span>|  
|<span data-ttu-id="1a7fd-110">채널</span><span class="sxs-lookup"><span data-stu-id="1a7fd-110">Channel</span></span>|<span data-ttu-id="1a7fd-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/분석</span><span class="sxs-lookup"><span data-stu-id="1a7fd-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="1a7fd-112">설명</span><span class="sxs-lookup"><span data-stu-id="1a7fd-112">Description</span></span>  
 <span data-ttu-id="1a7fd-113">이 이벤트는 `FaultProvider`가 호출된 후에 내보내집니다.</span><span class="sxs-lookup"><span data-stu-id="1a7fd-113">This event is emitted after a `FaultProvider` has been invoked.</span></span>  
  
## <a name="message"></a><span data-ttu-id="1a7fd-114">메시지</span><span class="sxs-lookup"><span data-stu-id="1a7fd-114">Message</span></span>  
 <span data-ttu-id="1a7fd-115">디스패처가 '%2' 형식의 예외와 함께 '%1' 형식의 FaultProvider를 호출했습니다.</span><span class="sxs-lookup"><span data-stu-id="1a7fd-115">The Dispatcher invoked a FaultProvider of type '%1' with an exception of type '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="1a7fd-116">설명</span><span class="sxs-lookup"><span data-stu-id="1a7fd-116">Details</span></span>  
  
|<span data-ttu-id="1a7fd-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="1a7fd-117">Data Item Name</span></span>|<span data-ttu-id="1a7fd-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="1a7fd-118">Data Item Type</span></span>|<span data-ttu-id="1a7fd-119">설명</span><span class="sxs-lookup"><span data-stu-id="1a7fd-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="1a7fd-120">TypeName</span><span class="sxs-lookup"><span data-stu-id="1a7fd-120">TypeName</span></span>|`xs:string`|<span data-ttu-id="1a7fd-121">호출된 `FaultProvider` 형식의 CLR FullName입니다.</span><span class="sxs-lookup"><span data-stu-id="1a7fd-121">The CLR FullName of the type of the invoked `FaultProvider`.</span></span>|  
|<span data-ttu-id="1a7fd-122">ExceptionTypeName</span><span class="sxs-lookup"><span data-stu-id="1a7fd-122">ExceptionTypeName</span></span>|`xs:string`|<span data-ttu-id="1a7fd-123">`FaultProvider`가 처리한 예외의 CLR FullName입니다.</span><span class="sxs-lookup"><span data-stu-id="1a7fd-123">The CLR FullName of the exception that the `FaultProvider` has operated on.</span></span>|  
|<span data-ttu-id="1a7fd-124">HostReference</span><span class="sxs-lookup"><span data-stu-id="1a7fd-124">HostReference</span></span>|`xs:string`|<span data-ttu-id="1a7fd-125">웹 호스팅 서비스의 경우 이 필드는 웹 계층의 서비스를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="1a7fd-125">For Web-hosted services, this field uniquely identifies the service in the Web hierarchy.</span></span> <span data-ttu-id="1a7fd-126">해당 형식으로 정의 됩니다 ' 웹 Site Name Application Virtual Path &#124; 서비스의 가상 경로 &#124; ServiceName'.</span><span class="sxs-lookup"><span data-stu-id="1a7fd-126">Its format is defined as 'Web Site Name Application Virtual Path&#124;Service Virtual Path&#124;ServiceName'.</span></span> <span data-ttu-id="1a7fd-127">예: ' 기본 웹 사이트/CalculatorApplication #124;/CalculatorService.svc &#124; CalculatorService'.</span><span class="sxs-lookup"><span data-stu-id="1a7fd-127">Example: 'Default Web Site/CalculatorApplication&#124;/CalculatorService.svc&#124;CalculatorService'.</span></span>|  
|<span data-ttu-id="1a7fd-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="1a7fd-128">AppDomain</span></span>|`xs:string`|<span data-ttu-id="1a7fd-129">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="1a7fd-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
