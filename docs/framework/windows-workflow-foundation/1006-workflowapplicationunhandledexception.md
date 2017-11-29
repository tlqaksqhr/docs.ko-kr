---
title: 1006 - WorkflowApplicationUnhandledException
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dfe0f316-e03b-47fb-b6a3-622c56bfd753
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a03809be5e5d61c505e295e2f769a0298f770f7f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="1006---workflowapplicationunhandledexception"></a><span data-ttu-id="118b6-102">1006 - WorkflowApplicationUnhandledException</span><span class="sxs-lookup"><span data-stu-id="118b6-102">1006 - WorkflowApplicationUnhandledException</span></span>
## <a name="properties"></a><span data-ttu-id="118b6-103">속성</span><span class="sxs-lookup"><span data-stu-id="118b6-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="118b6-104">ID</span><span class="sxs-lookup"><span data-stu-id="118b6-104">ID</span></span>|<span data-ttu-id="118b6-105">1006</span><span class="sxs-lookup"><span data-stu-id="118b6-105">1006</span></span>|  
|<span data-ttu-id="118b6-106">키워드</span><span class="sxs-lookup"><span data-stu-id="118b6-106">Keywords</span></span>|<span data-ttu-id="118b6-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="118b6-107">WFRuntime</span></span>|  
|<span data-ttu-id="118b6-108">수준</span><span class="sxs-lookup"><span data-stu-id="118b6-108">Level</span></span>|<span data-ttu-id="118b6-109">오류</span><span class="sxs-lookup"><span data-stu-id="118b6-109">Error</span></span>|  
|<span data-ttu-id="118b6-110">채널</span><span class="sxs-lookup"><span data-stu-id="118b6-110">Channel</span></span>|<span data-ttu-id="118b6-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="118b6-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="118b6-112">설명</span><span class="sxs-lookup"><span data-stu-id="118b6-112">Description</span></span>  
 <span data-ttu-id="118b6-113">워크플로 응용 프로그램에서 처리되지 않은 예외가 발생했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="118b6-113">Indicates a workflow application has encountered an unhandled exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="118b6-114">메시지</span><span class="sxs-lookup"><span data-stu-id="118b6-114">Message</span></span>  
 <span data-ttu-id="118b6-115">WorkflowInstance Id: '%1'에 처리 되지 않은 예외가 발생 했습니다.</span><span class="sxs-lookup"><span data-stu-id="118b6-115">WorkflowInstance Id: '%1' has encountered an unhandled exception.</span></span>  <span data-ttu-id="118b6-116">'%2', DisplayName 활동에서 발생 한 예외: '%3'.</span><span class="sxs-lookup"><span data-stu-id="118b6-116">The exception originated from Activity '%2', DisplayName: '%3'.</span></span>  <span data-ttu-id="118b6-117">다음과 같은 조치가 취해집니다: %4입니다.</span><span class="sxs-lookup"><span data-stu-id="118b6-117">The following action will be taken: %4.</span></span>  
  
## <a name="details"></a><span data-ttu-id="118b6-118">세부 정보</span><span class="sxs-lookup"><span data-stu-id="118b6-118">Details</span></span>  
  
|<span data-ttu-id="118b6-119">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="118b6-119">Data Item Name</span></span>|<span data-ttu-id="118b6-120">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="118b6-120">Data Item Type</span></span>|<span data-ttu-id="118b6-121">설명</span><span class="sxs-lookup"><span data-stu-id="118b6-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="118b6-122">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="118b6-122">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="118b6-123">워크플로의 인스턴스 ID</span><span class="sxs-lookup"><span data-stu-id="118b6-123">The instance id for the workflow</span></span>|  
|<span data-ttu-id="118b6-124">예외</span><span class="sxs-lookup"><span data-stu-id="118b6-124">Exception</span></span>|`xs:string`|<span data-ttu-id="118b6-125">예외에 대한 예외 정보</span><span class="sxs-lookup"><span data-stu-id="118b6-125">The exception details for the exception</span></span>|  
|<span data-ttu-id="118b6-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="118b6-126">AppDomain</span></span>|`xs:string`|<span data-ttu-id="118b6-127">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="118b6-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
