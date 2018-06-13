---
title: 1012 - StartExecuteActivityWorkItem
ms.date: 03/30/2017
ms.assetid: 29e9b1c6-c5d7-4b58-b59d-a06a923d3c80
ms.openlocfilehash: d6b330bc454c39584e5027f757fd9d9d3434d941
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510382"
---
# <a name="1012---startexecuteactivityworkitem"></a><span data-ttu-id="33aff-102">1012 - StartExecuteActivityWorkItem</span><span class="sxs-lookup"><span data-stu-id="33aff-102">1012 - StartExecuteActivityWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="33aff-103">속성</span><span class="sxs-lookup"><span data-stu-id="33aff-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="33aff-104">ID</span><span class="sxs-lookup"><span data-stu-id="33aff-104">ID</span></span>|<span data-ttu-id="33aff-105">1012</span><span class="sxs-lookup"><span data-stu-id="33aff-105">1012</span></span>|  
|<span data-ttu-id="33aff-106">키워드</span><span class="sxs-lookup"><span data-stu-id="33aff-106">Keywords</span></span>|<span data-ttu-id="33aff-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="33aff-107">WFRuntime</span></span>|  
|<span data-ttu-id="33aff-108">수준</span><span class="sxs-lookup"><span data-stu-id="33aff-108">Level</span></span>|<span data-ttu-id="33aff-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="33aff-109">Verbose</span></span>|  
|<span data-ttu-id="33aff-110">채널</span><span class="sxs-lookup"><span data-stu-id="33aff-110">Channel</span></span>|<span data-ttu-id="33aff-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="33aff-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="33aff-112">설명</span><span class="sxs-lookup"><span data-stu-id="33aff-112">Description</span></span>  
 <span data-ttu-id="33aff-113">ExecuteActivityWorkItem이 실행을 시작했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="33aff-113">Indicates an ExecuteActivityWorkItem is starting execution.</span></span>  
  
## <a name="message"></a><span data-ttu-id="33aff-114">메시지</span><span class="sxs-lookup"><span data-stu-id="33aff-114">Message</span></span>  
 <span data-ttu-id="33aff-115">작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 ExecuteActivityWorkItem 실행을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="33aff-115">Starting execution of an ExecuteActivityWorkItem for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="33aff-116">설명</span><span class="sxs-lookup"><span data-stu-id="33aff-116">Details</span></span>  
  
|<span data-ttu-id="33aff-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="33aff-117">Data Item Name</span></span>|<span data-ttu-id="33aff-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="33aff-118">Data Item Type</span></span>|<span data-ttu-id="33aff-119">설명</span><span class="sxs-lookup"><span data-stu-id="33aff-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="33aff-120">동작</span><span class="sxs-lookup"><span data-stu-id="33aff-120">Activity</span></span>|<span data-ttu-id="33aff-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="33aff-121">xs:string</span></span>|<span data-ttu-id="33aff-122">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="33aff-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="33aff-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="33aff-123">DisplayName</span></span>|<span data-ttu-id="33aff-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="33aff-124">xs:string</span></span>|<span data-ttu-id="33aff-125">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="33aff-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="33aff-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="33aff-126">InstanceId</span></span>|<span data-ttu-id="33aff-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="33aff-127">xs:string</span></span>|<span data-ttu-id="33aff-128">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="33aff-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="33aff-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="33aff-129">AppDomain</span></span>|<span data-ttu-id="33aff-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="33aff-130">xs:string</span></span>|<span data-ttu-id="33aff-131">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="33aff-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
