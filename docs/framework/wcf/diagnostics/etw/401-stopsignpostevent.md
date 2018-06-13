---
title: 401- StopSignPostEvent
ms.date: 03/30/2017
ms.assetid: e033d03a-510d-4300-aa65-ef02cb4807f2
ms.openlocfilehash: 1776252c362feb3c3ebc04651603944040ceee7b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33474170"
---
# <a name="401--stopsignpostevent"></a><span data-ttu-id="d90c0-102">401- StopSignPostEvent</span><span class="sxs-lookup"><span data-stu-id="d90c0-102">401- StopSignPostEvent</span></span>
## <a name="properties"></a><span data-ttu-id="d90c0-103">속성</span><span class="sxs-lookup"><span data-stu-id="d90c0-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d90c0-104">ID</span><span class="sxs-lookup"><span data-stu-id="d90c0-104">ID</span></span>|<span data-ttu-id="d90c0-105">401</span><span class="sxs-lookup"><span data-stu-id="d90c0-105">401</span></span>|  
|<span data-ttu-id="d90c0-106">키워드</span><span class="sxs-lookup"><span data-stu-id="d90c0-106">Keywords</span></span>|<span data-ttu-id="d90c0-107">문제 해결</span><span class="sxs-lookup"><span data-stu-id="d90c0-107">Troubleshooting</span></span>|  
|<span data-ttu-id="d90c0-108">수준</span><span class="sxs-lookup"><span data-stu-id="d90c0-108">Level</span></span>|<span data-ttu-id="d90c0-109">정보</span><span class="sxs-lookup"><span data-stu-id="d90c0-109">Information</span></span>|  
|<span data-ttu-id="d90c0-110">채널</span><span class="sxs-lookup"><span data-stu-id="d90c0-110">Channel</span></span>|<span data-ttu-id="d90c0-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/분석</span><span class="sxs-lookup"><span data-stu-id="d90c0-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d90c0-112">설명</span><span class="sxs-lookup"><span data-stu-id="d90c0-112">Description</span></span>  
 <span data-ttu-id="d90c0-113">이 이벤트는 종단 간 동작의 끝을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d90c0-113">This event marks the end of an end-to-end activity.</span></span> <span data-ttu-id="d90c0-114">여기에는 동작의 이름이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d90c0-114">It contains the name of the activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d90c0-115">메시지</span><span class="sxs-lookup"><span data-stu-id="d90c0-115">Message</span></span>  
 <span data-ttu-id="d90c0-116">동작 경계입니다.</span><span class="sxs-lookup"><span data-stu-id="d90c0-116">Activity boundary.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d90c0-117">설명</span><span class="sxs-lookup"><span data-stu-id="d90c0-117">Details</span></span>  
  
|<span data-ttu-id="d90c0-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="d90c0-118">Data Item Name</span></span>|<span data-ttu-id="d90c0-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="d90c0-119">Data Item Type</span></span>|<span data-ttu-id="d90c0-120">설명</span><span class="sxs-lookup"><span data-stu-id="d90c0-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d90c0-121">Extended Data</span><span class="sxs-lookup"><span data-stu-id="d90c0-121">Extended Data</span></span>|`xs:string`|<span data-ttu-id="d90c0-122">작업의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d90c0-122">The name of the activity.</span></span>|  
|<span data-ttu-id="d90c0-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d90c0-123">AppDomain</span></span>|`xs:string`|<span data-ttu-id="d90c0-124">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="d90c0-124">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
