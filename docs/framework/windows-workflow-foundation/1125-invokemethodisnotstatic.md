---
title: 1125 - InvokeMethodIsNotStatic
ms.date: 03/30/2017
ms.assetid: ea2b3827-63da-497b-b2c3-d5cebefe57a1
ms.openlocfilehash: 692c5e56dac0a69ab5705acd284f048391145641
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33511945"
---
# <a name="1125---invokemethodisnotstatic"></a><span data-ttu-id="91e48-102">1125 - InvokeMethodIsNotStatic</span><span class="sxs-lookup"><span data-stu-id="91e48-102">1125 - InvokeMethodIsNotStatic</span></span>
## <a name="properties"></a><span data-ttu-id="91e48-103">속성</span><span class="sxs-lookup"><span data-stu-id="91e48-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="91e48-104">ID</span><span class="sxs-lookup"><span data-stu-id="91e48-104">ID</span></span>|<span data-ttu-id="91e48-105">1125</span><span class="sxs-lookup"><span data-stu-id="91e48-105">1125</span></span>|  
|<span data-ttu-id="91e48-106">키워드</span><span class="sxs-lookup"><span data-stu-id="91e48-106">Keywords</span></span>|<span data-ttu-id="91e48-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="91e48-107">WFRuntime</span></span>|  
|<span data-ttu-id="91e48-108">수준</span><span class="sxs-lookup"><span data-stu-id="91e48-108">Level</span></span>|<span data-ttu-id="91e48-109">정보</span><span class="sxs-lookup"><span data-stu-id="91e48-109">Information</span></span>|  
|<span data-ttu-id="91e48-110">채널</span><span class="sxs-lookup"><span data-stu-id="91e48-110">Channel</span></span>|<span data-ttu-id="91e48-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="91e48-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="91e48-112">설명</span><span class="sxs-lookup"><span data-stu-id="91e48-112">Description</span></span>  
 <span data-ttu-id="91e48-113">CacheMetadata 단계 중 InvokeMethod 작업에서 호출할 메서드가 정적이 아님을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="91e48-113">During CacheMetadata step, InvokeMethod activity indicates the method to be invoked is not static.</span></span>  
  
## <a name="message"></a><span data-ttu-id="91e48-114">메시지</span><span class="sxs-lookup"><span data-stu-id="91e48-114">Message</span></span>  
 <span data-ttu-id="91e48-115">InvokeMethod ''%1' - 메서드가 Static이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="91e48-115">InvokeMethod '%1' - method is not Static.</span></span>  
  
## <a name="details"></a><span data-ttu-id="91e48-116">설명</span><span class="sxs-lookup"><span data-stu-id="91e48-116">Details</span></span>  
  
|<span data-ttu-id="91e48-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="91e48-117">Data Item Name</span></span>|<span data-ttu-id="91e48-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="91e48-118">Data Item Type</span></span>|<span data-ttu-id="91e48-119">설명</span><span class="sxs-lookup"><span data-stu-id="91e48-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="91e48-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="91e48-120">InvokeMethod</span></span>|<span data-ttu-id="91e48-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="91e48-121">xs:string</span></span>|<span data-ttu-id="91e48-122">InvokeMethod 작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="91e48-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="91e48-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="91e48-123">AppDomain</span></span>|<span data-ttu-id="91e48-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="91e48-124">xs:string</span></span>|<span data-ttu-id="91e48-125">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="91e48-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
