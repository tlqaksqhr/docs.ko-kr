---
title: 활동 관계 유효성 검사
ms.date: 03/30/2017
ms.assetid: 6f11a34e-ed67-4bce-88ce-7e96bbb4d052
ms.openlocfilehash: e6dd0e6a7b48444073ebae378e21c1b45977a1f0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33515110"
---
# <a name="activity-relationships-validation"></a><span data-ttu-id="ad525-102">활동 관계 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="ad525-102">Activity Relationships Validation</span></span>
<span data-ttu-id="ad525-103">이 샘플은 `CreateCity`, `CreateState` 및 `CreateCountry`의 세 가지 활동으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad525-103">This sample consists of three activities, `CreateCity`, `CreateState`, and `CreateCountry`.</span></span> <span data-ttu-id="ad525-104">`CreateCity`는 `CreateState` 활동 안에 있어야 하고, `CreateState`는 `CreateCountry` 활동 안에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad525-104">`CreateCity` must be inside a `CreateState` activity, and `CreateState` must be inside a `CreateCountry` activity.</span></span> <span data-ttu-id="ad525-105">이 샘플에서 사용할 유효성 검사 논리는 `CreateState` 활동의 경우 코드로 되어 있고 `CreateCity` 활동의 경우 XAML로 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad525-105">For the purpose of this sample, the validation logic is in code for the `CreateState` activity, and in XAML for the `CreateCity` activity.</span></span> <span data-ttu-id="ad525-106">두 제약 조건의 동작은 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="ad525-106">Both constraints have the same behavior.</span></span>  
  
 <span data-ttu-id="ad525-107">[!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]에서는 개발자가 활동 간 관계의 유효성을 검사할 수 있도록 다음과 같은 세 가지 도우미 활동을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ad525-107">The [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] provides the following three helper activities that allow the developer to validate relationships between activities:</span></span>  
  
 <xref:System.Activities.Validation.GetParentChain>  
 <span data-ttu-id="ad525-108">현재 노드의 부모에 속하는 모든 활동의 컬렉션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ad525-108">Provides the collection of all activities that belong to the parent of the current node</span></span>  
  
 <xref:System.Activities.Validation.GetChildSubtree>  
 <span data-ttu-id="ad525-109">현재 노드를 제외하고 현재 노드의 하위 트리에 속하는 모든 활동의 컬렉션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ad525-109">Provides the collection of all activities that belong to the sub-tree of the current node, excluding the current node</span></span>  
  
 <xref:System.Activities.Validation.GetWorkflowTree>  
 <span data-ttu-id="ad525-110">현재 노드와 동일한 트리에 있는 모든 활동의 컬렉션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ad525-110">Provides the collection of all activities in the same tree as the current node</span></span>  
  
 <span data-ttu-id="ad525-111">이 샘플에서 <xref:System.Activities.Statements.ForEach%601> 활동은 <xref:System.Activities.Validation.GetParentChain>에서 반환하는 컬렉션의 단계를 수행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad525-111">In the sample, a <xref:System.Activities.Statements.ForEach%601> activity is used to walk through the collection returned by <xref:System.Activities.Validation.GetParentChain>.</span></span> <span data-ttu-id="ad525-112">컬렉션에 있는 모든 요소의 형식은 `CreateCountry`(`CreateState`의 유효성을 검사하는 경우에는 `CreateCity`)와 비교되며, 일치하는 항목이 있으면 결과 플래그가 `true`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad525-112">For every element in the collection, its type is compared to `CreateCountry` (or `CreateState` if `CreateCity` is being validated), and when a match is found the result flag is set to `true`.</span></span> <span data-ttu-id="ad525-113">마지막으로, 결과 플래그가 <xref:System.Activities.Validation.AssertValidation>로 설정되어 있는 경우 `false`은 유효성 검사 오류를 생성하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ad525-113">Finally, an <xref:System.Activities.Validation.AssertValidation> is used to generate a validation error if the result flag is set to `false`.</span></span>  
  
### <a name="to-use-this-sample"></a><span data-ttu-id="ad525-114">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="ad525-114">To use this sample</span></span>  
  
1.  <span data-ttu-id="ad525-115">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 ContainmentValidation.sln 샘플 솔루션을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ad525-115">Open the ContainmentValidation.sln sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="ad525-116">솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="ad525-116">Build the solution.</span></span>  
  
3.  <span data-ttu-id="ad525-117">Ctrl+F5를 눌러 프로그램을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="ad525-117">Press CTRL + F5 to launch the program.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ad525-118">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad525-118">The samples may already be installed on your computer.</span></span> <span data-ttu-id="ad525-119">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="ad525-119">Check for the following (default) directory before continuing:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="ad525-120">이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="ad525-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ad525-121">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad525-121">This sample is located in the following directory:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Validation\ActivityRelationships`
