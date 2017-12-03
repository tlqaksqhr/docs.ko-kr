---
title: 1002 - WorkflowApplicationTerminated
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4e8b111f-79dc-4898-bb4a-e9b36f69420f
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 93a6a400576df84faae3cd58940462255b0073c6
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="1002---workflowapplicationterminated"></a><span data-ttu-id="1cf85-102">1002 - WorkflowApplicationTerminated</span><span class="sxs-lookup"><span data-stu-id="1cf85-102">1002 - WorkflowApplicationTerminated</span></span>
## <a name="properties"></a><span data-ttu-id="1cf85-103">속성</span><span class="sxs-lookup"><span data-stu-id="1cf85-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1cf85-104">ID</span><span class="sxs-lookup"><span data-stu-id="1cf85-104">ID</span></span>|<span data-ttu-id="1cf85-105">1002</span><span class="sxs-lookup"><span data-stu-id="1cf85-105">1002</span></span>|  
|<span data-ttu-id="1cf85-106">키워드</span><span class="sxs-lookup"><span data-stu-id="1cf85-106">Keywords</span></span>|<span data-ttu-id="1cf85-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="1cf85-107">WFRuntime</span></span>|  
|<span data-ttu-id="1cf85-108">수준</span><span class="sxs-lookup"><span data-stu-id="1cf85-108">Level</span></span>|<span data-ttu-id="1cf85-109">정보</span><span class="sxs-lookup"><span data-stu-id="1cf85-109">Information</span></span>|  
|<span data-ttu-id="1cf85-110">채널</span><span class="sxs-lookup"><span data-stu-id="1cf85-110">Channel</span></span>|<span data-ttu-id="1cf85-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="1cf85-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="1cf85-112">설명</span><span class="sxs-lookup"><span data-stu-id="1cf85-112">Description</span></span>  
 <span data-ttu-id="1cf85-113">워크플로 응용 프로그램에 예외가 발생하여 오류 상태로 종료되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1cf85-113">Indicates a workflow application has terminated in the Faulted state with an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="1cf85-114">메시지</span><span class="sxs-lookup"><span data-stu-id="1cf85-114">Message</span></span>  
 <span data-ttu-id="1cf85-115">WorkflowApplication Id: '%1'이(가) 종료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1cf85-115">WorkflowApplication Id: '%1' was terminated.</span></span> <span data-ttu-id="1cf85-116">예외가 발생하여 오류 상태로 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1cf85-116">It has completed in the Faulted state with an exception.</span></span>  
  
## <a name="details"></a><span data-ttu-id="1cf85-117">설명</span><span class="sxs-lookup"><span data-stu-id="1cf85-117">Details</span></span>  
  
|<span data-ttu-id="1cf85-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="1cf85-118">Data Item Name</span></span>|<span data-ttu-id="1cf85-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="1cf85-119">Data Item Type</span></span>|<span data-ttu-id="1cf85-120">설명</span><span class="sxs-lookup"><span data-stu-id="1cf85-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="1cf85-121">WorkflowApplicationId</span><span class="sxs-lookup"><span data-stu-id="1cf85-121">WorkflowApplicationId</span></span>|`xs:string`|<span data-ttu-id="1cf85-122">워크플로 응용 프로그램 ID</span><span class="sxs-lookup"><span data-stu-id="1cf85-122">The workflow application id</span></span>|  
|<span data-ttu-id="1cf85-123">예외</span><span class="sxs-lookup"><span data-stu-id="1cf85-123">Exception</span></span>|`xs:string`|<span data-ttu-id="1cf85-124">예외에 대한 예외 정보</span><span class="sxs-lookup"><span data-stu-id="1cf85-124">The exception details for the exception</span></span>|  
|<span data-ttu-id="1cf85-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="1cf85-125">AppDomain</span></span>|`xs:string`|<span data-ttu-id="1cf85-126">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="1cf85-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
