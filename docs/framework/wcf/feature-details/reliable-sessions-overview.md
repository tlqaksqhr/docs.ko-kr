---
title: "신뢰할 수 있는 세션 개요 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
ms.assetid: a7fc4146-ee2c-444c-82d4-ef6faffccc2d
caps.latest.revision: 30
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 30
---
# 신뢰할 수 있는 세션 개요
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] SOAP 신뢰할 수 있는 메시징은 SOAP 끝점 사이에서 종단 간 메시지 전송 안전성을 제공합니다.전송 오류 및 SOAP 메시지 수준 오류를 극복하여 신뢰할 수 없는 네트워크에서 이를 구현합니다.특히 SOAP 또는 전송 매개자를 통해 보낸 메시지에 대해 세션 기반, 단일 및 필요에 따라 순서가 지정된 배달을 제공합니다.세션 기반 배달은 선택적 메시지 순서 지정을 통해 세션 내의 메시지를 그룹화합니다.  
  
 아래에서는 신뢰할 수 있는 세션의 정의, 사용 방법 및 사용 시기와 보안을 유지하는 방법에 대해 설명합니다.  
  
## WCF 신뢰할 수 있는 세션  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 신뢰할 수 있는 세션은 WS\-ReliableMessaging 프로토콜에 정의된 대로 SOAP 신뢰할 수 있는 메시징의 구현입니다.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] SOAP 신뢰할 수 있는 메시징은 메시징 끝점을 구분하는 매개자의 수 또는 형식과 관계없이 두 개의 끝점 사이에 종단 간 신뢰할 수 있는 세션을 제공합니다.여기에는 끝점 간의 메시지 흐름에 필요한, SOAP를 사용하지 않는 전송 매개자\(예: HTTP 프록시\) 또는 SOAP를 사용하는 매개자\(예: SOAP 기반 라우터나 브리지\)가 포함됩니다.신뢰할 수 있는 세션 채널은 이러한 채널에 의해 연결된 서비스가 동시에 실행되고 짧은 대기 시간 조건, 즉 상대적으로 짧은 시간 간격 내에서 메시지를 교환하고 처리할 수 있도록 "대화형" 통신을 지원합니다.이 결합은 이러한 구성 요소가 함께 진행되거나 함께 실패되는 것을 의미하기 때문에 구성 요소는 서로 격리되지 않습니다.  
  
 신뢰할 수 있는 세션에서는 다음 두 가지 유형의 오류를 마스킹합니다.  
  
-   손실되거나 중복된 메시지 및 보낸 순서와 다른 순서로 도착한 메시지를 포함하는 SOAP 메시지 수준 오류  
  
-   전송 오류  
  
 신뢰할 수 있는 세션은 WS\-ReliableMessaging 프로토콜 및 내장 메모리 전송 창을 구현하여 SOAP 메시지 수준 오류를 마스킹하고 전송 오류가 발생할 경우 다시 연결합니다.  
  
 신뢰할 수 있는 세션은 TCP가 IP 패킷에 대해 제공하는 SOAP 메시지를 제공합니다.TCP 소켓 연결은 노드 간에 IP 패킷에 대한 단수형의 순서가 지정된 전송을 제공합니다.신뢰할 수 있는 채널은 신뢰할 수 있는 전송과 동일한 유형을 제공하지만 다음과 같은 방법에서 TCP 소켓 안정성이 다릅니다.  
  
-   안정성은 임의 크기 패킷\(바이트\)이 아닌 SOAP 메시지 수준에서 구현됩니다.  
  
-   안정성은 TCP를 통한 전송이 아닌 전송 중립적 방법으로 구현됩니다.  
  
-   안정성은 특정 전송 세션\(예: TCP 연결이 제공하는 세션\)에 연결되지 않고 신뢰할 수 있는 세션 수명 동안 여러 전송 세션을 동시에 또는 순차적으로 사용할 수 있습니다.  
  
-   신뢰할 수 있는 세션은 SOAP 끝점 간의 연결에 필요한 전송 연결 수에 관계없이 발신자 및 수신자 SOAP 끝점 사이에 위치합니다.즉, TCP 안정성은 전송 연결이 종료되는 위치에서 종료되는 반면에 신뢰할 수 있는 세션은 종단 간 안정성을 제공합니다.  
  
