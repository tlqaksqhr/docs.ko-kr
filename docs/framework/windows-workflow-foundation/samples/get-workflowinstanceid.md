---
title: "WorkflowInstanceId 가져오기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bd7eea3b-1c28-4b84-9a67-003bc553aa81
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f1eb6a1d9cd875d0332bb1d59933f75c807f74e7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="get-workflowinstanceid"></a>WorkflowInstanceId 가져오기
이 샘플에서는 사용자 지정 활동인 `GetWorkflowInstanceId`를 사용하여 워크플로 인스턴스 ID를 반환하는 방법을 보여 줍니다.  
  
## <a name="demonstrates"></a>세부 항목  
 사용자 지정 활동 개발, 워크플로 인스턴스에 액세스하는 방법  
  
## <a name="discussion"></a>토론  
 실행 중인 워크플로의 인스턴스 ID를 가져오려면 코드를 작성해야 합니다. 완전히 선언적인 워크플로를 작성하려면 워크플로 인스턴스 ID를 반환할 수 있는 활동이 필요합니다. 그래야만 워크플로에서 해당 활동을 참조하여 완전히 선언적인 워크플로 작성 환경을 제공할 수 있습니다. 인스턴스 ID에 액세스해야 하는 시나리오에는 여러 가지가 있습니다. 예를 들어 로깅 또는 감사를 위한 시나리오도 여기에 해당하며, (가령 SendReply 활동 내에 이 활동을 사용하는 등) 나중에 연결하기 위해 인스턴스 ID를 클라이언트에 다시 제공하여 응용 프로그램 수준의 상관 관계를 만드는 시나리오도 여기에 해당합니다.  
  
 `GetWorkflowInstanceId`는 <xref:System.Activities.CodeActivity%601>로 구현됩니다. 이는 <xref:System.Guid> 형식의 값을 반환해야 하고 워크플로의 인스턴스 ID를 가져오기 위해 <xref:System.Activities.CodeActivityContext>에 액세스해야 하기 때문입니다. 그 구현은 비교적 기본적입니다.  
  
```  
public sealed class GetWorkflowInstanceId : CodeActivity<Guid>  
{  
protected override Guid Execute(CodeActivityContext context)  
        {  
            return context.WorkflowInstanceId;  
        }  
}  
```  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\GetWorkflowInstanceId`
