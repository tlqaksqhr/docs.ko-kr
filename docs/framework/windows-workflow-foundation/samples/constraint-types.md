---
title: "제약 조건 형식"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b6b246e6-1130-4698-9625-c5c42abcbfed
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d42be018b6a92237b5914c180d329138fb95e7dc
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2017
---
# <a name="constraint-types"></a><span data-ttu-id="d763a-102">제약 조건 형식</span><span class="sxs-lookup"><span data-stu-id="d763a-102">Constraint Types</span></span>
<span data-ttu-id="d763a-103">이 샘플에서는 워크플로에 제약 조건을 적용하는 서로 다른 두 가지 방법을 보여 줍니다. 그 중 하나는 활동 내부에서(빌드) 적용하는 방법이고, 다른 하나는 활동 외부에서(정책) 적용하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="d763a-103">This sample shows two different ways to apply constraints to a workflow, one is from inside the activity (build) and one is from outside of it (policy).</span></span> <span data-ttu-id="d763a-104">이 시나리오에서는 타사 소프트웨어 회사의 활동 작성자가 두 인수 사이의 관계에 대한 유효성을 검사하려는 경우를 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="d763a-104">In this scenario, an activity author (from a 3rth-party software company) wants to validate the relationship between two arguments.</span></span> <span data-ttu-id="d763a-105">이 경우 비용이 금액을 초과하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d763a-105">In this case, the cost should be smaller than or equal to the price.</span></span> <span data-ttu-id="d763a-106">이는 일반적인 유효성 검사 빌드 제약 조건입니다.</span><span class="sxs-lookup"><span data-stu-id="d763a-106">This is a general validation build constraint.</span></span>  
  
 <span data-ttu-id="d763a-107">그런 다음 가게 주인이 이 일반적인 활동에 다른 유효성 검사를 더 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d763a-107">Then a shop owner wants to add some validation to this generic activity.</span></span> <span data-ttu-id="d763a-108">이 사람은 자신의 가게에서 취급하는 상품 대부분의 가격이 9.99달러를 넘지 않기를 원합니다.</span><span class="sxs-lookup"><span data-stu-id="d763a-108">In his case, he wants the majority of its products to be $9.99 or less.</span></span> <span data-ttu-id="d763a-109">따라서 이 가게 주인은 `CreateProduct` 활동을 기반으로 정책 제약 조건을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d763a-109">So, he uses a policy constraint that is on top of the `CreateProduct` activity.</span></span>  
  
 <span data-ttu-id="d763a-110">이 샘플의 내용은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d763a-110">In the sample:</span></span>  
  
 <span data-ttu-id="d763a-111">활동 작성자(빌드)가 다음을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d763a-111">The activity author (build) must:</span></span>  
  
-   <span data-ttu-id="d763a-112">제약 조건(`PriceGreaterThanCost`)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d763a-112">Create a constraint (`PriceGreaterThanCost`).</span></span> <span data-ttu-id="d763a-113">모든 유효성 검사 논리가 이 제약 조건에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d763a-113">This is where all the validation logic resides.</span></span>  
  
-   <span data-ttu-id="d763a-114">`System.Activities.CodeActivity.OnGetConstraints()`를 재정의하고 `PriceGreaterThanCost` 컬렉션에 제약 조건(<xref:System.Collections.IList>)을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d763a-114">Override `System.Activities.CodeActivity.OnGetConstraints()` and add the constraint (`PriceGreaterThanCost`) to the constraints <xref:System.Collections.IList>.</span></span>  
  
 <span data-ttu-id="d763a-115">워크플로 작성자(정책)가 다음을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d763a-115">The workflow author (policy) must:</span></span>  
  
-   <span data-ttu-id="d763a-116">유효성을 검사할 활동의 인스턴스(`CreateProduct`)를 사용하여 워크플로를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d763a-116">Create a workflow with an instance of the activity to validate (`CreateProduct`).</span></span>  
  
-   <span data-ttu-id="d763a-117">제약 조건(`MaxPrice`)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d763a-117">Create a constraint (`MaxPrice`).</span></span>  
  
-   <span data-ttu-id="d763a-118"><xref:System.Activities.Validation.ValidationSettings> 인스턴스(`validationSettings`)를 만들고 `MaxPrice` 컬렉션에 제약 조건(`AdditionalConstraints`)을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="d763a-118">Create a <xref:System.Activities.Validation.ValidationSettings> instance (`validationSettings`) and add the constraint (`MaxPrice`) to the collection `AdditionalConstraints`.</span></span> <span data-ttu-id="d763a-119">이때 워크플로 작성자는 순차 또는 병렬 등 임의의 활동에 정책 제약 조건을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d763a-119">Here the workflow author can add policy constraints to any activity, such as a sequence or parallel.</span></span>  
  
-   <span data-ttu-id="d763a-120"><xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> 개체의 <xref:System.Activities.Validation.ValidationResults> 컬렉션을 반환하는 <xref:System.Activities.Validation.ValidationError>를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="d763a-120">Call <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>, which returns a <xref:System.Activities.Validation.ValidationResults> collection of <xref:System.Activities.Validation.ValidationError> objects.</span></span>  
  
-   <span data-ttu-id="d763a-121">(선택 사항) <xref:System.Activities.Validation.ValidationError> 개체를 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="d763a-121">(Optional) Print the <xref:System.Activities.Validation.ValidationError> objects.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="d763a-122">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="d763a-122">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="d763a-123">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 ConstraintTypes.sln 샘플 솔루션을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d763a-123">Open the ConstraintTypes.sln sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="d763a-124">솔루션을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d763a-124">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d763a-125">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d763a-125">The samples may already be installed on your machine.</span></span> <span data-ttu-id="d763a-126">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="d763a-126">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="d763a-127">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="d763a-127">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="d763a-128">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d763a-128">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Validation\ConstraintLibrary`