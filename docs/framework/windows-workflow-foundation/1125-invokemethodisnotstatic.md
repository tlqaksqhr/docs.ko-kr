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
ms.workload: dotnet
ms.openlocfilehash: c8b5e255e9a753c6476a070609b0cbda189d37a1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="1125---invokemethodisnotstatic"></a><span data-ttu-id="5b0b4-102">1125 - InvokeMethodIsNotStatic</span><span class="sxs-lookup"><span data-stu-id="5b0b4-102">1125 - InvokeMethodIsNotStatic</span></span>
## <a name="properties"></a><span data-ttu-id="5b0b4-103">속성</span><span class="sxs-lookup"><span data-stu-id="5b0b4-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5b0b4-104">ID</span><span class="sxs-lookup"><span data-stu-id="5b0b4-104">ID</span></span>|<span data-ttu-id="5b0b4-105">1125</span><span class="sxs-lookup"><span data-stu-id="5b0b4-105">1125</span></span>|  
|<span data-ttu-id="5b0b4-106">키워드</span><span class="sxs-lookup"><span data-stu-id="5b0b4-106">Keywords</span></span>|<span data-ttu-id="5b0b4-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="5b0b4-107">WFRuntime</span></span>|  
|<span data-ttu-id="5b0b4-108">수준</span><span class="sxs-lookup"><span data-stu-id="5b0b4-108">Level</span></span>|<span data-ttu-id="5b0b4-109">정보</span><span class="sxs-lookup"><span data-stu-id="5b0b4-109">Information</span></span>|  
|<span data-ttu-id="5b0b4-110">채널</span><span class="sxs-lookup"><span data-stu-id="5b0b4-110">Channel</span></span>|<span data-ttu-id="5b0b4-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="5b0b4-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="5b0b4-112">설명</span><span class="sxs-lookup"><span data-stu-id="5b0b4-112">Description</span></span>  
 <span data-ttu-id="5b0b4-113">CacheMetadata 단계 중 InvokeMethod 작업에서 호출할 메서드가 정적이 아님을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5b0b4-113">During CacheMetadata step, InvokeMethod activity indicates the method to be invoked is not static.</span></span>  
  
## <a name="message"></a><span data-ttu-id="5b0b4-114">메시지</span><span class="sxs-lookup"><span data-stu-id="5b0b4-114">Message</span></span>  
 <span data-ttu-id="5b0b4-115">InvokeMethod ''%1' - 메서드가 Static이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="5b0b4-115">InvokeMethod '%1' - method is not Static.</span></span>  
  
## <a name="details"></a><span data-ttu-id="5b0b4-116">설명</span><span class="sxs-lookup"><span data-stu-id="5b0b4-116">Details</span></span>  
  
|<span data-ttu-id="5b0b4-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="5b0b4-117">Data Item Name</span></span>|<span data-ttu-id="5b0b4-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="5b0b4-118">Data Item Type</span></span>|<span data-ttu-id="5b0b4-119">설명</span><span class="sxs-lookup"><span data-stu-id="5b0b4-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="5b0b4-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="5b0b4-120">InvokeMethod</span></span>|<span data-ttu-id="5b0b4-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="5b0b4-121">xs:string</span></span>|<span data-ttu-id="5b0b4-122">InvokeMethod 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5b0b4-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="5b0b4-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="5b0b4-123">AppDomain</span></span>|<span data-ttu-id="5b0b4-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="5b0b4-124">xs:string</span></span>|<span data-ttu-id="5b0b4-125">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="5b0b4-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
