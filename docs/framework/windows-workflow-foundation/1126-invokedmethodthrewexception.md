---
title: 1126 - InvokedMethodThrewException
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0d3cff1a-97e6-4b6c-be18-108c6881bfc0
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5dc752a5c9d5bebe39a4d4be2c3642333aa041de
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="1126---invokedmethodthrewexception"></a><span data-ttu-id="2a809-102">1126 - InvokedMethodThrewException</span><span class="sxs-lookup"><span data-stu-id="2a809-102">1126 - InvokedMethodThrewException</span></span>
## <a name="properties"></a><span data-ttu-id="2a809-103">속성</span><span class="sxs-lookup"><span data-stu-id="2a809-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2a809-104">ID</span><span class="sxs-lookup"><span data-stu-id="2a809-104">ID</span></span>|<span data-ttu-id="2a809-105">1126</span><span class="sxs-lookup"><span data-stu-id="2a809-105">1126</span></span>|  
|<span data-ttu-id="2a809-106">키워드</span><span class="sxs-lookup"><span data-stu-id="2a809-106">Keywords</span></span>|<span data-ttu-id="2a809-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="2a809-107">WFRuntime</span></span>|  
|<span data-ttu-id="2a809-108">수준</span><span class="sxs-lookup"><span data-stu-id="2a809-108">Level</span></span>|<span data-ttu-id="2a809-109">정보</span><span class="sxs-lookup"><span data-stu-id="2a809-109">Information</span></span>|  
|<span data-ttu-id="2a809-110">채널</span><span class="sxs-lookup"><span data-stu-id="2a809-110">Channel</span></span>|<span data-ttu-id="2a809-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="2a809-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2a809-112">설명</span><span class="sxs-lookup"><span data-stu-id="2a809-112">Description</span></span>  
 <span data-ttu-id="2a809-113">InvokeMethod 작업에서 호출된 메서드에서 예외가 throw되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2a809-113">Indicates an exception was thrown by the method called by the InvokeMethod activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2a809-114">메시지</span><span class="sxs-lookup"><span data-stu-id="2a809-114">Message</span></span>  
 <span data-ttu-id="2a809-115">작업 '%1'에서 호출된 메서드에서 예외가 throw되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2a809-115">An exception was thrown in the method called by the activity '%1'.</span></span> <span data-ttu-id="2a809-116">%2</span><span class="sxs-lookup"><span data-stu-id="2a809-116">%2</span></span>  
  
## <a name="details"></a><span data-ttu-id="2a809-117">설명</span><span class="sxs-lookup"><span data-stu-id="2a809-117">Details</span></span>  
  
|<span data-ttu-id="2a809-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="2a809-118">Data Item Name</span></span>|<span data-ttu-id="2a809-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="2a809-119">Data Item Type</span></span>|<span data-ttu-id="2a809-120">설명</span><span class="sxs-lookup"><span data-stu-id="2a809-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="2a809-121">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="2a809-121">InvokeMethod</span></span>|<span data-ttu-id="2a809-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="2a809-122">xs:string</span></span>|<span data-ttu-id="2a809-123">InvokeMethod 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2a809-123">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="2a809-124">예외</span><span class="sxs-lookup"><span data-stu-id="2a809-124">Exception</span></span>|<span data-ttu-id="2a809-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="2a809-125">xs:string</span></span>|<span data-ttu-id="2a809-126">예외에 대한 예외 정보</span><span class="sxs-lookup"><span data-stu-id="2a809-126">The exception details for the exception</span></span>|  
|<span data-ttu-id="2a809-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="2a809-127">AppDomain</span></span>|<span data-ttu-id="2a809-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="2a809-128">xs:string</span></span>|<span data-ttu-id="2a809-129">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="2a809-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
