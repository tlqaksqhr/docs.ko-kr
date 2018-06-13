---
title: 1041 - WorkflowApplicationPersistableIdle
ms.date: 03/30/2017
ms.assetid: 966adf2f-e21d-44df-a3ec-a8e285e0a316
ms.openlocfilehash: 07be0ae603443a1ef06cb539bba7b227d7b3e325
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509669"
---
# <a name="1041---workflowapplicationpersistableidle"></a><span data-ttu-id="3ce0f-102">1041 - WorkflowApplicationPersistableIdle</span><span class="sxs-lookup"><span data-stu-id="3ce0f-102">1041 - WorkflowApplicationPersistableIdle</span></span>
## <a name="properties"></a><span data-ttu-id="3ce0f-103">속성</span><span class="sxs-lookup"><span data-stu-id="3ce0f-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3ce0f-104">ID</span><span class="sxs-lookup"><span data-stu-id="3ce0f-104">ID</span></span>|<span data-ttu-id="3ce0f-105">1041</span><span class="sxs-lookup"><span data-stu-id="3ce0f-105">1041</span></span>|  
|<span data-ttu-id="3ce0f-106">키워드</span><span class="sxs-lookup"><span data-stu-id="3ce0f-106">Keywords</span></span>|<span data-ttu-id="3ce0f-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="3ce0f-107">WFRuntime</span></span>|  
|<span data-ttu-id="3ce0f-108">수준</span><span class="sxs-lookup"><span data-stu-id="3ce0f-108">Level</span></span>|<span data-ttu-id="3ce0f-109">정보</span><span class="sxs-lookup"><span data-stu-id="3ce0f-109">Information</span></span>|  
|<span data-ttu-id="3ce0f-110">채널</span><span class="sxs-lookup"><span data-stu-id="3ce0f-110">Channel</span></span>|<span data-ttu-id="3ce0f-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="3ce0f-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3ce0f-112">설명</span><span class="sxs-lookup"><span data-stu-id="3ce0f-112">Description</span></span>  
 <span data-ttu-id="3ce0f-113">워크플로 응용 프로그램이 유휴 상태이며 지속 가능함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3ce0f-113">Indicates that a workflow application is idle and persistable.</span></span> <span data-ttu-id="3ce0f-114">워크플로 응용 프로그램이 유휴 상태이거나 지속됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ce0f-114">The workflow application will be idled or persisted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3ce0f-115">메시지</span><span class="sxs-lookup"><span data-stu-id="3ce0f-115">Message</span></span>  
 <span data-ttu-id="3ce0f-116">WorkflowApplication Id: '%1'는 유휴 상태로 지속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ce0f-116">WorkflowApplication Id: '%1' is idle and persistable.</span></span>  <span data-ttu-id="3ce0f-117">다음과 같은 조치가 취해집니다: %2입니다.</span><span class="sxs-lookup"><span data-stu-id="3ce0f-117">The following action will be taken: %2.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3ce0f-118">설명</span><span class="sxs-lookup"><span data-stu-id="3ce0f-118">Details</span></span>  
  
|<span data-ttu-id="3ce0f-119">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="3ce0f-119">Data Item Name</span></span>|<span data-ttu-id="3ce0f-120">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="3ce0f-120">Data Item Type</span></span>|<span data-ttu-id="3ce0f-121">설명</span><span class="sxs-lookup"><span data-stu-id="3ce0f-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3ce0f-122">WorkflowApplicationId</span><span class="sxs-lookup"><span data-stu-id="3ce0f-122">WorkflowApplicationId</span></span>|<span data-ttu-id="3ce0f-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="3ce0f-123">xs:string</span></span>|<span data-ttu-id="3ce0f-124">워크플로 응용 프로그램 ID</span><span class="sxs-lookup"><span data-stu-id="3ce0f-124">The workflow application id</span></span>|  
|<span data-ttu-id="3ce0f-125">ActionTaken</span><span class="sxs-lookup"><span data-stu-id="3ce0f-125">ActionTaken</span></span>|<span data-ttu-id="3ce0f-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="3ce0f-126">xs:string</span></span>|<span data-ttu-id="3ce0f-127">작업이 워크플로 응용 프로그램에서 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="3ce0f-127">The action that will be taken on the workflow application.</span></span>|  
|<span data-ttu-id="3ce0f-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="3ce0f-128">AppDomain</span></span>|<span data-ttu-id="3ce0f-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="3ce0f-129">xs:string</span></span>|<span data-ttu-id="3ce0f-130">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="3ce0f-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
