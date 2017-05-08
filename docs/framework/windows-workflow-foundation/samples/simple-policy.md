---
title: "Simple Policy | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6a94c834-2e32-4bed-9f47-ae5845eef6ff
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# Simple Policy
이 샘플에서는 워크플로에서 <xref:System.Workflow.Activities.PolicyActivity> 활동을 사용하는 방법을 보여 줍니다.  
  
 이 샘플의 순차 워크플로는 <xref:System.Workflow.Activities.PolicyActivity> 활동을 사용하여 만들어집니다.이 워크플로는 제품 할인 워크플로를 정의하는 데 사용되는 `orderValue`, `customerType` 및 `discount` 필드를 정의합니다.규칙 파일에 정의된 규칙이 `orderValue` 및 `customerType` 기반의 할인 가격을 설정합니다.`orderValue` 및 `customerType`은 `SimplePolicyWorkflow` 클래스 정의에서 설정되며 변경하여 동작을 바꿀 수 있습니다.그 결과 할인은 `SimplePolicyWorkflow` 클래스에 정의된 <xref:System.Workflow.Runtime.WorkflowRuntime.WorkflowCompleted> 이벤트 처리기의 콘솔에 쓰여집니다.  
  
### 이 샘플을 빌드하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 솔루션을 엽니다.  
  
2.  Ctrl\+Shift\+B를 눌러 솔루션을 빌드합니다.  
  
3.  Ctrl\+F5를 눌러 디버깅 없이 솔루션을 실행합니다.  
  
### 이 샘플을 실행하려면  
  
-   SDK 명령 프롬프트 창에서 샘플의 주 폴더 아래에 있는 SimplePolicy\\bin\\debug 폴더 또는 SimplePolicy\\bin 폴더\(Visual Basic 버전 샘플의 경우\)의 .exe 파일을 실행합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.계속하기 전에 다음\(기본\) 디렉터리를 확인하십시오.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780)로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하십시오.이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\Policy\SimplePolicy`  
  
## 참고 항목  
 <xref:System.Workflow.Activities.Rules.RuleSet>   
 <xref:System.Workflow.Activities.PolicyActivity>   
 [Advanced Policy](../../../../docs/framework/windows-workflow-foundation/samples/advanced-policy.md)