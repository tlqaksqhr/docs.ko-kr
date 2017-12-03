---
title: 1003 - WorkflowInstanceCanceled
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 64754dc2-c160-4bf3-869a-13d56694e2dc
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6930aeed8c3cd224d5d37dcecf357195e78390ed
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="1003---workflowinstancecanceled"></a><span data-ttu-id="a1151-102">1003 - WorkflowInstanceCanceled</span><span class="sxs-lookup"><span data-stu-id="a1151-102">1003 - WorkflowInstanceCanceled</span></span>
## <a name="properties"></a><span data-ttu-id="a1151-103">속성</span><span class="sxs-lookup"><span data-stu-id="a1151-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a1151-104">ID</span><span class="sxs-lookup"><span data-stu-id="a1151-104">ID</span></span>|<span data-ttu-id="a1151-105">1003</span><span class="sxs-lookup"><span data-stu-id="a1151-105">1003</span></span>|  
|<span data-ttu-id="a1151-106">키워드</span><span class="sxs-lookup"><span data-stu-id="a1151-106">Keywords</span></span>|<span data-ttu-id="a1151-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="a1151-107">WFRuntime</span></span>|  
|<span data-ttu-id="a1151-108">수준</span><span class="sxs-lookup"><span data-stu-id="a1151-108">Level</span></span>|<span data-ttu-id="a1151-109">정보</span><span class="sxs-lookup"><span data-stu-id="a1151-109">Information</span></span>|  
|<span data-ttu-id="a1151-110">채널</span><span class="sxs-lookup"><span data-stu-id="a1151-110">Channel</span></span>|<span data-ttu-id="a1151-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="a1151-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a1151-112">설명</span><span class="sxs-lookup"><span data-stu-id="a1151-112">Description</span></span>  
 <span data-ttu-id="a1151-113">워크플로 인스턴스가 Closed 상태에서 완료되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a1151-113">Indicates a workflow instance has completed in the Canceled state.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a1151-114">메시지</span><span class="sxs-lookup"><span data-stu-id="a1151-114">Message</span></span>  
 <span data-ttu-id="a1151-115">WorkflowInstance Id: '%1'이(가) Canceled 상태에서 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a1151-115">WorkflowInstance Id: '%1' has completed in the Canceled state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a1151-116">설명</span><span class="sxs-lookup"><span data-stu-id="a1151-116">Details</span></span>  
  
|<span data-ttu-id="a1151-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="a1151-117">Data Item Name</span></span>|<span data-ttu-id="a1151-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="a1151-118">Data Item Type</span></span>|<span data-ttu-id="a1151-119">설명</span><span class="sxs-lookup"><span data-stu-id="a1151-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a1151-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="a1151-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="a1151-121">워크플로의 인스턴스 ID</span><span class="sxs-lookup"><span data-stu-id="a1151-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="a1151-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="a1151-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="a1151-123">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="a1151-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
