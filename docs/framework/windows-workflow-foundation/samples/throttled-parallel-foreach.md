---
title: "Throttled Parallel ForEach | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f2855b5f-e9a7-433d-96a4-40fc31025215
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Throttled Parallel ForEach
`ThrottleParallelForEach` 활동은 실행할 동시 분기 수를 제한하는 동시 비율을 설정하도록 허용한다는 점만 제외하면 <xref:System.Activities.Statements.ParallelForEach> 활동과 비슷합니다.`ThrottleParallelForEach` 활동은 다른 활동\(자식 활동\)을 예약해야 하고 <xref:System.Activities.NativeActivityContext> 클래스를 통해서만 액세스 가능하기 때문에 <xref:System.Activities.NativeActivity>에서 파생됩니다.  
  
## 프로젝트  
  
||||  
|-|-|-|  
|**프로젝트 이름**|**설명**|**기본 파일**|  
|ThrottledParallelForEach|`ThrottledParallelForEach` 활동과 이 활동의 디자이너가 들어 있습니다.|ThrottledParallelForEach.cs<br /><br /> `ThrottledParallelForEach` 활동 정의입니다.|  
|CodeTestClient|명령적 코드를 사용하여 `ThrottledParallelForEach`가 있는 워크플로를 구성 및 실행하는 샘플 클라이언트 응용 프로그램입니다.|Program.cs<br /><br /> 샘플 워크플로의 인스턴스를 정의하고 실행합니다.|  
  
#### 이 샘플을 사용하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]을 사용하여 ThrottledParallelForEach.sln 파일을 엽니다.  
  
2.  Ctrl\+Shift\+B를 눌러 솔루션을 빌드합니다.  
  
3.  F5 키를 눌러 솔루션을 실행합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.계속하기 전에 다음\(기본\) 디렉터리를 확인하십시오.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780)로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하십시오.이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\ThrottledParallelForEach`  
  
## 참고 항목