---
title: 1012 - StartExecuteActivityWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 29e9b1c6-c5d7-4b58-b59d-a06a923d3c80
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6a06cec1ab251b8f7e82aef71589bd56e5f55f2e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="1012---startexecuteactivityworkitem"></a><span data-ttu-id="85cc3-102">1012 - StartExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="85cc3-102">1012 - StartExecuteActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="85cc3-103">속성</span><span class="sxs-lookup"><span data-stu-id="85cc3-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="85cc3-104">ID</span><span class="sxs-lookup"><span data-stu-id="85cc3-104">ID</span></span>|<span data-ttu-id="85cc3-105">1012</span><span class="sxs-lookup"><span data-stu-id="85cc3-105">1012</span></span>|  
|<span data-ttu-id="85cc3-106">키워드</span><span class="sxs-lookup"><span data-stu-id="85cc3-106">Keywords</span></span>|<span data-ttu-id="85cc3-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="85cc3-107">WFRuntime</span></span>|  
|<span data-ttu-id="85cc3-108">수준</span><span class="sxs-lookup"><span data-stu-id="85cc3-108">Level</span></span>|<span data-ttu-id="85cc3-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="85cc3-109">Verbose</span></span>|  
|<span data-ttu-id="85cc3-110">채널</span><span class="sxs-lookup"><span data-stu-id="85cc3-110">Channel</span></span>|<span data-ttu-id="85cc3-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="85cc3-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="85cc3-112">설명</span><span class="sxs-lookup"><span data-stu-id="85cc3-112">Description</span></span>  
 <span data-ttu-id="85cc3-113">ExecuteActivityWorkItem이 실행을 시작했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="85cc3-113">Indicates an ExecuteActivityWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="85cc3-114">메시지</span><span class="sxs-lookup"><span data-stu-id="85cc3-114">Message</span></span>  
 <span data-ttu-id="85cc3-115">작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 ExecuteActivityWorkItem 실행을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="85cc3-115">Starting execution of an ExecuteActivityWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="85cc3-116">설명</span><span class="sxs-lookup"><span data-stu-id="85cc3-116">Details</span></span>  
  
|<span data-ttu-id="85cc3-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="85cc3-117">Data Item Name</span></span>|<span data-ttu-id="85cc3-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="85cc3-118">Data Item Type</span></span>|<span data-ttu-id="85cc3-119">설명</span><span class="sxs-lookup"><span data-stu-id="85cc3-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="85cc3-120">동작</span><span class="sxs-lookup"><span data-stu-id="85cc3-120">Activity</span></span>|<span data-ttu-id="85cc3-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="85cc3-121">xs:string</span></span>|<span data-ttu-id="85cc3-122">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="85cc3-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="85cc3-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="85cc3-123">DisplayName</span></span>|<span data-ttu-id="85cc3-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="85cc3-124">xs:string</span></span>|<span data-ttu-id="85cc3-125">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="85cc3-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="85cc3-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="85cc3-126">InstanceId</span></span>|<span data-ttu-id="85cc3-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="85cc3-127">xs:string</span></span>|<span data-ttu-id="85cc3-128">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="85cc3-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="85cc3-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="85cc3-129">AppDomain</span></span>|<span data-ttu-id="85cc3-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="85cc3-130">xs:string</span></span>|<span data-ttu-id="85cc3-131">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="85cc3-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
