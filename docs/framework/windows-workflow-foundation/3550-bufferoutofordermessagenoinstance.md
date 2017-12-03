---
title: 3550 - BufferOutOfOrderMessageNoInstance
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1299d294-99b8-430e-98b1-55f5f17002f3
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: eabc6a6915560d8c49e695d5d681f1544689cb07
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="3550---bufferoutofordermessagenoinstance"></a><span data-ttu-id="e83be-102">3550 - BufferOutOfOrderMessageNoInstance</span><span class="sxs-lookup"><span data-stu-id="e83be-102">3550 - BufferOutOfOrderMessageNoInstance</span></span>
## <a name="properties"></a><span data-ttu-id="e83be-103">속성</span><span class="sxs-lookup"><span data-stu-id="e83be-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e83be-104">ID</span><span class="sxs-lookup"><span data-stu-id="e83be-104">ID</span></span>|<span data-ttu-id="e83be-105">3550</span><span class="sxs-lookup"><span data-stu-id="e83be-105">3550</span></span>|  
|<span data-ttu-id="e83be-106">키워드</span><span class="sxs-lookup"><span data-stu-id="e83be-106">Keywords</span></span>|<span data-ttu-id="e83be-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="e83be-107">WFServices</span></span>|  
|<span data-ttu-id="e83be-108">수준</span><span class="sxs-lookup"><span data-stu-id="e83be-108">Level</span></span>|<span data-ttu-id="e83be-109">정보</span><span class="sxs-lookup"><span data-stu-id="e83be-109">Information</span></span>|  
|<span data-ttu-id="e83be-110">채널</span><span class="sxs-lookup"><span data-stu-id="e83be-110">Channel</span></span>|<span data-ttu-id="e83be-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/분석</span><span class="sxs-lookup"><span data-stu-id="e83be-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e83be-112">설명</span><span class="sxs-lookup"><span data-stu-id="e83be-112">Description</span></span>  
 <span data-ttu-id="e83be-113">버퍼링된 수신이 실패했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e83be-113">Indicates a buffered receive has failed.</span></span> <span data-ttu-id="e83be-114">서비스 인스턴스에서 이 특정 작업을 처리할 준비가 되면 다시 작업이 시도됩니다.</span><span class="sxs-lookup"><span data-stu-id="e83be-114">The operation will be attempted again when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e83be-115">메시지</span><span class="sxs-lookup"><span data-stu-id="e83be-115">Message</span></span>  
 <span data-ttu-id="e83be-116">현재는 '%1' 작업을 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e83be-116">Operation '%1' cannot be performed at this time.</span></span> <span data-ttu-id="e83be-117">서비스 인스턴스에서 이 특정 작업을 처리할 준비가 되면 다시 작업이 시도됩니다.</span><span class="sxs-lookup"><span data-stu-id="e83be-117">Another attempt will be made when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e83be-118">설명</span><span class="sxs-lookup"><span data-stu-id="e83be-118">Details</span></span>  
  
|<span data-ttu-id="e83be-119">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="e83be-119">Data Item Name</span></span>|<span data-ttu-id="e83be-120">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="e83be-120">Data Item Type</span></span>|<span data-ttu-id="e83be-121">설명</span><span class="sxs-lookup"><span data-stu-id="e83be-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e83be-122">OperationName</span><span class="sxs-lookup"><span data-stu-id="e83be-122">OperationName</span></span>|<span data-ttu-id="e83be-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="e83be-123">xs:string</span></span>|<span data-ttu-id="e83be-124">작업의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e83be-124">The name of the operation.</span></span>|  
|<span data-ttu-id="e83be-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="e83be-125">AppDomain</span></span>|<span data-ttu-id="e83be-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="e83be-126">xs:string</span></span>|<span data-ttu-id="e83be-127">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="e83be-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
