---
title: 4212 - LockRetryTimeout
ms.date: 03/30/2017
ms.assetid: d4ad415a-9871-49fc-85b8-8ee2ea149b1d
ms.openlocfilehash: 9b7a463851d380eba1ef7b28fbc6decd0cfc979c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33511269"
---
# <a name="4212---lockretrytimeout"></a><span data-ttu-id="d4a8e-102">4212 - LockRetryTimeout</span><span class="sxs-lookup"><span data-stu-id="d4a8e-102">4212 - LockRetryTimeout</span></span>
## <a name="properties"></a><span data-ttu-id="d4a8e-103">속성</span><span class="sxs-lookup"><span data-stu-id="d4a8e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d4a8e-104">ID</span><span class="sxs-lookup"><span data-stu-id="d4a8e-104">ID</span></span>|<span data-ttu-id="d4a8e-105">4212</span><span class="sxs-lookup"><span data-stu-id="d4a8e-105">4212</span></span>|  
|<span data-ttu-id="d4a8e-106">키워드</span><span class="sxs-lookup"><span data-stu-id="d4a8e-106">Keywords</span></span>|<span data-ttu-id="d4a8e-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="d4a8e-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="d4a8e-108">수준</span><span class="sxs-lookup"><span data-stu-id="d4a8e-108">Level</span></span>|<span data-ttu-id="d4a8e-109">경고</span><span class="sxs-lookup"><span data-stu-id="d4a8e-109">Warning</span></span>|  
|<span data-ttu-id="d4a8e-110">채널</span><span class="sxs-lookup"><span data-stu-id="d4a8e-110">Channel</span></span>|<span data-ttu-id="d4a8e-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="d4a8e-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d4a8e-112">설명</span><span class="sxs-lookup"><span data-stu-id="d4a8e-112">Description</span></span>  
 <span data-ttu-id="d4a8e-113">SQL 공급자에서 인스턴스 잠금을 얻으려는 중 시간 초과가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="d4a8e-113">SQL provider encountered a timeout trying to acquire the instance lock.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d4a8e-114">메시지</span><span class="sxs-lookup"><span data-stu-id="d4a8e-114">Message</span></span>  
 <span data-ttu-id="d4a8e-115">인스턴스 잠금을 얻으려는 중 시간이 초과 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d4a8e-115">Timeout trying to acquire the instance lock.</span></span>  <span data-ttu-id="d4a8e-116">할당된 시간 제한인 %1 내에 작업을 완료하지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="d4a8e-116">The operation did not complete within the allotted timeout of %1.</span></span> <span data-ttu-id="d4a8e-117">이 작업에 할당된 시간은 더 긴 시간 제한의 일부였을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4a8e-117">The time allotted to this operation may have been a portion of a longer timeout.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d4a8e-118">설명</span><span class="sxs-lookup"><span data-stu-id="d4a8e-118">Details</span></span>  
  
|<span data-ttu-id="d4a8e-119">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="d4a8e-119">Data Item Name</span></span>|<span data-ttu-id="d4a8e-120">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="d4a8e-120">Data Item Type</span></span>|<span data-ttu-id="d4a8e-121">설명</span><span class="sxs-lookup"><span data-stu-id="d4a8e-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d4a8e-122">Delay</span><span class="sxs-lookup"><span data-stu-id="d4a8e-122">Delay</span></span>|<span data-ttu-id="d4a8e-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="d4a8e-123">xs:string</span></span>|<span data-ttu-id="d4a8e-124">재시도 사이의 지연입니다.</span><span class="sxs-lookup"><span data-stu-id="d4a8e-124">The delay between retries.</span></span>|  
|<span data-ttu-id="d4a8e-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d4a8e-125">AppDomain</span></span>|<span data-ttu-id="d4a8e-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="d4a8e-126">xs:string</span></span>|<span data-ttu-id="d4a8e-127">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="d4a8e-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
