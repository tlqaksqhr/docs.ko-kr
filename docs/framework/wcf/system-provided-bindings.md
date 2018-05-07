---
title: 시스템 제공 바인딩
ms.date: 03/30/2017
helpviewer_keywords:
- bindings [WCF], system-provided
ms.assetid: 2c243746-45ce-4588-995e-c17126a579a6
ms.openlocfilehash: 12382b0886970bc48345107008ee449d9653ec4f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="system-provided-bindings"></a>시스템 제공 바인딩
바인딩은 끝점과 통신할 때 사용할 통신 메커니즘을 지정하고 끝점에 연결하는 방법을 나타냅니다. 바인딩에 다음과 같은 요소가 포함됩니다.  
  
-   프로토콜 스택은 끝점에 보내는 메시지에 사용할 보안, 안정성 및 컨텍스트 흐름 설정을 결정합니다.  
  
-   전송은 끝점에 메시지를 보낼 때 사용할 TCP 또는 HTTP와 같은 기본 전송 프로토콜을 결정합니다.  
  
-   인코딩은 끝점에 보내는 메시지에 사용할 텍스트/XML, 이진 또는 MTOM(Message Transmission Optimization Mechanism) 등의 연결 인코딩을 결정합니다.  
  
 이 항목의 모든 Windows Communication Foundation (WCF) 시스템 제공 바인딩을 제공합니다. 이 중 하나라도 응용 프로그램의 정확한 조건을 충족하지 않을 경우 사용자 지정 바인딩을 만들 수 있습니다. 사용자 지정 바인딩 만들기에 대 한 자세한 내용은 참조 [사용자 지정 바인딩을](../../../docs/framework/wcf/extending/custom-bindings.md)합니다.  
  
 WS-Federation 프로토콜을 지원하는 안전하며 상호 운용 가능한 바인딩을 사용하면 페더레이션에 있는 조직이 사용자를 효율적으로 인증하고 권한을 부여할 수 있습니다.  
  
> [!IMPORTANT]
>  항상 보안을 포함하는 바인딩을 선택합니다. 기본적으로 제외한 모든 바인딩은 [ \<basicHttpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) 요소는 보안이 설정 되어 있습니다. 보안 바인딩을 선택하지 않거나 보안을 비활성화하는 경우 보안 데이터 센터 또는 격리된 네트워크에 저장하는 것과 같은 방식으로 데이터를 보호해야 합니다.  
  
> [!IMPORTANT]
>  다른 방법으로 데이터의 보안을 유지하지 않는 한 보안을 지원하지 않거나 보안이 설정되지 않은 바인딩과 함께 이중 계약을 사용하지 마십시오.  
  
## <a name="system-provided-bindings"></a>시스템 제공 바인딩  
 다음 바인딩은 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]와 함께 제공됩니다.  
  
