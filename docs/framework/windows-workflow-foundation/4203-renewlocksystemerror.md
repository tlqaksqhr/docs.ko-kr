---
title: 4203 - RenewLockSystemError
ms.date: 03/30/2017
ms.assetid: 6ec9ec6f-4ae2-45cf-b99b-02cdb9dc9ec9
ms.openlocfilehash: 984f7ddae8797cba17753a618d0820d21bde5eef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33513931"
---
# <a name="4203---renewlocksystemerror"></a><span data-ttu-id="1d88c-102">4203 - RenewLockSystemError</span><span class="sxs-lookup"><span data-stu-id="1d88c-102">4203 - RenewLockSystemError</span></span>
## <a name="properties"></a><span data-ttu-id="1d88c-103">속성</span><span class="sxs-lookup"><span data-stu-id="1d88c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1d88c-104">ID</span><span class="sxs-lookup"><span data-stu-id="1d88c-104">ID</span></span>|<span data-ttu-id="1d88c-105">4203</span><span class="sxs-lookup"><span data-stu-id="1d88c-105">4203</span></span>|  
|<span data-ttu-id="1d88c-106">키워드</span><span class="sxs-lookup"><span data-stu-id="1d88c-106">Keywords</span></span>|<span data-ttu-id="1d88c-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="1d88c-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="1d88c-108">수준</span><span class="sxs-lookup"><span data-stu-id="1d88c-108">Level</span></span>|<span data-ttu-id="1d88c-109">오류</span><span class="sxs-lookup"><span data-stu-id="1d88c-109">Error</span></span>|  
|<span data-ttu-id="1d88c-110">채널</span><span class="sxs-lookup"><span data-stu-id="1d88c-110">Channel</span></span>|<span data-ttu-id="1d88c-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="1d88c-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="1d88c-112">설명</span><span class="sxs-lookup"><span data-stu-id="1d88c-112">Description</span></span>  
 <span data-ttu-id="1d88c-113">잠금 만료가 이미 지났거나 잠금 소유자가 삭제되었기 때문에 SQL 공급자가 잠금 만료를 연장하지 못했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1d88c-113">Indicates SQL provider has failed to extend lock expiration due to either lock expiration already passed or the lock owner was deleted.</span></span> <span data-ttu-id="1d88c-114">SqlWorkflowInstanceStore가 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d88c-114">The SqlWorkflowInstanceStore will be aborted.</span></span>  
  
## <a name="message"></a><span data-ttu-id="1d88c-115">메시지</span><span class="sxs-lookup"><span data-stu-id="1d88c-115">Message</span></span>  
 <span data-ttu-id="1d88c-116">잠금 만료를 연장하지 못했습니다. 잠금 만료가 이미 지났거나 잠금 소유자가 삭제되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1d88c-116">Failed to extend lock expiration, lock expiration already passed or the lock owner was deleted.</span></span> <span data-ttu-id="1d88c-117">SqlWorkflowInstanceStore를 중단하는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="1d88c-117">Aborting SqlWorkflowInstanceStore.</span></span>  
  
## <a name="details"></a><span data-ttu-id="1d88c-118">설명</span><span class="sxs-lookup"><span data-stu-id="1d88c-118">Details</span></span>  
  
|<span data-ttu-id="1d88c-119">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="1d88c-119">Data Item Name</span></span>|<span data-ttu-id="1d88c-120">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="1d88c-120">Data Item Type</span></span>|<span data-ttu-id="1d88c-121">설명</span><span class="sxs-lookup"><span data-stu-id="1d88c-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="1d88c-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="1d88c-122">AppDomain</span></span>|<span data-ttu-id="1d88c-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="1d88c-123">xs:string</span></span>|<span data-ttu-id="1d88c-124">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="1d88c-124">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
