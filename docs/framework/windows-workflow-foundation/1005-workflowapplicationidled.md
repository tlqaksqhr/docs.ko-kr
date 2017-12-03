---
title: 1005 - WorkflowApplicationIdled
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 74d77dfa-f20d-4fe9-a6ae-e6d1b5fe4182
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2603621eb23747275e6db22a1743c5260967c6a3
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="1005---workflowapplicationidled"></a><span data-ttu-id="d1b71-102">1005 - WorkflowApplicationIdled</span><span class="sxs-lookup"><span data-stu-id="d1b71-102">1005 - WorkflowApplicationIdled</span></span>
## <a name="properties"></a><span data-ttu-id="d1b71-103">속성</span><span class="sxs-lookup"><span data-stu-id="d1b71-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d1b71-104">ID</span><span class="sxs-lookup"><span data-stu-id="d1b71-104">ID</span></span>|<span data-ttu-id="d1b71-105">1005</span><span class="sxs-lookup"><span data-stu-id="d1b71-105">1005</span></span>|  
|<span data-ttu-id="d1b71-106">키워드</span><span class="sxs-lookup"><span data-stu-id="d1b71-106">Keywords</span></span>|<span data-ttu-id="d1b71-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="d1b71-107">WFRuntime</span></span>|  
|<span data-ttu-id="d1b71-108">수준</span><span class="sxs-lookup"><span data-stu-id="d1b71-108">Level</span></span>|<span data-ttu-id="d1b71-109">정보</span><span class="sxs-lookup"><span data-stu-id="d1b71-109">Information</span></span>|  
|<span data-ttu-id="d1b71-110">채널</span><span class="sxs-lookup"><span data-stu-id="d1b71-110">Channel</span></span>|<span data-ttu-id="d1b71-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="d1b71-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d1b71-112">설명</span><span class="sxs-lookup"><span data-stu-id="d1b71-112">Description</span></span>  
 <span data-ttu-id="d1b71-113">워크플로 응용 프로그램은 유휴 상태임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d1b71-113">Indicates a workflow application has idled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d1b71-114">메시지</span><span class="sxs-lookup"><span data-stu-id="d1b71-114">Message</span></span>  
 <span data-ttu-id="d1b71-115">WorkflowApplication Id: '%1'이(가) 유휴 상태가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d1b71-115">WorkflowApplication Id: '%1' went idle.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d1b71-116">설명</span><span class="sxs-lookup"><span data-stu-id="d1b71-116">Details</span></span>  
  
|<span data-ttu-id="d1b71-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="d1b71-117">Data Item Name</span></span>|<span data-ttu-id="d1b71-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="d1b71-118">Data Item Type</span></span>|<span data-ttu-id="d1b71-119">설명</span><span class="sxs-lookup"><span data-stu-id="d1b71-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d1b71-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="d1b71-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="d1b71-121">워크플로 응용 프로그램 ID</span><span class="sxs-lookup"><span data-stu-id="d1b71-121">The workflow application id</span></span>|  
|<span data-ttu-id="d1b71-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d1b71-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="d1b71-123">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="d1b71-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
