---
title: "FlowChart와 Pick을 함께 사용하는 StateMachine 시나리오 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 88d81395-f7a3-41d8-8439-20a425c538a6
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# FlowChart와 Pick을 함께 사용하는 StateMachine 시나리오
이 샘플에서는 <xref:System.Activities.Statements.Flowchart> 및 <xref:System.Activities.Statements.Pick> 활동을 함께 사용하여 간단한 스톱워치 시나리오를 구현하는 방법을 보여 줍니다.이 샘플에서는 Pick 활동 내의 Receive 및 Send를 사용하여 스톱워치 이벤트를 수신 대기합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.계속하기 전에 다음\(기본\) 디렉터리를 확인하십시오.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 다운로드 페이지로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하십시오.이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\StateMachineWithPick`  
  
## 샘플 세부 정보  
 다음 표에서는 이 샘플의 프로젝트를 보여 줍니다.  
  
|||  
|-|-|  
|프로젝트 이름|설명|  
|StopWatchService|이 프로젝트에는 <xref:System.Activities.Statements.Flowchart> 및 <xref:System.Activities.Statements.Pick> 활동을 함께 사용한 스톱워치 샘플의 상태 시스템 구현이 포함되어 있습니다.<br /><br /> <xref:System.Activities.Statements.Pick> 활동에는 <xref:System.Activities.Statements.Pick.Branches%2A> 속성 내에서 `GetStart`, `GetStop` 및 `GetOff` 이벤트를 수신 대기하는 세 개의 <xref:System.Activities.Statements.PickBranch> 문이 있습니다.들어오는 이벤트를 기준으로 분기 중 하나의 트리거가 활성화되고 해당하는 <xref:System.Activities.Statements.PickBranch.Action%2A>이 트리거됩니다.<xref:System.Activities.Statements.PickBranch.Action%2A> 속성에는 <xref:System.Activities.Statements.Switch%601> 문이 있습니다. 이 문은 전환이 올바른지 확인하는데, 올바른 경우 `currentState` 속성이 전환 상태로 업데이트되고 클라이언트에 보내집니다.<br /><br /> <xref:System.Activities.Statements.Flowchart>의 마지막에 있는 <xref:System.Activities.Statements.FlowDecision> 활동은 `currentState` 속성을 확인하여 상태가 터미널 상태인지 여부를 확인합니다.터미널 상태이면 워크플로가 종료되고, 그렇지 않으면 제어가 <xref:System.Activities.Statements.Pick> 활동의 시작으로 다시 돌아가 루프를 실행하여 워크플로가 추가 스톱워치 이벤트를 기다립니다.|  
|StopWatchClient|간단한 Send 또는 Receive 활동 조합을 사용하여 다양한 스톱워치 이벤트를 보내는 간단한 순차 워크플로 콘솔 응용 프로그램입니다.|  
  
#### 이 샘플을 사용하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 StateMachineWithPick.sln 솔루션 파일을 엽니다.  
  
2.  Ctrl\+Shift\+B를 눌러 솔루션을 빌드합니다.  
  
3.  .exe 파일을 마우스 오른쪽 단추로 클릭하고 **관리자 권한으로 실행**을 선택하여 [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)]에서 관리자 권한으로 StopWatchService.exe를 시작합니다.  
  
    1.  StateMachineWithPick\\CS\\StopWatchService\\bin\\Debug 폴더로 이동합니다.  
  
    2.  StopWatchService.exe 파일을 마우스 오른쪽 단추로 클릭하고 **관리자 권한으로 실행**을 선택합니다.  
  
4.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 StopWatchClient 클라이언트 응용 프로그램을 시작합니다.  
  
    1.  **솔루션 탐색기**에서 **StopWatchClient** 프로젝트를 선택하고 **시작 프로젝트로 설정**을 마우스 오른쪽 단추로 클릭합니다.  
  
    2.  Ctrl\+F5를 눌러 솔루션을 실행합니다.  
  
5.  StopWatchService.exe에 대한 콘솔 창으로 다시 전환하여 상태 전환을 확인합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.계속하기 전에 다음\(기본\) 디렉터리를 확인하십시오.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780)로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하십시오.이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\StateMachineWithPick`  
  
## 참고 항목