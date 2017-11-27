---
title: 402 - StartSignpostEvent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5e5be126-765d-4ac9-88e7-008e9ef4f0e5
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c0cd786f78336be50ad2ef5447f74b92b2abbdc7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="402---startsignpostevent"></a><span data-ttu-id="94a8a-102">402 - StartSignpostEvent</span><span class="sxs-lookup"><span data-stu-id="94a8a-102">402 - StartSignpostEvent</span></span>
## <a name="properties"></a><span data-ttu-id="94a8a-103">속성</span><span class="sxs-lookup"><span data-stu-id="94a8a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="94a8a-104">ID</span><span class="sxs-lookup"><span data-stu-id="94a8a-104">ID</span></span>|<span data-ttu-id="94a8a-105">402</span><span class="sxs-lookup"><span data-stu-id="94a8a-105">402</span></span>|  
|<span data-ttu-id="94a8a-106">키워드가</span><span class="sxs-lookup"><span data-stu-id="94a8a-106">Keywords</span></span>|<span data-ttu-id="94a8a-107">문제 해결</span><span class="sxs-lookup"><span data-stu-id="94a8a-107">Troubleshooting</span></span>|  
|<span data-ttu-id="94a8a-108">수준</span><span class="sxs-lookup"><span data-stu-id="94a8a-108">Level</span></span>|<span data-ttu-id="94a8a-109">정보</span><span class="sxs-lookup"><span data-stu-id="94a8a-109">Information</span></span>|  
|<span data-ttu-id="94a8a-110">채널</span><span class="sxs-lookup"><span data-stu-id="94a8a-110">Channel</span></span>|<span data-ttu-id="94a8a-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/분석</span><span class="sxs-lookup"><span data-stu-id="94a8a-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="94a8a-112">설명</span><span class="sxs-lookup"><span data-stu-id="94a8a-112">Description</span></span>  
 <span data-ttu-id="94a8a-113">이 이벤트는 종단 간 동작의 시작을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="94a8a-113">This event marks the beginning of an end-to-end activity.</span></span> <span data-ttu-id="94a8a-114">여기에는 동작의 이름이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="94a8a-114">It contains the name of the activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="94a8a-115">메시지</span><span class="sxs-lookup"><span data-stu-id="94a8a-115">Message</span></span>  
 <span data-ttu-id="94a8a-116">동작 경계입니다.</span><span class="sxs-lookup"><span data-stu-id="94a8a-116">Activity boundary.</span></span>  
  
## <a name="details"></a><span data-ttu-id="94a8a-117">설명</span><span class="sxs-lookup"><span data-stu-id="94a8a-117">Details</span></span>  
  
|<span data-ttu-id="94a8a-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="94a8a-118">Data Item Name</span></span>|<span data-ttu-id="94a8a-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="94a8a-119">Data Item Type</span></span>|<span data-ttu-id="94a8a-120">설명</span><span class="sxs-lookup"><span data-stu-id="94a8a-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="94a8a-121">Extended Data</span><span class="sxs-lookup"><span data-stu-id="94a8a-121">Extended Data</span></span>|`xs:string`|<span data-ttu-id="94a8a-122">작업의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="94a8a-122">The name of the activity.</span></span>|  
|<span data-ttu-id="94a8a-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="94a8a-123">AppDomain</span></span>|`xs:string`|<span data-ttu-id="94a8a-124">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="94a8a-124">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
