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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: bc60af91088fd61910dc0301b93844f4771177af
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="1012---startexecuteactivityworkitem"></a><span data-ttu-id="33bf8-102">1012 - StartExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="33bf8-102">1012 - StartExecuteActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="33bf8-103">속성</span><span class="sxs-lookup"><span data-stu-id="33bf8-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="33bf8-104">ID</span><span class="sxs-lookup"><span data-stu-id="33bf8-104">ID</span></span>|<span data-ttu-id="33bf8-105">1012</span><span class="sxs-lookup"><span data-stu-id="33bf8-105">1012</span></span>|  
|<span data-ttu-id="33bf8-106">키워드</span><span class="sxs-lookup"><span data-stu-id="33bf8-106">Keywords</span></span>|<span data-ttu-id="33bf8-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="33bf8-107">WFRuntime</span></span>|  
|<span data-ttu-id="33bf8-108">수준</span><span class="sxs-lookup"><span data-stu-id="33bf8-108">Level</span></span>|<span data-ttu-id="33bf8-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="33bf8-109">Verbose</span></span>|  
|<span data-ttu-id="33bf8-110">채널</span><span class="sxs-lookup"><span data-stu-id="33bf8-110">Channel</span></span>|<span data-ttu-id="33bf8-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="33bf8-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="33bf8-112">설명</span><span class="sxs-lookup"><span data-stu-id="33bf8-112">Description</span></span>  
 <span data-ttu-id="33bf8-113">ExecuteActivityWorkItem이 실행을 시작했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="33bf8-113">Indicates an ExecuteActivityWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="33bf8-114">메시지</span><span class="sxs-lookup"><span data-stu-id="33bf8-114">Message</span></span>  
 <span data-ttu-id="33bf8-115">작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 ExecuteActivityWorkItem 실행을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="33bf8-115">Starting execution of an ExecuteActivityWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="33bf8-116">설명</span><span class="sxs-lookup"><span data-stu-id="33bf8-116">Details</span></span>  
  
|<span data-ttu-id="33bf8-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="33bf8-117">Data Item Name</span></span>|<span data-ttu-id="33bf8-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="33bf8-118">Data Item Type</span></span>|<span data-ttu-id="33bf8-119">설명</span><span class="sxs-lookup"><span data-stu-id="33bf8-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="33bf8-120">동작</span><span class="sxs-lookup"><span data-stu-id="33bf8-120">Activity</span></span>|<span data-ttu-id="33bf8-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="33bf8-121">xs:string</span></span>|<span data-ttu-id="33bf8-122">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="33bf8-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="33bf8-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="33bf8-123">DisplayName</span></span>|<span data-ttu-id="33bf8-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="33bf8-124">xs:string</span></span>|<span data-ttu-id="33bf8-125">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="33bf8-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="33bf8-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="33bf8-126">InstanceId</span></span>|<span data-ttu-id="33bf8-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="33bf8-127">xs:string</span></span>|<span data-ttu-id="33bf8-128">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="33bf8-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="33bf8-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="33bf8-129">AppDomain</span></span>|<span data-ttu-id="33bf8-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="33bf8-130">xs:string</span></span>|<span data-ttu-id="33bf8-131">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="33bf8-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
