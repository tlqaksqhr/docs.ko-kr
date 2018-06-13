---
title: 3557 - TransactedReceiveScopeEndCommitFailed
ms.date: 03/30/2017
ms.assetid: 079f0188-8146-49ee-b6ae-a08f4e4d2b9b
ms.openlocfilehash: 444fa2e51322edd793f709fd3f92c5f9fe826522
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33512163"
---
# <a name="3557---transactedreceivescopeendcommitfailed"></a><span data-ttu-id="8ced7-102">3557 - TransactedReceiveScopeEndCommitFailed</span><span class="sxs-lookup"><span data-stu-id="8ced7-102">3557 - TransactedReceiveScopeEndCommitFailed</span></span>
## <a name="properties"></a><span data-ttu-id="8ced7-103">속성</span><span class="sxs-lookup"><span data-stu-id="8ced7-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8ced7-104">ID</span><span class="sxs-lookup"><span data-stu-id="8ced7-104">ID</span></span>|<span data-ttu-id="8ced7-105">3557</span><span class="sxs-lookup"><span data-stu-id="8ced7-105">3557</span></span>|  
|<span data-ttu-id="8ced7-106">키워드</span><span class="sxs-lookup"><span data-stu-id="8ced7-106">Keywords</span></span>|<span data-ttu-id="8ced7-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="8ced7-107">WFServices</span></span>|  
|<span data-ttu-id="8ced7-108">수준</span><span class="sxs-lookup"><span data-stu-id="8ced7-108">Level</span></span>|<span data-ttu-id="8ced7-109">정보</span><span class="sxs-lookup"><span data-stu-id="8ced7-109">Information</span></span>|  
|<span data-ttu-id="8ced7-110">채널</span><span class="sxs-lookup"><span data-stu-id="8ced7-110">Channel</span></span>|<span data-ttu-id="8ced7-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/분석</span><span class="sxs-lookup"><span data-stu-id="8ced7-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="8ced7-112">설명</span><span class="sxs-lookup"><span data-stu-id="8ced7-112">Description</span></span>  
 <span data-ttu-id="8ced7-113">CommittableTransaction에 대한 EndCommit 호출에서 TransactionException이 발생했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8ced7-113">Indicates the call to EndCommit on a CommittableTransaction threw a TransactionException.</span></span>  
  
## <a name="message"></a><span data-ttu-id="8ced7-114">메시지</span><span class="sxs-lookup"><span data-stu-id="8ced7-114">Message</span></span>  
 <span data-ttu-id="8ced7-115">ID = '%1'인 CommittableTransaction에 대한 EndCommit 호출에서 다음 메시지와 함께 TransactionException이 발생했습니다. '%2'.</span><span class="sxs-lookup"><span data-stu-id="8ced7-115">The call to EndCommit on the CommittableTransaction with id = '%1' threw a TransactionException with the following message: '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="8ced7-116">설명</span><span class="sxs-lookup"><span data-stu-id="8ced7-116">Details</span></span>  
  
|<span data-ttu-id="8ced7-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="8ced7-117">Data Item Name</span></span>|<span data-ttu-id="8ced7-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="8ced7-118">Data Item Type</span></span>|<span data-ttu-id="8ced7-119">설명</span><span class="sxs-lookup"><span data-stu-id="8ced7-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="8ced7-120">TransactionId</span><span class="sxs-lookup"><span data-stu-id="8ced7-120">TransactionId</span></span>|<span data-ttu-id="8ced7-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="8ced7-121">xs:string</span></span>|<span data-ttu-id="8ced7-122">CommittableTransaction의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="8ced7-122">The id of the CommittableTransaction.</span></span>|  
|<span data-ttu-id="8ced7-123">예외</span><span class="sxs-lookup"><span data-stu-id="8ced7-123">Exception</span></span>|<span data-ttu-id="8ced7-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="8ced7-124">xs:string</span></span>|<span data-ttu-id="8ced7-125">예외에 대한 예외 정보</span><span class="sxs-lookup"><span data-stu-id="8ced7-125">The exception details for the exception</span></span>|  
|<span data-ttu-id="8ced7-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="8ced7-126">AppDomain</span></span>|<span data-ttu-id="8ced7-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="8ced7-127">xs:string</span></span>|<span data-ttu-id="8ced7-128">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="8ced7-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
