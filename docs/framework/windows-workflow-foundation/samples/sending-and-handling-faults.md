---
title: "오류 보내기 및 처리 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 98e8e04d-2ac9-4a33-ae08-462f757a7a14
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# 오류 보내기 및 처리
이 샘플에서는 <xref:System.ServiceModel.Activities.SendReply> 및 <xref:System.ServiceModel.Activities.ReceiveReply> 메시징 활동을 사용하여 예상된 오류와 예기치 않은 오류를 주고받는 방법을 보여 줍니다.이 시나리오에서는 맨 처음 클라이언트 요청의 결과로 <xref:System.ServiceModel.Activities.Send.KnownTypes%2A> 컬렉션에 포함되어 있는 예상된 오류가 발생합니다.그 이후 몇 번의 클라이언트 요청의 결과로 예기치 않은 오류가 발생한 다음 마지막 요청이 성공합니다.  
  
## 이 샘플을 사용하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 아이콘을 마우스 오른쪽 단추로 클릭하고 **관리자 권한으로 실행**을 선택하여 높은 권한으로 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]을 엽니다.  
  
2.  Faults.sln 솔루션 파일을 엽니다.  
  
3.  Ctrl\+Shift\+B를 눌러 솔루션을 빌드합니다.  
  
4.  서비스 프로젝트를 실행합니다.  
  
    1.  **솔루션 탐색기**에서 `FaultService` 프로젝트를 마우스 오른쪽 단추로 클릭하고 **시작 프로젝트로 설정**을 선택합니다.  
  
    2.  Ctrl\+F5를 누릅니다.  
  
5.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 아이콘을 마우스 오른쪽 단추로 클릭하고 **관리자 권한으로 실행**을 선택하여 높은 권한으로 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]의 다른 복사본을 엽니다.  
  
6.  Faults.sln 솔루션 파일을 엽니다.  
  
7.  클라이언트 프로젝트를 실행합니다.  
  
    1.  **솔루션 탐색기**에서 `FaultClient` 프로젝트를 마우스 오른쪽 단추로 클릭하고 **시작 프로젝트로 설정**을 선택합니다.  
  
    2.  Ctrl\+F5를 누릅니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.계속하기 전에 다음\(기본\) 디렉터리를 확인하십시오.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780)로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하십시오.이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Services\Faults`  
  
## 참고 항목