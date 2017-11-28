---
title: 2577 - TryCatchExceptionDuringCancelation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 35ee9f55-227f-4566-bcb4-4c7c75dea85b
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2a4bc0d9ab45fe8e2f025c651fce137d6a4255bc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="2577---trycatchexceptionduringcancelation"></a><span data-ttu-id="7e606-102">2577 - TryCatchExceptionDuringCancelation</span><span class="sxs-lookup"><span data-stu-id="7e606-102">2577 - TryCatchExceptionDuringCancelation</span></span>
## <a name="properties"></a><span data-ttu-id="7e606-103">속성</span><span class="sxs-lookup"><span data-stu-id="7e606-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7e606-104">ID</span><span class="sxs-lookup"><span data-stu-id="7e606-104">ID</span></span>|<span data-ttu-id="7e606-105">2577</span><span class="sxs-lookup"><span data-stu-id="7e606-105">2577</span></span>|  
|<span data-ttu-id="7e606-106">키워드</span><span class="sxs-lookup"><span data-stu-id="7e606-106">Keywords</span></span>|<span data-ttu-id="7e606-107">WFActivities</span><span class="sxs-lookup"><span data-stu-id="7e606-107">WFActivities</span></span>|  
|<span data-ttu-id="7e606-108">수준</span><span class="sxs-lookup"><span data-stu-id="7e606-108">Level</span></span>|<span data-ttu-id="7e606-109">경고</span><span class="sxs-lookup"><span data-stu-id="7e606-109">Warning</span></span>|  
|<span data-ttu-id="7e606-110">채널</span><span class="sxs-lookup"><span data-stu-id="7e606-110">Channel</span></span>|<span data-ttu-id="7e606-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="7e606-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="7e606-112">설명</span><span class="sxs-lookup"><span data-stu-id="7e606-112">Description</span></span>  
 <span data-ttu-id="7e606-113">취소하는 동안 TryCatch 작업의 자식 작업에서 예외가 throw되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7e606-113">Indicates a child activity of the TryCatch activity has thrown an exception during cancelation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="7e606-114">메시지</span><span class="sxs-lookup"><span data-stu-id="7e606-114">Message</span></span>  
 <span data-ttu-id="7e606-115">취소하는 동안 TryCatch 작업 '%1'의 자식 작업에서 예외가 throw되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7e606-115">A child activity of the TryCatch activity '%1' has thrown an exception during cancelation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="7e606-116">설명</span><span class="sxs-lookup"><span data-stu-id="7e606-116">Details</span></span>  
  
|<span data-ttu-id="7e606-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="7e606-117">Data Item Name</span></span>|<span data-ttu-id="7e606-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="7e606-118">Data Item Type</span></span>|<span data-ttu-id="7e606-119">설명</span><span class="sxs-lookup"><span data-stu-id="7e606-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="7e606-120">DisplayName</span><span class="sxs-lookup"><span data-stu-id="7e606-120">DisplayName</span></span>|<span data-ttu-id="7e606-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="7e606-121">xs:string</span></span>|<span data-ttu-id="7e606-122">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7e606-122">The display name of the activity.</span></span>|  
|<span data-ttu-id="7e606-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="7e606-123">AppDomain</span></span>|<span data-ttu-id="7e606-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="7e606-124">xs:string</span></span>|<span data-ttu-id="7e606-125">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="7e606-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
