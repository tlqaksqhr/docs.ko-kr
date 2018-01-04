---
title: 1041 - WorkflowApplicationPersistableIdle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 966adf2f-e21d-44df-a3ec-a8e285e0a316
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1efc32ed0304d5b0d222054e5c65abe279ef93ae
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="1041---workflowapplicationpersistableidle"></a><span data-ttu-id="0f2c0-102">1041 - WorkflowApplicationPersistableIdle</span><span class="sxs-lookup"><span data-stu-id="0f2c0-102">1041 - WorkflowApplicationPersistableIdle</span></span>
## <a name="properties"></a><span data-ttu-id="0f2c0-103">속성</span><span class="sxs-lookup"><span data-stu-id="0f2c0-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0f2c0-104">ID</span><span class="sxs-lookup"><span data-stu-id="0f2c0-104">ID</span></span>|<span data-ttu-id="0f2c0-105">1041</span><span class="sxs-lookup"><span data-stu-id="0f2c0-105">1041</span></span>|  
|<span data-ttu-id="0f2c0-106">키워드</span><span class="sxs-lookup"><span data-stu-id="0f2c0-106">Keywords</span></span>|<span data-ttu-id="0f2c0-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="0f2c0-107">WFRuntime</span></span>|  
|<span data-ttu-id="0f2c0-108">수준</span><span class="sxs-lookup"><span data-stu-id="0f2c0-108">Level</span></span>|<span data-ttu-id="0f2c0-109">정보</span><span class="sxs-lookup"><span data-stu-id="0f2c0-109">Information</span></span>|  
|<span data-ttu-id="0f2c0-110">채널</span><span class="sxs-lookup"><span data-stu-id="0f2c0-110">Channel</span></span>|<span data-ttu-id="0f2c0-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="0f2c0-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0f2c0-112">설명</span><span class="sxs-lookup"><span data-stu-id="0f2c0-112">Description</span></span>  
 <span data-ttu-id="0f2c0-113">워크플로 응용 프로그램이 유휴 상태이며 지속 가능함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0f2c0-113">Indicates that a workflow application is idle and persistable.</span></span> <span data-ttu-id="0f2c0-114">워크플로 응용 프로그램이 유휴 상태이거나 지속됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f2c0-114">The workflow application will be idled or persisted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0f2c0-115">메시지</span><span class="sxs-lookup"><span data-stu-id="0f2c0-115">Message</span></span>  
 <span data-ttu-id="0f2c0-116">WorkflowApplication Id: '%1'는 유휴 상태로 지속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f2c0-116">WorkflowApplication Id: '%1' is idle and persistable.</span></span>  <span data-ttu-id="0f2c0-117">다음과 같은 조치가 취해집니다: %2입니다.</span><span class="sxs-lookup"><span data-stu-id="0f2c0-117">The following action will be taken: %2.</span></span>  
  
## <a name="details"></a><span data-ttu-id="0f2c0-118">설명</span><span class="sxs-lookup"><span data-stu-id="0f2c0-118">Details</span></span>  
  
|<span data-ttu-id="0f2c0-119">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="0f2c0-119">Data Item Name</span></span>|<span data-ttu-id="0f2c0-120">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="0f2c0-120">Data Item Type</span></span>|<span data-ttu-id="0f2c0-121">설명</span><span class="sxs-lookup"><span data-stu-id="0f2c0-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0f2c0-122">WorkflowApplicationId</span><span class="sxs-lookup"><span data-stu-id="0f2c0-122">WorkflowApplicationId</span></span>|<span data-ttu-id="0f2c0-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="0f2c0-123">xs:string</span></span>|<span data-ttu-id="0f2c0-124">워크플로 응용 프로그램 ID</span><span class="sxs-lookup"><span data-stu-id="0f2c0-124">The workflow application id</span></span>|  
|<span data-ttu-id="0f2c0-125">ActionTaken</span><span class="sxs-lookup"><span data-stu-id="0f2c0-125">ActionTaken</span></span>|<span data-ttu-id="0f2c0-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="0f2c0-126">xs:string</span></span>|<span data-ttu-id="0f2c0-127">작업이 워크플로 응용 프로그램에서 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="0f2c0-127">The action that will be taken on the workflow application.</span></span>|  
|<span data-ttu-id="0f2c0-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="0f2c0-128">AppDomain</span></span>|<span data-ttu-id="0f2c0-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="0f2c0-129">xs:string</span></span>|<span data-ttu-id="0f2c0-130">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="0f2c0-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
