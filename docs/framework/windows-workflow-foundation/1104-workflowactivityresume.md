---
title: 1104 - WorkflowActivityResume
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7fe95d1e-34bd-43ca-b92e-587d2d248fff
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 029b1832259451beb458f8cbed4b0a3c44fdc490
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="1104---workflowactivityresume"></a><span data-ttu-id="a1f3f-102">1104 - WorkflowActivityResume</span><span class="sxs-lookup"><span data-stu-id="a1f3f-102">1104 - WorkflowActivityResume</span></span>
## <a name="properties"></a><span data-ttu-id="a1f3f-103">속성</span><span class="sxs-lookup"><span data-stu-id="a1f3f-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a1f3f-104">ID</span><span class="sxs-lookup"><span data-stu-id="a1f3f-104">ID</span></span>|<span data-ttu-id="a1f3f-105">1104</span><span class="sxs-lookup"><span data-stu-id="a1f3f-105">1104</span></span>|  
|<span data-ttu-id="a1f3f-106">키워드</span><span class="sxs-lookup"><span data-stu-id="a1f3f-106">Keywords</span></span>|<span data-ttu-id="a1f3f-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="a1f3f-107">WFRuntime</span></span>|  
|<span data-ttu-id="a1f3f-108">수준</span><span class="sxs-lookup"><span data-stu-id="a1f3f-108">Level</span></span>|<span data-ttu-id="a1f3f-109">정보</span><span class="sxs-lookup"><span data-stu-id="a1f3f-109">Information</span></span>|  
|<span data-ttu-id="a1f3f-110">채널</span><span class="sxs-lookup"><span data-stu-id="a1f3f-110">Channel</span></span>|<span data-ttu-id="a1f3f-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="a1f3f-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a1f3f-112">설명</span><span class="sxs-lookup"><span data-stu-id="a1f3f-112">Description</span></span>  
 <span data-ttu-id="a1f3f-113">워크플로 작업이 다시 시작되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a1f3f-113">Indicates a workflow activity has been resumed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a1f3f-114">메시지</span><span class="sxs-lookup"><span data-stu-id="a1f3f-114">Message</span></span>  
 <span data-ttu-id="a1f3f-115">WorkflowInstance Id: '%1' E2E 작업</span><span class="sxs-lookup"><span data-stu-id="a1f3f-115">WorkflowInstance Id: '%1' E2E Activity</span></span>  
  
## <a name="details"></a><span data-ttu-id="a1f3f-116">설명</span><span class="sxs-lookup"><span data-stu-id="a1f3f-116">Details</span></span>  
  
|<span data-ttu-id="a1f3f-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="a1f3f-117">Data Item Name</span></span>|<span data-ttu-id="a1f3f-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="a1f3f-118">Data Item Type</span></span>|<span data-ttu-id="a1f3f-119">설명</span><span class="sxs-lookup"><span data-stu-id="a1f3f-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a1f3f-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="a1f3f-120">WorkflowInstanceId</span></span>|<span data-ttu-id="a1f3f-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="a1f3f-121">xs:string</span></span>|<span data-ttu-id="a1f3f-122">워크플로 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="a1f3f-122">The workflow instance id.</span></span>|  
|<span data-ttu-id="a1f3f-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="a1f3f-123">AppDomain</span></span>|<span data-ttu-id="a1f3f-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="a1f3f-124">xs:string</span></span>|<span data-ttu-id="a1f3f-125">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="a1f3f-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
