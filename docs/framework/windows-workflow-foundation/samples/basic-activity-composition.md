---
title: "기본 활동 구성 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c283a1a7-1245-4ecd-8072-206c1b4ca379
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# 기본 활동 구성
이 샘플에서는 사용자 지정 활동을 추가로 빌드하기 위해 사용자 지정 활동과 시스템 제공 활동을 구성하는 방법을 보여 줍니다.  
  
 설문 조사 활동을 사용하는 워크플로에서 질문 목록을 준비하여 설문 조사 일정을 예약한 다음 설문을 통해 수집된 응답을 출력합니다.  
  
## 샘플 세부 정보  
 이 샘플에서는 다음과 같이 세 개의 사용자 지정 활동을 사용합니다.`ReadLine`은 예약되었을 때 <xref:System.Activities.Bookmark>를 만드는 간단한 <xref:System.Activities.NativeActivity>\<문자열\>이며 <xref:System.Activities.Bookmark>가 다시 시작되는 값으로 `Return`<xref:System.Activities.OutArgument%601>을 설정합니다.`Prompt`는 `Text`이라는 <xref:System.Activities.InArgument%601>\<문자열\>을 취하는 <xref:System.Activities.Activity%601>\<문자열\>이며 `Result`<xref:System.Activities.OutArgument%601>\<문자열\>에 사용자 응답을 반환합니다.`Prompt` 활동에는 .NET Framework의 일부로 제공되는 <xref:System.Activities.Statements.Sequence> 및 <xref:System.Activities.Statements.WriteLine> 활동이 사용되며, 사용자로부터 입력을 받기 위한 사용자 지정 `ReadLine` 활동도 여기에 통합됩니다.마지막 사용자 지정 활동은 `Survey` 활동입니다.이는 <xref:System.Activities.Activity>\<ICollection\<string\>\>입니다.이 활동에서는 `Questions`이라는 <xref:System.Activities.InArgument%601>\<IEnumerable\<string\>\>을 취하고 `Result` 출력 인수에 응답을 채웁니다.`Survey` 활동에는 .NET Framework의 <xref:System.Activities.Statements.ForEach>, <xref:System.Activities.Statements.Sequence> 및 <xref:System.Activities.Statements.AddToCollection%601>이 사용되며, 설문 조사 문항을 묻고 응답을 얻기 위한 `Prompt` 활동도 사용됩니다.  
  
#### 샘플을 설치, 빌드 및 실행하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 **BasicActivityComposition.sln** 샘플 솔루션을 엽니다.  
  
2.  솔루션을 빌드하고 실행합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.계속하기 전에 다음\(기본\) 디렉터리를 확인하십시오.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780)로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하십시오.이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Composite\ActivityComposition`  
  
## 참고 항목