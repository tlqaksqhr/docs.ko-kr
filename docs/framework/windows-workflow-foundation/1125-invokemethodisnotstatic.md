---
title: 1125 - InvokeMethodIsNotStatic
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ea2b3827-63da-497b-b2c3-d5cebefe57a1
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b31bb8db8252474d20f7523e08cadf35bfcc84a8
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="1125---invokemethodisnotstatic"></a><span data-ttu-id="b2510-102">1125 - InvokeMethodIsNotStatic</span><span class="sxs-lookup"><span data-stu-id="b2510-102">1125 - InvokeMethodIsNotStatic</span></span>
## <a name="properties"></a><span data-ttu-id="b2510-103">속성</span><span class="sxs-lookup"><span data-stu-id="b2510-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b2510-104">ID</span><span class="sxs-lookup"><span data-stu-id="b2510-104">ID</span></span>|<span data-ttu-id="b2510-105">1125</span><span class="sxs-lookup"><span data-stu-id="b2510-105">1125</span></span>|  
|<span data-ttu-id="b2510-106">키워드</span><span class="sxs-lookup"><span data-stu-id="b2510-106">Keywords</span></span>|<span data-ttu-id="b2510-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="b2510-107">WFRuntime</span></span>|  
|<span data-ttu-id="b2510-108">수준</span><span class="sxs-lookup"><span data-stu-id="b2510-108">Level</span></span>|<span data-ttu-id="b2510-109">정보</span><span class="sxs-lookup"><span data-stu-id="b2510-109">Information</span></span>|  
|<span data-ttu-id="b2510-110">채널</span><span class="sxs-lookup"><span data-stu-id="b2510-110">Channel</span></span>|<span data-ttu-id="b2510-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="b2510-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b2510-112">설명</span><span class="sxs-lookup"><span data-stu-id="b2510-112">Description</span></span>  
 <span data-ttu-id="b2510-113">CacheMetadata 단계 중 InvokeMethod 작업에서 호출할 메서드가 정적이 아님을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b2510-113">During CacheMetadata step, InvokeMethod activity indicates the method to be invoked is not static.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b2510-114">메시지</span><span class="sxs-lookup"><span data-stu-id="b2510-114">Message</span></span>  
 <span data-ttu-id="b2510-115">InvokeMethod ''%1' - 메서드가 Static이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="b2510-115">InvokeMethod '%1' - method is not Static.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b2510-116">설명</span><span class="sxs-lookup"><span data-stu-id="b2510-116">Details</span></span>  
  
|<span data-ttu-id="b2510-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="b2510-117">Data Item Name</span></span>|<span data-ttu-id="b2510-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="b2510-118">Data Item Type</span></span>|<span data-ttu-id="b2510-119">설명</span><span class="sxs-lookup"><span data-stu-id="b2510-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b2510-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="b2510-120">InvokeMethod</span></span>|<span data-ttu-id="b2510-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="b2510-121">xs:string</span></span>|<span data-ttu-id="b2510-122">InvokeMethod 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b2510-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="b2510-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b2510-123">AppDomain</span></span>|<span data-ttu-id="b2510-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="b2510-124">xs:string</span></span>|<span data-ttu-id="b2510-125">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="b2510-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
