---
title: 1019 - CompleteCancelActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 75a4a1ab-e5a3-4f4e-88e4-d19806e671d7
ms.openlocfilehash: 28d19742055c51ca94c36ffddf15dced7dfc14cf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510210"
---
# <a name="1019---completecancelactivityworkitem"></a><span data-ttu-id="fced0-102">1019 - CompleteCancelActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="fced0-102">1019 - CompleteCancelActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="fced0-103">속성</span><span class="sxs-lookup"><span data-stu-id="fced0-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fced0-104">ID</span><span class="sxs-lookup"><span data-stu-id="fced0-104">ID</span></span>|<span data-ttu-id="fced0-105">1019</span><span class="sxs-lookup"><span data-stu-id="fced0-105">1019</span></span>|  
|<span data-ttu-id="fced0-106">키워드</span><span class="sxs-lookup"><span data-stu-id="fced0-106">Keywords</span></span>|<span data-ttu-id="fced0-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="fced0-107">WFRuntime</span></span>|  
|<span data-ttu-id="fced0-108">수준</span><span class="sxs-lookup"><span data-stu-id="fced0-108">Level</span></span>|<span data-ttu-id="fced0-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="fced0-109">Verbose</span></span>|  
|<span data-ttu-id="fced0-110">채널</span><span class="sxs-lookup"><span data-stu-id="fced0-110">Channel</span></span>|<span data-ttu-id="fced0-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="fced0-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="fced0-112">설명</span><span class="sxs-lookup"><span data-stu-id="fced0-112">Description</span></span>  
 <span data-ttu-id="fced0-113">CancelActivityWorkItem이 완료되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fced0-113">Indicates a CancelActivityWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="fced0-114">메시지</span><span class="sxs-lookup"><span data-stu-id="fced0-114">Message</span></span>  
 <span data-ttu-id="fced0-115">작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 CancelActivityWorkItem이 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fced0-115">A CancelActivityWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="fced0-116">설명</span><span class="sxs-lookup"><span data-stu-id="fced0-116">Details</span></span>  
  
|<span data-ttu-id="fced0-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="fced0-117">Data Item Name</span></span>|<span data-ttu-id="fced0-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="fced0-118">Data Item Type</span></span>|<span data-ttu-id="fced0-119">설명</span><span class="sxs-lookup"><span data-stu-id="fced0-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="fced0-120">동작</span><span class="sxs-lookup"><span data-stu-id="fced0-120">Activity</span></span>|<span data-ttu-id="fced0-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="fced0-121">xs:string</span></span>|<span data-ttu-id="fced0-122">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="fced0-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="fced0-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="fced0-123">DisplayName</span></span>|<span data-ttu-id="fced0-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="fced0-124">xs:string</span></span>|<span data-ttu-id="fced0-125">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="fced0-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="fced0-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="fced0-126">InstanceId</span></span>|<span data-ttu-id="fced0-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="fced0-127">xs:string</span></span>|<span data-ttu-id="fced0-128">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="fced0-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="fced0-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="fced0-129">AppDomain</span></span>|<span data-ttu-id="fced0-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="fced0-130">xs:string</span></span>|<span data-ttu-id="fced0-131">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="fced0-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
