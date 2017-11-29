---
title: 1131 - InvokeMethodUseAsyncPattern
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eca50fa7-5276-4759-ad1c-e490b9bd1f82
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6f9f8f4e836d5c5b437edcfaff6460c7b97210ce
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="1131---invokemethoduseasyncpattern"></a><span data-ttu-id="45359-102">1131 - InvokeMethodUseAsyncPattern</span><span class="sxs-lookup"><span data-stu-id="45359-102">1131 - InvokeMethodUseAsyncPattern</span></span>
## <a name="properties"></a><span data-ttu-id="45359-103">속성</span><span class="sxs-lookup"><span data-stu-id="45359-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="45359-104">ID</span><span class="sxs-lookup"><span data-stu-id="45359-104">ID</span></span>|<span data-ttu-id="45359-105">1131</span><span class="sxs-lookup"><span data-stu-id="45359-105">1131</span></span>|  
|<span data-ttu-id="45359-106">키워드</span><span class="sxs-lookup"><span data-stu-id="45359-106">Keywords</span></span>|<span data-ttu-id="45359-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="45359-107">WFRuntime</span></span>|  
|<span data-ttu-id="45359-108">수준</span><span class="sxs-lookup"><span data-stu-id="45359-108">Level</span></span>|<span data-ttu-id="45359-109">정보</span><span class="sxs-lookup"><span data-stu-id="45359-109">Information</span></span>|  
|<span data-ttu-id="45359-110">채널</span><span class="sxs-lookup"><span data-stu-id="45359-110">Channel</span></span>|<span data-ttu-id="45359-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="45359-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="45359-112">설명</span><span class="sxs-lookup"><span data-stu-id="45359-112">Description</span></span>  
 <span data-ttu-id="45359-113">CacheMetadata 단계 중 InvokeMethod 작업에서 메서드를 호출할 때 비동기 패턴을 사용함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="45359-113">During CacheMetadata step, InvokeMethod activity indicates that it is using the async pattern when invoking the method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="45359-114">메시지</span><span class="sxs-lookup"><span data-stu-id="45359-114">Message</span></span>  
 <span data-ttu-id="45359-115">InvokeMethod '%1'' - 메서드에서 ''%2' 및 '%3'의 비동기 패턴을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="45359-115">InvokeMethod '%1' - method uses asynchronous pattern of '%2' and '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="45359-116">설명</span><span class="sxs-lookup"><span data-stu-id="45359-116">Details</span></span>  
  
|<span data-ttu-id="45359-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="45359-117">Data Item Name</span></span>|<span data-ttu-id="45359-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="45359-118">Data Item Type</span></span>|<span data-ttu-id="45359-119">설명</span><span class="sxs-lookup"><span data-stu-id="45359-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="45359-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="45359-120">InvokeMethod</span></span>|<span data-ttu-id="45359-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="45359-121">xs:string</span></span>|<span data-ttu-id="45359-122">InvokeMethod 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="45359-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="45359-123">BeginMethod</span><span class="sxs-lookup"><span data-stu-id="45359-123">BeginMethod</span></span>|<span data-ttu-id="45359-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="45359-124">xs:string</span></span>|<span data-ttu-id="45359-125">Begin 메서드의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="45359-125">The name of the begin method.</span></span>|  
|<span data-ttu-id="45359-126">EndMethod</span><span class="sxs-lookup"><span data-stu-id="45359-126">EndMethod</span></span>|<span data-ttu-id="45359-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="45359-127">xs:string</span></span>|<span data-ttu-id="45359-128">End 메서드의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="45359-128">The name of the end method.</span></span>|  
|<span data-ttu-id="45359-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="45359-129">AppDomain</span></span>|<span data-ttu-id="45359-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="45359-130">xs:string</span></span>|<span data-ttu-id="45359-131">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="45359-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
