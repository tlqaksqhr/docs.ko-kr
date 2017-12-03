---
title: 1036 - RuntimeTransactionCompletionRequested
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d36b9f44-7c0f-4083-9d3a-9034dd2b98de
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 112063d5cd550f438541b2d775eaa49124d9cc02
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="1036---runtimetransactioncompletionrequested"></a><span data-ttu-id="523f7-102">1036 - RuntimeTransactionCompletionRequested</span><span class="sxs-lookup"><span data-stu-id="523f7-102">1036 - RuntimeTransactionCompletionRequested</span></span>
## <a name="properties"></a><span data-ttu-id="523f7-103">속성</span><span class="sxs-lookup"><span data-stu-id="523f7-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="523f7-104">ID</span><span class="sxs-lookup"><span data-stu-id="523f7-104">ID</span></span>|<span data-ttu-id="523f7-105">1036</span><span class="sxs-lookup"><span data-stu-id="523f7-105">1036</span></span>|  
|<span data-ttu-id="523f7-106">키워드</span><span class="sxs-lookup"><span data-stu-id="523f7-106">Keywords</span></span>|<span data-ttu-id="523f7-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="523f7-107">WFRuntime</span></span>|  
|<span data-ttu-id="523f7-108">수준</span><span class="sxs-lookup"><span data-stu-id="523f7-108">Level</span></span>|<span data-ttu-id="523f7-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="523f7-109">Verbose</span></span>|  
|<span data-ttu-id="523f7-110">채널</span><span class="sxs-lookup"><span data-stu-id="523f7-110">Channel</span></span>|<span data-ttu-id="523f7-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="523f7-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="523f7-112">설명</span><span class="sxs-lookup"><span data-stu-id="523f7-112">Description</span></span>  
 <span data-ttu-id="523f7-113">작업이 런타임 트랜잭션의 완료를 예약했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="523f7-113">Indicates an activity has scheduled the completion of the runtime transaction.</span></span>  
  
## <a name="message"></a><span data-ttu-id="523f7-114">메시지</span><span class="sxs-lookup"><span data-stu-id="523f7-114">Message</span></span>  
 <span data-ttu-id="523f7-115">작업 '%1', DisplayName: '%2', InstanceId: '%3'이(가) 런타임 트랜잭션 완료를 예약했습니다.</span><span class="sxs-lookup"><span data-stu-id="523f7-115">Activity '%1', DisplayName: '%2', InstanceId: '%3' has scheduled completion of the runtime transaction.</span></span>  
  
## <a name="details"></a><span data-ttu-id="523f7-116">설명</span><span class="sxs-lookup"><span data-stu-id="523f7-116">Details</span></span>  
  
|<span data-ttu-id="523f7-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="523f7-117">Data Item Name</span></span>|<span data-ttu-id="523f7-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="523f7-118">Data Item Type</span></span>|<span data-ttu-id="523f7-119">설명</span><span class="sxs-lookup"><span data-stu-id="523f7-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="523f7-120">동작</span><span class="sxs-lookup"><span data-stu-id="523f7-120">Activity</span></span>|<span data-ttu-id="523f7-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="523f7-121">xs:string</span></span>|<span data-ttu-id="523f7-122">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="523f7-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="523f7-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="523f7-123">DisplayName</span></span>|<span data-ttu-id="523f7-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="523f7-124">xs:string</span></span>|<span data-ttu-id="523f7-125">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="523f7-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="523f7-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="523f7-126">InstanceId</span></span>|<span data-ttu-id="523f7-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="523f7-127">xs:string</span></span>|<span data-ttu-id="523f7-128">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="523f7-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="523f7-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="523f7-129">AppDomain</span></span>|<span data-ttu-id="523f7-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="523f7-130">xs:string</span></span>|<span data-ttu-id="523f7-131">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="523f7-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
