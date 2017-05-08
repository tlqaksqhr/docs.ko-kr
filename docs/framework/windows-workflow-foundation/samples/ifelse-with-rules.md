---
title: "IfElse With Rules | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c4ad9bb2-9037-413a-8b14-59ed7b927a9e
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# IfElse With Rules
이 샘플에서는 <xref:System.Workflow.Activities.IfElseActivity> 활동에 규칙 조건을 사용하는 방법을 보여 줍니다.  
  
 이 샘플은 호스트로부터 `OrderValue` 매개 변수를 전달합니다.이 매개 변수의 값은 <xref:System.Workflow.Activities.IfElseActivity> 활동의 첫 번째 분기에 대한 규칙 조건에 사용됩니다.값이 10,000보다 작으면 첫 번째 분기가 실행되며, 첫 번째 분기의 <xref:System.Workflow.Activities.CodeActivity> 활동 후에는 콘솔에 **Get Manager Approval**이 출력됩니다.값이 10,000보다 크면 두 번째 분기의 <xref:System.Workflow.Activities.CodeActivity> 활동이 실행되고 **Get VP Approval**이 출력됩니다.  
  
### 이 샘플을 빌드하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 솔루션을 엽니다.  
  
2.  Ctrl\+Shift\+B를 눌러 솔루션을 빌드합니다.  
  
3.  Ctrl\+F5를 눌러 디버깅 없이 솔루션을 실행합니다.  
  
### 이 샘플을 실행하려면  
  
-   SDK 명령 프롬프트 창에서 샘플의 주 폴더 아래에 있는 IfElseWithRules\\bin\\debug 폴더 또는 IfElseWithRules\\bin 폴더\(Visual Basic 버전 샘플의 경우\)의 .exe 파일을 실행합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.계속하기 전에 다음\(기본\) 디렉터리를 확인하십시오.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780)로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하십시오.이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Rules\IfElseWithRules`  
  
## 참고 항목  
 <xref:System.Workflow.Activities.Rules>   
 <xref:System.Workflow.Activities.IfElseActivity>   
 <xref:System.Workflow.Activities.CodeActivity>   
 <xref:System.Workflow.Activities.Rules.RuleDefinitions>