## 신뢰할 수 있는 세션 및 바인딩  
 앞서 설명한 것처럼 신뢰할 수 있는 세션은 전송 중립적이며 여러 전송을 통해 구현될 수 있습니다.또한 신뢰할 수 있는 세션은 요청\-회신 또는 이중과 같은 여러 메시지 교환 패턴을 통해 설정될 수 있습니다.따라서 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 신뢰할 수 있는 세션은 바인딩 집합의 속성으로 노출됩니다.  
  
 다음을 사용하는 끝점에서 신뢰할 수 있는 세션을 사용할 수 있습니다.  
  
-   HTTP 기반 전송 표준 바인딩:  
  
    -   `WsHttpBinding` 및 요청\-회신 또는 단방향 계약을 노출합니다.  
  
    -   요청\-회신 또는 간단한 단방향 서비스 계약을 통해 신뢰할 수 있는 세션을 사용하는 경우 사용할 수 있습니다.  
  
    -   `WsDualHttpBinding` 및 이중, 요청\-회신 또는 단방향 계약을 노출합니다.  
  
    -   `WsFederationHttpBinding` 및 요청\-회신 또는 단방향 계약을 노출합니다.  
  
-   TCP 기반 전송 표준 바인딩:  
  
    -   `NetTcpBinding` 및 이중, 요청\-회신 또는 단방향 계약을 노출합니다.  
  
 또한 HTTPS와 같은 사용자 지정 바인딩 또는 명명된 파이프 바인딩을 만들어 다른 모든 바인딩에서 신뢰할 수 있는 세션을 사용할 수 있습니다\(문제에 대한 자세한 내용은 "신뢰할 수 있는 세션 및 보안" 참조\).  
  
 신뢰할 수 있는 세션을 서로 다른 기본 채널 형식에 쌓을 수 있으며 결과적으로 신뢰할 수 있는 세션 채널 모양이 변경됩니다.클라이언트 및 서버 모두에서 지원되는 신뢰할 수 있는 세션 채널 형식은 사용 중인 기본 채널 형식에 따라 다릅니다.다음 표에서는 기본 채널 형식의 기능으로서 클라이언트에서 지원되는 세션 채널 형식에 대해 설명합니다.  
  
|지원되는 신뢰할 수 있는 세션 채널 형식\(기본 채널 형식을 제공하는 `TChannel`의 지원되는 값\)|`IRequestChannel`|`IRequestSessionChanne`l|`IDuplexChannel`|`IDuplexSessionChannel`|  
|-----------------------------------------------------------------|-----------------------|------------------------------|----------------------|-----------------------------|  
|`IOutputSessionChannel`|예|예|예|예|  
|`IRequestSessionChannel`|예|예|아니요|아니요|  
|`IDuplexSessionChannel`|아니요|아니요|예|예|  
  
 지원되는 채널 형식은 <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.BuildChannelFactory%60%601%28System.ServiceModel.Channels.BindingContext%29> 메서드로 전달된 제네릭 `TChannel` 매개 변수 값에 대해 사용할 수 있는 값입니다.  
  
 다음 표에서는 기본 채널 형식의 기능으로서 서버에서 지원되는 세션 채널 형식에 대해 설명합니다.  
  
|지원되는 신뢰할 수 있는 세션 채널 형식\(기본 채널 형식을 제공하는 `TChannel`의 지원되는 값\)|`IReplyChannel`|`IReplySessionChannel`|`IDuplexChannel`|`IDuplexSessionChannel`|  
|-----------------------------------------------------------------|---------------------|----------------------------|----------------------|-----------------------------|  
|`IInputSessionChannel`|예|예|예|예|  
|`IReplySessionChannel`|예|예|아니요|아니요|  
|`IDuplexSessionChannel`|아니요|아니요|예|예|  
  
 지원되는 채널 형식은 <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.BuildChannelListener%60%601%28System.ServiceModel.Channels.BindingContext%29> 메서드로 전달된 제네릭 `TChannel` 매개 변수 값에 대해 사용할 수 있는 값입니다.  
  
