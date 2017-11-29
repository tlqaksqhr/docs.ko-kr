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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b11c2f167ce7afce992cddb2f32f840212d4ac8d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="1126---invokedmethodthrewexception"></a><span data-ttu-id="e0d91-102">1126 - InvokedMethodThrewException</span><span class="sxs-lookup"><span data-stu-id="e0d91-102">1126 - InvokedMethodThrewException</span></span>
## <a name="properties"></a><span data-ttu-id="e0d91-103">속성</span><span class="sxs-lookup"><span data-stu-id="e0d91-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e0d91-104">ID</span><span class="sxs-lookup"><span data-stu-id="e0d91-104">ID</span></span>|<span data-ttu-id="e0d91-105">1126</span><span class="sxs-lookup"><span data-stu-id="e0d91-105">1126</span></span>|  
|<span data-ttu-id="e0d91-106">키워드</span><span class="sxs-lookup"><span data-stu-id="e0d91-106">Keywords</span></span>|<span data-ttu-id="e0d91-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="e0d91-107">WFRuntime</span></span>|  
|<span data-ttu-id="e0d91-108">수준</span><span class="sxs-lookup"><span data-stu-id="e0d91-108">Level</span></span>|<span data-ttu-id="e0d91-109">정보</span><span class="sxs-lookup"><span data-stu-id="e0d91-109">Information</span></span>|  
|<span data-ttu-id="e0d91-110">채널</span><span class="sxs-lookup"><span data-stu-id="e0d91-110">Channel</span></span>|<span data-ttu-id="e0d91-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="e0d91-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e0d91-112">설명</span><span class="sxs-lookup"><span data-stu-id="e0d91-112">Description</span></span>  
 <span data-ttu-id="e0d91-113">InvokeMethod 작업에서 호출된 메서드에서 예외가 throw되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e0d91-113">Indicates an exception was thrown by the method called by the InvokeMethod activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e0d91-114">메시지</span><span class="sxs-lookup"><span data-stu-id="e0d91-114">Message</span></span>  
 <span data-ttu-id="e0d91-115">작업 '%1'에서 호출된 메서드에서 예외가 throw되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e0d91-115">An exception was thrown in the method called by the activity '%1'.</span></span> <span data-ttu-id="e0d91-116">%2</span><span class="sxs-lookup"><span data-stu-id="e0d91-116">%2</span></span>  
  
## <a name="details"></a><span data-ttu-id="e0d91-117">설명</span><span class="sxs-lookup"><span data-stu-id="e0d91-117">Details</span></span>  
  
|<span data-ttu-id="e0d91-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="e0d91-118">Data Item Name</span></span>|<span data-ttu-id="e0d91-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="e0d91-119">Data Item Type</span></span>|<span data-ttu-id="e0d91-120">설명</span><span class="sxs-lookup"><span data-stu-id="e0d91-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e0d91-121">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="e0d91-121">InvokeMethod</span></span>|<span data-ttu-id="e0d91-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="e0d91-122">xs:string</span></span>|<span data-ttu-id="e0d91-123">InvokeMethod 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e0d91-123">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="e0d91-124">예외</span><span class="sxs-lookup"><span data-stu-id="e0d91-124">Exception</span></span>|<span data-ttu-id="e0d91-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="e0d91-125">xs:string</span></span>|<span data-ttu-id="e0d91-126">예외에 대한 예외 정보</span><span class="sxs-lookup"><span data-stu-id="e0d91-126">The exception details for the exception</span></span>|  
|<span data-ttu-id="e0d91-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="e0d91-127">AppDomain</span></span>|<span data-ttu-id="e0d91-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="e0d91-128">xs:string</span></span>|<span data-ttu-id="e0d91-129">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="e0d91-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
