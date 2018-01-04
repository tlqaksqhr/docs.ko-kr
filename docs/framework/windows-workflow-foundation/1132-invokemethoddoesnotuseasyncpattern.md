---
title: 1132 - InvokeMethodDoesNotUseAsyncPattern
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 436b3767-4460-46b0-9ea3-fc2963260c11
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 75386b56f7926b9ddb883e0ca212d795898fe6f8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="1132---invokemethoddoesnotuseasyncpattern"></a><span data-ttu-id="c3d37-102">1132 - InvokeMethodDoesNotUseAsyncPattern</span><span class="sxs-lookup"><span data-stu-id="c3d37-102">1132 - InvokeMethodDoesNotUseAsyncPattern</span></span>
## <a name="properties"></a><span data-ttu-id="c3d37-103">속성</span><span class="sxs-lookup"><span data-stu-id="c3d37-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c3d37-104">ID</span><span class="sxs-lookup"><span data-stu-id="c3d37-104">ID</span></span>|<span data-ttu-id="c3d37-105">1132</span><span class="sxs-lookup"><span data-stu-id="c3d37-105">1132</span></span>|  
|<span data-ttu-id="c3d37-106">키워드</span><span class="sxs-lookup"><span data-stu-id="c3d37-106">Keywords</span></span>|<span data-ttu-id="c3d37-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="c3d37-107">WFRuntime</span></span>|  
|<span data-ttu-id="c3d37-108">수준</span><span class="sxs-lookup"><span data-stu-id="c3d37-108">Level</span></span>|<span data-ttu-id="c3d37-109">정보</span><span class="sxs-lookup"><span data-stu-id="c3d37-109">Information</span></span>|  
|<span data-ttu-id="c3d37-110">채널</span><span class="sxs-lookup"><span data-stu-id="c3d37-110">Channel</span></span>|<span data-ttu-id="c3d37-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="c3d37-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c3d37-112">설명</span><span class="sxs-lookup"><span data-stu-id="c3d37-112">Description</span></span>  
 <span data-ttu-id="c3d37-113">CacheMetadata 단계 중 InvokeMethod 작업에서 메서드를 호출할 때 비동기 패턴을 사용하지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c3d37-113">During CacheMetadata step, InvokeMethod activity indicates that it is not using the async pattern when invoking the method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c3d37-114">메시지</span><span class="sxs-lookup"><span data-stu-id="c3d37-114">Message</span></span>  
 <span data-ttu-id="c3d37-115">InvokeMethod '%1' - 메서드에서 비동기 패턴을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c3d37-115">InvokeMethod '%1' - method does not use asynchronous pattern.</span></span>  
  
## <a name="details"></a><span data-ttu-id="c3d37-116">설명</span><span class="sxs-lookup"><span data-stu-id="c3d37-116">Details</span></span>  
  
|<span data-ttu-id="c3d37-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="c3d37-117">Data Item Name</span></span>|<span data-ttu-id="c3d37-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="c3d37-118">Data Item Type</span></span>|<span data-ttu-id="c3d37-119">설명</span><span class="sxs-lookup"><span data-stu-id="c3d37-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="c3d37-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="c3d37-120">InvokeMethod</span></span>|<span data-ttu-id="c3d37-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="c3d37-121">xs:string</span></span>|<span data-ttu-id="c3d37-122">InvokeMethod 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c3d37-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="c3d37-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="c3d37-123">AppDomain</span></span>|<span data-ttu-id="c3d37-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="c3d37-124">xs:string</span></span>|<span data-ttu-id="c3d37-125">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="c3d37-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
