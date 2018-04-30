---
title: 전송 선택
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- choosing transports [WCF]
ms.assetid: b169462b-f7b6-4cf4-9fca-d306909ee8bf
caps.latest.revision: 25
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 989ae3d70bce2a4cb374904ee6b2f30f770ccf8a
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/30/2018
---
# <a name="choosing-a-transport"></a>전송 선택
이 항목에서는 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]에 포함된 3개의 주요 전송인 HTTP, TCP 및 명명된 파이프 사이의 선택 기준에 대해 설명합니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에는 MSMQ라고도 하는 메시지 큐 전송도 포함되지만, 이 문서에서는 메시지 큐에 대해 설명하지 않습니다.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 프로그래밍 모델에서는 서비스 계약에 표현된 끝점 작업을 두 끝점을 연결하는 전송 메커니즘과 구분합니다. 그 결과 네트워크에 서비스를 노출시키는 방법을 결정할 수 있는 유연성이 보장됩니다.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]를 사용 하 여 끝점 간의 네트워크를 통해 데이터를 전송 하는 방법을 지정는 *바인딩*의 시퀀스로 구성 된 *바인딩 요소의*합니다. 전송은 바인딩에 속한 전송 바인딩 요소로 표현됩니다. 바인딩에는 보안, 필수 메시지 인코더 바인딩 요소, 그리고 필수 전송 바인딩 요소와 같은 선택적인 프로토콜 바인딩 요소가 포함됩니다. 전송에서는 다른 응용 프로그램과의 사이에서 serialize된 형식의 메시지를 주고 받습니다.  
  
 기존 클라이언트 또는 서버에 연결해야 하는 경우에는 특정 전송을 선택할 수 없습니다. 하지만 여러 끝점을 통해 각각 서로 다른 전송을 사용하여 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스에 액세스할 수 있습니다. 단일 전송이 서비스에서 의도하는 대상을 수용하지 못하는 경우 여러 끝점을 통해 서비스를 공개해 보십시오. 그러면 클라이언트 응용 프로그램에서 가장 적합한 끝점을 사용할 수 있습니다.  
  
 전송을 선택하고 나면 이를 사용하는 바인딩을 선택해야 합니다. 시스템 제공 바인딩을 선택할 수 있습니다 (참조 [시스템 제공 바인딩](../../../../docs/framework/wcf/system-provided-bindings.md)), 하거나 사용자 지정 바인딩을 작성할 수 있습니다 (참조 [사용자 지정 바인딩을](../../../../docs/framework/wcf/extending/custom-bindings.md)). 바인딩을 직접 만들 수도 있습니다. 자세한 내용은 참조 [Creating User-Defined 바인딩](../../../../docs/framework/wcf/extending/creating-user-defined-bindings.md)합니다.  
  
## <a name="advantages-of-each-transport"></a>각 전송의 이점  
 이 단원에서는 3개의 주요 전송 중에서 하나를 선택하는 데 대한 주된 이유를 자세한 의사 결정 차트와 함께 설명합니다.  
  
### <a name="when-to-use-http-transport"></a>HTTP 전송을 사용해야 하는 경우  
 HTTP는 클라이언트와 서버 사이의 요청/응답 프로토콜입니다. 가장 일반적인 응용 프로그램은 웹 서버와 통신하는 웹 브라우저 클라이언트로 구성됩니다. 클라이언트에서 서버로 요청을 보내면 서버에서 클라이언트 요청 메시지를 수신 대기합니다. 서버에서 요청을 받으면 요청 상태가 포함된 응답을 반환합니다. 성공적인 경우 웹 페이지, 오류 메시지 또는 기타 정보와 같은 선택적인 데이터가 반환됩니다. HTTP 프로토콜에 대 한 자세한 내용은 참조 [HTTP-Hypertext Transfer Protocol](http://go.microsoft.com/fwlink/?LinkId=94858)합니다.  
  
 HTTP 프로토콜은 연결 기반이 아닙니다. 응답을 보내고 나면 상태가 유지되지 않습니다. 여러 페이지로 된 트랜잭션을 처리하려면 응용 프로그램에서 모든 필요한 상태를 유지해야 합니다.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 HTTP 전송 바인딩은 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]가 아닌 레거시 시스템과의 상호 운용성을 위해 최적화됩니다. 통신에 참여하는 모든 당사자가 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]를 사용하는 경우에는 TCP 기반 또는 명명된 파이프 기반 바인딩이 가장 빠릅니다. 자세한 내용은 <xref:System.ServiceModel.NetTcpBinding> 및 <xref:System.ServiceModel.NetNamedPipeBinding>를 참조하세요.  
  
