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
ms.workload: dotnet
ms.openlocfilehash: 7d38009ea0f384319938204cae41f64a71203731
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="1104---workflowactivityresume"></a><span data-ttu-id="67c2c-102">1104 - WorkflowActivityResume</span><span class="sxs-lookup"><span data-stu-id="67c2c-102">1104 - WorkflowActivityResume</span></span>
## <a name="properties"></a><span data-ttu-id="67c2c-103">속성</span><span class="sxs-lookup"><span data-stu-id="67c2c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="67c2c-104">ID</span><span class="sxs-lookup"><span data-stu-id="67c2c-104">ID</span></span>|<span data-ttu-id="67c2c-105">1104</span><span class="sxs-lookup"><span data-stu-id="67c2c-105">1104</span></span>|  
|<span data-ttu-id="67c2c-106">키워드</span><span class="sxs-lookup"><span data-stu-id="67c2c-106">Keywords</span></span>|<span data-ttu-id="67c2c-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="67c2c-107">WFRuntime</span></span>|  
|<span data-ttu-id="67c2c-108">수준</span><span class="sxs-lookup"><span data-stu-id="67c2c-108">Level</span></span>|<span data-ttu-id="67c2c-109">정보</span><span class="sxs-lookup"><span data-stu-id="67c2c-109">Information</span></span>|  
|<span data-ttu-id="67c2c-110">채널</span><span class="sxs-lookup"><span data-stu-id="67c2c-110">Channel</span></span>|<span data-ttu-id="67c2c-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="67c2c-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="67c2c-112">설명</span><span class="sxs-lookup"><span data-stu-id="67c2c-112">Description</span></span>  
 <span data-ttu-id="67c2c-113">워크플로 작업이 다시 시작되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="67c2c-113">Indicates a workflow activity has been resumed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="67c2c-114">메시지</span><span class="sxs-lookup"><span data-stu-id="67c2c-114">Message</span></span>  
 <span data-ttu-id="67c2c-115">WorkflowInstance Id: '%1' E2E 작업</span><span class="sxs-lookup"><span data-stu-id="67c2c-115">WorkflowInstance Id: '%1' E2E Activity</span></span>  
  
## <a name="details"></a><span data-ttu-id="67c2c-116">설명</span><span class="sxs-lookup"><span data-stu-id="67c2c-116">Details</span></span>  
  
|<span data-ttu-id="67c2c-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="67c2c-117">Data Item Name</span></span>|<span data-ttu-id="67c2c-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="67c2c-118">Data Item Type</span></span>|<span data-ttu-id="67c2c-119">설명</span><span class="sxs-lookup"><span data-stu-id="67c2c-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="67c2c-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="67c2c-120">WorkflowInstanceId</span></span>|<span data-ttu-id="67c2c-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="67c2c-121">xs:string</span></span>|<span data-ttu-id="67c2c-122">워크플로 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="67c2c-122">The workflow instance id.</span></span>|  
|<span data-ttu-id="67c2c-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="67c2c-123">AppDomain</span></span>|<span data-ttu-id="67c2c-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="67c2c-124">xs:string</span></span>|<span data-ttu-id="67c2c-125">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="67c2c-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
