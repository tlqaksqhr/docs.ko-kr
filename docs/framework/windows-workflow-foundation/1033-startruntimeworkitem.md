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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 0de8e45a592cae49060f976b28a7a7bcf8781265
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="1033---startruntimeworkitem"></a><span data-ttu-id="dd307-102">1033 - StartRuntimeWorkItem</span><span class="sxs-lookup"><span data-stu-id="dd307-102">1033 - StartRuntimeWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="dd307-103">속성</span><span class="sxs-lookup"><span data-stu-id="dd307-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="dd307-104">ID</span><span class="sxs-lookup"><span data-stu-id="dd307-104">ID</span></span>|<span data-ttu-id="dd307-105">1033</span><span class="sxs-lookup"><span data-stu-id="dd307-105">1033</span></span>|  
|<span data-ttu-id="dd307-106">키워드</span><span class="sxs-lookup"><span data-stu-id="dd307-106">Keywords</span></span>|<span data-ttu-id="dd307-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="dd307-107">WFRuntime</span></span>|  
|<span data-ttu-id="dd307-108">수준</span><span class="sxs-lookup"><span data-stu-id="dd307-108">Level</span></span>|<span data-ttu-id="dd307-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="dd307-109">Verbose</span></span>|  
|<span data-ttu-id="dd307-110">채널</span><span class="sxs-lookup"><span data-stu-id="dd307-110">Channel</span></span>|<span data-ttu-id="dd307-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="dd307-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="dd307-112">설명</span><span class="sxs-lookup"><span data-stu-id="dd307-112">Description</span></span>  
 <span data-ttu-id="dd307-113">RuntimeWorkItem이 실행을 시작했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="dd307-113">Indicates a RuntimeWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="dd307-114">메시지</span><span class="sxs-lookup"><span data-stu-id="dd307-114">Message</span></span>  
 <span data-ttu-id="dd307-115">작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 런타임 작업 항목의 실행을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="dd307-115">Starting execution of a runtime work item for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="dd307-116">설명</span><span class="sxs-lookup"><span data-stu-id="dd307-116">Details</span></span>  
  
|<span data-ttu-id="dd307-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="dd307-117">Data Item Name</span></span>|<span data-ttu-id="dd307-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="dd307-118">Data Item Type</span></span>|<span data-ttu-id="dd307-119">설명</span><span class="sxs-lookup"><span data-stu-id="dd307-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="dd307-120">동작</span><span class="sxs-lookup"><span data-stu-id="dd307-120">Activity</span></span>|<span data-ttu-id="dd307-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="dd307-121">xs:string</span></span>|<span data-ttu-id="dd307-122">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="dd307-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="dd307-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="dd307-123">DisplayName</span></span>|<span data-ttu-id="dd307-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="dd307-124">xs:string</span></span>|<span data-ttu-id="dd307-125">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="dd307-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="dd307-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="dd307-126">InstanceId</span></span>|<span data-ttu-id="dd307-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="dd307-127">xs:string</span></span>|<span data-ttu-id="dd307-128">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="dd307-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="dd307-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="dd307-129">AppDomain</span></span>|<span data-ttu-id="dd307-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="dd307-130">xs:string</span></span>|<span data-ttu-id="dd307-131">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="dd307-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
