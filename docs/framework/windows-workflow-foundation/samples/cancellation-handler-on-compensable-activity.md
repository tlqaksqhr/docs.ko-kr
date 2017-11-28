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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b39b5d9277767160225a34be9e0c71a36e7b6d78
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="cancellation-handler-on-compensable-activity"></a>보정 가능한 활동에 대한 취소 처리기
이 샘플에서는 <xref:System.Activities.Statements.CompensableActivity>에 대해 취소 처리기를 사용하는 방법을 보여 줍니다.  
  
 이 샘플에는 <xref:System.Activities.Statements.CompensableActivity> 취소를 사용하는 방법을 보여 주는 두 가지 시나리오가 포함되어 있습니다. 첫째 시나리오에는 보정 가능한 루트 활동이 있으며 이 활동에는 보정 가능한 자식 활동 세 개가 포함되어 있습니다. 자식 활동 두 개는 해당 활동 본문의 실행을 성공적으로 마칩니다. 그러나 셋째 자식 활동의 경우에는 해당 본문을 실행하는 동안 예외가 발생합니다. 이 예외를 처리하기 위해 셋째 활동의 진행이 취소되며, 그 후에는 루트 활동의 취소가 트리거됩니다. 이 샘플에서 루트 활동의 논리는 앞서 완료된 다른 두 자식 활동을 보정하는 것입니다.  
  
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
  
 둘째 시나리오에서는 <xref:System.Activities.Statements.TryCatch> 분기 전에 완료되는 <xref:System.Activities.Statements.Delay>와 병렬로 <xref:System.Activities.Statements.TryCatch>를 실행하는 방법을 보여 줍니다. 첫째 분기를 완료하고 나면 완료 조건이 `true`로 설정되므로 다른 분기가 취소됩니다.  
  
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
  
### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]을 사용하여 CompensationCancellation.sln을 엽니다.  
  
2.  Ctrl+Shift+B 키를 누르거나 빌드 메뉴에서 "솔루션 빌드"를 선택하여 샘플을 빌드합니다.  
  
3.  F5 키를 누르거나 디버그 메뉴에서 "디버깅 시작"을 선택하여 샘플을 실행합니다. 또는 Ctrl+F5를 누르거나 디버그 메뉴에서 "디버깅하지 않고 시작"을 선택하여 샘플을 디버깅하지 않고 실행할 수도 있습니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Compensation\CompensationCancellation`  
  
## <a name="see-also"></a>참고 항목
