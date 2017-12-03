---
title: 3557 - TransactedReceiveScopeEndCommitFailed
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 079f0188-8146-49ee-b6ae-a08f4e4d2b9b
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8ea57cc60f9626763308267a98624c825f8312b0
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="3557---transactedreceivescopeendcommitfailed"></a><span data-ttu-id="d8c37-102">3557 - TransactedReceiveScopeEndCommitFailed</span><span class="sxs-lookup"><span data-stu-id="d8c37-102">3557 - TransactedReceiveScopeEndCommitFailed</span></span>
## <a name="properties"></a><span data-ttu-id="d8c37-103">속성</span><span class="sxs-lookup"><span data-stu-id="d8c37-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d8c37-104">ID</span><span class="sxs-lookup"><span data-stu-id="d8c37-104">ID</span></span>|<span data-ttu-id="d8c37-105">3557</span><span class="sxs-lookup"><span data-stu-id="d8c37-105">3557</span></span>|  
|<span data-ttu-id="d8c37-106">키워드</span><span class="sxs-lookup"><span data-stu-id="d8c37-106">Keywords</span></span>|<span data-ttu-id="d8c37-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="d8c37-107">WFServices</span></span>|  
|<span data-ttu-id="d8c37-108">수준</span><span class="sxs-lookup"><span data-stu-id="d8c37-108">Level</span></span>|<span data-ttu-id="d8c37-109">정보</span><span class="sxs-lookup"><span data-stu-id="d8c37-109">Information</span></span>|  
|<span data-ttu-id="d8c37-110">채널</span><span class="sxs-lookup"><span data-stu-id="d8c37-110">Channel</span></span>|<span data-ttu-id="d8c37-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/분석</span><span class="sxs-lookup"><span data-stu-id="d8c37-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d8c37-112">설명</span><span class="sxs-lookup"><span data-stu-id="d8c37-112">Description</span></span>  
 <span data-ttu-id="d8c37-113">CommittableTransaction에 대한 EndCommit 호출에서 TransactionException이 발생했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d8c37-113">Indicates the call to EndCommit on a CommittableTransaction threw a TransactionException.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d8c37-114">메시지</span><span class="sxs-lookup"><span data-stu-id="d8c37-114">Message</span></span>  
 <span data-ttu-id="d8c37-115">ID = '%1'인 CommittableTransaction에 대한 EndCommit 호출에서 다음 메시지와 함께 TransactionException이 발생했습니다. '%2'.</span><span class="sxs-lookup"><span data-stu-id="d8c37-115">The call to EndCommit on the CommittableTransaction with id = '%1' threw a TransactionException with the following message: '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d8c37-116">설명</span><span class="sxs-lookup"><span data-stu-id="d8c37-116">Details</span></span>  
  
|<span data-ttu-id="d8c37-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="d8c37-117">Data Item Name</span></span>|<span data-ttu-id="d8c37-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="d8c37-118">Data Item Type</span></span>|<span data-ttu-id="d8c37-119">설명</span><span class="sxs-lookup"><span data-stu-id="d8c37-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d8c37-120">TransactionId</span><span class="sxs-lookup"><span data-stu-id="d8c37-120">TransactionId</span></span>|<span data-ttu-id="d8c37-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="d8c37-121">xs:string</span></span>|<span data-ttu-id="d8c37-122">CommittableTransaction의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d8c37-122">The id of the CommittableTransaction.</span></span>|  
|<span data-ttu-id="d8c37-123">예외</span><span class="sxs-lookup"><span data-stu-id="d8c37-123">Exception</span></span>|<span data-ttu-id="d8c37-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="d8c37-124">xs:string</span></span>|<span data-ttu-id="d8c37-125">예외에 대한 예외 정보</span><span class="sxs-lookup"><span data-stu-id="d8c37-125">The exception details for the exception</span></span>|  
|<span data-ttu-id="d8c37-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d8c37-126">AppDomain</span></span>|<span data-ttu-id="d8c37-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="d8c37-127">xs:string</span></span>|<span data-ttu-id="d8c37-128">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="d8c37-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
