---
title: "신뢰할 수 있는 보안 프로필 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 921edc41-e91b-40f9-bde9-b6148b633e61
caps.latest.revision: 8
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 8
---
# 신뢰할 수 있는 보안 프로필
이 샘플에서는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 및 RSP\([Reliable Secure Profile](http://go.microsoft.com/fwlink/?LinkId=178140)\)를 구성하는 방법을 보여 줍니다.이 샘플에서는 RSP 사양에 따라 신뢰할 수 있는 보안 바인딩을 만들기 위해 신뢰할 수 있는 메시징 및 보안 채널\(선택적\)과 함께 구성할 수 있는 [Make Connection](http://go.microsoft.com/fwlink/?LinkId=178141) 채널의 구현을 보여 줍니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.계속하기 전에 다음\(기본\) 디렉터리를 확인하십시오.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780)로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하십시오.이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Channels\ReliableSecureProfile`  
  
## 추가 설명  
 이 샘플에서는 신뢰할 수 있는 비동기 양방향 메시지 교환 시나리오를 보여 줍니다.서비스에는 이중 계약이 있으며 클라이언트에서는 이중 콜백 계약을 구현합니다.클라이언트는 서비스에 대한 요청을 시작하며 해당 응답을 별도의 연결에서 받아야 합니다.요청 메시지는 신뢰할 수 있는 상태로 보내집니다.그러나 클라이언트 쪽에서는 수신 대기 끝점을 열지 않으려고 하므로서비스에 대한 ‘Make Connection’ 요청으로 서비스를 폴링하여 이 ‘Make Connection’ 요청의 백 채널에서 응답을 다시 보냅니다.이 샘플에서는 클라이언트에서 수신 대기 끝점을 노출하지 않고 방화벽 예외도 생성하지 않으면서 HTTP를 통해 신뢰할 수 있는 이중 보안 통신을 하는 방법을 보여 줍니다.  
  
## 샘플을 설치, 빌드 및 실행하려면  
  
1.  **ReliableSecureProfile** 솔루션을 엽니다.  
  
2.  **솔루션 탐색기**에서 **Service** 프로젝트를 마우스 오른쪽 단추로 클릭하고 상황에 맞는 메뉴에서 **디버그**, **새 인스턴스 시작**을 차례로 선택합니다.그러면 서비스 호스트가 시작됩니다.  
  
3.  **솔루션 탐색기**에서 **Client** 프로젝트를 마우스 오른쪽 단추로 클릭하고 상황에 맞는 메뉴에서 **디버그**, **새 인스턴스 시작**을 차례로 선택합니다.그러면 클라이언트가 시작됩니다.  
  
4.  클라이언트 콘솔 창의 프롬프트에 임의의 문자열을 입력하고 Enter 키를 클릭합니다. 그러면 입력 문자열이 이 문자열의 해시를 계산하는 서비스로 보내집니다.  
  
5.  서비스에서 이중 콜백 계약 작업을 콜백하여 클라이언트 콘솔 창에 결과가 표시되면 클라이언트 창에서 결과를 확인합니다.서비스에는 장시간 실행되는 데이터 처리 작업을 시뮬레이션하기 위한 의도적인 지연이 있습니다.  
  
6.  네트워크 모니터, Fiddler 등의 온라인 네트워크 모니터링 도구를 사용하여 HTTP 트래픽을 모니터링하면 클라이언트와 서비스 간의 통신 시퀀스가 Reliable Secure Profile에 규정된 대로 설정되어 있음을 알 수 있으며, 클라이언트에서 ‘Make Connection’ 요청을 사용하여 서비스를 폴링하는 방식도 알 수 있습니다.서비스에서는 처리된 응답을 다시 보낼 수 있는 준비가 되면 마지막 ‘Make Connection’ 요청의 백 채널을 사용하여 결과를 다시 보냅니다.  
  
7.  서비스 콘솔 창에서 Enter 키를 눌러 서비스를 닫습니다.클라이언트 콘솔 창에서 Enter 키를 눌러 클라이언트를 닫습니다.