---
title: IfElse With Rules
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c4ad9bb2-9037-413a-8b14-59ed7b927a9e
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bec818ca5492e9a49a602a4f7baef4b45cb073c1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ifelse-with-rules"></a><span data-ttu-id="16dcc-102">IfElse With Rules</span><span class="sxs-lookup"><span data-stu-id="16dcc-102">IfElse With Rules</span></span>
<span data-ttu-id="16dcc-103">이 샘플에서는 <xref:System.Workflow.Activities.IfElseActivity> 활동에 규칙 조건을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="16dcc-103">This sample shows the use of a rule condition with an <xref:System.Workflow.Activities.IfElseActivity> activity.</span></span>  
  
 <span data-ttu-id="16dcc-104">이 샘플은 호스트로부터 `OrderValue` 매개 변수를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="16dcc-104">The sample passes in an `OrderValue` parameter from the host.</span></span> <span data-ttu-id="16dcc-105">이 매개 변수의 값은 <xref:System.Workflow.Activities.IfElseActivity> 활동의 첫 번째 분기에 대한 규칙 조건에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="16dcc-105">The value of the parameter is used in a rule condition on the first branch of the <xref:System.Workflow.Activities.IfElseActivity> activity.</span></span> <span data-ttu-id="16dcc-106">첫 번째 분기가 실행 값에 10, 000 보다 작은 경우 및 <xref:System.Workflow.Activities.CodeActivity> 인쇄 하는 첫 번째 분기에서 활동 **관리자 승인을 가져올** 콘솔에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16dcc-106">If the value is less than 10,000, the first branch executes, and the <xref:System.Workflow.Activities.CodeActivity> activity in the first branch prints **Get Manager Approval** to the console.</span></span> <span data-ttu-id="16dcc-107">값이 10, 000 보다 큰는 <xref:System.Workflow.Activities.CodeActivity> 두 번째 분기에서 작업 실행 하 고 출력 **VP 승인 가져오기**합니다.</span><span class="sxs-lookup"><span data-stu-id="16dcc-107">If the value is greater than 10,000, the <xref:System.Workflow.Activities.CodeActivity> activity in the second branch executes and prints **Get VP Approval**.</span></span>  
  
### <a name="to-build-the-sample"></a><span data-ttu-id="16dcc-108">이 샘플을 빌드하려면</span><span class="sxs-lookup"><span data-stu-id="16dcc-108">To build the sample</span></span>  
  
1.  <span data-ttu-id="16dcc-109">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 솔루션을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="16dcc-109">Open the solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="16dcc-110">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="16dcc-110">Build the solution by pressing CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="16dcc-111">Ctrl+F5를 눌러 디버깅 없이 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="16dcc-111">Run the solution without debugging by pressing CTRL+F5.</span></span>  
  
### <a name="to-run-the-sample"></a><span data-ttu-id="16dcc-112">이 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="16dcc-112">To run the sample</span></span>  
  
-   <span data-ttu-id="16dcc-113">SDK 명령 프롬프트 창에서 샘플의 주 폴더 아래에 있는 IfElseWithRules\bin\debug 폴더 또는 IfElseWithRules\bin 폴더(Visual Basic 버전 샘플의 경우)의 .exe 파일을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="16dcc-113">In the SDK Command Prompt window, run the .exe file in the IfElseWithRules\bin\debug folder (or the IfElseWithRules\bin folder for the Visual Basic version of the sample), which is located below the main folder for the sample.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="16dcc-114">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16dcc-114">The samples may already be installed on your computer.</span></span> <span data-ttu-id="16dcc-115">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="16dcc-115">Check for the following (default) directory before continuing:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="16dcc-116">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="16dcc-116">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="16dcc-117">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16dcc-117">This sample is located in the following directory:</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\IfElseWithRules`  
  
## <a name="see-also"></a><span data-ttu-id="16dcc-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="16dcc-118">See Also</span></span>  
 <xref:System.Workflow.Activities.Rules>  
 <xref:System.Workflow.Activities.IfElseActivity>  
 <xref:System.Workflow.Activities.CodeActivity>  
 <xref:System.Workflow.Activities.Rules.RuleDefinitions>
