---
title: "확인 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8637aeaf-ac9e-49b8-93f4-da15dee45277
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# 확인
이 샘플에서는 <xref:System.Activities.Statements.CompensableActivity>의 사용 및 확인과 관련된 일반적인 네 개의 시나리오를 보여 주고,네 개의 워크플로를 실행하여 확인하는 방법을 보여 줍니다.이 샘플은 선언적 버전과 명령적 버전으로 사용할 수 있습니다.  
  
## 보정 가능한 활동 확인  
 첫 번째 워크플로는 보정 가능한 활동을 확인하는 방법을 보여 주며, 두 개의 <xref:System.Activities.Statements.CompensableActivity> 인스턴스로 이루어진 시퀀스로 구성되어 있습니다.확인 활동은 두 번째 <xref:System.Activities.Statements.CompensableActivity>가 완료된 후 첫 번째 활동을 확인합니다.확인되지 않거나 보정되지 않은 <xref:System.Activities.Statements.CompensableActivity> 모든 인스턴스는 워크플로가 성공적으로 완료되면 기본 순서를 사용하여 자동으로 확인됩니다.확인하지 않을 경우 두 번째 <xref:System.Activities.Statements.CompensableActivity>가 먼저 확인됩니다.  
  
## 명시적 보정  
 두 번째 시나리오에서는 <xref:System.Activities.Statements.CompensableActivity>가 명시적으로 보정되는 경우 기본 확인에 어떤 영향을 주는지 보여 줍니다.워크플로는 두 개의 <xref:System.Activities.Statements.CompensableActivity> 활동으로 이루어진 시퀀스로 구성되어 있으며, 두 번째 활동이 완료된 후 첫 번째 활동이 명시적으로 보정됩니다.따라서 워크플로가 완료되면 두 번째 <xref:System.Activities.Statements.CompensableActivity>만 확인됩니다.  
  
## 중첩된 CompensableActivity 활동의 확인 순서 제어  
 세 번째 시나리오에서는 중첩된 <xref:System.Activities.Statements.CompensableActivity>의 확인 순서를 제어하는 방법을 보여 줍니다.시나리오는 워크플로 루트 역할을 하는 <xref:System.Activities.Statements.CompensableActivity>로 구성되어 있습니다.루트 <xref:System.Activities.Statements.CompensableActivity>의 본문은 세 개의 <xref:System.Activities.Statements.CompensableActivity>로 구성된 시퀀스입니다.루트 <xref:System.Activities.Statements.CompensableActivity>의 <xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A>는 첫 번째와 두 번째 중첩된 <xref:System.Activities.Statements.CompensableActivity>를 차례로 확인하도록 지정하는 시퀀스입니다.워크플로는 완료될 때 루트 <xref:System.Activities.Statements.CompensableActivity>를 확인하며, 그 다음에 첫 번째, 두 번째, 세 번째 중첩된 <xref:System.Activities.Statements.CompensableActivity>를 차례로 확인합니다.따라서 기본 확인 순서는 반대입니다.세 번째 <xref:System.Activities.Statements.CompensableActivity>는 <xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A>에 의해 명시적으로 루트 <xref:System.Activities.Statements.CompensableActivity>의 일부로 확인되지 않았기 때문에 기본 순서에 따라 확인됩니다.그러나 이 활동은 유일하게 확인되지 않은 <xref:System.Activities.Statements.CompensableActivity>이기 때문에 확인된 것으로 간주됩니다.  
  
## 변수 범위 지정  
 네 번째 시나리오에서는 활동 또는 워크플로가 완료된 경우에도  <xref:System.Activities.Statements.CompensableActivity.CompensationHandler%2A>, <xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A> 또는 <xref:System.Activities.Statements.CompensableActivity.CancellationHandler%2A> 처리기가 실행될 때 <xref:System.Activities.Statements.CompensableActivity> 또는 이 활동의 부모 중 하나에 대해 정의된 변수의 수명이 여전히 범위 내에 있게 하는 방법을 보여 줍니다.워크플로는 두 개의 <xref:System.Activities.Statements.CompensableActivity>로 이루어진 시퀀스로 구성되어 있습니다.첫 번째 활동의 본문에서는 `mySum` 변수가 5와 10의 합계로 설정되어 있고 결과가 출력됩니다.두 번째 <xref:System.Activities.Statements.CompensableActivity>의 본문에서는 합계가 기존 합계와 7의 합계로 설정되어 있고 결과가 출력됩니다.사용자 지정 확인 처리기는 합계를 출력하고 7을 뺀 다음 합계를 다시 출력하는 첫 번째 <xref:System.Activities.Statements.CompensableActivity>에 대해 정의됩니다.출력된 합계를 검사해 보면 두 <xref:System.Activities.Statements.CompensableActivity>의 본문뿐 아니라 <xref:System.Activities.Statements.CompensableActivity.ConfirmationHandler%2A>의 경우에도 변수가 범위 내에 있음을 확실하게 알 수 있습니다.  
  
#### 예제를 실행하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 솔루션을 로드합니다.  
  
2.  ConfirmationSample.exe 응용 프로그램을 실행합니다.  
  
3.  다음 출력을 확인합니다.  
  
 **Explicit confirmation:Start of workflowCompensableActivity1: BodyCompensableActivity2: BodyCompensableActivity1: Confirmation HandlerEnd of workflowCompensableActivity2: Confirmation HandlerExplicit compensation:Start of workflowCompensableActivity1: BodyCompensableActivity2: BodyCompensableActivity1: Compensation HandlerEnd of workflowCompensableActivity2: Confirmation HandlerCustom confirmation handler:Start of workflowCompensableActivity1: BodyCompensableActivity2: BodyCompensableActivity3: BodyEnd of workflowCompensableActivity1: Confirmation HandlerCompensableActivity2: Confirmation HandlerCompensableActivity3: Confirmation HandlerVariable access in a confirmation handler:Start of workflowCompensableActivity1: BodyCompensableActivity1: The sum is: 15CompensableActivity2: BodyCompensableActivity2: Adding 7 to the sumCompensableActivity2: The sum is now: 22End of workflowCompensableActivity2: Confirmation HandlerCompensableActivity1: Confirmation HandlerCompensableActivity2: The sum is: 22CompensableActivity2: After subtracting 12 the sum is now: 10Press ENTER to exit.**  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.계속하기 전에 다음\(기본\) 디렉터리를 확인하십시오.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780)로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하십시오.이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Compensation\Confirmation`  
  
## 참고 항목