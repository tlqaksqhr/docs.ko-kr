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
ms.workload: dotnet
ms.openlocfilehash: e3f025be90a997839eec2edfea12a099b4c58f0b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="1002---workflowapplicationterminated"></a><span data-ttu-id="a5354-102">1002 - WorkflowApplicationTerminated</span><span class="sxs-lookup"><span data-stu-id="a5354-102">1002 - WorkflowApplicationTerminated</span></span>
## <a name="properties"></a><span data-ttu-id="a5354-103">속성</span><span class="sxs-lookup"><span data-stu-id="a5354-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a5354-104">ID</span><span class="sxs-lookup"><span data-stu-id="a5354-104">ID</span></span>|<span data-ttu-id="a5354-105">1002</span><span class="sxs-lookup"><span data-stu-id="a5354-105">1002</span></span>|  
|<span data-ttu-id="a5354-106">키워드</span><span class="sxs-lookup"><span data-stu-id="a5354-106">Keywords</span></span>|<span data-ttu-id="a5354-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="a5354-107">WFRuntime</span></span>|  
|<span data-ttu-id="a5354-108">수준</span><span class="sxs-lookup"><span data-stu-id="a5354-108">Level</span></span>|<span data-ttu-id="a5354-109">정보</span><span class="sxs-lookup"><span data-stu-id="a5354-109">Information</span></span>|  
|<span data-ttu-id="a5354-110">채널</span><span class="sxs-lookup"><span data-stu-id="a5354-110">Channel</span></span>|<span data-ttu-id="a5354-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="a5354-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a5354-112">설명</span><span class="sxs-lookup"><span data-stu-id="a5354-112">Description</span></span>  
 <span data-ttu-id="a5354-113">워크플로 응용 프로그램에 예외가 발생하여 오류 상태로 종료되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a5354-113">Indicates a workflow application has terminated in the Faulted state with an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a5354-114">메시지</span><span class="sxs-lookup"><span data-stu-id="a5354-114">Message</span></span>  
 <span data-ttu-id="a5354-115">WorkflowApplication Id: '%1'이(가) 종료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a5354-115">WorkflowApplication Id: '%1' was terminated.</span></span> <span data-ttu-id="a5354-116">예외가 발생하여 오류 상태로 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a5354-116">It has completed in the Faulted state with an exception.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a5354-117">설명</span><span class="sxs-lookup"><span data-stu-id="a5354-117">Details</span></span>  
  
|<span data-ttu-id="a5354-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="a5354-118">Data Item Name</span></span>|<span data-ttu-id="a5354-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="a5354-119">Data Item Type</span></span>|<span data-ttu-id="a5354-120">설명</span><span class="sxs-lookup"><span data-stu-id="a5354-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a5354-121">WorkflowApplicationId</span><span class="sxs-lookup"><span data-stu-id="a5354-121">WorkflowApplicationId</span></span>|`xs:string`|<span data-ttu-id="a5354-122">워크플로 응용 프로그램 ID</span><span class="sxs-lookup"><span data-stu-id="a5354-122">The workflow application id</span></span>|  
|<span data-ttu-id="a5354-123">예외</span><span class="sxs-lookup"><span data-stu-id="a5354-123">Exception</span></span>|`xs:string`|<span data-ttu-id="a5354-124">예외에 대한 예외 정보</span><span class="sxs-lookup"><span data-stu-id="a5354-124">The exception details for the exception</span></span>|  
|<span data-ttu-id="a5354-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="a5354-125">AppDomain</span></span>|`xs:string`|<span data-ttu-id="a5354-126">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="a5354-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
