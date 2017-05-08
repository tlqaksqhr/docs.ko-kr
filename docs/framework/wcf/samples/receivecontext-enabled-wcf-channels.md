---
title: "ReceiveContext 사용 WCF 채널 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d990d119-7321-4b8c-852b-10256f59f9b0
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# ReceiveContext 사용 WCF 채널
이 샘플에서는 <xref:System.ServiceModel.Channels.ReceiveContext> 사용 WCF 채널의 유용성을 보여 줍니다.  이 샘플에서는 NetMSMQ 채널을 사용하여 두 수의 곱을 찾기 위한 서비스를 구현합니다.  
  
 <xref:System.ServiceModel.Channels.ReceiveContext> 클래스를 사용하면 응용 프로그램에서는 메시지 내용을 검사한 후라도 메시지에 액세스할지 아니면 추가 처리를 위해 메시지를 큐에 둘지를 결정할 수 있습니다.  이 샘플의 클라이언트는 트랜잭션 큐에 임의의 정수를 보냅니다.  `ProductCalculator` 서비스에서는 메시지를 받고 메시지 내용, 즉 정수를 검사하여 곱을 계산할 수 있는지 여부를 확인합니다.  서비스 작업에서 곱을 계산하지 않는 경우에는 메시지가 큐에 다시 배치되므로 해당 큐에서 수신 대기하는 서비스가 이 메시지를 다시 받을 수 있습니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.  계속하기 전에 다음\(기본\) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [.NET Framework 4용 WCF\(Windows Communication Foundation\) 및 Windows WF\(Workflow Foundation\) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780)\(영문\)로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요.  이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\ReceiveContextProductGenerator`  
  
#### 이 샘플을 사용하려면  
  
1.  MSMQ\(Microsoft Message Queuing\)가 설치되어 있는지 확인합니다.  
  
    1.  [!INCLUDE[lserver](../../../../includes/lserver-md.md)]에 MSMQ를 설치하려면  
  
        1.  **서버 관리자**에서 **기능**을 클릭합니다.  
  
        2.  오른쪽 창의 **기능 요약**에서 **기능 추가**를 클릭합니다.  
  
        3.  결과 창에서 **메시지 큐**를 확장합니다.  
  
        4.  **메시지 큐 서비스**를 확장합니다.  
  
        5.  **디렉터리 서비스 통합**을 클릭한 다음\(도메인에 가입된 컴퓨터의 경우\) **HTTP 지원**을 클릭합니다.  
  
        6.  **다음**을 클릭한 후 **설치**를 클릭합니다.  
  
    2.  [!INCLUDE[wv](../../../../includes/wv-md.md)]에 MSMQ를 설치하려면  
  
        1.  **제어판**을 엽니다.  
  
        2.  **프로그램**을 클릭한 다음 **프로그램 및 기능**에서 **Windows 기능 사용\/사용 안 함**을 클릭합니다.  
  
        3.  **Microsoft Message Queue\(MSMQ\) Server**, **Microsoft Message Queue\(MSMQ\) Server Core**를 차례로 확장하고 다음 메시지 큐 기능의 확인란을 선택하여 설치합니다.  
  
            -   메시지 큐 서버  
  
            -   MSMQ Active Directory 도메인 서비스 통합\(도메인에 가입된 컴퓨터의 경우\)  
  
            -   MSMQ HTTP 지원  
  
        4.  **확인**을 클릭합니다.  
  
        5.  컴퓨터를 다시 시작할지 묻는 메시지가 나타나면 **확인**을 클릭하여 설치를 완료합니다.  
  
2.  컴퓨터에 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]이 설치되어 있는지 확인합니다.  
  
3.  [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]에서 ReceiveContextProductGenerator.sln 솔루션 파일을 엽니다.  
  
4.  Ctrl\+Shift\+B를 눌러 솔루션을 빌드합니다.  
  
5.  Ctrl\+F5를 눌러 솔루션을 실행합니다.