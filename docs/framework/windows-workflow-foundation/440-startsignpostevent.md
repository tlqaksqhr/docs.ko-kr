---
title: 440 - StartSignpostEvent
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 27b551b5-ae76-49f8-bab8-6300009eb4c1
caps.latest.revision: "5"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c6cc59e1394c33321d74b9f48dd4a78af204ae31
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="440---startsignpostevent1"></a><span data-ttu-id="dda8a-102">440 - StartSignpostEvent</span><span class="sxs-lookup"><span data-stu-id="dda8a-102">440 - StartSignpostEvent1</span></span>
## <a name="properties"></a><span data-ttu-id="dda8a-103">속성</span><span class="sxs-lookup"><span data-stu-id="dda8a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="dda8a-104">ID</span><span class="sxs-lookup"><span data-stu-id="dda8a-104">ID</span></span>|<span data-ttu-id="dda8a-105">440</span><span class="sxs-lookup"><span data-stu-id="dda8a-105">440</span></span>|  
|<span data-ttu-id="dda8a-106">키워드</span><span class="sxs-lookup"><span data-stu-id="dda8a-106">Keywords</span></span>|<span data-ttu-id="dda8a-107">문제 해결</span><span class="sxs-lookup"><span data-stu-id="dda8a-107">Troubleshooting</span></span>|  
|<span data-ttu-id="dda8a-108">수준</span><span class="sxs-lookup"><span data-stu-id="dda8a-108">Level</span></span>|<span data-ttu-id="dda8a-109">정보</span><span class="sxs-lookup"><span data-stu-id="dda8a-109">Information</span></span>|  
|<span data-ttu-id="dda8a-110">채널</span><span class="sxs-lookup"><span data-stu-id="dda8a-110">Channel</span></span>|<span data-ttu-id="dda8a-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/분석</span><span class="sxs-lookup"><span data-stu-id="dda8a-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="dda8a-112">설명</span><span class="sxs-lookup"><span data-stu-id="dda8a-112">Description</span></span>  
 <span data-ttu-id="dda8a-113">동작 추적에서 보내거나 받을 메시지가 동작 경계를 넘기 시작했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="dda8a-113">In activity tracing, indicates a message has started crossing an activity boundary in send or receive.</span></span>  
  
## <a name="message"></a><span data-ttu-id="dda8a-114">메시지</span><span class="sxs-lookup"><span data-stu-id="dda8a-114">Message</span></span>  
 <span data-ttu-id="dda8a-115">동작 경계입니다.</span><span class="sxs-lookup"><span data-stu-id="dda8a-115">Activity boundary.</span></span>  
  
## <a name="details"></a><span data-ttu-id="dda8a-116">설명</span><span class="sxs-lookup"><span data-stu-id="dda8a-116">Details</span></span>  
  
|<span data-ttu-id="dda8a-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="dda8a-117">Data Item Name</span></span>|<span data-ttu-id="dda8a-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="dda8a-118">Data Item Type</span></span>|<span data-ttu-id="dda8a-119">설명</span><span class="sxs-lookup"><span data-stu-id="dda8a-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="dda8a-120">ExtendedData</span><span class="sxs-lookup"><span data-stu-id="dda8a-120">ExtendedData</span></span>|`xs:string`|<span data-ttu-id="dda8a-121">작업의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="dda8a-121">The name of the activity.</span></span>|  
|<span data-ttu-id="dda8a-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="dda8a-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="dda8a-123">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="dda8a-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
