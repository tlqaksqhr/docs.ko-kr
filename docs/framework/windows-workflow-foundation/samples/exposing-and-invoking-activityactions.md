---
title: "ActivityAction 노출 및 호출 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 97ce4797-426e-463d-9cc4-1261afad6df4
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# ActivityAction 노출 및 호출
이 샘플에서는 <xref:System.Activities.ActivityAction>이 있는 사용자 지정 활동을 개발하는 방법을 보여 줍니다.또한 <xref:System.Activities.ActivityAction>의 구현을 제공하여 이 활동을 사용하는 방법도 보여 줍니다.  
  
 <xref:System.Activities.ActivityAction>을 통해 활동 작성자는 활동 사용자가 사용자 지정 동작을 플러그 인할 수 있는 특정 시그니처를 사용하여 “허점”을 노출할 수 있습니다.예를 들어 항목 컬렉션에 대해 작동하는 <xref:System.Activities.Statements.ForEach> 활동에 <xref:System.Activities.ActivityAction>이 있으며 이를 통해 활동 사용자가 현재 반복 항목에 대해 작동하는 동작을 플러그 인할 수 있습니다.  
  
#### 샘플을 설치, 빌드 및 실행하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 **ActivityAction.sln** 샘플 솔루션을 엽니다.  
  
2.  솔루션을 빌드하고 실행합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.계속하기 전에 다음\(기본\) 디렉터리를 확인하십시오.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780)로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하십시오.이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\ActivityAction`  
  
## 참고 항목