|바인딩|구성 요소|설명|  
|-------------|---------------------------|-----------------|  
|<xref:System.ServiceModel.BasicHttpBinding>|[\<basicHttpBinding>](../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)|WS-Basic Profile 사양의 웹 서비스와 통신하는 데 적합한 바인딩에는 ASP.NET 웹 서비스(ASMX) 기반 서비스 등이 있습니다. 이 바인딩은 HTTP를 전송으로 사용하고 텍스트/XML을 기본 메시지 인코딩으로 사용합니다.|  
|<xref:System.ServiceModel.WSHttpBinding>|[\<wsHttpBinding>](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)|비이중 서비스 계약에 적합한 안전하고 상호 운용할 수 있는 바인딩입니다.|  
|<xref:System.ServiceModel.WSDualHttpBinding>|[\<wsDualHttpBinding>](../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md)|이중 서비스 계약 또는 SOAP 매개자를 통한 통신에 적합한 안전하고 상호 운용할 수 있는 바인딩입니다.|  
|<xref:System.ServiceModel.WSFederationHttpBinding>|[\<wsFederationHttpBinding>](../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)|WS-Federation 프로토콜을 지원하는 안전하며 상호 운용 가능한 바인딩을 사용하면 페더레이션에 있는 조직이 사용자를 효율적으로 인증하고 권한을 부여할 수 있습니다.|  
|<xref:System.ServiceModel.NetHttpBinding>|\<netHttpBinding>|기본적으로 이진 인코딩을 사용하는 HTTP 또는 WebSocket 서비스를 사용하도록 디자인된 바인딩입니다.|  
|<xref:System.ServiceModel.NetHttpsBinding>|\<nethttpsbinding은 >|HTTP 또는 WebSocket 서비스를 사용하기 디자인된 보안 바인딩이며 기본적으로 이진 인코딩을 사용합니다.|  
|<xref:System.ServiceModel.NetTcpBinding>|[\<netTcpBinding>](../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)|[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 응용 프로그램 간 시스템 통신에 적합한 안전하고 최적화된 바인딩입니다.|  
|<xref:System.ServiceModel.NetNamedPipeBinding>|[\<netNamedPipeBinding >](../../../docs/framework/configure-apps/file-schema/wcf/netnamedpipebinding.md)|[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 응용 프로그램 간 시스템 통신에 적합한, 안전하고 신뢰할 수 있으며 최적화된 바인딩입니다.|  
|<xref:System.ServiceModel.NetMsmqBinding>|[\<netMsmqBinding >](../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md)|[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 응용 프로그램 간 시스템 통신에 적합한 대기 중인 바인딩입니다.|  
|<xref:System.ServiceModel.NetPeerTcpBinding>|[\<netPeerTcpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md)|안전하게 여러 시스템 간에 통신할 수 있는 바인딩입니다.|  
|<xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>|[\<msmqIntegrationBinding>](../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md)|[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 응용 프로그램과 기존 메시지 큐 응용 프로그램 간 시스템 통신에 적합한 바인딩입니다.|  
|<xref:System.ServiceModel.BasicHttpContextBinding>|[\<basicHttpContextBinding >](../../../docs/framework/configure-apps/file-schema/wcf/basichttpcontextbinding.md)|HTTP 쿠키를 사용하여 컨텍스트를 교환할 수 있는 WS-Basic Profile 사양의 웹 서비스와 통신하는 데 적합한 바인딩입니다.|  
|<xref:System.ServiceModel.NetTcpContextBinding>|[\<netTcpContextBinding >](../../../docs/framework/configure-apps/file-schema/wcf/nettcpcontextbinding.md)|SOAP 헤더를 사용하여 컨텍스트를 교환할 수 있는 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 응용 프로그램 간 시스템 통신에 적합한 안전하고 최적화된 바인딩입니다.|  
|<xref:System.ServiceModel.WebHttpBinding>|[\<webHttpBinding>](../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)|SOAP 메시지 대신 HTTP 요청을 통해 노출되는 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 웹 서비스에 대한 끝점을 구성하는 데 사용되는 바인딩입니다.|  
|<xref:System.ServiceModel.WSHttpContextBinding>|[\<wsHttpContextBinding >](../../../docs/framework/configure-apps/file-schema/wcf/wshttpcontextbinding.md)|보안 및 |<xref:System.ServiceModel.UdpBinding>|\<udpBinding>|다수의 클라이언트에 다수의 간단한 메시지를 보낼 때 사용하는 바인딩입니다.|  
  
 다음 표에서는 각 시스템 제공 바인딩의 기능을 보여 줍니다. 바인딩은 표 열에 있고, 기능은 행에 나열되며 두 번째 표에 설명되어 있습니다. 다음 표에는 사용된 바인딩 약어에 대한 키가 나와 있습니다. 바인딩을 선택하려면 필요한 행 기능을 모두 만족하는 열을 결정합니다.  
  
|바인딩|상호 운용성|보안(기본값)|세션<br /><br /> (기본값)|트랜잭션|이중|인코딩(기본값)|스트리밍<br /><br /> (기본값)|  
|-------------|----------------------|--------------------------|-----------------------------|------------------|------------|--------------------------|-------------------------------|  
|<xref:System.ServiceModel.BasicHttpBinding>|Basic Profile 1.1|(None), Transport, Message, Mixed|(None)|(None)|N/A|Text, (MTOM)|예<br /><br /> (buffered)|  
|<xref:System.ServiceModel.WSHttpBinding>|WS|Transport, (Message), Mixed|(None), Reliable Session, Security Session|(None), 예|N/A|(Text), MTOM|아니요|  
|<xref:System.ServiceModel.WSDualHttpBinding>|WS|(Message), None|(Reliable Session), Security Session|(None), 예|예|(Text), MTOM|아니요|  
|<xref:System.ServiceModel.WSFederationHttpBinding>|WS-Federation|(Message), Mixed, None|(None), Reliable Session, Security Session|(None), 예|아니요|(Text), MTOM|아니요|  
|<xref:System.ServiceModel.NetHttpBinding>|.NET|(None), Transport, Message, TransportWithMessageCredential, TransportCredentialOnly|다음의 참고를 참조하십시오.|없음|다음의 참고를 참조하십시오.|(이진), 텍스트, MTOM|예(버퍼링됨)|  
|<xref:System.ServiceModel.NetHttpsBinding>|.NET|(전송), TransportWithMessageCredential|다음의 참고를 참조하십시오.|없음|다음의 참고를 참조하십시오.|(이진), 텍스트, MTOM|예(버퍼링됨)|  
|<xref:System.ServiceModel.NetTcpBinding>|.NET|(Transport), Message, None, Mixed|(Transport), Reliable Session, Security Session|(None), 예|예|이항|예<br /><br /> (buffered)|  
|<xref:System.ServiceModel.NetNamedPipeBinding>|.NET|(Transport), None|None, (Transport)|(None), 예|예|이항|예<br /><br /> (buffered)|  
|<xref:System.ServiceModel.NetMsmqBinding>|.NET|Message, (Transport), None|(None), Transport|None, (예)|아니요|이항|아니요|  
|<xref:System.ServiceModel.NetPeerTcpBinding>|Peer|(Transport)|(None)|(None)|예||아니요|  
|<xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>|MSMQ|(Transport)|(None)|None, (예)|N/A|N/A|아니요|  
|<xref:System.ServiceModel.BasicHttpContextBinding>|Basic Profile 1.1|(None), Transport, Message, Mixed|(None)|(None)|N/A|Text, (MTOM)|예<br /><br /> (buffered)|  
|<xref:System.ServiceModel.NetTcpContextBinding>|.NET|(Transport), Message, None, Mixed|(Transport), Reliable Session, Security Session|(None), 예|예|이항|예<br /><br /> (buffered)|  
|<xref:System.ServiceModel.WSHttpContextBinding>|WS|Transport, (Message), Mixed|(None), Reliable Session, Security Session|(None), 예|N/A|Text, (MTOM)|아니요|  
|<xref:System.ServiceModel.UdpBinding>|.NET **참고:** 이 바인딩 구현 표준 SOAP-over-UDP 사양을 구현 하 여 상호 운용성을 구현할 수 있습니다.|(None)|(None)|(None)|N/A|(Text)|아니요|  
  
> [!IMPORTANT]
>  <xref:System.ServiceModel.NetHttpBinding>은 HTTP 또는 WebSocket 서비스를 사용하도록 디자인된 바인딩이며 기본적으로 이진 인코딩을 사용합니다. <xref:System.ServiceModel.NetHttpBinding>은 해당 바인딩이 HTTP 요청-회신 계약에 사용되는지 이중 계약에 사용되는지를 검색하고 그에 맞게 동작을 변경합니다. 요청-회신에는 HTTP가 사용되고 이중 계약에는 WebSocket이 사용됩니다. 사용 하 여이 동작을 재정의할 수 있습니다는 <!--zz <xref:System.ServiceModel.NetHttpBinding.WebSocketTransportUsage%2A>--> `System.ServiceModel.NetHttpBinding.WebSocketTransportUsage` 바인딩 설정을: 허용-기본값 이므로 위에서 설명한 것 처럼 동작 합니다. NotAllowed-을 사용 하는 Websocket이 차단 합니다. 이 설정을 사용 하 여 이중 계약을 사용 하려고 하면 예외가 발생 합니다. 필수-이 설정은 Websocket 요청-회신 계약에도 사용할 수 있습니다. NetHttpBinding은 HTTP 모드 및 WebSocket 모드에서 신뢰할 수 있는 세션을 지원합니다. WebSocket 모드에서는 세션이 전송에 의해 제공됩니다.  
  
 다음 표에서는 앞의 표에 나열되어 있는 기능에 대해 설명합니다.  
  
|기능|설명|  
|-------------|-----------------|  
|상호 운용성 형식|바인딩이 상호 운용하는 프로토콜 또는 기술에 이름을 지정합니다.|  
|보안|채널 보안 방식을 지정합니다.<br /><br /> -None: SOAP 메시지 보안이 설정 되지 않은 및 클라이언트가 인증 되지 않습니다.<br />-Transport: 전송 계층에서 보안 요구 사항은 충족 합니다.<br />-Message: 메시지 계층에서 보안 요구 사항은 충족 합니다.<br />-Mixed: 클레임이 메시지에 포함 됩니다. 전송 계층에서 무결성 및 기밀성 요구 사항은 충족 합니다.|  
|세션|이 바인딩이 세션 계약을 지원할지 여부를 지정합니다.|  
|트랜잭션|트랜잭션이 활성화되었는지 여부를 지정합니다.|  
|이중|이중 계약이 지원되는지 여부를 지정합니다. 이 기능을 사용하려면 바인딩의 세션을 지원해야 합니다.|  
|인코딩|메시지의 통신 형식을 지정합니다. 허용 가능한 값은 다음과 같습니다.<br /><br /> -Text: 예를 들어 u t F-8입니다.<br />-이진<br />-메시지 전송 최적화 메커니즘 (MTOM): SOAP 봉투의 컨텍스트 내에서 이진 XML 요소를 효율적으로 인코딩하는 것에 대 한 방법입니다.|  
|스트리밍|스트리밍이 들어오는 메시지와 보내는 메시지를 지원하는지 여부를 지정합니다. 바인딩의 `TransferMode` 속성을 사용하여 값을 설정합니다. 허용 가능한 값은 다음과 같습니다.<br /><br /> -   <xref:System.ServiceModel.TransferMode.Buffered>: 요청 및 응답 메시지가 모두 버퍼링 됩니다.<br />-   <xref:System.ServiceModel.TransferMode.Streamed>: 요청 및 응답 메시지가 모두 스트리밍됩니다.<br />-   <xref:System.ServiceModel.TransferMode.StreamedRequest>: 요청 메시지는 스트리밍되고 응답 메시지는 버퍼링 됩니다.<br />-   <xref:System.ServiceModel.TransferMode.StreamedResponse>: 요청 메시지는 버퍼링 하 고 응답 메시지는 스트리밍됩니다.|  
  
## <a name="see-also"></a>참고 항목  
 [끝점 만들기 개요](../../../docs/framework/wcf/endpoint-creation-overview.md)  
 [바인딩을 사용하여 서비스 및 클라이언트 구성](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [기본 WCF 프로그래밍](../../../docs/framework/wcf/basic-wcf-programming.md)
