---
title: 4211 - QueuingSqlRetry
ms.date: 03/30/2017
ms.assetid: df569f88-c86b-4503-840d-1399b67f4df7
ms.openlocfilehash: ede74eb642c5c2c79b90cf1458db424d9f83b087
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33514571"
---
# <a name="4211---queuingsqlretry"></a><span data-ttu-id="ffcf7-102">4211 - QueuingSqlRetry</span><span class="sxs-lookup"><span data-stu-id="ffcf7-102">4211 - QueuingSqlRetry</span></span>
## <a name="properties"></a><span data-ttu-id="ffcf7-103">속성</span><span class="sxs-lookup"><span data-stu-id="ffcf7-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ffcf7-104">ID</span><span class="sxs-lookup"><span data-stu-id="ffcf7-104">ID</span></span>|<span data-ttu-id="ffcf7-105">4211</span><span class="sxs-lookup"><span data-stu-id="ffcf7-105">4211</span></span>|  
|<span data-ttu-id="ffcf7-106">키워드</span><span class="sxs-lookup"><span data-stu-id="ffcf7-106">Keywords</span></span>|<span data-ttu-id="ffcf7-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="ffcf7-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="ffcf7-108">수준</span><span class="sxs-lookup"><span data-stu-id="ffcf7-108">Level</span></span>|<span data-ttu-id="ffcf7-109">경고</span><span class="sxs-lookup"><span data-stu-id="ffcf7-109">Warning</span></span>|  
|<span data-ttu-id="ffcf7-110">채널</span><span class="sxs-lookup"><span data-stu-id="ffcf7-110">Channel</span></span>|<span data-ttu-id="ffcf7-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="ffcf7-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="ffcf7-112">설명</span><span class="sxs-lookup"><span data-stu-id="ffcf7-112">Description</span></span>  
 <span data-ttu-id="ffcf7-113">SQL 재시도를 큐에 넣고 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="ffcf7-113">Indicates queuing SQL retry.</span></span>  
  
## <a name="message"></a><span data-ttu-id="ffcf7-114">메시지</span><span class="sxs-lookup"><span data-stu-id="ffcf7-114">Message</span></span>  
 <span data-ttu-id="ffcf7-115">%1밀리초의 지연으로 SQL 재시도를 큐에 넣고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffcf7-115">Queuing SQL retry with delay %1 milliseconds.</span></span>  
  
## <a name="details"></a><span data-ttu-id="ffcf7-116">설명</span><span class="sxs-lookup"><span data-stu-id="ffcf7-116">Details</span></span>  
  
|<span data-ttu-id="ffcf7-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="ffcf7-117">Data Item Name</span></span>|<span data-ttu-id="ffcf7-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="ffcf7-118">Data Item Type</span></span>|<span data-ttu-id="ffcf7-119">설명</span><span class="sxs-lookup"><span data-stu-id="ffcf7-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="ffcf7-120">Delay</span><span class="sxs-lookup"><span data-stu-id="ffcf7-120">Delay</span></span>|<span data-ttu-id="ffcf7-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="ffcf7-121">xs:string</span></span>|<span data-ttu-id="ffcf7-122">재시도 사이의 지연입니다.</span><span class="sxs-lookup"><span data-stu-id="ffcf7-122">The delay between retries.</span></span>|  
|<span data-ttu-id="ffcf7-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="ffcf7-123">AppDomain</span></span>|<span data-ttu-id="ffcf7-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="ffcf7-124">xs:string</span></span>|<span data-ttu-id="ffcf7-125">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="ffcf7-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
