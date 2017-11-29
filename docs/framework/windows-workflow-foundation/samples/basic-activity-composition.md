---
title: "기본 활동 구성"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c283a1a7-1245-4ecd-8072-206c1b4ca379
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6f1c94a276cf2e76d595a22c5c930614818bbf2b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="basic-activity-composition"></a><span data-ttu-id="12bce-102">기본 활동 구성</span><span class="sxs-lookup"><span data-stu-id="12bce-102">Basic Activity Composition</span></span>
<span data-ttu-id="12bce-103">이 샘플에서는 사용자 지정 활동을 추가로 빌드하기 위해 사용자 지정 활동과 시스템 제공 활동을 구성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="12bce-103">This sample demonstrates how to compose custom activities and system-provided activities to build more custom activities.</span></span>  
  
 <span data-ttu-id="12bce-104">설문 조사 활동을 사용하는 워크플로에서 질문 목록을 준비하여 설문 조사 일정을 예약한 다음 설문을 통해 수집된 응답을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="12bce-104">The workflow using the Survey activity schedules the Survey with a list of questions, and then outputs the responses received.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="12bce-105">샘플 세부 정보</span><span class="sxs-lookup"><span data-stu-id="12bce-105">Sample Details</span></span>  
 <span data-ttu-id="12bce-106">이 샘플에서는 다음과 같이 세 개의 사용자 지정 활동을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="12bce-106">This sample uses three custom activities.</span></span> <span data-ttu-id="12bce-107">`ReadLine`단순 <xref:System.Activities.NativeActivity> \<문자열 > 만들어지는 <xref:System.Activities.Bookmark> 예약 되 고 다음을 설정 하는 경우는 `Return` <xref:System.Activities.OutArgument%601> 되는 값으로 하는 <xref:System.Activities.Bookmark> 다시 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="12bce-107">`ReadLine` is a simple <xref:System.Activities.NativeActivity>\<string> that creates a <xref:System.Activities.Bookmark> when scheduled, and then sets the `Return`<xref:System.Activities.OutArgument%601> to the value with which the <xref:System.Activities.Bookmark> is resumed.</span></span> <span data-ttu-id="12bce-108">`Prompt`이 <xref:System.Activities.Activity%601> \<문자열 >를 사용 하는 <xref:System.Activities.InArgument%601>< 문자열\> 라는 `Text` 사용자의 응답을 반환 하 고는 `Result` <xref:System.Activities.OutArgument%601> \<문자열 > 합니다.</span><span class="sxs-lookup"><span data-stu-id="12bce-108">`Prompt` is an <xref:System.Activities.Activity%601>\<string> that takes an <xref:System.Activities.InArgument%601><string\> named `Text` and returns the users response in the `Result`<xref:System.Activities.OutArgument%601>\<string>.</span></span> <span data-ttu-id="12bce-109">`Prompt` 활동에는 .NET Framework의 일부로 제공되는 <xref:System.Activities.Statements.Sequence> 및 <xref:System.Activities.Statements.WriteLine> 활동이 사용되며, 사용자로부터 입력을 받기 위한 사용자 지정 `ReadLine` 활동도 여기에 통합됩니다.</span><span class="sxs-lookup"><span data-stu-id="12bce-109">The `Prompt` activity uses the <xref:System.Activities.Statements.Sequence> and <xref:System.Activities.Statements.WriteLine> activities that ship as part of the .NET Framework, and also incorporates the custom `ReadLine` activity for getting user input.</span></span> <span data-ttu-id="12bce-110">마지막 사용자 지정 활동은 `Survey` 활동입니다.</span><span class="sxs-lookup"><span data-stu-id="12bce-110">The last custom activity is the `Survey` activity.</span></span> <span data-ttu-id="12bce-111">한 <xref:System.Activities.Activity>< c t i o\<문자열 >> 합니다.</span><span class="sxs-lookup"><span data-stu-id="12bce-111">It is an <xref:System.Activities.Activity><ICollection\<string>>.</span></span>  <span data-ttu-id="12bce-112">이 활동에서는 <xref:System.Activities.InArgument%601>< a b l e < 문자열\>> 라는 `Questions` 채웁니다는 `Result` out 인수에 응답 합니다.</span><span class="sxs-lookup"><span data-stu-id="12bce-112">This activity takes an <xref:System.Activities.InArgument%601><IEnumerable<string\>> named `Questions` and populates the `Result` out argument with the responses.</span></span> <span data-ttu-id="12bce-113">`Survey` 활동에는 .NET Framework의 <xref:System.Activities.Statements.ForEach%601>, <xref:System.Activities.Statements.Sequence> 및 <xref:System.Activities.Statements.AddToCollection%601>이 사용되며, 설문 조사 문항을 묻고 응답을 얻기 위한 `Prompt` 활동도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="12bce-113">The `Survey` activity uses <xref:System.Activities.Statements.ForEach%601>, <xref:System.Activities.Statements.Sequence> and <xref:System.Activities.Statements.AddToCollection%601> from the .NET Framework and employs the `Prompt` activity for asking the survey questions and getting responses.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="12bce-114">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="12bce-114">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="12bce-115">열기는 **BasicActivityComposition.sln** 샘플 솔루션을 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="12bce-115">Open the **BasicActivityComposition.sln** sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="12bce-116">솔루션을 빌드하고 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="12bce-116">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="12bce-117">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12bce-117">The samples may already be installed on your machine.</span></span> <span data-ttu-id="12bce-118">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="12bce-118">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="12bce-119">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="12bce-119">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="12bce-120">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12bce-120">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Composite\ActivityComposition`  
  
## <a name="see-also"></a><span data-ttu-id="12bce-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="12bce-121">See Also</span></span>
