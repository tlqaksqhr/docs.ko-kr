---
title: "Asynchronous Communication | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 128dc092-9eb2-4e33-9470-9a7f62b60df6
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Asynchronous Communication
이 샘플에서는 기본적으로 서로 다른 두 [!INCLUDE[wf](../../../../includes/wf-md.md)] 서비스 간에 비동기 통신이 이루어지는 방식을 보여 줍니다.  
  
## 세부 항목  
 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 서비스 간의 비동기 통신  
  
## 추가 설명  
 이 샘플에서는 .NET Framework에서 제공되는 메시징 활동을 통해 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 응용 프로그램 간의 통신이 비동기적으로 이루어지는 방식을 보여 줍니다.  
  
 이 샘플은 다음 세 개의 프로젝트로 구성되어 있습니다.  
  
 CreditCheckService  
 이 서비스는 특정 개인의 신용 점수나 승인할 품목의 가치를 받은 다음 해당 개인에게 신용을 부여할지 여부를 결정합니다.  
  
 RentalApprovalService  
 이 서비스는 신용 거래를 필요로 하는 개인으로부터 신청을 받습니다.이 서비스는 `CreditCheckService`와 비동기적으로 통신하여 신용 거래 신청이 유효한지 여부를 결정합니다.  
  
 Client  
 클라이언트는 `RentalApprovalService`와 동기적으로 통신하여 신용 거래가 승인되었는지 여부를 확인합니다.  
  
#### 샘플을 설치, 빌드 및 실행하려면  
  
1.  **AsynchronousCommunication** 솔루션을 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다.  
  
2.  **공용 속성**에서 **시작 프로젝트**를 선택하고 **여러 개의 시작 프로젝트**를 선택합니다.  
  
3.  **RentalApprovalService**를 목록의 첫 번째 위치로 이동하고 **CreditCheckService**와 **Client**를 차례로 그 다음 위치로 이동합니다.세 프로젝트 모두에 대해 **시작** 동작을 설정합니다.  
  
4.  **확인**을 클릭하고 F5 키를 눌러 샘플을 실행합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.계속하기 전에 다음\(기본\) 디렉터리를 확인하십시오.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780)로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하십시오.이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\Services\AsynchronousCommunication`