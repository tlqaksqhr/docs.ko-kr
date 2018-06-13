---
title: 3502 - InferredOperationDescription
ms.date: 03/30/2017
ms.assetid: 6aebb614-3c72-4537-ba11-3cc7200ef1f1
ms.openlocfilehash: 752cd73066c3c15ecbb36c40c417ee84b3fcf184
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33512007"
---
# <a name="3502---inferredoperationdescription"></a><span data-ttu-id="fd7fe-102">3502 - InferredOperationDescription</span><span class="sxs-lookup"><span data-stu-id="fd7fe-102">3502 - InferredOperationDescription</span></span>
## <a name="properties"></a><span data-ttu-id="fd7fe-103">속성</span><span class="sxs-lookup"><span data-stu-id="fd7fe-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fd7fe-104">ID</span><span class="sxs-lookup"><span data-stu-id="fd7fe-104">ID</span></span>|<span data-ttu-id="fd7fe-105">3502</span><span class="sxs-lookup"><span data-stu-id="fd7fe-105">3502</span></span>|  
|<span data-ttu-id="fd7fe-106">키워드</span><span class="sxs-lookup"><span data-stu-id="fd7fe-106">Keywords</span></span>|<span data-ttu-id="fd7fe-107">WFServices</span><span class="sxs-lookup"><span data-stu-id="fd7fe-107">WFServices</span></span>|  
|<span data-ttu-id="fd7fe-108">수준</span><span class="sxs-lookup"><span data-stu-id="fd7fe-108">Level</span></span>|<span data-ttu-id="fd7fe-109">정보</span><span class="sxs-lookup"><span data-stu-id="fd7fe-109">Information</span></span>|  
|<span data-ttu-id="fd7fe-110">채널</span><span class="sxs-lookup"><span data-stu-id="fd7fe-110">Channel</span></span>|<span data-ttu-id="fd7fe-111">Microsoft-Windows-응용 프로그램 서버-응용 프로그램/분석</span><span class="sxs-lookup"><span data-stu-id="fd7fe-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="fd7fe-112">설명</span><span class="sxs-lookup"><span data-stu-id="fd7fe-112">Description</span></span>  
 <span data-ttu-id="fd7fe-113">OperationDescription이 WorkflowService에서 유추되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fd7fe-113">Indicates an OperationDescription has been inferred from WorkflowService.</span></span>  
  
## <a name="message"></a><span data-ttu-id="fd7fe-114">메시지</span><span class="sxs-lookup"><span data-stu-id="fd7fe-114">Message</span></span>  
 <span data-ttu-id="fd7fe-115">계약 '%2'에서 Name='%1'인 OperationDescription이 WorkflowService에서 유추되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fd7fe-115">OperationDescription with Name='%1' in contract '%2' has been inferred from WorkflowService.</span></span> <span data-ttu-id="fd7fe-116">IsOneWay=%3.</span><span class="sxs-lookup"><span data-stu-id="fd7fe-116">IsOneWay=%3.</span></span>  
  
## <a name="details"></a><span data-ttu-id="fd7fe-117">설명</span><span class="sxs-lookup"><span data-stu-id="fd7fe-117">Details</span></span>  
  
|<span data-ttu-id="fd7fe-118">데이터 항목 이름</span><span class="sxs-lookup"><span data-stu-id="fd7fe-118">Data Item Name</span></span>|<span data-ttu-id="fd7fe-119">데이터 항목 형식</span><span class="sxs-lookup"><span data-stu-id="fd7fe-119">Data Item Type</span></span>|<span data-ttu-id="fd7fe-120">설명</span><span class="sxs-lookup"><span data-stu-id="fd7fe-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="fd7fe-121">OperationName</span><span class="sxs-lookup"><span data-stu-id="fd7fe-121">OperationName</span></span>|<span data-ttu-id="fd7fe-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="fd7fe-122">xs:string</span></span>|<span data-ttu-id="fd7fe-123">작업의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="fd7fe-123">The name of the operation.</span></span>|  
|<span data-ttu-id="fd7fe-124">ContractName</span><span class="sxs-lookup"><span data-stu-id="fd7fe-124">ContractName</span></span>|<span data-ttu-id="fd7fe-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="fd7fe-125">xs:string</span></span>|<span data-ttu-id="fd7fe-126">계약 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="fd7fe-126">The name of the contract.</span></span>|  
|<span data-ttu-id="fd7fe-127">IsOneWay</span><span class="sxs-lookup"><span data-stu-id="fd7fe-127">IsOneWay</span></span>|<span data-ttu-id="fd7fe-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="fd7fe-128">xs:string</span></span>|<span data-ttu-id="fd7fe-129">계약이 단방향인지 여부를 나타내는 True 또는 False입니다.</span><span class="sxs-lookup"><span data-stu-id="fd7fe-129">True or False indicating if the contract is one-way.</span></span>|  
|<span data-ttu-id="fd7fe-130">AppDomain</span><span class="sxs-lookup"><span data-stu-id="fd7fe-130">AppDomain</span></span>|<span data-ttu-id="fd7fe-131">xs:string</span><span class="sxs-lookup"><span data-stu-id="fd7fe-131">xs:string</span></span>|<span data-ttu-id="fd7fe-132">AppDomain.CurrentDomain.FriendlyName에서 반환되는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="fd7fe-132">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
