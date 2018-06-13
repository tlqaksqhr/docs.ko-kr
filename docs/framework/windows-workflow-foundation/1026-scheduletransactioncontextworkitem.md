---
title: 1026 - ScheduleTransactionContextWorkItem
ms.date: 03/30/2017
ms.assetid: 0d5f86ba-ec21-4129-a726-5432e425384c
ms.openlocfilehash: 6d0b43208f86c52e8863d4415a64466b0531832c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510285"
---
# <a name="1026---scheduletransactioncontextworkitem"></a><span data-ttu-id="b175e-102">1026 - ScheduleTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="b175e-102">1026 - ScheduleTransactionContextWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="b175e-103">속성</span><span class="sxs-lookup"><span data-stu-id="b175e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b175e-104">ID</span><span class="sxs-lookup"><span data-stu-id="b175e-104">ID</span></span>|<span data-ttu-id="b175e-105">1026</span><span class="sxs-lookup"><span data-stu-id="b175e-105">1026</span></span>|  
|<span data-ttu-id="b175e-106">키워드</span><span class="sxs-lookup"><span data-stu-id="b175e-106">Keywords</span></span>|<span data-ttu-id="b175e-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="b175e-107">WFRuntime</span></span>|  
|<span data-ttu-id="b175e-108">수준</span><span class="sxs-lookup"><span data-stu-id="b175e-108">Level</span></span>|<span data-ttu-id="b175e-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="b175e-109">Verbose</span></span>|  
|<span data-ttu-id="b175e-110">채널</span><span class="sxs-lookup"><span data-stu-id="b175e-110">Channel</span></span>|<span data-ttu-id="b175e-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="b175e-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="b175e-112">설명</span><span class="sxs-lookup"><span data-stu-id="b175e-112">Description</span></span>  
 <span data-ttu-id="b175e-113">TransactionContextWorkItem이 예약되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b175e-113">Indicates a TransactionContextWorkItem has been scheduled.</span></span>  
  
## <a name="message"></a><span data-ttu-id="b175e-114">메시지</span><span class="sxs-lookup"><span data-stu-id="b175e-114">Message</span></span>  
 <span data-ttu-id="b175e-115">작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 TransactionContextWorkItem이 예약되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b175e-115">A TransactionContextWorkItem has been scheduled for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="b175e-116">설명</span><span class="sxs-lookup"><span data-stu-id="b175e-116">Details</span></span>  
  
|<span data-ttu-id="b175e-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="b175e-117">Data Item Name</span></span>|<span data-ttu-id="b175e-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="b175e-118">Data Item Type</span></span>|<span data-ttu-id="b175e-119">설명</span><span class="sxs-lookup"><span data-stu-id="b175e-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="b175e-120">동작</span><span class="sxs-lookup"><span data-stu-id="b175e-120">Activity</span></span>|<span data-ttu-id="b175e-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="b175e-121">xs:string</span></span>|<span data-ttu-id="b175e-122">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b175e-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="b175e-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="b175e-123">DisplayName</span></span>|<span data-ttu-id="b175e-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="b175e-124">xs:string</span></span>|<span data-ttu-id="b175e-125">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b175e-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="b175e-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="b175e-126">InstanceId</span></span>|<span data-ttu-id="b175e-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="b175e-127">xs:string</span></span>|<span data-ttu-id="b175e-128">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b175e-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="b175e-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="b175e-129">AppDomain</span></span>|<span data-ttu-id="b175e-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="b175e-130">xs:string</span></span>|<span data-ttu-id="b175e-131">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="b175e-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
