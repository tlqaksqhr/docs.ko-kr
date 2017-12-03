---
title: "보정 가능한 활동에 대한 취소 처리기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: afd98bee-eccf-47e9-99c9-27cea84ce5ce
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 89a5350d61600124e3e5073d6788e4f9042cd70f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="cancellation-handler-on-compensable-activity"></a><span data-ttu-id="88d15-102">보정 가능한 활동에 대한 취소 처리기</span><span class="sxs-lookup"><span data-stu-id="88d15-102">Cancellation Handler on Compensable Activity</span></span>
<span data-ttu-id="88d15-103">이 샘플에서는 <xref:System.Activities.Statements.CompensableActivity>에 대해 취소 처리기를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="88d15-103">This sample demonstrates the use of a cancellation handler on a <xref:System.Activities.Statements.CompensableActivity>.</span></span>  
  
 <span data-ttu-id="88d15-104">이 샘플에는 <xref:System.Activities.Statements.CompensableActivity> 취소를 사용하는 방법을 보여 주는 두 가지 시나리오가 포함되어 있습니다. 첫째 시나리오에는 보정 가능한 루트 활동이 있으며 이 활동에는 보정 가능한 자식 활동 세 개가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88d15-104">This sample contains two scenarios that demonstrate the use of <xref:System.Activities.Statements.CompensableActivity> cancellation.The first scenario contains a root compensable activity that contains three child compensable activities.</span></span> <span data-ttu-id="88d15-105">자식 활동 두 개는 해당 활동 본문의 실행을 성공적으로 마칩니다.</span><span class="sxs-lookup"><span data-stu-id="88d15-105">Two child activities finish running their activity bodies successfully.</span></span> <span data-ttu-id="88d15-106">그러나 셋째 자식 활동의 경우에는 해당 본문을 실행하는 동안 예외가 발생합니다. 이 예외를 처리하기 위해 셋째 활동의 진행이 취소되며, 그 후에는 루트 활동의 취소가 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="88d15-106">When the third child activity body runs, it encounters an exception that is handled by canceling the third activity processing, after which the cancellation of the root activity is triggered.</span></span> <span data-ttu-id="88d15-107">이 샘플에서 루트 활동의 논리는 앞서 완료된 다른 두 자식 활동을 보정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="88d15-107">The logic in the root activity in this example is to compensate the other two child activities that completed earlier.</span></span>  
  
```  
Try  
{  
    CA   
    {  
        CA1   
        {  
        }  
        CA2  
        {  
        }  
        CA3  
        {  
            //Exception here  
            // Then this will get cancelled  
        }  
  
       // Cancellation for the root activity automatically gets called, which, in turn, adds some logic to revert what was done (Or can decide to actually confirm CA1 & CA2 if the user so desires).  
    }  
}  
Catches {  
// Can do more stuff...  
}  
```  
  
 <span data-ttu-id="88d15-108">둘째 시나리오에서는 <xref:System.Activities.Statements.TryCatch> 분기 전에 완료되는 <xref:System.Activities.Statements.Delay>와 병렬로 <xref:System.Activities.Statements.TryCatch>를 실행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="88d15-108">The second scenario demonstrates executing a <xref:System.Activities.Statements.TryCatch> in parallel with a <xref:System.Activities.Statements.Delay>, which finishes before the <xref:System.Activities.Statements.TryCatch> branch.</span></span> <span data-ttu-id="88d15-109">첫째 분기를 완료하고 나면 완료 조건이 `true`로 설정되므로 다른 분기가 취소됩니다.</span><span class="sxs-lookup"><span data-stu-id="88d15-109">The completion condition is set to `true` once the first branch finishes, causing the other branch to be canceled.</span></span>  
  
```  
Parallel   
{  
    Branch1   
    {  
        // Small Delay that times out (timeout1) before branch2.  
    }  
    Branch2   
    {  
        CA   
        {  
            CA1   
            {  
            }  
            CA2   
            {  
            }  
            CA3   
            {  
            }  
            If (timeout1)    
            {  
                call Cancel CA  
            }  
        }  
    }  
}  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="88d15-110">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="88d15-110">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="88d15-111">[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]을 사용하여 CompensationCancellation.sln을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="88d15-111">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open CompensationCancellation.sln.</span></span>  
  
2.  <span data-ttu-id="88d15-112">Ctrl+Shift+B 키를 누르거나 빌드 메뉴에서 "솔루션 빌드"를 선택하여 샘플을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="88d15-112">Build the sample by pressing CTRL+SHIFT+B or select "Build Solution" from the Build menu..</span></span>  
  
3.  <span data-ttu-id="88d15-113">F5 키를 누르거나 디버그 메뉴에서 "디버깅 시작"을 선택하여 샘플을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="88d15-113">Run the sample by pressing F5 or select "Start Debugging" from the Debug menu.</span></span> <span data-ttu-id="88d15-114">또는 Ctrl+F5를 누르거나 디버그 메뉴에서 "디버깅하지 않고 시작"을 선택하여 샘플을 디버깅하지 않고 실행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88d15-114">Alternately you may press Ctrl+F5 or select "Start without Debugging" from the Debug menu.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="88d15-115">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88d15-115">The samples may already be installed on your machine.</span></span> <span data-ttu-id="88d15-116">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="88d15-116">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="88d15-117">이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.</span><span class="sxs-lookup"><span data-stu-id="88d15-117">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="88d15-118">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88d15-118">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Compensation\CompensationCancellation`