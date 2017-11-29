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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7b287c99453724f855a51e9a1b8068337dd5e373
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="1003---workflowinstancecanceled"></a><span data-ttu-id="f2f0d-102">1003 - WorkflowInstanceCanceled</span><span class="sxs-lookup"><span data-stu-id="f2f0d-102">1003 - WorkflowInstanceCanceled</span></span>
## <a name="properties"></a><span data-ttu-id="f2f0d-103">속성</span><span class="sxs-lookup"><span data-stu-id="f2f0d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f2f0d-104">ID</span><span class="sxs-lookup"><span data-stu-id="f2f0d-104">ID</span></span>|<span data-ttu-id="f2f0d-105">1003</span><span class="sxs-lookup"><span data-stu-id="f2f0d-105">1003</span></span>|  
|<span data-ttu-id="f2f0d-106">키워드</span><span class="sxs-lookup"><span data-stu-id="f2f0d-106">Keywords</span></span>|<span data-ttu-id="f2f0d-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="f2f0d-107">WFRuntime</span></span>|  
|<span data-ttu-id="f2f0d-108">수준</span><span class="sxs-lookup"><span data-stu-id="f2f0d-108">Level</span></span>|<span data-ttu-id="f2f0d-109">정보</span><span class="sxs-lookup"><span data-stu-id="f2f0d-109">Information</span></span>|  
|<span data-ttu-id="f2f0d-110">채널</span><span class="sxs-lookup"><span data-stu-id="f2f0d-110">Channel</span></span>|<span data-ttu-id="f2f0d-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="f2f0d-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f2f0d-112">설명</span><span class="sxs-lookup"><span data-stu-id="f2f0d-112">Description</span></span>  
 <span data-ttu-id="f2f0d-113">워크플로 인스턴스가 Closed 상태에서 완료되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f2f0d-113">Indicates a workflow instance has completed in the Canceled state.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f2f0d-114">메시지</span><span class="sxs-lookup"><span data-stu-id="f2f0d-114">Message</span></span>  
 <span data-ttu-id="f2f0d-115">WorkflowInstance Id: '%1'이(가) Canceled 상태에서 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f2f0d-115">WorkflowInstance Id: '%1' has completed in the Canceled state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f2f0d-116">설명</span><span class="sxs-lookup"><span data-stu-id="f2f0d-116">Details</span></span>  
  
|<span data-ttu-id="f2f0d-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="f2f0d-117">Data Item Name</span></span>|<span data-ttu-id="f2f0d-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="f2f0d-118">Data Item Type</span></span>|<span data-ttu-id="f2f0d-119">설명</span><span class="sxs-lookup"><span data-stu-id="f2f0d-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f2f0d-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="f2f0d-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="f2f0d-121">워크플로의 인스턴스 ID</span><span class="sxs-lookup"><span data-stu-id="f2f0d-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="f2f0d-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f2f0d-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="f2f0d-123">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="f2f0d-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
