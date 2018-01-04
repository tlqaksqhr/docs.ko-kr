---
title: 1004 - WorkflowInstanceAborted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: edb9ab8c-0b9a-488d-aa96-9c8c7984b53c
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cc940e1781f821f12efb42c5198e77eb0451a164
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="1004---workflowinstanceaborted"></a><span data-ttu-id="0122c-102">1004 - WorkflowInstanceAborted</span><span class="sxs-lookup"><span data-stu-id="0122c-102">1004 - WorkflowInstanceAborted</span></span>
## <a name="properties"></a><span data-ttu-id="0122c-103">속성</span><span class="sxs-lookup"><span data-stu-id="0122c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0122c-104">ID</span><span class="sxs-lookup"><span data-stu-id="0122c-104">ID</span></span>|<span data-ttu-id="0122c-105">1004</span><span class="sxs-lookup"><span data-stu-id="0122c-105">1004</span></span>|  
|<span data-ttu-id="0122c-106">키워드</span><span class="sxs-lookup"><span data-stu-id="0122c-106">Keywords</span></span>|<span data-ttu-id="0122c-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="0122c-107">WFRuntime</span></span>|  
|<span data-ttu-id="0122c-108">수준</span><span class="sxs-lookup"><span data-stu-id="0122c-108">Level</span></span>|<span data-ttu-id="0122c-109">정보</span><span class="sxs-lookup"><span data-stu-id="0122c-109">Information</span></span>|  
|<span data-ttu-id="0122c-110">채널</span><span class="sxs-lookup"><span data-stu-id="0122c-110">Channel</span></span>|<span data-ttu-id="0122c-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="0122c-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0122c-112">설명</span><span class="sxs-lookup"><span data-stu-id="0122c-112">Description</span></span>  
 <span data-ttu-id="0122c-113">워크플로 인스턴스가 예외와 함께 중단되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0122c-113">Indicates a worfklow instance has aborted with an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0122c-114">메시지</span><span class="sxs-lookup"><span data-stu-id="0122c-114">Message</span></span>  
 <span data-ttu-id="0122c-115">WorkflowInstance Id: '%1'이(가) 예외와 함께 중단되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0122c-115">WorkflowInstance Id: '%1' was aborted with an exception.</span></span>  
  
## <a name="details"></a><span data-ttu-id="0122c-116">설명</span><span class="sxs-lookup"><span data-stu-id="0122c-116">Details</span></span>  
  
|<span data-ttu-id="0122c-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="0122c-117">Data Item Name</span></span>|<span data-ttu-id="0122c-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="0122c-118">Data Item Type</span></span>|<span data-ttu-id="0122c-119">설명</span><span class="sxs-lookup"><span data-stu-id="0122c-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0122c-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="0122c-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="0122c-121">워크플로의 인스턴스 ID</span><span class="sxs-lookup"><span data-stu-id="0122c-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="0122c-122">예외</span><span class="sxs-lookup"><span data-stu-id="0122c-122">Exception</span></span>|`xs:string`|<span data-ttu-id="0122c-123">예외에 대한 예외 정보</span><span class="sxs-lookup"><span data-stu-id="0122c-123">The exception details for the exception</span></span>|  
|<span data-ttu-id="0122c-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="0122c-124">AppDomain</span></span>|`xs:string`|<span data-ttu-id="0122c-125">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="0122c-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
