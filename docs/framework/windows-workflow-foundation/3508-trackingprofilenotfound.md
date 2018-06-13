---
title: 3508 - TrackingProfileNotFound
ms.date: 03/30/2017
ms.assetid: 4cee3c4a-0490-4c94-aa19-ef7ce7287c02
ms.openlocfilehash: 94c7ce231df241778f7c6ec5fe5998eae364750d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33512186"
---
# <a name="3508---trackingprofilenotfound"></a><span data-ttu-id="52fb6-102">3508 - TrackingProfileNotFound</span><span class="sxs-lookup"><span data-stu-id="52fb6-102">3508 - TrackingProfileNotFound</span></span>
## <a name="properties"></a><span data-ttu-id="52fb6-103">속성</span><span class="sxs-lookup"><span data-stu-id="52fb6-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="52fb6-104">ID</span><span class="sxs-lookup"><span data-stu-id="52fb6-104">ID</span></span>|<span data-ttu-id="52fb6-105">3508</span><span class="sxs-lookup"><span data-stu-id="52fb6-105">3508</span></span>|  
|<span data-ttu-id="52fb6-106">키워드</span><span class="sxs-lookup"><span data-stu-id="52fb6-106">Keywords</span></span>|<span data-ttu-id="52fb6-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="52fb6-107">WFServices</span></span>|  
|<span data-ttu-id="52fb6-108">수준</span><span class="sxs-lookup"><span data-stu-id="52fb6-108">Level</span></span>|<span data-ttu-id="52fb6-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="52fb6-109">Verbose</span></span>|  
|<span data-ttu-id="52fb6-110">채널</span><span class="sxs-lookup"><span data-stu-id="52fb6-110">Channel</span></span>|<span data-ttu-id="52fb6-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/분석</span><span class="sxs-lookup"><span data-stu-id="52fb6-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="52fb6-112">설명</span><span class="sxs-lookup"><span data-stu-id="52fb6-112">Description</span></span>  
 <span data-ttu-id="52fb6-113">구성 파일에 TrackingProfile이 없거나 ActivityDefinitionId가 프로필과 일치하지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="52fb6-113">Indicates either a TrackingProfile is not found in the config file or the ActivityDefinitionId does not match the profile.</span></span>  
  
## <a name="message"></a><span data-ttu-id="52fb6-114">메시지</span><span class="sxs-lookup"><span data-stu-id="52fb6-114">Message</span></span>  
 <span data-ttu-id="52fb6-115">ActivityDefinitionId '%2'에 대한 TrackingProfile '%1'을(를) 찾지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="52fb6-115">TrackingProfile '%1' for the ActivityDefinitionId '%2' not found.</span></span> <span data-ttu-id="52fb6-116">구성 파일에 TrackingProfile이 없거나 ActivityDefinitionId가 일치하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="52fb6-116">Either the TrackingProfile is not found in the config file or the ActivityDefinitionId does not match.</span></span>  
  
## <a name="details"></a><span data-ttu-id="52fb6-117">설명</span><span class="sxs-lookup"><span data-stu-id="52fb6-117">Details</span></span>  
  
|<span data-ttu-id="52fb6-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="52fb6-118">Data Item Name</span></span>|<span data-ttu-id="52fb6-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="52fb6-119">Data Item Type</span></span>|<span data-ttu-id="52fb6-120">설명</span><span class="sxs-lookup"><span data-stu-id="52fb6-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="52fb6-121">TrackingProfile</span><span class="sxs-lookup"><span data-stu-id="52fb6-121">TrackingProfile</span></span>|<span data-ttu-id="52fb6-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="52fb6-122">xs:string</span></span>|<span data-ttu-id="52fb6-123">추적 프로필의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="52fb6-123">The name of the tracking profile.</span></span>|  
|<span data-ttu-id="52fb6-124">ActivityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="52fb6-124">ActivityDefinitionId</span></span>|<span data-ttu-id="52fb6-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="52fb6-125">xs:string</span></span>|<span data-ttu-id="52fb6-126">작업 정의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="52fb6-126">The activity definition id.</span></span>|  
|<span data-ttu-id="52fb6-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="52fb6-127">AppDomain</span></span>|<span data-ttu-id="52fb6-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="52fb6-128">xs:string</span></span>|<span data-ttu-id="52fb6-129">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="52fb6-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
