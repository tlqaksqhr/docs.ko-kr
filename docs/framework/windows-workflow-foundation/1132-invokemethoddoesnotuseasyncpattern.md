---
title: 1132 - InvokeMethodDoesNotUseAsyncPattern
ms.date: 03/30/2017
ms.assetid: 436b3767-4460-46b0-9ea3-fc2963260c11
ms.openlocfilehash: 64701d4c38c042e8273129be19f9caeb2c442abf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33511878"
---
# <a name="1132---invokemethoddoesnotuseasyncpattern"></a><span data-ttu-id="28c3f-102">1132 - InvokeMethodDoesNotUseAsyncPattern</span><span class="sxs-lookup"><span data-stu-id="28c3f-102">1132 - InvokeMethodDoesNotUseAsyncPattern</span></span>
## <a name="properties"></a><span data-ttu-id="28c3f-103">속성</span><span class="sxs-lookup"><span data-stu-id="28c3f-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="28c3f-104">ID</span><span class="sxs-lookup"><span data-stu-id="28c3f-104">ID</span></span>|<span data-ttu-id="28c3f-105">1132</span><span class="sxs-lookup"><span data-stu-id="28c3f-105">1132</span></span>|  
|<span data-ttu-id="28c3f-106">키워드</span><span class="sxs-lookup"><span data-stu-id="28c3f-106">Keywords</span></span>|<span data-ttu-id="28c3f-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="28c3f-107">WFRuntime</span></span>|  
|<span data-ttu-id="28c3f-108">수준</span><span class="sxs-lookup"><span data-stu-id="28c3f-108">Level</span></span>|<span data-ttu-id="28c3f-109">정보</span><span class="sxs-lookup"><span data-stu-id="28c3f-109">Information</span></span>|  
|<span data-ttu-id="28c3f-110">채널</span><span class="sxs-lookup"><span data-stu-id="28c3f-110">Channel</span></span>|<span data-ttu-id="28c3f-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="28c3f-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="28c3f-112">설명</span><span class="sxs-lookup"><span data-stu-id="28c3f-112">Description</span></span>  
 <span data-ttu-id="28c3f-113">CacheMetadata 단계 중 InvokeMethod 작업에서 메서드를 호출할 때 비동기 패턴을 사용하지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="28c3f-113">During CacheMetadata step, InvokeMethod activity indicates that it is not using the async pattern when invoking the method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="28c3f-114">메시지</span><span class="sxs-lookup"><span data-stu-id="28c3f-114">Message</span></span>  
 <span data-ttu-id="28c3f-115">InvokeMethod '%1' - 메서드에서 비동기 패턴을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="28c3f-115">InvokeMethod '%1' - method does not use asynchronous pattern.</span></span>  
  
## <a name="details"></a><span data-ttu-id="28c3f-116">설명</span><span class="sxs-lookup"><span data-stu-id="28c3f-116">Details</span></span>  
  
|<span data-ttu-id="28c3f-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="28c3f-117">Data Item Name</span></span>|<span data-ttu-id="28c3f-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="28c3f-118">Data Item Type</span></span>|<span data-ttu-id="28c3f-119">설명</span><span class="sxs-lookup"><span data-stu-id="28c3f-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="28c3f-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="28c3f-120">InvokeMethod</span></span>|<span data-ttu-id="28c3f-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="28c3f-121">xs:string</span></span>|<span data-ttu-id="28c3f-122">InvokeMethod 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="28c3f-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="28c3f-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="28c3f-123">AppDomain</span></span>|<span data-ttu-id="28c3f-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="28c3f-124">xs:string</span></span>|<span data-ttu-id="28c3f-125">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="28c3f-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
