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
ms.openlocfilehash: b321f8c20fbd79b5e748601ee06f975dc75a7d56
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="1041---workflowapplicationpersistableidle"></a><span data-ttu-id="3f884-102">1041 - WorkflowApplicationPersistableIdle</span><span class="sxs-lookup"><span data-stu-id="3f884-102">1041 - WorkflowApplicationPersistableIdle</span></span>
## <a name="properties"></a><span data-ttu-id="3f884-103">속성</span><span class="sxs-lookup"><span data-stu-id="3f884-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3f884-104">ID</span><span class="sxs-lookup"><span data-stu-id="3f884-104">ID</span></span>|<span data-ttu-id="3f884-105">1041</span><span class="sxs-lookup"><span data-stu-id="3f884-105">1041</span></span>|  
|<span data-ttu-id="3f884-106">키워드</span><span class="sxs-lookup"><span data-stu-id="3f884-106">Keywords</span></span>|<span data-ttu-id="3f884-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="3f884-107">WFRuntime</span></span>|  
|<span data-ttu-id="3f884-108">수준</span><span class="sxs-lookup"><span data-stu-id="3f884-108">Level</span></span>|<span data-ttu-id="3f884-109">정보</span><span class="sxs-lookup"><span data-stu-id="3f884-109">Information</span></span>|  
|<span data-ttu-id="3f884-110">채널</span><span class="sxs-lookup"><span data-stu-id="3f884-110">Channel</span></span>|<span data-ttu-id="3f884-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="3f884-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3f884-112">설명</span><span class="sxs-lookup"><span data-stu-id="3f884-112">Description</span></span>  
 <span data-ttu-id="3f884-113">워크플로 응용 프로그램이 유휴 상태이며 지속 가능함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3f884-113">Indicates that a workflow application is idle and persistable.</span></span> <span data-ttu-id="3f884-114">워크플로 응용 프로그램이 유휴 상태이거나 지속됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f884-114">The workflow application will be idled or persisted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3f884-115">메시지</span><span class="sxs-lookup"><span data-stu-id="3f884-115">Message</span></span>  
 <span data-ttu-id="3f884-116">WorkflowApplication Id: '%1'는 유휴 상태로 지속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f884-116">WorkflowApplication Id: '%1' is idle and persistable.</span></span>  <span data-ttu-id="3f884-117">다음과 같은 조치가 취해집니다: %2입니다.</span><span class="sxs-lookup"><span data-stu-id="3f884-117">The following action will be taken: %2.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3f884-118">세부 정보</span><span class="sxs-lookup"><span data-stu-id="3f884-118">Details</span></span>  
  
|<span data-ttu-id="3f884-119">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="3f884-119">Data Item Name</span></span>|<span data-ttu-id="3f884-120">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="3f884-120">Data Item Type</span></span>|<span data-ttu-id="3f884-121">설명</span><span class="sxs-lookup"><span data-stu-id="3f884-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3f884-122">WorkflowApplicationId</span><span class="sxs-lookup"><span data-stu-id="3f884-122">WorkflowApplicationId</span></span>|<span data-ttu-id="3f884-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="3f884-123">xs:string</span></span>|<span data-ttu-id="3f884-124">워크플로 응용 프로그램 ID</span><span class="sxs-lookup"><span data-stu-id="3f884-124">The workflow application id</span></span>|  
|<span data-ttu-id="3f884-125">ActionTaken</span><span class="sxs-lookup"><span data-stu-id="3f884-125">ActionTaken</span></span>|<span data-ttu-id="3f884-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="3f884-126">xs:string</span></span>|<span data-ttu-id="3f884-127">작업이 워크플로 응용 프로그램에서 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f884-127">The action that will be taken on the workflow application.</span></span>|  
|<span data-ttu-id="3f884-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="3f884-128">AppDomain</span></span>|<span data-ttu-id="3f884-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="3f884-129">xs:string</span></span>|<span data-ttu-id="3f884-130">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="3f884-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
