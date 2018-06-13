---
title: 1131 - InvokeMethodUseAsyncPattern
ms.date: 03/30/2017
ms.assetid: eca50fa7-5276-4759-ad1c-e490b9bd1f82
ms.openlocfilehash: 150973935d12455aa671043a619fbd6fd7e77425
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33512668"
---
# <a name="1131---invokemethoduseasyncpattern"></a><span data-ttu-id="327a0-102">1131 - InvokeMethodUseAsyncPattern</span><span class="sxs-lookup"><span data-stu-id="327a0-102">1131 - InvokeMethodUseAsyncPattern</span></span>
## <a name="properties"></a><span data-ttu-id="327a0-103">속성</span><span class="sxs-lookup"><span data-stu-id="327a0-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="327a0-104">ID</span><span class="sxs-lookup"><span data-stu-id="327a0-104">ID</span></span>|<span data-ttu-id="327a0-105">1131</span><span class="sxs-lookup"><span data-stu-id="327a0-105">1131</span></span>|  
|<span data-ttu-id="327a0-106">키워드</span><span class="sxs-lookup"><span data-stu-id="327a0-106">Keywords</span></span>|<span data-ttu-id="327a0-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="327a0-107">WFRuntime</span></span>|  
|<span data-ttu-id="327a0-108">수준</span><span class="sxs-lookup"><span data-stu-id="327a0-108">Level</span></span>|<span data-ttu-id="327a0-109">정보</span><span class="sxs-lookup"><span data-stu-id="327a0-109">Information</span></span>|  
|<span data-ttu-id="327a0-110">채널</span><span class="sxs-lookup"><span data-stu-id="327a0-110">Channel</span></span>|<span data-ttu-id="327a0-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="327a0-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="327a0-112">설명</span><span class="sxs-lookup"><span data-stu-id="327a0-112">Description</span></span>  
 <span data-ttu-id="327a0-113">CacheMetadata 단계 중 InvokeMethod 작업에서 메서드를 호출할 때 비동기 패턴을 사용함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="327a0-113">During CacheMetadata step, InvokeMethod activity indicates that it is using the async pattern when invoking the method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="327a0-114">메시지</span><span class="sxs-lookup"><span data-stu-id="327a0-114">Message</span></span>  
 <span data-ttu-id="327a0-115">InvokeMethod '%1'' - 메서드에서 ''%2' 및 '%3'의 비동기 패턴을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="327a0-115">InvokeMethod '%1' - method uses asynchronous pattern of '%2' and '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="327a0-116">설명</span><span class="sxs-lookup"><span data-stu-id="327a0-116">Details</span></span>  
  
|<span data-ttu-id="327a0-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="327a0-117">Data Item Name</span></span>|<span data-ttu-id="327a0-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="327a0-118">Data Item Type</span></span>|<span data-ttu-id="327a0-119">설명</span><span class="sxs-lookup"><span data-stu-id="327a0-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="327a0-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="327a0-120">InvokeMethod</span></span>|<span data-ttu-id="327a0-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="327a0-121">xs:string</span></span>|<span data-ttu-id="327a0-122">InvokeMethod 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="327a0-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="327a0-123">BeginMethod</span><span class="sxs-lookup"><span data-stu-id="327a0-123">BeginMethod</span></span>|<span data-ttu-id="327a0-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="327a0-124">xs:string</span></span>|<span data-ttu-id="327a0-125">Begin 메서드의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="327a0-125">The name of the begin method.</span></span>|  
|<span data-ttu-id="327a0-126">EndMethod</span><span class="sxs-lookup"><span data-stu-id="327a0-126">EndMethod</span></span>|<span data-ttu-id="327a0-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="327a0-127">xs:string</span></span>|<span data-ttu-id="327a0-128">End 메서드의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="327a0-128">The name of the end method.</span></span>|  
|<span data-ttu-id="327a0-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="327a0-129">AppDomain</span></span>|<span data-ttu-id="327a0-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="327a0-130">xs:string</span></span>|<span data-ttu-id="327a0-131">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="327a0-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
