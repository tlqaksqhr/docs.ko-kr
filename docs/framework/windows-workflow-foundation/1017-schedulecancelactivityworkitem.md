---
title: 1017 - ScheduleCancelActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 864546ab-d65c-4989-8fcb-537ba03a3cdd
ms.openlocfilehash: 186b012cdd554ec7dd0d195b460619cca04eddcb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510174"
---
# <a name="1017---schedulecancelactivityworkitem"></a><span data-ttu-id="8f257-102">1017 - ScheduleCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="8f257-102">1017 - ScheduleCancelActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="8f257-103">속성</span><span class="sxs-lookup"><span data-stu-id="8f257-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8f257-104">ID</span><span class="sxs-lookup"><span data-stu-id="8f257-104">ID</span></span>|<span data-ttu-id="8f257-105">1017</span><span class="sxs-lookup"><span data-stu-id="8f257-105">1017</span></span>|  
|<span data-ttu-id="8f257-106">키워드</span><span class="sxs-lookup"><span data-stu-id="8f257-106">Keywords</span></span>|<span data-ttu-id="8f257-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="8f257-107">WFRuntime</span></span>|  
|<span data-ttu-id="8f257-108">수준</span><span class="sxs-lookup"><span data-stu-id="8f257-108">Level</span></span>|<span data-ttu-id="8f257-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="8f257-109">Verbose</span></span>|  
|<span data-ttu-id="8f257-110">채널</span><span class="sxs-lookup"><span data-stu-id="8f257-110">Channel</span></span>|<span data-ttu-id="8f257-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="8f257-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="8f257-112">설명</span><span class="sxs-lookup"><span data-stu-id="8f257-112">Description</span></span>  
 <span data-ttu-id="8f257-113">CancelActivityWorkItem이 예약되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8f257-113">Indicates a CancelActivityWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="8f257-114">메시지</span><span class="sxs-lookup"><span data-stu-id="8f257-114">Message</span></span>  
 <span data-ttu-id="8f257-115">작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 CancelActivityWorkItem이 예약되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8f257-115">A CancelActivityWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="8f257-116">설명</span><span class="sxs-lookup"><span data-stu-id="8f257-116">Details</span></span>  
  
|<span data-ttu-id="8f257-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="8f257-117">Data Item Name</span></span>|<span data-ttu-id="8f257-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="8f257-118">Data Item Type</span></span>|<span data-ttu-id="8f257-119">설명</span><span class="sxs-lookup"><span data-stu-id="8f257-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="8f257-120">동작</span><span class="sxs-lookup"><span data-stu-id="8f257-120">Activity</span></span>|<span data-ttu-id="8f257-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="8f257-121">xs:string</span></span>|<span data-ttu-id="8f257-122">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8f257-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="8f257-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="8f257-123">DisplayName</span></span>|<span data-ttu-id="8f257-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="8f257-124">xs:string</span></span>|<span data-ttu-id="8f257-125">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8f257-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="8f257-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="8f257-126">InstanceId</span></span>|<span data-ttu-id="8f257-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="8f257-127">xs:string</span></span>|<span data-ttu-id="8f257-128">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="8f257-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="8f257-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="8f257-129">AppDomain</span></span>|<span data-ttu-id="8f257-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="8f257-130">xs:string</span></span>|<span data-ttu-id="8f257-131">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="8f257-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
