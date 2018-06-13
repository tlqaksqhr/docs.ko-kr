---
title: 1010 - ActivityCompleted
ms.date: 03/30/2017
ms.assetid: d256284e-3fd2-4c33-82f4-abb617575706
ms.openlocfilehash: 355281e6aa8f621bd2f9c0862e641fafec872750
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509699"
---
# <a name="1010---activitycompleted"></a><span data-ttu-id="3ca76-102">1010 - ActivityCompleted</span><span class="sxs-lookup"><span data-stu-id="3ca76-102">1010 - ActivityCompleted</span></span>
## <a name="properties"></a><span data-ttu-id="3ca76-103">속성</span><span class="sxs-lookup"><span data-stu-id="3ca76-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3ca76-104">ID</span><span class="sxs-lookup"><span data-stu-id="3ca76-104">ID</span></span>|<span data-ttu-id="3ca76-105">1010</span><span class="sxs-lookup"><span data-stu-id="3ca76-105">1010</span></span>|  
|<span data-ttu-id="3ca76-106">키워드</span><span class="sxs-lookup"><span data-stu-id="3ca76-106">Keywords</span></span>|<span data-ttu-id="3ca76-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="3ca76-107">WFRuntime</span></span>|  
|<span data-ttu-id="3ca76-108">수준</span><span class="sxs-lookup"><span data-stu-id="3ca76-108">Level</span></span>|<span data-ttu-id="3ca76-109">정보</span><span class="sxs-lookup"><span data-stu-id="3ca76-109">Information</span></span>|  
|<span data-ttu-id="3ca76-110">채널</span><span class="sxs-lookup"><span data-stu-id="3ca76-110">Channel</span></span>|<span data-ttu-id="3ca76-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="3ca76-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3ca76-112">설명</span><span class="sxs-lookup"><span data-stu-id="3ca76-112">Description</span></span>  
 <span data-ttu-id="3ca76-113">작업의 실행이 완료되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3ca76-113">Indicates an activity has completed execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3ca76-114">메시지</span><span class="sxs-lookup"><span data-stu-id="3ca76-114">Message</span></span>  
 <span data-ttu-id="3ca76-115">Activity '%1', DisplayName: '%2', InstanceId: '%3'이(가) '%4' 상태로 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3ca76-115">Activity '%1', DisplayName: '%2', InstanceId: '%3' has completed in the '%4' state.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3ca76-116">설명</span><span class="sxs-lookup"><span data-stu-id="3ca76-116">Details</span></span>  
  
|<span data-ttu-id="3ca76-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="3ca76-117">Data Item Name</span></span>|<span data-ttu-id="3ca76-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="3ca76-118">Data Item Type</span></span>|<span data-ttu-id="3ca76-119">설명</span><span class="sxs-lookup"><span data-stu-id="3ca76-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3ca76-120">동작</span><span class="sxs-lookup"><span data-stu-id="3ca76-120">Activity</span></span>|<span data-ttu-id="3ca76-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="3ca76-121">xs:string</span></span>|<span data-ttu-id="3ca76-122">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3ca76-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="3ca76-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="3ca76-123">DisplayName</span></span>|<span data-ttu-id="3ca76-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="3ca76-124">xs:string</span></span>|<span data-ttu-id="3ca76-125">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3ca76-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="3ca76-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="3ca76-126">InstanceId</span></span>|<span data-ttu-id="3ca76-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="3ca76-127">xs:string</span></span>|<span data-ttu-id="3ca76-128">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="3ca76-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="3ca76-129">상태</span><span class="sxs-lookup"><span data-stu-id="3ca76-129">State</span></span>|<span data-ttu-id="3ca76-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="3ca76-130">xs:string</span></span>|<span data-ttu-id="3ca76-131">작업의 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="3ca76-131">The state of the activity.</span></span>|  
|<span data-ttu-id="3ca76-132">AppDomain</span><span class="sxs-lookup"><span data-stu-id="3ca76-132">AppDomain</span></span>|<span data-ttu-id="3ca76-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="3ca76-133">xs:string</span></span>|<span data-ttu-id="3ca76-134">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="3ca76-134">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
