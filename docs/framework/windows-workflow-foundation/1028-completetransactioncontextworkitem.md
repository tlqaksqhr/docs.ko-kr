---
title: 1028 - CompleteTransactionContextWorkItem
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 95423f9d-d29a-460e-bcd8-096e80af5bd0
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 77ef22bd29c167b5be26ceb5360397d38c547c22
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="1028---completetransactioncontextworkitem"></a><span data-ttu-id="94010-102">1028 - CompleteTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="94010-102">1028 - CompleteTransactionContextWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="94010-103">속성</span><span class="sxs-lookup"><span data-stu-id="94010-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="94010-104">ID</span><span class="sxs-lookup"><span data-stu-id="94010-104">ID</span></span>|<span data-ttu-id="94010-105">1028</span><span class="sxs-lookup"><span data-stu-id="94010-105">1028</span></span>|  
|<span data-ttu-id="94010-106">키워드</span><span class="sxs-lookup"><span data-stu-id="94010-106">Keywords</span></span>|<span data-ttu-id="94010-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="94010-107">WFRuntime</span></span>|  
|<span data-ttu-id="94010-108">수준</span><span class="sxs-lookup"><span data-stu-id="94010-108">Level</span></span>|<span data-ttu-id="94010-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="94010-109">Verbose</span></span>|  
|<span data-ttu-id="94010-110">채널</span><span class="sxs-lookup"><span data-stu-id="94010-110">Channel</span></span>|<span data-ttu-id="94010-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="94010-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="94010-112">설명</span><span class="sxs-lookup"><span data-stu-id="94010-112">Description</span></span>  
 <span data-ttu-id="94010-113">TransactionContextWorkItem이 완료되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="94010-113">Indicates a TransactionContextWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="94010-114">메시지</span><span class="sxs-lookup"><span data-stu-id="94010-114">Message</span></span>  
 <span data-ttu-id="94010-115">작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 TransactionContextWorkItem이 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="94010-115">A TransactionContextWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="94010-116">설명</span><span class="sxs-lookup"><span data-stu-id="94010-116">Details</span></span>  
  
|<span data-ttu-id="94010-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="94010-117">Data Item Name</span></span>|<span data-ttu-id="94010-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="94010-118">Data Item Type</span></span>|<span data-ttu-id="94010-119">설명</span><span class="sxs-lookup"><span data-stu-id="94010-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="94010-120">동작</span><span class="sxs-lookup"><span data-stu-id="94010-120">Activity</span></span>|<span data-ttu-id="94010-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="94010-121">xs:string</span></span>|<span data-ttu-id="94010-122">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="94010-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="94010-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="94010-123">DisplayName</span></span>|<span data-ttu-id="94010-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="94010-124">xs:string</span></span>|<span data-ttu-id="94010-125">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="94010-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="94010-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="94010-126">InstanceId</span></span>|<span data-ttu-id="94010-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="94010-127">xs:string</span></span>|<span data-ttu-id="94010-128">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="94010-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="94010-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="94010-129">AppDomain</span></span>|<span data-ttu-id="94010-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="94010-130">xs:string</span></span>|<span data-ttu-id="94010-131">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="94010-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
