---
title: ".NET Framework 3.5 Ruleset으로 변수 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 27b56249-22fe-4252-840f-74c0d6c7a6b3
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# .NET Framework 3.5 Ruleset으로 변수 사용
이 샘플에서는 <xref:System.Activities.Statements.Interop> 활동을 사용하여 [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)]에서 작성되고 정책과 규칙을 사용하는 사용자 지정 활동을 통합하는 워크플로를 만드는 방법을 보여 줍니다.이 샘플에서는 사용자 지정 활동에서 노출하는 종속성 속성에 변수를 바인딩하여 사용자 지정 활동에 데이터를 전달합니다.  
  
## 샘플 연습  
  
#### TravelRuleLibrary를 검사하려면  
  
1.  [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)]에서 InteropWith35RuleSet.sln 솔루션 파일을 엽니다.  
  
2.  Workflow Designer에서 TravelRuleSet.cs를 엽니다.  
  
     <xref:System.Workflow.Activities.PolicyActivity>가 포함된 사용자 지정 순차 활동이 표시됩니다.  
  
3.  DiscountPolicy 정책 활동을 두 번 클릭하여 규칙을 검사합니다.  
  
     규칙 편집기에 규칙이 표시됩니다.  
  
4.  `DiscountPolicy`를 마우스 오른쪽 단추로 클릭하고 **코드 보기** 옵션을 선택하여 이 활동의 코드 병행 C\# 코드를 검사합니다.  
  
     `DiscountLevel`의 종속성 속성 설정을 확인합니다.이 설정은 [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)]의 인수에 해당합니다.인수에 대한 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]는 [변수 및 인수](../../../../docs/framework/windows-workflow-foundation//variables-and-arguments.md)를 참조하십시오.  
  
## InteropWith35RuleSet  
 <xref:System.Activities.Statements.Interop> 활동을 사용하여 `TravelRuleLibrary` 프로젝트에 만든 사용자 지정 규칙 집합과 통합되는 순차 워크플로 프로젝트입니다.변수는 최상위 <xref:System.Activities.Statements.Sequence> 활동에서 만들어집니다.<xref:System.Activities.Statements.Interop> 활동은 `TravelRuleSet` 활동과 통합하는 데 사용됩니다.<xref:System.Activities.Statements.Sequence>에 선언된 변수는 종속성 속성에 바인딩하는 데 사용됩니다.  
  
## 이 샘플을 사용하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 InteropWith35RuleSet.sln 솔루션 파일을 엽니다.  
  
2.  Ctrl\+Shift\+B를 눌러 솔루션을 빌드합니다.  
  
3.  Ctrl\+F5를 눌러 솔루션을 실행합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.계속하기 전에 다음\(기본\) 디렉터리를 확인하십시오.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780)로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하십시오.이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\InteropWith35RuleSet`  
  
## 참고 항목