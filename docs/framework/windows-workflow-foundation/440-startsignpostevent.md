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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5e1674dc7d242a89498360c3e285fa77a08a9004
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="440---startsignpostevent1"></a><span data-ttu-id="25568-102">440 - StartSignpostEvent</span><span class="sxs-lookup"><span data-stu-id="25568-102">440 - StartSignpostEvent1</span></span>
## <a name="properties"></a><span data-ttu-id="25568-103">속성</span><span class="sxs-lookup"><span data-stu-id="25568-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="25568-104">ID</span><span class="sxs-lookup"><span data-stu-id="25568-104">ID</span></span>|<span data-ttu-id="25568-105">440</span><span class="sxs-lookup"><span data-stu-id="25568-105">440</span></span>|  
|<span data-ttu-id="25568-106">키워드</span><span class="sxs-lookup"><span data-stu-id="25568-106">Keywords</span></span>|<span data-ttu-id="25568-107">문제 해결</span><span class="sxs-lookup"><span data-stu-id="25568-107">Troubleshooting</span></span>|  
|<span data-ttu-id="25568-108">수준</span><span class="sxs-lookup"><span data-stu-id="25568-108">Level</span></span>|<span data-ttu-id="25568-109">정보</span><span class="sxs-lookup"><span data-stu-id="25568-109">Information</span></span>|  
|<span data-ttu-id="25568-110">채널</span><span class="sxs-lookup"><span data-stu-id="25568-110">Channel</span></span>|<span data-ttu-id="25568-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/분석</span><span class="sxs-lookup"><span data-stu-id="25568-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="25568-112">설명</span><span class="sxs-lookup"><span data-stu-id="25568-112">Description</span></span>  
 <span data-ttu-id="25568-113">동작 추적에서 보내거나 받을 메시지가 동작 경계를 넘기 시작했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="25568-113">In activity tracing, indicates a message has started crossing an activity boundary in send or receive.</span></span>  
  
## <a name="message"></a><span data-ttu-id="25568-114">메시지</span><span class="sxs-lookup"><span data-stu-id="25568-114">Message</span></span>  
 <span data-ttu-id="25568-115">동작 경계입니다.</span><span class="sxs-lookup"><span data-stu-id="25568-115">Activity boundary.</span></span>  
  
## <a name="details"></a><span data-ttu-id="25568-116">설명</span><span class="sxs-lookup"><span data-stu-id="25568-116">Details</span></span>  
  
|<span data-ttu-id="25568-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="25568-117">Data Item Name</span></span>|<span data-ttu-id="25568-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="25568-118">Data Item Type</span></span>|<span data-ttu-id="25568-119">설명</span><span class="sxs-lookup"><span data-stu-id="25568-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="25568-120">ExtendedData</span><span class="sxs-lookup"><span data-stu-id="25568-120">ExtendedData</span></span>|`xs:string`|<span data-ttu-id="25568-121">작업의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="25568-121">The name of the activity.</span></span>|  
|<span data-ttu-id="25568-122">AppDomain</span><span class="sxs-lookup"><span data-stu-id="25568-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="25568-123">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="25568-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
