---
title: IfElse With Rules
ms.date: 03/30/2017
ms.assetid: c4ad9bb2-9037-413a-8b14-59ed7b927a9e
ms.openlocfilehash: 179ec29f957894433fb527a14048460f5ff6ee5b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33515123"
---
# <a name="ifelse-with-rules"></a><span data-ttu-id="88fa2-102">IfElse With Rules</span><span class="sxs-lookup"><span data-stu-id="88fa2-102">IfElse With Rules</span></span>
<span data-ttu-id="88fa2-103">이 샘플에서는 <xref:System.Workflow.Activities.IfElseActivity> 활동에 규칙 조건을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="88fa2-103">This sample shows the use of a rule condition with an <xref:System.Workflow.Activities.IfElseActivity> activity.</span></span>  
  
 <span data-ttu-id="88fa2-104">이 샘플은 호스트로부터 `OrderValue` 매개 변수를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="88fa2-104">The sample passes in an `OrderValue` parameter from the host.</span></span> <span data-ttu-id="88fa2-105">이 매개 변수의 값은 <xref:System.Workflow.Activities.IfElseActivity> 활동의 첫 번째 분기에 대한 규칙 조건에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="88fa2-105">The value of the parameter is used in a rule condition on the first branch of the <xref:System.Workflow.Activities.IfElseActivity> activity.</span></span> <span data-ttu-id="88fa2-106">첫 번째 분기가 실행 값에 10, 000 보다 작은 경우 및 <xref:System.Workflow.Activities.CodeActivity> 인쇄 하는 첫 번째 분기에서 활동 **관리자 승인을 가져올** 콘솔에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88fa2-106">If the value is less than 10,000, the first branch executes, and the <xref:System.Workflow.Activities.CodeActivity> activity in the first branch prints **Get Manager Approval** to the console.</span></span> <span data-ttu-id="88fa2-107">값이 10, 000 보다 큰는 <xref:System.Workflow.Activities.CodeActivity> 두 번째 분기에서 작업 실행 하 고 출력 **VP 승인 가져오기**합니다.</span><span class="sxs-lookup"><span data-stu-id="88fa2-107">If the value is greater than 10,000, the <xref:System.Workflow.Activities.CodeActivity> activity in the second branch executes and prints **Get VP Approval**.</span></span>  
  
### <a name="to-build-the-sample"></a><span data-ttu-id="88fa2-108">이 샘플을 빌드하려면</span><span class="sxs-lookup"><span data-stu-id="88fa2-108">To build the sample</span></span>  
  
1.  <span data-ttu-id="88fa2-109">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 솔루션을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="88fa2-109">Open the solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="88fa2-110">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="88fa2-110">Build the solution by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="88fa2-111">Ctrl+F5를 눌러 디버깅 없이 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="88fa2-111">Run the solution without debugging by pressing CTRL+F5.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="88fa2-112">이 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="88fa2-112">To run the sample</span></span>  
  
-   <span data-ttu-id="88fa2-113">SDK 명령 프롬프트 창에서 샘플의 주 폴더 아래에 있는 IfElseWithRules\bin\debug 폴더 또는 IfElseWithRules\bin 폴더(Visual Basic 버전 샘플의 경우)의 .exe 파일을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="88fa2-113">In the SDK Command Prompt window, run the .exe file in the IfElseWithRules\bin\debug folder (or the IfElseWithRules\bin folder for the Visual Basic version of the sample), which is located below the main folder for the sample.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="88fa2-114">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88fa2-114">The samples may already be installed on your computer.</span></span> <span data-ttu-id="88fa2-115">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="88fa2-115">Check for the following (default) directory before continuing:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="88fa2-116">이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플.</span><span class="sxs-lookup"><span data-stu-id="88fa2-116">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="88fa2-117">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88fa2-117">This sample is located in the following directory:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\IfElseWithRules`  
  
## <a name="see-also"></a><span data-ttu-id="88fa2-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="88fa2-118">See Also</span></span>  
 <xref:System.Workflow.Activities.Rules>  
 <xref:System.Workflow.Activities.IfElseActivity>  
 <xref:System.Workflow.Activities.CodeActivity>  
 <xref:System.Workflow.Activities.Rules.RuleDefinitions>
