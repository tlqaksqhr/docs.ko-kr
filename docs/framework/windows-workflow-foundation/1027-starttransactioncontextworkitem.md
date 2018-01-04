---
title: 1027 - StartTransactionContextWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 116ae5ec-b9d5-4231-824e-270d00eea7b8
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: baa644cb7693b8608f119cf211b3b08ab4b1a2b8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="1027---starttransactioncontextworkitem"></a><span data-ttu-id="09903-102">1027 - StartTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="09903-102">1027 - StartTransactionContextWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="09903-103">속성</span><span class="sxs-lookup"><span data-stu-id="09903-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="09903-104">ID</span><span class="sxs-lookup"><span data-stu-id="09903-104">ID</span></span>|<span data-ttu-id="09903-105">1027</span><span class="sxs-lookup"><span data-stu-id="09903-105">1027</span></span>|  
|<span data-ttu-id="09903-106">키워드</span><span class="sxs-lookup"><span data-stu-id="09903-106">Keywords</span></span>|<span data-ttu-id="09903-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="09903-107">WFRuntime</span></span>|  
|<span data-ttu-id="09903-108">수준</span><span class="sxs-lookup"><span data-stu-id="09903-108">Level</span></span>|<span data-ttu-id="09903-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="09903-109">Verbose</span></span>|  
|<span data-ttu-id="09903-110">채널</span><span class="sxs-lookup"><span data-stu-id="09903-110">Channel</span></span>|<span data-ttu-id="09903-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="09903-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="09903-112">설명</span><span class="sxs-lookup"><span data-stu-id="09903-112">Description</span></span>  
 <span data-ttu-id="09903-113">TransactionContextWorkItem이 실행을 시작했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="09903-113">Indicates a TransactionContextWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="09903-114">메시지</span><span class="sxs-lookup"><span data-stu-id="09903-114">Message</span></span>  
 <span data-ttu-id="09903-115">작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 TransactionContextWorkItem의 실행 시작입니다.</span><span class="sxs-lookup"><span data-stu-id="09903-115">Starting execution of a TransactionContextWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="09903-116">설명</span><span class="sxs-lookup"><span data-stu-id="09903-116">Details</span></span>  
  
|<span data-ttu-id="09903-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="09903-117">Data Item Name</span></span>|<span data-ttu-id="09903-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="09903-118">Data Item Type</span></span>|<span data-ttu-id="09903-119">설명</span><span class="sxs-lookup"><span data-stu-id="09903-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="09903-120">동작</span><span class="sxs-lookup"><span data-stu-id="09903-120">Activity</span></span>|<span data-ttu-id="09903-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="09903-121">xs:string</span></span>|<span data-ttu-id="09903-122">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="09903-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="09903-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="09903-123">DisplayName</span></span>|<span data-ttu-id="09903-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="09903-124">xs:string</span></span>|<span data-ttu-id="09903-125">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="09903-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="09903-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="09903-126">InstanceId</span></span>|<span data-ttu-id="09903-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="09903-127">xs:string</span></span>|<span data-ttu-id="09903-128">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="09903-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="09903-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="09903-129">AppDomain</span></span>|<span data-ttu-id="09903-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="09903-130">xs:string</span></span>|<span data-ttu-id="09903-131">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="09903-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
