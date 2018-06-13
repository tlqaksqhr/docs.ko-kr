---
title: 1027 - StartTransactionContextWorkItem
ms.date: 03/30/2017
ms.assetid: 116ae5ec-b9d5-4231-824e-270d00eea7b8
ms.openlocfilehash: 231a7607f2ce9a38e8dd6c1486a68bc9eb459e5e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510811"
---
# <a name="1027---starttransactioncontextworkitem"></a><span data-ttu-id="dc49a-102">1027 - StartTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="dc49a-102">1027 - StartTransactionContextWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="dc49a-103">속성</span><span class="sxs-lookup"><span data-stu-id="dc49a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="dc49a-104">ID</span><span class="sxs-lookup"><span data-stu-id="dc49a-104">ID</span></span>|<span data-ttu-id="dc49a-105">1027</span><span class="sxs-lookup"><span data-stu-id="dc49a-105">1027</span></span>|  
|<span data-ttu-id="dc49a-106">키워드</span><span class="sxs-lookup"><span data-stu-id="dc49a-106">Keywords</span></span>|<span data-ttu-id="dc49a-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="dc49a-107">WFRuntime</span></span>|  
|<span data-ttu-id="dc49a-108">수준</span><span class="sxs-lookup"><span data-stu-id="dc49a-108">Level</span></span>|<span data-ttu-id="dc49a-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="dc49a-109">Verbose</span></span>|  
|<span data-ttu-id="dc49a-110">채널</span><span class="sxs-lookup"><span data-stu-id="dc49a-110">Channel</span></span>|<span data-ttu-id="dc49a-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="dc49a-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="dc49a-112">설명</span><span class="sxs-lookup"><span data-stu-id="dc49a-112">Description</span></span>  
 <span data-ttu-id="dc49a-113">TransactionContextWorkItem이 실행을 시작했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="dc49a-113">Indicates a TransactionContextWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="dc49a-114">메시지</span><span class="sxs-lookup"><span data-stu-id="dc49a-114">Message</span></span>  
 <span data-ttu-id="dc49a-115">작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 TransactionContextWorkItem의 실행 시작입니다.</span><span class="sxs-lookup"><span data-stu-id="dc49a-115">Starting execution of a TransactionContextWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="dc49a-116">설명</span><span class="sxs-lookup"><span data-stu-id="dc49a-116">Details</span></span>  
  
|<span data-ttu-id="dc49a-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="dc49a-117">Data Item Name</span></span>|<span data-ttu-id="dc49a-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="dc49a-118">Data Item Type</span></span>|<span data-ttu-id="dc49a-119">설명</span><span class="sxs-lookup"><span data-stu-id="dc49a-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="dc49a-120">동작</span><span class="sxs-lookup"><span data-stu-id="dc49a-120">Activity</span></span>|<span data-ttu-id="dc49a-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="dc49a-121">xs:string</span></span>|<span data-ttu-id="dc49a-122">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="dc49a-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="dc49a-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="dc49a-123">DisplayName</span></span>|<span data-ttu-id="dc49a-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="dc49a-124">xs:string</span></span>|<span data-ttu-id="dc49a-125">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="dc49a-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="dc49a-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="dc49a-126">InstanceId</span></span>|<span data-ttu-id="dc49a-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="dc49a-127">xs:string</span></span>|<span data-ttu-id="dc49a-128">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="dc49a-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="dc49a-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="dc49a-129">AppDomain</span></span>|<span data-ttu-id="dc49a-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="dc49a-130">xs:string</span></span>|<span data-ttu-id="dc49a-131">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="dc49a-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
