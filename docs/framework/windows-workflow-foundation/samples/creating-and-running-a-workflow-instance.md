---
title: "워크플로 인스턴스 만들기 및 실행"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 19d27f47-0491-4569-8f53-51bc1d940e80
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b25acebfaf6df68ac3163a5ef4bcb235077139cc
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="creating-and-running-a-workflow-instance"></a>워크플로 인스턴스 만들기 및 실행
이 샘플에서는 워크플로 인스턴스를 실행하는 방법을 보여 줍니다. 동기적 실행 방법과 비동기적 실행 방법을 모두 보여 줍니다.  
  
## <a name="demonstrates"></a>세부 항목  
 <xref:System.Activities.WorkflowInvoker>, <xref:System.Activities.WorkflowApplication>.  
  
## <a name="discussion"></a>토론  
 샘플의 첫 번째 부분에서는 <xref:System.Activities.WorkflowInvoker.Invoke%2A>를 사용합니다. 이는 워크플로를 실행하는 가장 기본적인 방법입니다. <xref:System.Activities.WorkflowInvoker.Invoke%2A>를 사용할 경우 워크플로를 동기적으로 실행할 수 있습니다.  
  
 샘플의 다음 부분에서는 <xref:System.Activities.WorkflowApplication> 클래스를 사용합니다. <xref:System.Activities.WorkflowApplication> 클래스를 사용하면 실행 중인 워크플로와 상호 작용하고 워크플로를 비동기적으로 실행하는 등 각 인스턴스를 보다 효과적으로 제어할 수 있습니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Execution\CreatingWorkflowInstances`  
  
## <a name="see-also"></a>참고 항목  
 [WorkflowInvoker 및 WorkflowApplication 사용](../../../../docs/framework/windows-workflow-foundation/using-workflowinvoker-and-workflowapplication.md)
