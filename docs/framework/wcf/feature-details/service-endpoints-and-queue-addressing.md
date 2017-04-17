---
title: "서비스 끝점 및 큐 주소 지정 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7d2d59d7-f08b-44ed-bd31-913908b83d97
caps.latest.revision: 18
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 18
---
# 서비스 끝점 및 큐 주소 지정
이 항목에서는 클라이언트가 큐에서 읽는 서비스에 주소를 지정하는 방법 및 서비스 끝점이 큐에 매핑되는 방법을 설명합니다.다음 그림은 기본 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]의 대기 중인 응용 프로그램 배포를 보여 줍니다.  
  
 ![대기 중인 응용 프로그램 다이어그램](../../../../docs/framework/wcf/feature-details/media/distributed-queue-figure.jpg "Distributed\-Queue\-Figure")  
  
 클라이언트가 서비스에 메시지를 보낼 수 있도록 하려면 대상 큐에 메시지 주소를 지정합니다.서비스가 큐에서 메시지를 읽을 수 있도록 하려면 해당 수신 주소를 대상 큐로 설정합니다.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 주소 지정은 URI\(Uniform Resource Identifier\)를 기반으로 하지만 메시지 큐\(MSMQ\) 큐 이름은 URI를 기반으로 하지 않습니다.따라서 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]를 사용하여 MSMQ에서 만든 큐에 주소를 지정하는 방법을 반드시 알아 두어야 합니다.  
  
## MSMQ 주소 지정  
 MSMQ는 경로 및 형식 이름을 사용하여 큐를 식별합니다.경로는 호스트 이름 및 `QueueName`을 지정합니다.필요한 경우 호스트 이름과 `QueueName` 간에 Active Directory 디렉터리 서비스에 게시되지 않은 개인 큐를 나타내도록 `Private$`가 있을 수 있습니다.  
  
 경로 이름이 “FormatNames”에 매핑되어 라우팅 및 큐 관리자 전송 프로토콜을 비롯하여 주소의 여러 측면을 확인할 수 있습니다.큐 관리자는 기본 MSMQ 프로토콜과 SRMP\(SOAP Reliable Messaging Protocol\)의 두 가지 전송 프로토콜을 지원합니다.  
  
 MSMQ 경로 및 형식 이름[!INCLUDE[crabout](../../../../includes/crabout-md.md)][About Message Queuing](http://go.microsoft.com/fwlink/?LinkId=94837)을 참조하십시오.  
  
## NetMsmqBinding 및 서비스 주소 지정  
 서비스로 메시지 주소를 지정할 때 URI의 체계는 통신에 사용되는 전송에 따라 선택됩니다.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]의 각 전송에는 고유한 체계가 있습니다.체계는 통신에 사용되는 전송의 특성을 반영해야 합니다.예를 들어 net.tcp, net.pipe, HTTP 등입니다.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 MSMQ 대기 중인 전송은 net.msmq 체계를 노출합니다.net.msmq 체계를 사용하여 주소가 지정된 메시지는 MSMQ 대기 중인 전송 채널을 통해 `NetMsmqBinding`을 사용하여 보내집니다.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 큐 주소 지정은 다음 패턴을 기반으로 합니다.  
  
 net.msmq: \/\/ \<*host\-name*\> \/ \[private\/\] \<*queue\-name*\>  
  
 다음은 각 요소에 대한 설명입니다.  
  
-   \<*host\-name*\>은 대상 큐를 호스팅하는 컴퓨터의 이름입니다.  
  
-   \[private\]는 선택 사항입니다.개인 큐인 대상 큐에 주소를 지정할 때 사용됩니다.공개 큐에 주소를 지정하려면 private를 지정하지 않아야 합니다.MSMQ 경로와 달리 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] URI 형식에는 "$"가 없습니다.  
  
