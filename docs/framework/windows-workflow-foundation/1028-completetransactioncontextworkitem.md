---
title: 1028 - CompleteTransactionContextWorkItem
ms.date: 03/30/2017
ms.assetid: 95423f9d-d29a-460e-bcd8-096e80af5bd0
ms.openlocfilehash: 806a437822cef8802a2bef6a54f924f84c88ef60
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33511389"
---
# <a name="1028---completetransactioncontextworkitem"></a><span data-ttu-id="2582a-102">1028 - CompleteTransactionContextWorkItem</span><span class="sxs-lookup"><span data-stu-id="2582a-102">1028 - CompleteTransactionContextWorkItem</span></span>
## <a name="properties"></a><span data-ttu-id="2582a-103">속성</span><span class="sxs-lookup"><span data-stu-id="2582a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2582a-104">ID</span><span class="sxs-lookup"><span data-stu-id="2582a-104">ID</span></span>|<span data-ttu-id="2582a-105">1028</span><span class="sxs-lookup"><span data-stu-id="2582a-105">1028</span></span>|  
|<span data-ttu-id="2582a-106">키워드</span><span class="sxs-lookup"><span data-stu-id="2582a-106">Keywords</span></span>|<span data-ttu-id="2582a-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="2582a-107">WFRuntime</span></span>|  
|<span data-ttu-id="2582a-108">수준</span><span class="sxs-lookup"><span data-stu-id="2582a-108">Level</span></span>|<span data-ttu-id="2582a-109">Verbose</span><span class="sxs-lookup"><span data-stu-id="2582a-109">Verbose</span></span>|  
|<span data-ttu-id="2582a-110">채널</span><span class="sxs-lookup"><span data-stu-id="2582a-110">Channel</span></span>|<span data-ttu-id="2582a-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/디버그</span><span class="sxs-lookup"><span data-stu-id="2582a-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="2582a-112">설명</span><span class="sxs-lookup"><span data-stu-id="2582a-112">Description</span></span>  
 <span data-ttu-id="2582a-113">TransactionContextWorkItem이 완료되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2582a-113">Indicates a TransactionContextWorkItem has completed.</span></span>  
  
## <a name="message"></a><span data-ttu-id="2582a-114">메시지</span><span class="sxs-lookup"><span data-stu-id="2582a-114">Message</span></span>  
 <span data-ttu-id="2582a-115">작업 '%1', DisplayName: '%2', InstanceId: '%3'에 대해 TransactionContextWorkItem이 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2582a-115">A TransactionContextWorkItem has completed for Activity '%1', DisplayName: '%2', InstanceId: '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="2582a-116">설명</span><span class="sxs-lookup"><span data-stu-id="2582a-116">Details</span></span>  
  
|<span data-ttu-id="2582a-117">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="2582a-117">Data Item Name</span></span>|<span data-ttu-id="2582a-118">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="2582a-118">Data Item Type</span></span>|<span data-ttu-id="2582a-119">설명</span><span class="sxs-lookup"><span data-stu-id="2582a-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="2582a-120">동작</span><span class="sxs-lookup"><span data-stu-id="2582a-120">Activity</span></span>|<span data-ttu-id="2582a-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="2582a-121">xs:string</span></span>|<span data-ttu-id="2582a-122">작업의 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2582a-122">The type name of the activity.</span></span>|  
|<span data-ttu-id="2582a-123">DisplayName</span><span class="sxs-lookup"><span data-stu-id="2582a-123">DisplayName</span></span>|<span data-ttu-id="2582a-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="2582a-124">xs:string</span></span>|<span data-ttu-id="2582a-125">작업의 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2582a-125">The display name of the activity.</span></span>|  
|<span data-ttu-id="2582a-126">InstanceId</span><span class="sxs-lookup"><span data-stu-id="2582a-126">InstanceId</span></span>|<span data-ttu-id="2582a-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="2582a-127">xs:string</span></span>|<span data-ttu-id="2582a-128">작업의 인스턴스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="2582a-128">The instance id of the activity.</span></span>|  
|<span data-ttu-id="2582a-129">AppDomain</span><span class="sxs-lookup"><span data-stu-id="2582a-129">AppDomain</span></span>|<span data-ttu-id="2582a-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="2582a-130">xs:string</span></span>|<span data-ttu-id="2582a-131">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="2582a-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
