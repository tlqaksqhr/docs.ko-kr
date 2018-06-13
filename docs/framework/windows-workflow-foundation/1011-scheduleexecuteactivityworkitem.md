---
title: 1011 - ScheduleExecuteActivityWorkItem
ms.date: 03/30/2017
ms.assetid: e503ae46-ad6b-4fcb-8c0e-146d59a8eff1
ms.openlocfilehash: 299d09b7c4db94a2e27378ba0cc3dfeb03734ab4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509618"
---
# <a name="1011---scheduleexecuteactivityworkitem"></a><span data-ttu-id="26294-102">1011 - ScheduleExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="26294-102">1011 - ScheduleExecuteActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="26294-103">속성</span><span class="sxs-lookup"><span data-stu-id="26294-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="26294-104">ID</span><span class="sxs-lookup"><span data-stu-id="26294-104">ID</span></span>|<span data-ttu-id="26294-105">1011</span><span class="sxs-lookup"><span data-stu-id="26294-105">1011</span></span>|  
|<span data-ttu-id="26294-106">키워드</span><span class="sxs-lookup"><span data-stu-id="26294-106">Keywords</span></span>|<span data-ttu-id="26294-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="26294-107">WFRuntime</span></span>|  
|<span data-ttu-id="26294-108">수준</span><span class="sxs-lookup"><span data-stu-id="26294-108">Level</span></span>|<span data-ttu-id="26294-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="26294-109">Verbose</span></span>|  
|<span data-ttu-id="26294-110">채널</span><span class="sxs-lookup"><span data-stu-id="26294-110">Channel</span></span>|<span data-ttu-id="26294-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="26294-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="26294-112">설명</span><span class="sxs-lookup"><span data-stu-id="26294-112">Description</span></span>  
 <span data-ttu-id="26294-113">ExecuteActivityWorkItem이 예약되어 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="26294-113">Indicates an ExecuteActivityWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="26294-114">메시지</span><span class="sxs-lookup"><span data-stu-id="26294-114">Message</span></span>  
 <span data-ttu-id="26294-115">작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 ExecuteActivityWorkItem이 예약되었습니다.</span><span class="sxs-lookup"><span data-stu-id="26294-115">An ExecuteActivityWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="26294-116">설명</span><span class="sxs-lookup"><span data-stu-id="26294-116">Details</span></span>  
  
|<span data-ttu-id="26294-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="26294-117">Data Item Name</span></span>|<span data-ttu-id="26294-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="26294-118">Data Item Type</span></span>|<span data-ttu-id="26294-119">설명</span><span class="sxs-lookup"><span data-stu-id="26294-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="26294-120">동작</span><span class="sxs-lookup"><span data-stu-id="26294-120">Activity</span></span>|<span data-ttu-id="26294-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="26294-121">xs:string</span></span>|<span data-ttu-id="26294-122">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="26294-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="26294-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="26294-123">DisplayName</span></span>|<span data-ttu-id="26294-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="26294-124">xs:string</span></span>|<span data-ttu-id="26294-125">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="26294-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="26294-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="26294-126">InstanceId</span></span>|<span data-ttu-id="26294-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="26294-127">xs:string</span></span>|<span data-ttu-id="26294-128">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="26294-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="26294-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="26294-129">AppDomain</span></span>|<span data-ttu-id="26294-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="26294-130">xs:string</span></span>|<span data-ttu-id="26294-131">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="26294-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
