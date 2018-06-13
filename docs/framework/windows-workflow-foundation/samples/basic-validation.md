---
title: 기본 유효성 검사
ms.date: 03/30/2017
ms.assetid: ba1343cc-aaab-4ade-b0c0-1dd5063bf4ad
ms.openlocfilehash: db7db339d0b7bfd756d8ba22fb8488b8f7ecfa3c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33514088"
---
# <a name="basic-validation"></a><span data-ttu-id="f8976-102">기본 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="f8976-102">Basic Validation</span></span>
<span data-ttu-id="f8976-103">이 샘플은 `CreateProduct` 인수가 `Cost` 인수보다 작거나 같은지 확인하는 `Price` 활동으로 이루어져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8976-103">This sample consists of an activity, `CreateProduct`, which validates that its `Cost` argument is smaller than or equal to its `Price` argument.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="f8976-104">샘플 세부 정보</span><span class="sxs-lookup"><span data-stu-id="f8976-104">Sample Details</span></span>  
 <span data-ttu-id="f8976-105">유효성 검사를 사용하는 작성자는 둘입니다. 그 중 하나는 활동에 대한 유효성 검사 논리를 만드는 활동 작성자이고, 다른 하나는 특정 워크플로에 대해 유효성 검사 서비스를 호출하는 워크플로 작성자입니다.</span><span class="sxs-lookup"><span data-stu-id="f8976-105">There are two authors that use validation, the activity author (creates the validation logic for the activity) and the workflow author that calls validation services on a specific workflow.</span></span> <span data-ttu-id="f8976-106">이 시나리오에서 활동 작성자는 자신의 모든 활동 인스턴스의 비용이 가격을 초과하지 않도록 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8976-106">In this scenario, the activity author wants to enforce that every instance of his activity must have a smaller or equal cost than that of the price.</span></span>  
  
 <span data-ttu-id="f8976-107">활동 작성자는 (활동 내에서) 다음을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8976-107">The activity author (inside the activity) must:</span></span>  
  
-   <span data-ttu-id="f8976-108">제약 조건(`PriceGreaterThanCost`)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f8976-108">Create a constraint (`PriceGreaterThanCost`).</span></span> <span data-ttu-id="f8976-109">모든 유효성 검사 논리가 이 제약 조건에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8976-109">This is where all the validation logic resides.</span></span>  
  
-   <span data-ttu-id="f8976-110">`System.Activities.CodeActivity.OnGetConstraints()`를 재정의하고 `PriceGreaterThanCost` 컬렉션에 제약 조건(<xref:System.Collections.IList>)을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f8976-110">Override `System.Activities.CodeActivity.OnGetConstraints()` and add the constraint (`PriceGreaterThanCost`) to the constraints <xref:System.Collections.IList>.</span></span>  
  
 <span data-ttu-id="f8976-111">워크플로 작성자(주 프로그램)는 다음을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8976-111">The workflow author (main program) must:</span></span>  
  
-   <span data-ttu-id="f8976-112">유효성을 검사할 활동의 인스턴스(`CreateProduct`)를 사용하여 워크플로를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f8976-112">Create a workflow with an instance of the activity to validate (`CreateProduct`).</span></span>  
  
-   <span data-ttu-id="f8976-113"><xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>의 <xref:System.Activities.Validation.ValidationResults> 컬렉션을 반환하는 <xref:System.Activities.Validation.ValidationError>를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="f8976-113">Call <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>, which returns a <xref:System.Activities.Validation.ValidationResults> collection of <xref:System.Activities.Validation.ValidationError>.</span></span>  
  
-   <span data-ttu-id="f8976-114">(선택 사항) <xref:System.Activities.Validation.ValidationError> 개체를 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="f8976-114">(Optional) Print the <xref:System.Activities.Validation.ValidationError> objects.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="f8976-115">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="f8976-115">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="f8976-116">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 BasicValidation.sln 샘플 솔루션을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f8976-116">Open the BasicValidation.sln sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="f8976-117">솔루션을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f8976-117">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f8976-118">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8976-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="f8976-119">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="f8976-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="f8976-120">이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="f8976-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f8976-121">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8976-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Validation\BasicValidation`