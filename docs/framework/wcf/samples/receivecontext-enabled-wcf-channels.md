---
title: ReceiveContext 사용 WCF 채널
ms.date: 03/30/2017
ms.assetid: d990d119-7321-4b8c-852b-10256f59f9b0
ms.openlocfilehash: 3e5ac914ae4d0c97ed617ea4a8d5a893ec740179
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33502936"
---
# <a name="receivecontext-enabled-wcf-channels"></a>ReceiveContext 사용 WCF 채널
이 샘플에서는 <xref:System.ServiceModel.Channels.ReceiveContext> 사용 WCF 채널의 유용성을 보여 줍니다. 이 샘플에서는 NetMSMQ 채널을 사용하여 두 수의 곱을 찾기 위한 서비스를 구현합니다.  
  
 <xref:System.ServiceModel.Channels.ReceiveContext> 클래스를 사용하면 응용 프로그램에서는 메시지 내용을 검사한 후라도 메시지에 액세스할지 아니면 추가 처리를 위해 메시지를 큐에 둘지를 결정할 수 있습니다. 이 샘플의 클라이언트는 트랜잭션 큐에 임의의 정수를 보냅니다. `ProductCalculator` 서비스에서는 메시지를 받고 메시지 내용, 즉 정수를 검사하여 곱을 계산할 수 있는지 여부를 확인합니다. 서비스 작업에서 곱을 계산하지 않는 경우에는 메시지가 큐에 다시 배치되므로 해당 큐에서 수신 대기하는 서비스가 이 메시지를 다시 받을 수 있습니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\ReceiveContextProductGenerator`  
  
#### <a name="to-use-this-sample"></a>이 샘플을 사용하려면  
  
1.  MSMQ(Microsoft Message Queuing)가 설치되어 있는지 확인합니다.  
  
    1.  [!INCLUDE[lserver](../../../../includes/lserver-md.md)]에 MSMQ를 설치하려면  
  
        1.  **서버 관리자**, 클릭 **기능**합니다.  
  
        2.  아래의 오른쪽 창에서 **기능 요약**, 클릭 **기능 추가**합니다.  
  
        3.  결과 창에서 확장 **메시지 큐**합니다.  
  
        4.  확장 **메시지 대기열 서비스**합니다.  
  
        5.  클릭 **디렉터리 서비스 통합** (컴퓨터에 대 한 도메인에 가입)를 클릭 하 고 **HTTP 지원**합니다.  
  
        6.  클릭 **다음**, 클릭 하 고 **설치**합니다.  
  
    2.  [!INCLUDE[wv](../../../../includes/wv-md.md)]에 MSMQ를 설치하려면  
  
        1.  **제어판**을 엽니다.  
  
        2.  클릭 **프로그램** 차례로 선택한 다음 **프로그램 및 기능**, 클릭 **Windows 기능 사용을 설정 및 해제**합니다.  
  
        3.  확장 **Microsoft Message Queue (MSMQ) Server**, 확장 **Microsoft Message Queue (MSMQ) Server Core**, 한 후 설치 하려면 다음과 같은 메시지 큐 기능에 대 한 확인란을 선택 합니다.  
  
            -   메시지 큐 서버  
  
            -   MSMQ Active Directory 도메인 서비스 통합(도메인에 가입된 컴퓨터의 경우)  
  
            -   MSMQ HTTP 지원  
  
        4.  **확인**을 클릭합니다.  
  
        5.  컴퓨터를 다시 시작 하는 메시지가 클릭 **확인** 설치를 완료 합니다.  
  
2.  컴퓨터에 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]이 설치되어 있는지 확인합니다.  
  
3.  [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)]에서 ReceiveContextProductGenerator.sln 솔루션 파일을 엽니다.  
  
4.  Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.  
  
5.  Ctrl+F5를 눌러 솔루션을 실행합니다.