### <a name="when-to-use-the-tcp-transport"></a>TCP 전송을 사용해야 하는 경우  
 TCP는 스트리밍 지향의 연결 기반 서비스로, 종단 간 오류 검색과 수정 기능이 있습니다. *연결 기반* 데이터를 교환 하기 전에 호스트 사이의 통신 세션이 설정 되었음을 의미 합니다. 호스트는 TCP/IP 네트워크에서 논리 IP 주소로 식별되는 모든 장치입니다.  
  
 TCP를 사용하면 데이터 배달이 안정적이고 사용이 쉽습니다. 특히 TCP에서는 발신자에게 패킷 배달에 대해 알리고, 패킷이 보낸 순서와 같은 순서로 배달되도록 보장하며, 손실된 패킷을 다시 전송하고, 데이터 패킷이 중복되지 않았는지 확인합니다. 이 안정적인 배달은 2 개의 TCP/IP 노드 사이 적용 되며와 같은 작업 않습니다 *WS-RELIABLE Messaging*, 끝점 간에 적용 되는, 중간 노드 수에 관계 없이 포함 될 수 있습니다.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] TCP 전송은 통신의 양 끝에서 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]를 사용하는 시나리오를 위해 최적화되어 있습니다. 이 바인딩은 서로 다른 시스템 사이의 통신과 관련된 시나리오에서 가장 빠른 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 바인딩입니다. 메시지 교환에서는 최적화된 메시지 전송을 위해 <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>를 사용합니다. TCP는 이중 통신을 제공하기 때문에 클라이언트가 NAT(Network Address Translation) 뒤에 있더라도 이중 계약을 구현하는 데 사용할 수 있습니다.  
  
### <a name="when-to-use-the-named-pipe-transport"></a>명명된 파이프 전송을 사용해야 하는 경우  
 명명된 파이프는 프로세스에서 통신에 사용할 수 있는 공유 메모리 섹션과 같이 Windows 운영 체제 커널에 있는 개체입니다. 명명된 파이프는 이름이 있으며 한 시스템에서 프로세스 사이의 단방향 또는 이중 통신에 사용할 수 있습니다.  
  
 단일 컴퓨터에 있는 서로 다른 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 응용 프로그램 사이에서 통신이 필요한 경우 다른 시스템으로부터의 통신을 방지하려면 명명된 파이프 전송을 사용합니다. 추가 제한으로는 따로 권한을 부여하지 않은 한 Windows 원격 데스크톱에서 실행하는 프로세스가 같은 Windows 원격 데스크톱으로 제한될 수 있다는 것이 있습니다.  
  
> [!WARNING]
>  명명된 된 파이프 전송을 IIS에서 호스팅된 여러 사이트에서 약한 와일드 카드 URL 예약을 사용할 경우 다음과 같은 오류가 발생할 수 있습니다: '2', 사이트에 대 한 수신 대기 하는 동안 프로토콜 'net.pipe'의 ' NetPipeActivator'의 Activation Service에서 오류가 발생 했습니다 따라서 프로토콜을 임시로 사용할 수는 사이트에 대 한 합니다. 자세한 내용은 예외 메시지를 참조 하십시오. URL: weakwildcard: Net.pipe\<컴퓨터 이름 > / 상태: ConflictingRegistration 예외: 프로세스 이름: SMSvcHost 프로세스 ID: 1076 \  
  
## <a name="decision-points-for-choosing-a-transport"></a>전송을 선택할 때의 의사 결정 요점  
 다음 표에서는 전송을 선택할 때 흔히 사용되는 의사 결정 요점에 대해 설명합니다. 응용 프로그램에 적용되는 추가 특성과 전송을 모두 고려해야 합니다. 응용 프로그램에서 중요한 특성을 확인하고 각 특성과 잘 연결되는 전송을 확인한 다음 특성 집합에 가장 적합한 전송을 선택해야 합니다.  
  
