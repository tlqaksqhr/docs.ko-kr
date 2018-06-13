---
title: 조건화된 활동 그룹
ms.date: 03/30/2017
ms.assetid: f76ef924-34ce-48ae-8c8d-48faf9697754
ms.openlocfilehash: 3560542b912f9697ec2e77c8d5c82e148a41d485
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33514067"
---
# <a name="conditioned-activity-group"></a><span data-ttu-id="bd3a2-102">조건화된 활동 그룹</span><span class="sxs-lookup"><span data-stu-id="bd3a2-102">Conditioned Activity Group</span></span>
<span data-ttu-id="bd3a2-103">이 샘플에서는 여행 예약 응용 프로그램을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bd3a2-103">The sample demonstrates a travel booking application.</span></span> <span data-ttu-id="bd3a2-104"><xref:System.Workflow.Activities.ConditionedActivityGroup>(CAG)에는 Car 동작과 Airline 동작이라는 두 개의 코드 동작이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd3a2-104">The <xref:System.Workflow.Activities.ConditionedActivityGroup> (CAG) has two code activities: a Car activity and an Airline activity.</span></span> <span data-ttu-id="bd3a2-105">`SimpleCAGWorkflow` 생성자에서 "travelNeedType" ArrayList 개체는 필요한 여행 예약 유형으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="bd3a2-105">In the `SimpleCAGWorkflow` constructor, a "travelNeedType" ArrayList object is populated with the types of travel bookings that are required.</span></span> <span data-ttu-id="bd3a2-106">`travelNeeds.Add` 문 중 하나 또는 두 개 모두를 주석으로 처리하여 이에 맞게 CAG 동작을 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="bd3a2-106">By commenting out one or both of the `travelNeeds.Add` statements, you modify the CAG behavior accordingly.</span></span> <span data-ttu-id="bd3a2-107">Car 동작과 Airline 동작 모두 <xref:System.Workflow.Activities.ConditionedActivityGroup.WhenConditionProperty> 조건이 <xref:System.Workflow.Activities.CodeCondition>으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="bd3a2-107">Both the Car and Airline activities have their <xref:System.Workflow.Activities.ConditionedActivityGroup.WhenConditionProperty> condition populated with a <xref:System.Workflow.Activities.CodeCondition>.</span></span> <span data-ttu-id="bd3a2-108">Car 동작은 `travelNeeds` 컬렉션에 `TravelNeeds.Car` 항목이 있을 때만 실행되고, Airline 동작은 `travelNeeds` 컬렉션에 `TravelNeeds.Airline` 항목이 있을 때만 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd3a2-108">The Car activity executes only if the `travelNeeds` collection has a `TravelNeeds.Car` entry, and the Airline activity executes only if the `travelNeeds` collection has a `TravelNeeds.Airline` entry.</span></span>  
  
 <span data-ttu-id="bd3a2-109">각 동작이 실행되면 해당 항목이 컬렉션에서 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd3a2-109">The execution of each activity removes the corresponding entry from the collection.</span></span> <span data-ttu-id="bd3a2-110">기본 <xref:System.Workflow.Activities.ConditionedActivityGroup.UntilCondition%2A> 조건은 <xref:System.Workflow.Activities.ConditionedActivityGroup.WhenConditionProperty> 조건에 따라 실행 중이거나 실행 준비된 자식 항목이 없을 경우 CAG가 종료되도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bd3a2-110">The default <xref:System.Workflow.Activities.ConditionedActivityGroup.UntilCondition%2A> condition specifies that the CAG should exit when no children are executing or are ready for execution (based on their <xref:System.Workflow.Activities.ConditionedActivityGroup.WhenConditionProperty> conditions).</span></span> <span data-ttu-id="bd3a2-111">이 샘플에서는 `travelNeeds` 컬렉션이 비어 있을 때 CAG가 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd3a2-111">In this sample, this means that the CAG exits when the `travelNeeds` collection is empty.</span></span>  
  
### <a name="to-build-the-sample"></a><span data-ttu-id="bd3a2-112">이 샘플을 빌드하려면</span><span class="sxs-lookup"><span data-stu-id="bd3a2-112">To build the sample</span></span>  
  
1.  <span data-ttu-id="bd3a2-113">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 솔루션을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="bd3a2-113">Open the solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="bd3a2-114">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="bd3a2-114">Build the solution by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="bd3a2-115">Ctrl+F5를 눌러 디버깅 없이 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="bd3a2-115">Run the solution without debugging by pressing CTRL+F5.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="bd3a2-116">이 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="bd3a2-116">To run the sample</span></span>  
  
-   <span data-ttu-id="bd3a2-117">SDK 명령 프롬프트 창에서 샘플의 주 폴더 아래에 있는 SimpleCAG\bin\debug 폴더 또는 SimpleCAG\bin 폴더(Visual Basic 버전 샘플의 경우)의 .exe 파일을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="bd3a2-117">In the SDK Command Prompt window, run the .exe file in the SimpleCAG\bin\debug folder (or the SimpleCAG\bin folder for the Visual Basic version of the sample), which is located below the main folder for the sample.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="bd3a2-118">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd3a2-118">The samples may already be installed on your computer.</span></span> <span data-ttu-id="bd3a2-119">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="bd3a2-119">Check for the following (default) directory before continuing:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="bd3a2-120">이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="bd3a2-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="bd3a2-121">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd3a2-121">This sample is located in the following directory:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\SimpleCAG`  
  
## <a name="see-also"></a><span data-ttu-id="bd3a2-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bd3a2-122">See Also</span></span>  
 <xref:System.Workflow.Activities.ConditionedActivityGroup>  
 <xref:System.Workflow.Activities.ConditionedActivityGroup.WhenConditionProperty>  
 <xref:System.Workflow.Activities.CodeCondition>  
 <xref:System.Workflow.Activities.ConditionedActivityGroup.UntilCondition%2A>
