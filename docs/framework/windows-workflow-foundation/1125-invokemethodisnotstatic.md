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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 934c2947e86b429e9b990c273f22c0511f209a53
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="1125---invokemethodisnotstatic"></a><span data-ttu-id="d8865-102">1125 - InvokeMethodIsNotStatic</span><span class="sxs-lookup"><span data-stu-id="d8865-102">1125 - InvokeMethodIsNotStatic</span></span>
## <a name="properties"></a><span data-ttu-id="d8865-103">속성</span><span class="sxs-lookup"><span data-stu-id="d8865-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d8865-104">ID</span><span class="sxs-lookup"><span data-stu-id="d8865-104">ID</span></span>|<span data-ttu-id="d8865-105">1125</span><span class="sxs-lookup"><span data-stu-id="d8865-105">1125</span></span>|  
|<span data-ttu-id="d8865-106">키워드</span><span class="sxs-lookup"><span data-stu-id="d8865-106">Keywords</span></span>|<span data-ttu-id="d8865-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="d8865-107">WFRuntime</span></span>|  
|<span data-ttu-id="d8865-108">수준</span><span class="sxs-lookup"><span data-stu-id="d8865-108">Level</span></span>|<span data-ttu-id="d8865-109">정보</span><span class="sxs-lookup"><span data-stu-id="d8865-109">Information</span></span>|  
|<span data-ttu-id="d8865-110">채널</span><span class="sxs-lookup"><span data-stu-id="d8865-110">Channel</span></span>|<span data-ttu-id="d8865-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="d8865-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d8865-112">설명</span><span class="sxs-lookup"><span data-stu-id="d8865-112">Description</span></span>  
 <span data-ttu-id="d8865-113">CacheMetadata 단계 중 InvokeMethod 작업에서 호출할 메서드가 정적이 아님을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d8865-113">During CacheMetadata step, InvokeMethod activity indicates the method to be invoked is not static.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d8865-114">메시지</span><span class="sxs-lookup"><span data-stu-id="d8865-114">Message</span></span>  
 <span data-ttu-id="d8865-115">InvokeMethod ''%1' - 메서드가 Static이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="d8865-115">InvokeMethod '%1' - method is not Static.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d8865-116">설명</span><span class="sxs-lookup"><span data-stu-id="d8865-116">Details</span></span>  
  
|<span data-ttu-id="d8865-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="d8865-117">Data Item Name</span></span>|<span data-ttu-id="d8865-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="d8865-118">Data Item Type</span></span>|<span data-ttu-id="d8865-119">설명</span><span class="sxs-lookup"><span data-stu-id="d8865-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d8865-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="d8865-120">InvokeMethod</span></span>|<span data-ttu-id="d8865-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="d8865-121">xs:string</span></span>|<span data-ttu-id="d8865-122">InvokeMethod 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d8865-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="d8865-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d8865-123">AppDomain</span></span>|<span data-ttu-id="d8865-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="d8865-124">xs:string</span></span>|<span data-ttu-id="d8865-125">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="d8865-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
