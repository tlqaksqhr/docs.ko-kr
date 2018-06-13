---
title: 1036 - RuntimeTransactionCompletionRequested
ms.date: 03/30/2017
ms.assetid: d36b9f44-7c0f-4083-9d3a-9034dd2b98de
ms.openlocfilehash: 649ba542a9ed2f330ac71e447602d637530dc601
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33510395"
---
# <a name="1036---runtimetransactioncompletionrequested"></a><span data-ttu-id="34b45-102">1036 - RuntimeTransactionCompletionRequested</span><span class="sxs-lookup"><span data-stu-id="34b45-102">1036 - RuntimeTransactionCompletionRequested</span></span>
## <a name="properties"></a><span data-ttu-id="34b45-103">속성</span><span class="sxs-lookup"><span data-stu-id="34b45-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="34b45-104">ID</span><span class="sxs-lookup"><span data-stu-id="34b45-104">ID</span></span>|<span data-ttu-id="34b45-105">1036</span><span class="sxs-lookup"><span data-stu-id="34b45-105">1036</span></span>|  
|<span data-ttu-id="34b45-106">키워드</span><span class="sxs-lookup"><span data-stu-id="34b45-106">Keywords</span></span>|<span data-ttu-id="34b45-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="34b45-107">WFRuntime</span></span>|  
|<span data-ttu-id="34b45-108">수준</span><span class="sxs-lookup"><span data-stu-id="34b45-108">Level</span></span>|<span data-ttu-id="34b45-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="34b45-109">Verbose</span></span>|  
|<span data-ttu-id="34b45-110">채널</span><span class="sxs-lookup"><span data-stu-id="34b45-110">Channel</span></span>|<span data-ttu-id="34b45-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="34b45-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="34b45-112">설명</span><span class="sxs-lookup"><span data-stu-id="34b45-112">Description</span></span>  
 <span data-ttu-id="34b45-113">작업이 런타임 트랜잭션의 완료를 예약했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="34b45-113">Indicates an activity has scheduled the completion of the runtime transaction.</span></span>  
  
## <a name="message"></a><span data-ttu-id="34b45-114">메시지</span><span class="sxs-lookup"><span data-stu-id="34b45-114">Message</span></span>  
 <span data-ttu-id="34b45-115">작업 '%1', DisplayName: '%2', InstanceId: '%3'이(가) 런타임 트랜잭션 완료를 예약했습니다.</span><span class="sxs-lookup"><span data-stu-id="34b45-115">Activity '%1', DisplayName: '%2', InstanceId: '%3' has scheduled completion of the runtime transaction.</span></span>  
  
## <a name="details"></a><span data-ttu-id="34b45-116">설명</span><span class="sxs-lookup"><span data-stu-id="34b45-116">Details</span></span>  
  
|<span data-ttu-id="34b45-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="34b45-117">Data Item Name</span></span>|<span data-ttu-id="34b45-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="34b45-118">Data Item Type</span></span>|<span data-ttu-id="34b45-119">설명</span><span class="sxs-lookup"><span data-stu-id="34b45-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="34b45-120">동작</span><span class="sxs-lookup"><span data-stu-id="34b45-120">Activity</span></span>|<span data-ttu-id="34b45-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="34b45-121">xs:string</span></span>|<span data-ttu-id="34b45-122">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="34b45-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="34b45-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="34b45-123">DisplayName</span></span>|<span data-ttu-id="34b45-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="34b45-124">xs:string</span></span>|<span data-ttu-id="34b45-125">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="34b45-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="34b45-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="34b45-126">InstanceId</span></span>|<span data-ttu-id="34b45-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="34b45-127">xs:string</span></span>|<span data-ttu-id="34b45-128">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="34b45-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="34b45-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="34b45-129">AppDomain</span></span>|<span data-ttu-id="34b45-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="34b45-130">xs:string</span></span>|<span data-ttu-id="34b45-131">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="34b45-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
