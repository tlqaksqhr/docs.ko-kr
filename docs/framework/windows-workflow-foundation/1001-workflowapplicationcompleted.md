---
title: 1001 - WorkflowApplicationCompleted
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7a2ab59a-cf66-437a-b01e-f8f7268a3f7a
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a62a8448319e7b07a3ea302f00f2fa269bf654ae
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="1001---workflowapplicationcompleted"></a><span data-ttu-id="a0cfd-102">1001 - WorkflowApplicationCompleted</span><span class="sxs-lookup"><span data-stu-id="a0cfd-102">1001 - WorkflowApplicationCompleted</span></span>
## <a name="properties"></a><span data-ttu-id="a0cfd-103">속성</span><span class="sxs-lookup"><span data-stu-id="a0cfd-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a0cfd-104">ID</span><span class="sxs-lookup"><span data-stu-id="a0cfd-104">ID</span></span>|<span data-ttu-id="a0cfd-105">1001</span><span class="sxs-lookup"><span data-stu-id="a0cfd-105">1001</span></span>|  
|<span data-ttu-id="a0cfd-106">키워드</span><span class="sxs-lookup"><span data-stu-id="a0cfd-106">Keywords</span></span>|<span data-ttu-id="a0cfd-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="a0cfd-107">WFRuntime</span></span>|  
|<span data-ttu-id="a0cfd-108">수준</span><span class="sxs-lookup"><span data-stu-id="a0cfd-108">Level</span></span>|<span data-ttu-id="a0cfd-109">정보</span><span class="sxs-lookup"><span data-stu-id="a0cfd-109">Information</span></span>|  
|<span data-ttu-id="a0cfd-110">채널</span><span class="sxs-lookup"><span data-stu-id="a0cfd-110">Channel</span></span>|<span data-ttu-id="a0cfd-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="a0cfd-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a0cfd-112">설명</span><span class="sxs-lookup"><span data-stu-id="a0cfd-112">Description</span></span>  
 <span data-ttu-id="a0cfd-113">워크플로 응용 프로그램이 Closed 상태에서 완료되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a0cfd-113">Indicates a workflow application has completed in the Closed state.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a0cfd-114">메시지</span><span class="sxs-lookup"><span data-stu-id="a0cfd-114">Message</span></span>  
 <span data-ttu-id="a0cfd-115">WorkflowInstance Id: '%1'이(가) Closed 상태에서 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a0cfd-115">WorkflowInstance Id: '%1' has completed in the Closed state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="a0cfd-116">설명</span><span class="sxs-lookup"><span data-stu-id="a0cfd-116">Details</span></span>  
  
|<span data-ttu-id="a0cfd-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="a0cfd-117">Data Item Name</span></span>|<span data-ttu-id="a0cfd-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="a0cfd-118">Data Item Type</span></span>|<span data-ttu-id="a0cfd-119">설명</span><span class="sxs-lookup"><span data-stu-id="a0cfd-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a0cfd-120">WorkflowInstanceId</span><span class="sxs-lookup"><span data-stu-id="a0cfd-120">WorkflowInstanceId</span></span>|`xs:string`|<span data-ttu-id="a0cfd-121">워크플로의 인스턴스 ID</span><span class="sxs-lookup"><span data-stu-id="a0cfd-121">The instance id for the workflow</span></span>|  
|<span data-ttu-id="a0cfd-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="a0cfd-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="a0cfd-123">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="a0cfd-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