|특성|설명|선호 전송|  
|---------------|-----------------|------------------------|  
|진단|진단을 사용하면 전송 연결 문제를 자동으로 검색할 수 있습니다. 모든 전송에서는 연결을 설명하는 오류 정보를 돌려보내는 기능을 지원합니다. 하지만 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에는 네트워크 문제를 조사하기 위한 진단 도구가 포함되어 있지 않습니다.|없음|  
|호스팅|모든 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 끝점은 응용 프로그램 내에 호스팅되어야 합니다. [!INCLUDE[iis601](../../../../includes/iis601-md.md)] 이하는 HTTP 전송을 사용하는 응용 프로그램의 호스팅만 지원합니다. [!INCLUDE[wv](../../../../includes/wv-md.md)]에서는 TCP 및 명명된 파이프를 비롯한 모든 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 전송에 대한 지원이 추가되었습니다. 자세한 내용은 참조 [인터넷 정보 서비스에서의 호스팅](../../../../docs/framework/wcf/feature-details/hosting-in-internet-information-services.md) 및 [Windows Process Activation Service에서의 호스팅](../../../../docs/framework/wcf/feature-details/hosting-in-windows-process-activation-service.md)합니다.|HTTP|  
|검사|검사는 전송 중에 메시지에서 정보를 추출하고 처리하는 기능입니다. HTTP 프로토콜에서는 메시지를 검사 및 분석하는 도구를 더 쉽게 작성할 수 있도록 데이터에서 라우팅 및 제어 정보를 분리합니다. 검사하기 쉬운 전송에는 네트워크 제품의 처리 능력도 덜 필요합니다. 사용되는 보안 수준에 따라 메시지의 검사 가능 여부가 결정됩니다.|HTTP|  
|대기 시간|대기 시간은 메시지 교환을 완료하는 데 필요한 최소 시간입니다. 모든 네트워크 작업에는 선택한 전송에 따라 어느 정도의 대기 시간이 필요합니다. HTTP와 같이 네이티브 메시지 교환 패턴이 요청 응답인 이중 또는 단방향 통신을 사용하면 메시지에 적용되는 상관 관계 때문에 대기 시간이 추가될 수도 있습니다. 이런 경우에는 TCP와 같이 네이티브 메시지 교환 패턴이 이중인 전송을 사용할 수 있습니다.|TCP, 명명된<br /><br /> 파이프|  
|도달 범위|전송의 도달 범위는 전송에서 다른 시스템과 연결하는 능력을 나타냅니다. 명명된 파이프 전송은 도달 범위가 짧으며, 같은 시스템에서 실행되는 서비스에만 연결할 수 있습니다. TCP 및 HTTP 전송은 모두 도달 범위가 크며 일부 NAT 및 방화벽 구성도 통과할 수 있습니다. 자세한 내용은 참조 [Nat 및 방화벽 작업](../../../../docs/framework/wcf/feature-details/working-with-nats-and-firewalls.md)합니다.|HTTP, TCP|  
|보안|보안은 전송 중에 기밀성, 무결성 또는 인증을 제공하여 메시지를 보호하는 기능입니다. 기밀성은 메시지를 검토로부터 보호하고, 무결성은 메시지를 수정으로부터 보호하고, 인증은 메시지의 발신자 또는 수신자에게 보증을 제공합니다.<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 메시지 수준과 전송 수준 모드 둘 다에서 전송 보안을 지원합니다. 전송에서 버퍼링된 전송 모드를 지원하는 경우 메시지 보안은 전송과 함께 사용할 수 있습니다. 전송 보안에 대한 지원은 선택한 전송에 따라 달라집니다. HTTP, TCP 및 명명된 파이프 전송의 전송 보안 지원에는 적정 수준의 패리티가 사용됩니다.|모두|  
|처리량|처리량은 지정된 기간 내에 전송 및 처리할 수 있는 데이터의 양을 나타냅니다. 대기 시간과 마찬가지로 선택한 전송에 따라 서비스 작업의 처리량이 달라질 수 있습니다. 전송의 처리량을 최대화하려면 전송 콘텐츠의 오버헤드를 최소화하고 메시지 교환이 완료될 때까지 기다리는 시간을 최소화해야 합니다. TCP 및 명명된 파이프 전송 모두에서 메시지 본문에 약간의 오버헤드를 추가하며 메시지 응답의 대기 시간을 줄여 주는 네이티브 이중 셰이프를 지원합니다.|TCP, 명명된 파이프|  
|도구|도구는 개발, 진단, 호스팅 및 기타 작업의 프로토콜에 대한 타사 응용 프로그램 지원을 나타냅니다. HTTP 프로토콜에 사용되는 도구 및 소프트웨어를 개발하는 일에는 특히 큰 투자가 필요합니다.|HTTP|  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.BasicHttpBinding>  
 <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`>  
  <<!--zz <xref:System.ServiceModel.WsDualHttpBinding> --> `System.ServiceModel.WsDualHttpBinding`
 <<!--zz <xref:System.ServiceModel.WsFederationHttpBinding>  --> `System.ServiceModel.WsFederationHttpBinding` <xref:System.ServiceModel.Channels.HttpTransportBindingElement>  
 <xref:System.ServiceModel.NetTcpBinding>  
 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>  
 <xref:System.ServiceModel.NetNamedPipeBinding>  
 <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>  
 [바인딩](../../../../docs/framework/wcf/feature-details/bindings.md)  
 [시스템 제공 바인딩](../../../../docs/framework/wcf/system-provided-bindings.md)  
 [사용자 정의 바인딩 만들기](../../../../docs/framework/wcf/extending/creating-user-defined-bindings.md)
