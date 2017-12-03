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
ms.openlocfilehash: a1021d7d23b8e9c25684da567b769c24380a8a0a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="1126---invokedmethodthrewexception"></a><span data-ttu-id="09b43-102">1126 - InvokedMethodThrewException</span><span class="sxs-lookup"><span data-stu-id="09b43-102">1126 - InvokedMethodThrewException</span></span>
## <a name="properties"></a><span data-ttu-id="09b43-103">속성</span><span class="sxs-lookup"><span data-stu-id="09b43-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="09b43-104">ID</span><span class="sxs-lookup"><span data-stu-id="09b43-104">ID</span></span>|<span data-ttu-id="09b43-105">1126</span><span class="sxs-lookup"><span data-stu-id="09b43-105">1126</span></span>|  
|<span data-ttu-id="09b43-106">키워드</span><span class="sxs-lookup"><span data-stu-id="09b43-106">Keywords</span></span>|<span data-ttu-id="09b43-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="09b43-107">WFRuntime</span></span>|  
|<span data-ttu-id="09b43-108">수준</span><span class="sxs-lookup"><span data-stu-id="09b43-108">Level</span></span>|<span data-ttu-id="09b43-109">정보</span><span class="sxs-lookup"><span data-stu-id="09b43-109">Information</span></span>|  
|<span data-ttu-id="09b43-110">채널</span><span class="sxs-lookup"><span data-stu-id="09b43-110">Channel</span></span>|<span data-ttu-id="09b43-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="09b43-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="09b43-112">설명</span><span class="sxs-lookup"><span data-stu-id="09b43-112">Description</span></span>  
 <span data-ttu-id="09b43-113">InvokeMethod 작업에서 호출된 메서드에서 예외가 throw되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="09b43-113">Indicates an exception was thrown by the method called by the InvokeMethod activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="09b43-114">메시지</span><span class="sxs-lookup"><span data-stu-id="09b43-114">Message</span></span>  
 <span data-ttu-id="09b43-115">작업 '%1'에서 호출된 메서드에서 예외가 throw되었습니다.</span><span class="sxs-lookup"><span data-stu-id="09b43-115">An exception was thrown in the method called by the activity '%1'.</span></span> <span data-ttu-id="09b43-116">%2</span><span class="sxs-lookup"><span data-stu-id="09b43-116">%2</span></span>  
  
## <a name="details"></a><span data-ttu-id="09b43-117">설명</span><span class="sxs-lookup"><span data-stu-id="09b43-117">Details</span></span>  
  
|<span data-ttu-id="09b43-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="09b43-118">Data Item Name</span></span>|<span data-ttu-id="09b43-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="09b43-119">Data Item Type</span></span>|<span data-ttu-id="09b43-120">설명</span><span class="sxs-lookup"><span data-stu-id="09b43-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="09b43-121">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="09b43-121">InvokeMethod</span></span>|<span data-ttu-id="09b43-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="09b43-122">xs:string</span></span>|<span data-ttu-id="09b43-123">InvokeMethod 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="09b43-123">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="09b43-124">예외</span><span class="sxs-lookup"><span data-stu-id="09b43-124">Exception</span></span>|<span data-ttu-id="09b43-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="09b43-125">xs:string</span></span>|<span data-ttu-id="09b43-126">예외에 대한 예외 정보</span><span class="sxs-lookup"><span data-stu-id="09b43-126">The exception details for the exception</span></span>|  
|<span data-ttu-id="09b43-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="09b43-127">AppDomain</span></span>|<span data-ttu-id="09b43-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="09b43-128">xs:string</span></span>|<span data-ttu-id="09b43-129">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="09b43-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
