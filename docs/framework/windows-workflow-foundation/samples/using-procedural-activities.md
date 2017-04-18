---
title: "Using Procedural Activities | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1c67f739-3878-48ad-806c-b2ce0d6733a0
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# Using Procedural Activities
이 샘플에서는 <xref:System.Activities.Statements.Sequence>, <xref:System.Activities.Statements.Assign>, <xref:System.Activities.Statements.If>, <xref:System.Activities.Statements.While>, <xref:System.Activities.Statements.Switch%601>, <xref:System.Activities.Statements.TryCatch> 및 <xref:System.Activities.Statements.WriteLine> 활동을 사용하여 추측 게임을 구현합니다.이 추측 게임이 임의의 숫자를 선택하면 플레이어는 해당 숫자를 추측해야 합니다.플레이어의 추측이 틀리면 워크플로에서는 더 높은 숫자나 더 낮은 숫자를 추측하라는 힌트를 제공합니다.플레이어가 7회 미만의 시도에서 숫자를 맞추면 특별한 축하 화면이 표시됩니다.  
  
## 이 샘플의 사용자 지정 활동  
  
### ReadLine  
 콘솔에서 텍스트 줄을 읽어 옵니다.이 활동은 <xref:System.Activities.NativeActivity> 클래스에서 파생된 것으로, 줄을 읽었을 때 콘솔 응용 프로그램에 의해 다시 시작되는 책갈피를 만듭니다.  
  
### PromptInt  
 사용자에게 숫자를 입력하라는 메시지를 표시하고 콘솔 창에서 해당 숫자를 읽습니다.이 활동은 <xref:System.Activities.Activity%601>에서 파생된 것으로, <xref:System.Activities.Statements.WriteLine> 및 `ReadLine` 활동을 사용합니다.  
  
##### 이 샘플을 사용하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 GuessingGame.sln 솔루션 파일을 엽니다.  
  
2.  Ctrl\+Shift\+B를 눌러 솔루션을 빌드합니다.  
  
3.  Ctrl\+F5를 눌러 솔루션을 실행합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.계속하기 전에 다음\(기본\) 디렉터리를 확인하십시오.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780)로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하십시오.이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\Procedurals`  
  
## 참고 항목