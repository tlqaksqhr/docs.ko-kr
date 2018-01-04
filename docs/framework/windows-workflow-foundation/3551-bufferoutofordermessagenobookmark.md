---
title: 3551 - BufferOutOfOrderMessageNoBookmark
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7930d6c4-c843-4a83-933a-cecd71b80d1e
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5e785e40afcb91620940f952022eda4c4b799f4a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="3551---bufferoutofordermessagenobookmark"></a><span data-ttu-id="f1569-102">3551 - BufferOutOfOrderMessageNoBookmark</span><span class="sxs-lookup"><span data-stu-id="f1569-102">3551 - BufferOutOfOrderMessageNoBookmark</span></span>
## <a name="properties"></a><span data-ttu-id="f1569-103">속성</span><span class="sxs-lookup"><span data-stu-id="f1569-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f1569-104">ID</span><span class="sxs-lookup"><span data-stu-id="f1569-104">ID</span></span>|<span data-ttu-id="f1569-105">3551</span><span class="sxs-lookup"><span data-stu-id="f1569-105">3551</span></span>|  
|<span data-ttu-id="f1569-106">키워드</span><span class="sxs-lookup"><span data-stu-id="f1569-106">Keywords</span></span>|<span data-ttu-id="f1569-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="f1569-107">WFServices</span></span>|  
|<span data-ttu-id="f1569-108">수준</span><span class="sxs-lookup"><span data-stu-id="f1569-108">Level</span></span>|<span data-ttu-id="f1569-109">정보</span><span class="sxs-lookup"><span data-stu-id="f1569-109">Information</span></span>|  
|<span data-ttu-id="f1569-110">채널</span><span class="sxs-lookup"><span data-stu-id="f1569-110">Channel</span></span>|<span data-ttu-id="f1569-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/분석</span><span class="sxs-lookup"><span data-stu-id="f1569-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f1569-112">설명</span><span class="sxs-lookup"><span data-stu-id="f1569-112">Description</span></span>  
 <span data-ttu-id="f1569-113">책갈피 다시 시작이 실패했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f1569-113">Indicates a bookmark resumption has failed.</span></span> <span data-ttu-id="f1569-114">서비스 인스턴스에서 이 특정 작업을 처리할 준비가 되면 다시 버퍼링된 수신 작업이 시도됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1569-114">The buffered receive operation will be attempted again when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f1569-115">메시지</span><span class="sxs-lookup"><span data-stu-id="f1569-115">Message</span></span>  
 <span data-ttu-id="f1569-116">현재는 서비스 인스턴스 '%1'에서 '%2' 작업을 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f1569-116">Operation '%2' on service instance '%1' cannot be performed at this time.</span></span> <span data-ttu-id="f1569-117">서비스 인스턴스에서 이 특정 작업을 처리할 준비가 되면 다시 작업이 시도됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1569-117">Another attempt will be made when the service instance is ready to process this particular operation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f1569-118">설명</span><span class="sxs-lookup"><span data-stu-id="f1569-118">Details</span></span>  
  
|<span data-ttu-id="f1569-119">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="f1569-119">Data Item Name</span></span>|<span data-ttu-id="f1569-120">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="f1569-120">Data Item Type</span></span>|<span data-ttu-id="f1569-121">설명</span><span class="sxs-lookup"><span data-stu-id="f1569-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f1569-122">OperationName</span><span class="sxs-lookup"><span data-stu-id="f1569-122">OperationName</span></span>|<span data-ttu-id="f1569-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="f1569-123">xs:string</span></span>|<span data-ttu-id="f1569-124">작업의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f1569-124">The name of the operation.</span></span>|  
|<span data-ttu-id="f1569-125">ServiceInstanceId</span><span class="sxs-lookup"><span data-stu-id="f1569-125">ServiceInstanceId</span></span>|<span data-ttu-id="f1569-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="f1569-126">xs:string</span></span>|<span data-ttu-id="f1569-127">서비스 인스턴스의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="f1569-127">The id of the service instance.</span></span>|  
|<span data-ttu-id="f1569-128">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f1569-128">AppDomain</span></span>|<span data-ttu-id="f1569-129">xs:string</span><span class="sxs-lookup"><span data-stu-id="f1569-129">xs:string</span></span>|<span data-ttu-id="f1569-130">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="f1569-130">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
