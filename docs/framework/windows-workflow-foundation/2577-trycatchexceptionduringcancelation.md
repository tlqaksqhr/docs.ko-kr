---
title: 2577 - TryCatchExceptionDuringCancelation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 35ee9f55-227f-4566-bcb4-4c7c75dea85b
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 11781bcab37a5034f3bbfadf2c50cbc1c6d378a2
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="2577---trycatchexceptionduringcancelation"></a><span data-ttu-id="776de-102">2577 - TryCatchExceptionDuringCancelation</span><span class="sxs-lookup"><span data-stu-id="776de-102">2577 - TryCatchExceptionDuringCancelation</span></span>
## <a name="properties"></a><span data-ttu-id="776de-103">속성</span><span class="sxs-lookup"><span data-stu-id="776de-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="776de-104">ID</span><span class="sxs-lookup"><span data-stu-id="776de-104">ID</span></span>|<span data-ttu-id="776de-105">2577</span><span class="sxs-lookup"><span data-stu-id="776de-105">2577</span></span>|  
|<span data-ttu-id="776de-106">키워드</span><span class="sxs-lookup"><span data-stu-id="776de-106">Keywords</span></span>|<span data-ttu-id="776de-107">WFActivities</span><span class="sxs-lookup"><span data-stu-id="776de-107">WFActivities</span></span>|  
|<span data-ttu-id="776de-108">수준</span><span class="sxs-lookup"><span data-stu-id="776de-108">Level</span></span>|<span data-ttu-id="776de-109">경고</span><span class="sxs-lookup"><span data-stu-id="776de-109">Warning</span></span>|  
|<span data-ttu-id="776de-110">채널</span><span class="sxs-lookup"><span data-stu-id="776de-110">Channel</span></span>|<span data-ttu-id="776de-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="776de-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="776de-112">설명</span><span class="sxs-lookup"><span data-stu-id="776de-112">Description</span></span>  
 <span data-ttu-id="776de-113">취소하는 동안 TryCatch 작업의 자식 작업에서 예외가 throw되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="776de-113">Indicates a child activity of the TryCatch activity has thrown an exception during cancelation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="776de-114">메시지</span><span class="sxs-lookup"><span data-stu-id="776de-114">Message</span></span>  
 <span data-ttu-id="776de-115">취소하는 동안 TryCatch 작업 '%1'의 자식 작업에서 예외가 throw되었습니다.</span><span class="sxs-lookup"><span data-stu-id="776de-115">A child activity of the TryCatch activity '%1' has thrown an exception during cancelation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="776de-116">설명</span><span class="sxs-lookup"><span data-stu-id="776de-116">Details</span></span>  
  
|<span data-ttu-id="776de-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="776de-117">Data Item Name</span></span>|<span data-ttu-id="776de-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="776de-118">Data Item Type</span></span>|<span data-ttu-id="776de-119">설명</span><span class="sxs-lookup"><span data-stu-id="776de-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="776de-120">DisplayName</span><span class="sxs-lookup"><span data-stu-id="776de-120">DisplayName</span></span>|<span data-ttu-id="776de-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="776de-121">xs:string</span></span>|<span data-ttu-id="776de-122">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="776de-122">The display name of the activity.</span></span>|  
|<span data-ttu-id="776de-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="776de-123">AppDomain</span></span>|<span data-ttu-id="776de-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="776de-124">xs:string</span></span>|<span data-ttu-id="776de-125">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="776de-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