-   \<*queue\-name*\>은 큐의 이름입니다.큐 이름은 하위 큐를 참조할 수도 있습니다.그러므로, \<*queue\-name*\> \= \<*name\-of\-queue*\>\[;*sub\-queue\-name*\].  
  
 예제 1: abc atadatum.com 컴퓨터에서 호스팅된 개인 큐 PurchaseOrders에 주소를 지정하는 경우 URI는 net.msmq:\/\/abc.adatum.com\/private\/PurchaseOrders입니다.  
  
 예제 2: def atadatum.com 컴퓨터에서 호스팅된 공개 큐 AccountsPayable에 주소를 지정하는 경우 URI는 net.msmq:\/\/def.adatum.com\/AccountsPayable입니다.  
  
 큐 주소는 메시지를 읽을 수신기에 의해 수신 대기 URI로 사용됩니다.즉, 큐 주소는 TCP 소켓의 수신 대기 포트에 해당합니다.  
  
 큐에서 읽는 끝점에서는 ServiceHost를 열 때 이전에 지정한 같은 체계를 사용하여 큐의 주소를 지정해야 합니다.예제를 보려면 [Net MSMQ 바인딩](../../../../docs/framework/wcf/samples/net-msmq-binding.md) 및 [Message Queuing Integration Binding Samples](http://msdn.microsoft.com/ko-kr/997d11cb-f2c5-4ba0-9209-92843d4d0e1a)을 참조하십시오.  
  
### 큐의 여러 계약  
 큐의 메시지는 서로 다른 계약을 구현할 수 있습니다.이 경우 다음 중 하나가 충족되어야 모든 메시지를 읽고 처리할 수 있습니다.  
  
-   모든 계약을 구현하는 서비스 끝점을 지정합니다.이는 권장되는 방법입니다.  
  
-   서로 다른 계약으로 여러 끝점을 지정하지만 모든 끝점이 같은 `NetMsmqBinding` 개체를 사용해야 합니다.ServiceModel에서 디스패치 논리는 디스패치용 전송 채널에서 메시지를 읽는 메시지 펌프를 사용하므로, 서로 다른 끝점으로 계약 기반 메시지를 역 멀티플렉싱합니다.메시지 펌프는 수신 대기 URI\/바인딩 쌍에 대해 만들어집니다.큐 주소는 대기 중인 수신기에 의해 수신 대기 URI로 사용됩니다.모든 끝점이 같은 바인딩 개체를 사용하는 경우 단일 메시지 펌프가 메시지를 읽고 계약을 기반으로 관련 끝점에 역 멀티플렉싱하는 데 사용됩니다.  
  
### SRMP 메시징  
 앞에서 설명한 대로 큐 간 전송에 SRMP 프로토콜을 사용할 수 있습니다.일반적으로 이 방법은 HTTP 전송이 전송 큐와 대상 큐 간에 메시지를 전송할 때 사용됩니다.  
  
 SRMP 전송 프로토콜을 사용하려면 앞에서 언급했듯이 net.msmq URI 체계를 사용하여 메시지에 주소를 지정하고 `NetMsmqBinding`의 `QueueTransferProtocol` 속성에 SRMP 또는 보안 SRMP를 지정합니다.  
  
 `QueueTransferProtocol` 속성을 지정하면 보내기 전용 기능이 됩니다.이것은 클라이언트가 사용할 큐 전송 프로토콜의 종류를 나타냅니다.  
  
### Active Directory 사용  
 MSMQ에는 Active Directory 통합에 대한 지원이 포함되어 있습니다.MSMQ가 Active Directory 통합과 함께 설치되는 경우 해당 컴퓨터는 Windows 도메인에 속해야 합니다.Active Directory는 검색할 큐를 게시하는 데 사용되며, 그러한 큐를 *공개 큐*라고 합니다.큐에 주소를 지정할 때 Active Directory를 사용하여 해당 큐를 확인할 수 있습니다.이 방법은 네트워크 이름의 IP 주소를 확인할 때 DNS\(Domain Name System\)를 사용하는 방법과 비슷합니다.`NetMsmqBinding`의 `UseActiveDirectory` 속성은 대기 중인 채널이 Active Directory를 사용하여 큐 URI를 확인해야 하는지 여부를 나타내는 부울입니다.기본적으로 이 속성은 `false`로 설정됩니다.`UseActiveDirectory` 속성이 `true`로 설정되는 경우 대기 중인 채널은 Active Directory를 사용하여 net.msmq:\/\/ URI를 형식 이름으로 변환합니다.  
  
 `UseActiveDirectory` 속성이 메시지를 보낼 때 큐의 주소를 확인하는 데 사용되므로 메시지를 보내는 클라이언트에 대해서만 설정할 수 있습니다.  
  
### 메시지 큐 형식 이름에 net.msmq URI 매핑  
 대기 중인 채널에서 채널에 제공된 net.msmq URI 이름을 MSMQ 형식 이름으로 매핑하는 작업을 처리합니다.다음 표에서는 이들 간 매핑에 사용된 규칙을 요약하여 설명합니다.  
  
|WCF URI 기반 큐 주소|Active Directory 속성 사용|큐 전송 프로토콜 속성|결과 MSMQ 형식 이름|  
|---------------------|----------------------------|------------------|-------------------|  
|Net.msmq:\/\/\<컴퓨터 이름\>\/private\/abc|False\(기본값\)|Native\(기본값\)|DIRECT\=OS:machine\-name\\private$\\abc|  
|Net.msmq:\/\/\<컴퓨터 이름\>\/private\/abc|False|SRMP|DIRECT\=http:\/\/machine\/msmq\/private$\/abc|  
|Net.msmq:\/\/\<컴퓨터 이름\>\/private\/abc|True|Native|PUBLIC\=some\-guid\(큐의 GUID\)|  
  
### 배달 못 한 편지 큐 또는 포이즌 메시지 큐에서 메시지 읽기  
 대상 큐의 하위 큐인 포이즌 메시지 큐에서 메시지를 읽으려면 하위 큐의 주소가 있는 `ServiceHost`를 엽니다.  
  
 예제: 로컬 컴퓨터에 있는 개인 큐 PurchaseOrders의 포이즌 메시지 큐에서 읽는 서비스는 net.msmq:\/\/localhost\/private\/PurchaseOrders;poison 주소를 지정합니다.  
  
 시스템 트랜잭션 배달 못 한 편지 큐에서 메시지를 읽으려면 URI가 net.msmq:\/\/localhost\/system$;DeadXact 형식이어야 합니다.  
  
 시스템 비트랜잭션 배달 못 한 편지 큐에서 메시지를 읽으려면 URI가 net.msmq:\/\/localhost\/system$;DeadLetter 형식이어야 합니다.  
  
 사용자 지정 배달 못 한 편지 큐를 사용할 때 배달 못 한 편지 큐가 로컬 컴퓨터에 있어야 합니다.따라서 배달 못 한 편지 큐의 URI는 다음 형식으로 제한됩니다.  
  
 net.msmq: \/\/localhost\/ \[private\/\]  \<*custom\-dead\-letter\-queue\-name*\>.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스는 받은 모든 메시지에 현재 수신 중인 특정 큐로 주소가 지정되었는지 확인합니다.메시지의 대상 큐가 메시지가 있는 큐와 일치하지 않으면 서비스가 메시지를 처리하지 않습니다.이 경우 배달 못 한 편지 큐의 메시지를 다른 곳으로 배달해야 하므로 배달 못 한 편지 큐를 수신하는 서비스가 주소를 지정해야 하는 문제가 있습니다.배달 못 한 편지 큐에서 또는 포이즌 큐에서 메시지를 읽으려면 <xref:System.ServiceModel.AddressFilterMode> 매개 변수를 포함하는 `ServiceBehavior`를 사용해야 합니다.예제를 보려면 [배달 못 한 편지 큐](../../../../docs/framework/wcf/samples/dead-letter-queues.md)를 참조하십시오.  
  
## MsmqIntegrationBinding 및 서비스 주소 지정  
 `MsmqIntegrationBinding`은 기존 MSMQ 응용 프로그램과의 통신에 사용됩니다.기존 MSMQ 응용 프로그램과의 상호 운용성을 쉽게 하기 위해 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 형식 이름 주소 지정만을 지원합니다.따라서 이 바인딩을 사용하여 보낸 메시지는 URI 체계를 따라야 합니다.  
  
 msmq.formatname:\<*MSMQ\-format\-name*\>\>  
  
 MSMQ 형식 이름은 [About Message Queuing](http://go.microsoft.com/fwlink/?LinkId=94837)의 MSMQ에서 지정한 형식입니다.  
  
 `MsmqIntegrationBinding`을 사용하여 큐에서 메시지를 받을 때 직접 형식 이름, 공개 및 개인 형식 이름만 사용할 수 있습니다\(Active Directory 통합 필요\).그러나 직접 형식 이름을 사용하는 것이 좋습니다.예를 들어 [!INCLUDE[wv](../../../../includes/wv-md.md)]에서 다른 형식 이름을 사용하면 시스템이 직접 형식 이름으로만 열 수 있는 하위 큐를 열려고 하므로 오류가 발생합니다.  
  
 `MsmqIntegrationBinding`을 사용하여 SRMP에 주소를 지정할 때 IIS\(인터넷 정보 서비스\)가 디스패치할 수 있도록 직접 형식 이름에 \/msmq\/를 추가하지 않아도 됩니다.예를 들면, DIRECT\=http:\/\/adatum.com\/msmq\/private$\/abc 대신 SRMP 프로토콜을 사용하여 큐 abc에 주소를 지정할 때 DIRECT\=http:\/\/adatum.com\/private$\/abc를 사용해야 합니다.  
  
 `MsmqIntegrationBinding`과 함께 net.msmq:\/\/ 주소 지정을 사용할 수 없습니다.`MsmqIntegrationBinding`이 자유 형식의 MSMQ 형식 이름 주소 지정을 지원하므로 이 바인딩을 통해 MSMQ의 멀티캐스트 및 메일 그룹 기능을 사용하는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스를 사용할 수 있습니다.한 가지 예외의 경우는 `MsmqIntegrationBinding`을 사용할 때 `CustomDeadLetterQueue`를 지정하는 것입니다.이 경우 net.msmq:\/\/ 형식이어야 하며, `NetMsmqBinding`을 사용하여 지정하는 방법과 비슷합니다.  
  
## 참고 항목  
 [대기 중인 응용 프로그램 웹 호스팅](../../../../docs/framework/wcf/feature-details/web-hosting-a-queued-application.md)