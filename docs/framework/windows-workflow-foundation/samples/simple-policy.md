---
title: Simple Policy
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6a94c834-2e32-4bed-9f47-ae5845eef6ff
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 0c704a9f3f27d63fb1a28db61f03cdc9b8de4370
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="simple-policy"></a><span data-ttu-id="aa0af-102">Simple Policy</span><span class="sxs-lookup"><span data-stu-id="aa0af-102">Simple Policy</span></span>
<span data-ttu-id="aa0af-103">이 샘플에서는 워크플로에서 <xref:System.Workflow.Activities.PolicyActivity> 활동을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="aa0af-103">This sample shows how to use a <xref:System.Workflow.Activities.PolicyActivity> activity in a workflow.</span></span>  
  
 <span data-ttu-id="aa0af-104">이 샘플의 순차 워크플로는 <xref:System.Workflow.Activities.PolicyActivity> 활동을 사용하여 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="aa0af-104">The sequential workflow in this sample is created by using a <xref:System.Workflow.Activities.PolicyActivity> activity.</span></span> <span data-ttu-id="aa0af-105">이 워크플로는 제품 할인 워크플로를 정의하는 데 사용되는 `orderValue`, `customerType` 및 `discount` 필드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="aa0af-105">The workflow defines `orderValue`, `customerType`, and `discount` fields that are used to define a product discount workflow.</span></span> <span data-ttu-id="aa0af-106">규칙 파일에 정의된 규칙이 `orderValue` 및 `customerType` 기반의 할인 가격을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="aa0af-106">The rules defined in the rules file set a discount value that is based on the `orderValue` and `customerType`.</span></span> <span data-ttu-id="aa0af-107">`orderValue` 및 `customerType`은 `SimplePolicyWorkflow` 클래스 정의에서 설정되며 변경하여 동작을 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa0af-107">The `orderValue` and `customerType` are set in the `SimplePolicyWorkflow` class definition and can be changed to alter the behavior.</span></span> <span data-ttu-id="aa0af-108">그 결과 할인은 <xref:System.Workflow.Runtime.WorkflowRuntime.WorkflowCompleted> 클래스에 정의된 `SimplePolicyWorkflow` 이벤트 처리기의 콘솔에 쓰여집니다.</span><span class="sxs-lookup"><span data-stu-id="aa0af-108">The resulting discount is written to the console in the <xref:System.Workflow.Runtime.WorkflowRuntime.WorkflowCompleted> event handler that is defined in the `SimplePolicyWorkflow` class.</span></span>  
  
### <a name="to-build-the-sample"></a><span data-ttu-id="aa0af-109">이 샘플을 빌드하려면</span><span class="sxs-lookup"><span data-stu-id="aa0af-109">To build the sample</span></span>  
  
1.  <span data-ttu-id="aa0af-110">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 솔루션을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="aa0af-110">Open the solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="aa0af-111">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="aa0af-111">Build the solution by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="aa0af-112">Ctrl+F5를 눌러 디버깅 없이 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="aa0af-112">Run the solution without debugging by pressing CTRL+F5.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="aa0af-113">이 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="aa0af-113">To run the sample</span></span>  
  
-   <span data-ttu-id="aa0af-114">SDK 명령 프롬프트 창에서 샘플의 주 폴더 아래에 있는 SimplePolicy\bin\debug 폴더 또는 SimplePolicy\bin 폴더(Visual Basic 버전 샘플의 경우)의 .exe 파일을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="aa0af-114">In the SDK Command Prompt window, run the .exe file in the SimplePolicy\bin\debug folder (or the SimplePolicy\bin folder for the Visual Basic version of the sample), which is located below the main folder for the sample.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="aa0af-115">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa0af-115">The samples may already be installed on your computer.</span></span> <span data-ttu-id="aa0af-116">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="aa0af-116">Check for the following (default) directory before continuing:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="aa0af-117">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="aa0af-117">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="aa0af-118">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa0af-118">This sample is located in the following directory:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\Policy\SimplePolicy`  
  
## <a name="see-also"></a><span data-ttu-id="aa0af-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="aa0af-119">See Also</span></span>  
 <xref:System.Workflow.Activities.Rules.RuleSet>  
 <xref:System.Workflow.Activities.PolicyActivity>  
 [<span data-ttu-id="aa0af-120">고급 정책</span><span class="sxs-lookup"><span data-stu-id="aa0af-120">Advanced Policy</span></span>](../../../../docs/framework/windows-workflow-foundation/samples/advanced-policy.md)
