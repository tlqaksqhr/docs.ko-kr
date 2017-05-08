---
title: "실행 속성 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 31c009db-397c-4653-87e2-32dc77fa4b13
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# 실행 속성
이 샘플에서는 사용자 지정 활동에 실행 속성을 정의하고 사용하는 방법을 보여 줍니다.이 예제에서는 실행 속성에 따라 콘솔의 전경색이 결정됩니다.예제 워크플로는 실행의 논리 경로\(<xref:System.Activities.Statements.Parallel> 활동의 분기\)가 달라지는 경우 <xref:System.Activities.Statements.Parallel> 활동의 분기 전반에서 활동이 인터리브 방식으로 실행되더라도 다른 콘솔 색이 유지되는 방식을 보여 줍니다.  
  
#### 샘플을 설치, 빌드 및 실행하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 ExecutionProperties.sln 샘플 솔루션을 엽니다.  
  
    > [!NOTE]
    >  솔루션을 빌드하기 전에 ThreeColors.xaml을 보면 오류가 표시됩니다. 사용하는 사용자 지정 활동은 솔루션과 동시에 빌드되어야 하기 때문입니다.  
  
2.  솔루션을 빌드하고 실행합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.계속하기 전에 다음\(기본\) 디렉터리를 확인하십시오.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780)로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하십시오.이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\ExecutionProperties`  
  
## 참고 항목