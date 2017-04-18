---
title: "Using AsyncOperationContext in an Activity 샘플 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0888a0bd-d227-4c00-ad6a-b654a01740e8
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# Using AsyncOperationContext in an Activity 샘플
이 샘플에서는 <xref:System.Activities.AsyncOperationContext>를 사용하여 워크플로 외부에서 비동기적으로 작업을 수행하는 사용자 지정 <xref:System.Activities.CodeActivity>를 개발하는 방법을 보여 줍니다.  
  
## 샘플 세부 정보  
 샘플 활동에서는 <xref:System.IO.FileStream> 클래스의 <xref:System.IO.FileStream.BeginWrite> 및 <xref:System.IO.FileStream.EndWrite> 메서드를 사용하여 비동기적으로 파일에 데이터를 씁니다.여기에서 사용되는 패턴은 다른 비동기 메서드에도 사용할 수 있습니다.비동기 작업이 실행 중일 때 워크플로의 다른 활동을 실행할 수는 있지만 워크플로를 유지할 수는 없습니다.  
  
#### 샘플을 설치, 빌드 및 실행하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 Async.sln 샘플 솔루션을 엽니다.  
  
2.  솔루션을 빌드하고 실행합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.계속하기 전에 다음\(기본\) 디렉터리를 확인하십시오.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780)로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하십시오.이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\Code-Bodied\Async`  
  
## 참고 항목