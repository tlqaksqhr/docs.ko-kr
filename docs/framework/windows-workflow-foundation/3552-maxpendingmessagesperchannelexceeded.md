---
title: 3552 - MaxPendingMessagesPerChannelExceeded
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fc8309d9-eb3a-4636-a6f0-dd0018c1361d
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 5ba5e4aa8e1338321838e40db7d976107315ef64
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="3552---maxpendingmessagesperchannelexceeded"></a><span data-ttu-id="d8598-102">3552 - MaxPendingMessagesPerChannelExceeded</span><span class="sxs-lookup"><span data-stu-id="d8598-102">3552 - MaxPendingMessagesPerChannelExceeded</span></span>
## <a name="properties"></a><span data-ttu-id="d8598-103">속성</span><span class="sxs-lookup"><span data-stu-id="d8598-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d8598-104">ID</span><span class="sxs-lookup"><span data-stu-id="d8598-104">ID</span></span>|<span data-ttu-id="d8598-105">3552</span><span class="sxs-lookup"><span data-stu-id="d8598-105">3552</span></span>|  
|<span data-ttu-id="d8598-106">키워드</span><span class="sxs-lookup"><span data-stu-id="d8598-106">Keywords</span></span>|<span data-ttu-id="d8598-107">할당량, WFServices</span><span class="sxs-lookup"><span data-stu-id="d8598-107">Quota, WFServices</span></span>|  
|<span data-ttu-id="d8598-108">수준</span><span class="sxs-lookup"><span data-stu-id="d8598-108">Level</span></span>|<span data-ttu-id="d8598-109">경고</span><span class="sxs-lookup"><span data-stu-id="d8598-109">Warning</span></span>|  
|<span data-ttu-id="d8598-110">채널</span><span class="sxs-lookup"><span data-stu-id="d8598-110">Channel</span></span>|<span data-ttu-id="d8598-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/분석</span><span class="sxs-lookup"><span data-stu-id="d8598-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d8598-112">설명</span><span class="sxs-lookup"><span data-stu-id="d8598-112">Description</span></span>  
 <span data-ttu-id="d8598-113">스로틀 'MaxPendingMessagesPerChannel' 한도에 도달했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d8598-113">Indicates the throttle 'MaxPendingMessagesPerChannel' limit was hit.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d8598-114">메시지</span><span class="sxs-lookup"><span data-stu-id="d8598-114">Message</span></span>  
 <span data-ttu-id="d8598-115">스로틀 ' maxpendingmessagesperchannel ' '%1'에 도달 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d8598-115">The throttle 'MaxPendingMessagesPerChannel' limit of  '%1' was hit.</span></span> <span data-ttu-id="d8598-116">이 한도를 늘리려면 BufferedReceiveServiceBehavior에서 MaxPendingMessagesPerChannel 속성을 조정하세요.</span><span class="sxs-lookup"><span data-stu-id="d8598-116">To increase this limit, adjust the MaxPendingMessagesPerChannel property on BufferedReceiveServiceBehavior.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d8598-117">설명</span><span class="sxs-lookup"><span data-stu-id="d8598-117">Details</span></span>  
  
|<span data-ttu-id="d8598-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="d8598-118">Data Item Name</span></span>|<span data-ttu-id="d8598-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="d8598-119">Data Item Type</span></span>|<span data-ttu-id="d8598-120">설명</span><span class="sxs-lookup"><span data-stu-id="d8598-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d8598-121">Limit</span><span class="sxs-lookup"><span data-stu-id="d8598-121">Limit</span></span>|<span data-ttu-id="d8598-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="d8598-122">xs:string</span></span>|<span data-ttu-id="d8598-123">MaxPendingMessagesPerChannel 스로틀의 한도입니다.</span><span class="sxs-lookup"><span data-stu-id="d8598-123">The limit of the MaxPendingMessagesPerChannel throttle.</span></span>|  
|<span data-ttu-id="d8598-124">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d8598-124">AppDomain</span></span>|<span data-ttu-id="d8598-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="d8598-125">xs:string</span></span>|<span data-ttu-id="d8598-126">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="d8598-126">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
