---
title: "외부 활동 유효성 검사"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 49619f59-9819-484a-bcd8-5596308e8551
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e3fdc37e22bf06cdfdad3141af5657a1b20911a2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="external-activity-validation"></a><span data-ttu-id="44c73-102">외부 활동 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="44c73-102">External Activity Validation</span></span>
<span data-ttu-id="44c73-103">이 샘플에서는 직접 작성하지 않은 기본 제공 활동에 유효성 검사 논리를 추가하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="44c73-103">This sample shows how to add validation logic to a built-in activity that you are not the author of.</span></span> <span data-ttu-id="44c73-104">유효성 검사 논리는 워크플로에 있는 모든 <xref:System.Activities.Statements.If> 활동의 <xref:System.Activities.Statements.If.Then%2A> 속성이 설정되거나 <xref:System.Activities.Statements.If.Else%2A> 속성이 설정되도록 적용하는 것으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="44c73-104">The validation logic consists of enforcing that all <xref:System.Activities.Statements.If> activities present in the workflow either have their <xref:System.Activities.Statements.If.Then%2A> property set or their <xref:System.Activities.Statements.If.Else%2A> property set.</span></span> <span data-ttu-id="44c73-105">또한 유효성 검사 논리에는 워크플로에 있는 모든 <xref:System.Activities.Statements.Pick> 활동에 둘 이상의 분기가 있는지 확인하고, 그렇지 않은 경우 경고를 생성하는 것도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="44c73-105">Also, the validation logic includes checking that all <xref:System.Activities.Statements.Pick> activities present in the workflow have more than one branch, and if that is not the case, a warning is generated.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="44c73-106">샘플 세부 정보</span><span class="sxs-lookup"><span data-stu-id="44c73-106">Sample details</span></span>  
 <span data-ttu-id="44c73-107">이 샘플에서는 유효성을 검사할 각 활동, 즉 <xref:System.Activities.Statements.If> 활동과 <xref:System.Activities.Statements.Pick> 활동의 인스턴스를 사용하여 워크플로를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="44c73-107">This sample creates a workflow with an instance of each activity to validate: the <xref:System.Activities.Statements.If> activity and the <xref:System.Activities.Statements.Pick> activity.</span></span> <span data-ttu-id="44c73-108">각 유효성 검사 동작마다 <xref:System.Activities.Validation.Constraint>가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="44c73-108">A <xref:System.Activities.Validation.Constraint> is created for each validation behavior.</span></span> <span data-ttu-id="44c73-109">이 샘플에서 만들어지는 제약 조건은 `ConstraintError_IfShouldHaveThenOrElse`와 `ConstraintWarning_PickHasOneBranch`입니다.</span><span class="sxs-lookup"><span data-stu-id="44c73-109">The constraints created in this sample are `ConstraintError_IfShouldHaveThenOrElse` and `ConstraintWarning_PickHasOneBranch`.</span></span> <span data-ttu-id="44c73-110">그런 다음 이러한 제약 조건이 `AdditionalConstraints` 인스턴스의 <xref:System.Activities.Validation.ValidationSettings> 컬렉션에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="44c73-110">Next, these constraints are added to the `AdditionalConstraints` collection of a <xref:System.Activities.Validation.ValidationSettings> instance.</span></span> <span data-ttu-id="44c73-111">마지막으로, `static`의 <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A><xref:System.Activities.Validation.ActivityValidationServices> 메서드를 호출하여 워크플로의 활동에 대한 유효성을 검사하고 유효성 검사 결과를 콘솔에 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="44c73-111">Finally, the `static`<xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> method of <xref:System.Activities.Validation.ActivityValidationServices> is called to validate the activities in the workflow and the validation results are printed out to the console.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="44c73-112">모든 활동에 정책 제약 조건을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44c73-112">You can add policy constraints to any activity.</span></span> <span data-ttu-id="44c73-113">예를 들어 <xref:System.Activities.Statements.Sequence> 또는 <xref:System.Activities.Statements.Parallel> 활동에 정책 제약 조건을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44c73-113">For example, you can add a policy constraint to a <xref:System.Activities.Statements.Sequence> or <xref:System.Activities.Statements.Parallel> activity.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="44c73-114">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="44c73-114">To use this sample</span></span>  
  
1.  <span data-ttu-id="44c73-115">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]을 사용하여 ExternalActivityValidation.sln 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="44c73-115">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the ExternalActivityValidation.sln file.</span></span>  
  
2.  <span data-ttu-id="44c73-116">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="44c73-116">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="44c73-117">Ctrl+F5를 눌러 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="44c73-117">To run the solution, press Ctrl+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="44c73-118">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44c73-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="44c73-119">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="44c73-119">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="44c73-120">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="44c73-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="44c73-121">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44c73-121">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Validation\ExternalActivityValidation`  
  
## <a name="see-also"></a><span data-ttu-id="44c73-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="44c73-122">See Also</span></span>
