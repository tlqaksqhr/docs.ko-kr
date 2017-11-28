---
title: 2578 - TryCatchExceptionFromCatchOrFinally
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4803fee6-b8d8-4937-9907-d5c5fd5299db
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 22a798dabd2253d340d7fb3dffb9f95fc66d0a9a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="2578---trycatchexceptionfromcatchorfinally"></a><span data-ttu-id="68dc6-102">2578 - TryCatchExceptionFromCatchOrFinally</span><span class="sxs-lookup"><span data-stu-id="68dc6-102">2578 - TryCatchExceptionFromCatchOrFinally</span></span>
## <a name="properties"></a><span data-ttu-id="68dc6-103">속성</span><span class="sxs-lookup"><span data-stu-id="68dc6-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="68dc6-104">ID</span><span class="sxs-lookup"><span data-stu-id="68dc6-104">ID</span></span>|<span data-ttu-id="68dc6-105">2578</span><span class="sxs-lookup"><span data-stu-id="68dc6-105">2578</span></span>|  
|<span data-ttu-id="68dc6-106">키워드</span><span class="sxs-lookup"><span data-stu-id="68dc6-106">Keywords</span></span>|<span data-ttu-id="68dc6-107">WFActivities</span><span class="sxs-lookup"><span data-stu-id="68dc6-107">WFActivities</span></span>|  
|<span data-ttu-id="68dc6-108">수준</span><span class="sxs-lookup"><span data-stu-id="68dc6-108">Level</span></span>|<span data-ttu-id="68dc6-109">경고</span><span class="sxs-lookup"><span data-stu-id="68dc6-109">Warning</span></span>|  
|<span data-ttu-id="68dc6-110">채널</span><span class="sxs-lookup"><span data-stu-id="68dc6-110">Channel</span></span>|<span data-ttu-id="68dc6-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="68dc6-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="68dc6-112">설명</span><span class="sxs-lookup"><span data-stu-id="68dc6-112">Description</span></span>  
 <span data-ttu-id="68dc6-113">Catch 또는 Finally 작업에서 예외가 throw되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="68dc6-113">Indicates a Catch or Finally activity has thrown an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="68dc6-114">메시지</span><span class="sxs-lookup"><span data-stu-id="68dc6-114">Message</span></span>  
 <span data-ttu-id="68dc6-115">TryCatch 작업 '%1'에 연결된 Catch 또는 Finally 작업에서 예외가 throw되었습니다.</span><span class="sxs-lookup"><span data-stu-id="68dc6-115">A Catch or Finally activity that is associated with the TryCatch activity '%1' has thrown an exception.</span></span>  
  
## <a name="details"></a><span data-ttu-id="68dc6-116">설명</span><span class="sxs-lookup"><span data-stu-id="68dc6-116">Details</span></span>  
  
|<span data-ttu-id="68dc6-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="68dc6-117">Data Item Name</span></span>|<span data-ttu-id="68dc6-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="68dc6-118">Data Item Type</span></span>|<span data-ttu-id="68dc6-119">설명</span><span class="sxs-lookup"><span data-stu-id="68dc6-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="68dc6-120">DisplayName</span><span class="sxs-lookup"><span data-stu-id="68dc6-120">DisplayName</span></span>|<span data-ttu-id="68dc6-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="68dc6-121">xs:string</span></span>|<span data-ttu-id="68dc6-122">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="68dc6-122">The display name of the activity.</span></span>|  
|<span data-ttu-id="68dc6-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="68dc6-123">AppDomain</span></span>|<span data-ttu-id="68dc6-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="68dc6-124">xs:string</span></span>|<span data-ttu-id="68dc6-125">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="68dc6-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
