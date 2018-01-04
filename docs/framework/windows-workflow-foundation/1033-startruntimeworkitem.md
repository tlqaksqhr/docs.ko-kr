---
title: 1033 - StartRuntimeWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 172b5346-9f3b-46ae-bc06-39872022376a
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: df5502c3d2cb1e9ec9454ed43c3a468a27307d07
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="1033---startruntimeworkitem"></a><span data-ttu-id="fab6f-102">1033 - StartRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="fab6f-102">1033 - StartRuntimeWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="fab6f-103">속성</span><span class="sxs-lookup"><span data-stu-id="fab6f-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fab6f-104">ID</span><span class="sxs-lookup"><span data-stu-id="fab6f-104">ID</span></span>|<span data-ttu-id="fab6f-105">1033</span><span class="sxs-lookup"><span data-stu-id="fab6f-105">1033</span></span>|  
|<span data-ttu-id="fab6f-106">키워드</span><span class="sxs-lookup"><span data-stu-id="fab6f-106">Keywords</span></span>|<span data-ttu-id="fab6f-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="fab6f-107">WFRuntime</span></span>|  
|<span data-ttu-id="fab6f-108">수준</span><span class="sxs-lookup"><span data-stu-id="fab6f-108">Level</span></span>|<span data-ttu-id="fab6f-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="fab6f-109">Verbose</span></span>|  
|<span data-ttu-id="fab6f-110">채널</span><span class="sxs-lookup"><span data-stu-id="fab6f-110">Channel</span></span>|<span data-ttu-id="fab6f-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="fab6f-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="fab6f-112">설명</span><span class="sxs-lookup"><span data-stu-id="fab6f-112">Description</span></span>  
 <span data-ttu-id="fab6f-113">RuntimeWorkItem이 실행을 시작했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fab6f-113">Indicates a RuntimeWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="fab6f-114">메시지</span><span class="sxs-lookup"><span data-stu-id="fab6f-114">Message</span></span>  
 <span data-ttu-id="fab6f-115">작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 런타임 작업 항목의 실행을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="fab6f-115">Starting execution of a runtime work item for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="fab6f-116">설명</span><span class="sxs-lookup"><span data-stu-id="fab6f-116">Details</span></span>  
  
|<span data-ttu-id="fab6f-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="fab6f-117">Data Item Name</span></span>|<span data-ttu-id="fab6f-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="fab6f-118">Data Item Type</span></span>|<span data-ttu-id="fab6f-119">설명</span><span class="sxs-lookup"><span data-stu-id="fab6f-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="fab6f-120">동작</span><span class="sxs-lookup"><span data-stu-id="fab6f-120">Activity</span></span>|<span data-ttu-id="fab6f-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="fab6f-121">xs:string</span></span>|<span data-ttu-id="fab6f-122">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="fab6f-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="fab6f-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="fab6f-123">DisplayName</span></span>|<span data-ttu-id="fab6f-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="fab6f-124">xs:string</span></span>|<span data-ttu-id="fab6f-125">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="fab6f-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="fab6f-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="fab6f-126">InstanceId</span></span>|<span data-ttu-id="fab6f-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="fab6f-127">xs:string</span></span>|<span data-ttu-id="fab6f-128">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="fab6f-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="fab6f-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="fab6f-129">AppDomain</span></span>|<span data-ttu-id="fab6f-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="fab6f-130">xs:string</span></span>|<span data-ttu-id="fab6f-131">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="fab6f-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
