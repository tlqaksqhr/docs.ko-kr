---
title: 1101 - WorkflowActivityStart
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 831cd386-b9b5-47a9-9690-aff6292ff348
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 8d89b6f41838ee89b503746be4020b93db0ac96e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="1101---workflowactivitystart"></a><span data-ttu-id="2c443-102">1101 - WorkflowActivityStart</span><span class="sxs-lookup"><span data-stu-id="2c443-102">1101 - WorkflowActivityStart</span></span>
## <a name="properties"></a><span data-ttu-id="2c443-103">속성</span><span class="sxs-lookup"><span data-stu-id="2c443-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2c443-104">ID</span><span class="sxs-lookup"><span data-stu-id="2c443-104">ID</span></span>|<span data-ttu-id="2c443-105">1101</span><span class="sxs-lookup"><span data-stu-id="2c443-105">1101</span></span>|  
|<span data-ttu-id="2c443-106">키워드</span><span class="sxs-lookup"><span data-stu-id="2c443-106">Keywords</span></span>|<span data-ttu-id="2c443-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="2c443-107">WFRuntime</span></span>|  
|<span data-ttu-id="2c443-108">수준</span><span class="sxs-lookup"><span data-stu-id="2c443-108">Level</span></span>|<span data-ttu-id="2c443-109">정보</span><span class="sxs-lookup"><span data-stu-id="2c443-109">Information</span></span>|  
|<span data-ttu-id="2c443-110">채널</span><span class="sxs-lookup"><span data-stu-id="2c443-110">Channel</span></span>|<span data-ttu-id="2c443-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="2c443-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2c443-112">설명</span><span class="sxs-lookup"><span data-stu-id="2c443-112">Description</span></span>  
 <span data-ttu-id="2c443-113">워크플로 작업이 시작되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2c443-113">Indicates a workflow activity has started.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2c443-114">메시지</span><span class="sxs-lookup"><span data-stu-id="2c443-114">Message</span></span>  
 <span data-ttu-id="2c443-115">WorkflowInstance Id: '%1' E2E 작업</span><span class="sxs-lookup"><span data-stu-id="2c443-115">WorkflowInstance Id: '%1' E2E Activity</span></span>  
  
## <a name="details"></a><span data-ttu-id="2c443-116">설명</span><span class="sxs-lookup"><span data-stu-id="2c443-116">Details</span></span>  
  
|<span data-ttu-id="2c443-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="2c443-117">Data Item Name</span></span>|<span data-ttu-id="2c443-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="2c443-118">Data Item Type</span></span>|<span data-ttu-id="2c443-119">설명</span><span class="sxs-lookup"><span data-stu-id="2c443-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="2c443-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="2c443-120">WorkflowInstanceId</span></span>|<span data-ttu-id="2c443-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="2c443-121">xs:string</span></span>|<span data-ttu-id="2c443-122">워크플로 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="2c443-122">The workflow instance id.</span></span>|  
|<span data-ttu-id="2c443-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="2c443-123">AppDomain</span></span>|<span data-ttu-id="2c443-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="2c443-124">xs:string</span></span>|<span data-ttu-id="2c443-125">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="2c443-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