## 신뢰할 수 있는 세션 및 보안  
 신뢰할 수 있는 세션의 보안을 유지하기 위해서는 통신 당사자\(서비스 및 클라이언트\)가 인증되고 세션 내에서 교환된 메시지가 훼손되지 않도록 해야 합니다.또한 각 개별 신뢰할 수 있는 세션의 무결성을 확인해야 합니다.신뢰할 수 있는 세션은 보안 세션 채널에 의해 표시되고 관리되는 보안 컨텍스트에 바인딩하여 보안을 유지합니다.보안 채널은 보안 세션을 제공합니다.세션 설정 동안 교환된 보안 토큰은 신뢰할 수 있는 세션의 메시지 보안을 유지하는 데 사용됩니다.  
  
 신뢰할 수 있는 세션을 TCP\-S를 통해 구현하는 경우 TCP 세션이 신뢰할 수 있는 세션에 연결되고 마찬가지로 전송 보안은 보안이 신뢰할 수 있는 세션에 연결되었는지 확인합니다.이 경우 연결 재설정이 꺼집니다.  
  
 HTTPS를 사용하는 경우에만 예외입니다.SSL\(Secure Sockets Layer\) 세션은 신뢰할 수 있는 세션에 바인딩되지 않습니다.이로 인해 보안 컨텍스트를 공유하는 세션\(SSL 세션\)이 서로 간에 보호되지 않기 때문에 위협이 될 수 있습니다. 이것은 응용 프로그램에 따라 실제 위협이 되거나 되지 않을 수도 있습니다.  
  
## 신뢰할 수 있는 세션 사용  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 신뢰할 수 있는 세션을 사용하려면 신뢰할 수 있는 세션을 지원하는 바인딩으로 끝점을 만듭니다.신뢰할 수 있는 세션이 활성화된 상태에서 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]가 제공하는 시스템 제공 바인딩 중 하나를 사용하거나 이를 수행하는 사용자 지정 바인딩을 만듭니다.기본적으로 신뢰할 수 있는 세션을 지원하고 사용하도록 설정하는 시스템 정의 바인딩은 다음과 같습니다.  
  
-   <xref:System.ServiceModel.WSDualHttpBinding>  
  
 선택 사항으로 신뢰할 수 있는 세션을 지원하지만 기본적으로 사용하지 않는 시스템 제공 바인딩은 다음과 같습니다.  
  
-   <xref:System.ServiceModel.WSHttpBinding>  
  
-   <xref:System.ServiceModel.WSFederationHttpBinding>  
  
-   <xref:System.ServiceModel.NetTcpBinding>  
  
 사용자 지정 바인딩을 만드는 방법에 대한 예제는 [방법: HTTPS를 사용하여 신뢰할 수 있는 사용자 지정 세션 바인딩 만들기](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md)를 참조하십시오.  
  
 신뢰할 수 있는 세션을 지원하는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 바인딩에 대한 설명은 [시스템 제공 바인딩](../../../../docs/framework/wcf/system-provided-bindings.md)을 참조하십시오.  
  
## 신뢰할 수 있는 세션을 사용하는 시기  
 응용 프로그램에서 신뢰할 수 있는 세션을 사용하는 시기를 이해하는 것이 중요합니다.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 동시에 활성화되어 작동하는 끝점 간에 신뢰할 수 있는 세션을 지원합니다.응용 프로그램에서 일정 시간 동안 끝점 중 하나를 사용할 수 없도록 설정하려면 큐를 사용하여 안정성을 확보합니다.  
  
 시나리오에서 두 개의 끝점을 TCP를 통해 연결해야 하는 경우 신뢰할 수 있는 세션을 반드시 사용할 필요는 없지만 TCP는 신뢰할 수 있는 메시지 교환을 제공하기에 충분할 수 있습니다. TCP는 패킷이 순서대로 한 번에 하나씩 도착하는지 확인합니다.  
  
 시나리오에 다음과 같은 특징이 있는 경우 신뢰할 수 있는 세션 사용을 심각하게 고려해야 합니다.  
  
-   SOAP 라우터와 같은 SOAP 매개자  
  
-   프록시 매개자 또는 전송 브리지  
  
-   중간 연결  
  
-   HTTP를 통한 세션  
  
## 참고 항목  
 [바인딩을 사용하여 서비스 및 클라이언트 구성](../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)   
 [WS 신뢰할 수 있는 세션](../../../../docs/framework/wcf/samples/ws-reliable-session.md)