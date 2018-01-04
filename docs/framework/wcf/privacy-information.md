---
title: "Windows Communication Foundation 개인 정보 취급 방침"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Communication Foundation, privacy information
- WCF, privacy information
- privacy information [WCF]
ms.assetid: c9553724-f3e7-45cb-9ea5-450a22d309d9
caps.latest.revision: "34"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f66f773551f45f9e4c5978ef09bbe4061a3326bd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="windows-communication-foundation-privacy-information"></a>Windows Communication Foundation 개인 정보 취급 방침
Microsoft는 최종 사용자의 개인 정보 보호를 위해 최선을 다할 것을 약속합니다. [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 버전 3.0을 사용하여 응용 프로그램을 빌드하는 경우 응용 프로그램이 최종 사용자의 개인 정보 보호에 영향을 줄 수 있습니다. 예를 들어 응용 프로그램에서 사용자 연락처 정보를 명시적으로 수집하거나, 정보를 요청하거나 인터넷을 통해 정보를 웹 사이트로 보낼 수 있습니다. 응용 프로그램에 Microsoft 기술을 포함하는 경우 해당 기술의 동작이 개인 정보 보호에 영향을 줄 수 있습니다. [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]는 사용자 또는 최종 사용자가 정보 전송을 선택하지 않는 한 아무 정보도 Microsoft로 보내지 않습니다.  
  
## <a name="wcf-in-brief"></a>WCF에 대한 간략한 설명  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]는 Microsoft .NET Framework를 사용한 분산 메시징 프레임워크로, 개발자가 분산 응용 프로그램을 빌드할 수 있도록 합니다. 두 응용 프로그램 간에 전달된 메시지에는 헤더 및 본문 정보가 들어 있습니다.  
  
 응용 프로그램에서 사용하는 서비스에 따라 헤더에는 메시지 라우팅, 보안 정보, 트랜잭션 등이 포함될 수 있습니다. 기본적으로 메시지는 암호화됩니다. 단, 비보안 레거시 웹 서비스에 사용하도록 디자인된 `BasicHttpBinding`을 사용하는 경우는 예외입니다. 최종 디자인의 책임은 응용 프로그램 디자이너에게 있습니다. SOAP 본문의 메시지에는 응용 프로그램별 데이터가 들어 있습니다. 그러나 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 암호화 또는 기밀성 기능을 사용하여 응용 프로그램에서 정의된 개인 정보 같은 이 데이터의 보안을 유지할 수 있습니다. 다음 단원에서는 개인 정보 보호에 영향을 주는 기능에 대해 설명합니다.  
  
## <a name="messaging"></a>메시징  
 각 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 메시지에는 메시지 대상과 회신이 전송되는 위치를 지정하는 주소 헤더가 있습니다.  
  
 끝점 주소의 주소 구성 요소는 끝점을 식별하는 URI(Uniform Resource Identifier)입니다. 주소는 네트워크 주소나 논리 주소일 수 있습니다. 주소에는 컴퓨터 이름(호스트 이름, 정규화된 도메인 이름) 및 IP 주소가 포함될 수 있습니다. 끝점 주소에는 각 주소를 구분하는 데 사용되는 임시 주소 지정을 위한 GUID(고유한 전역 식별자) 또는 GUID 컬렉션이 포함될 수도 있습니다. 각 메시지에는 GUID인 메시지 ID가 포함되어 있습니다. 이 기능은 WS-Addressing 참조 표준을 준수합니다.  
  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 메시징 계층에서는 개인 정보를 로컬 컴퓨터에 쓰지 않습니다. 그러나 끝점 이름에 개인 이름을 사용하거나 끝점의 웹 서비스 기술 언어에 개인 정보를 포함하지만 클라이언트에 https를 사용하여 WSDL에 액세스하도록 요구하지 않는 경우 등 서비스 개발자가 이러한 정보를 노출하는 서비스를 만든 경우 네트워크 수준에서 개인 정보를 전파할 수도 있습니다. 또한 개발자가 실행 되는 경우는 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 개인 정보를 해당 출력을 노출 하는 끝점에 대해 도구 해당 정보를 포함 하 고 출력 파일에 기록 됩니다는 로컬 하드 디스크입니다.  
  
## <a name="hosting"></a>호스팅  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]의 호스팅 기능을 사용하면 응용 프로그램이 필요할 때 시작될 수 있거나 여러 응용 프로그램 간에 포트 공유를 사용할 수 있습니다. [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]과 유사하게 [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] 응용 프로그램을 IIS(인터넷 정보 서비스)에서 호스트할 수 있습니다.  
  
 호스팅은 네트워크에 특정 정보를 노출하지 않으며 컴퓨터에 데이터를 보관하지 않습니다.  
  
## <a name="message-security"></a>메시지 보안  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 보안은 메시징 응용 프로그램에 보안 기능을 제공합니다. 제공된 보안 기능에는 인증과 권한 부여가 포함됩니다.  
  
 인증은 클라이언트와 서비스 간에 자격 증명을 전달하여 수행됩니다. 다음과 같이 전송 수준 보안이나 SOAP 메시지 수준 보안을 통해 인증을 수행할 수 있습니다.  
  
-   SOAP 메시지 보안에서는 사용자 이름/암호, X.509 인증서, Kerberos 티켓 및 SAML 토큰 같은 자격 증명을 통해 인증이 수행됩니다. 이러한 모든 자격 증명에는 발급자에 따라 개인 정보가 포함될 수 있습니다.  
  
-   전송 보안을 사용하는 경우 HTTP 인증 체계(기본, 다이제스트, 협상, Negotiate, Windows 통합 인증, NTLM, 없음 및 익명) 같은 일반적인 전송 인증 메커니즘과 폼 인증을 통해 인증이 수행됩니다.  
  
 인증을 통해 통신하는 끝점 간에 보안 세션이 설정될 수 있습니다. 세션은 보안 세션의 수명 동안 지속되는 GUID로 식별됩니다. 다음 표에서는 보관되는 데이터와 위치를 보여 줍니다.  
  
|데이터|저장소|  
|----------|-------------|  
|사용자 이름, X.509 인증서, Kerberos 토큰, 자격 증명에 대한 참조 등의 프레젠테이션 자격 증명|Windows 인증서 저장소 등의 표준 Windows 자격 증명 관리 메커니즘|  
|사용자 이름, 암호 등의 사용자 멤버 자격 정보|[!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] 멤버 자격 공급자|  
|서비스를 클라이언트에 인증하는 데 사용되는 서비스에 대한 ID 정보|서비스의 끝점 주소|  
|호출자 정보|감사 로그|  
  
## <a name="auditing"></a>감사  
 감사는 인증 및 권한 부여 이벤트의 성공과 실패를 기록합니다. 감사 레코드에는 서비스 URI, 작업 URI, 호출자 ID 등의 데이터가 들어 있습니다.  
  
 또한 감사는 메시지 로깅에서 응용 프로그램별 데이터를 헤더와 본문에 기록할 수 있으므로 관리자가 설정 또는 해제하여 메시지 로깅의 구성을 수정하는 시기를 기록합니다. [!INCLUDE[wxp](../../../includes/wxp-md.md)]의 경우 응용 프로그램 이벤트 로그에 레코드가 기록됩니다. [!INCLUDE[wv](../../../includes/wv-md.md)] 및 [!INCLUDE[ws2003](../../../includes/ws2003-md.md)]의 경우 보안 이벤트 로그에 레코드가 기록됩니다.  
  
## <a name="transactions"></a>트랜잭션  
 트랜잭션 기능은 트랜잭션 서비스를 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 응용 프로그램에 제공합니다.  
  
 트랜잭션 전파에 사용된 트랜잭션 헤더에는 GUID인 트랜잭션 ID 또는 인리스트먼트 ID가 포함될 수도 있습니다.  
  
 트랜잭션 기능은 MSDTC(Microsoft Distributed Transaction Coordinator) 트랜잭션 관리자(Windows 구성 요소)를 사용하여 트랜잭션 상태를 관리합니다. 트랜잭션 관리자 간의 통신은 기본적으로 암호화됩니다. 트랜잭션 관리자는 끝점 참조, 트랜잭션 ID 및 인리스트먼트 ID를 지속적 상태의 일부로 기록할 수 있습니다. 이 상태의 수명은 트랜잭션 관리자의 로그 파일 수명에 의해 결정됩니다. MSDTC 서비스는 이 로그를 소유하고 유지 관리합니다.  
  
 트랜잭션 기능은 WS-Coordination 및 WS-Atomic Transaction 표준을 구현합니다.  
  
## <a name="reliable-sessions"></a>신뢰할 수 있는 세션  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]의 신뢰할 수 있는 세션은 전송 또는 중간 오류가 발생할 때 메시지를 전송합니다. 내부 전송에서 연결이 끊어지거나(예: 무선 네트워크의 TCP 연결) 메시지가 손실되는 경우(HTTP 프록시에서 보내는 메시지 또는 들어오는 메시지 삭제)에도 정확히 한 번만 메시지를 전송합니다. 또한 신뢰할 수 있는 세션은 다중 경로 라우팅의 경우와 같이 메시지가 전송된 순서를 유지하여 메시지 다시 정렬을 복구합니다.  
  
 신뢰할 수 있는 세션은 WS-RM(WS-ReliableMessaging) 프로토콜을 사용하여 구현됩니다. 신뢰할 수 있는 특정 세션과 연결된 모든 메시지 식별에 사용되는 세션 정보가 들어 있는 WS-RM 헤더를 추가합니다. 각 WS-RM 세션에는 GUID인 식별자가 있습니다.  
  
 최종 사용자의 컴퓨터에는 개인 정보가 보관되지 않습니다.  
  
## <a name="queued-channels"></a>대기 중인 채널  
 큐는 수신 응용 프로그램을 대신하여 송신 응용 프로그램의 메시지를 저장하고 나중에 이 메시지를 수신 응용 프로그램에 전달합니다. 예를 들어 큐는 수신 응용 프로그램이 임시일 때 송신 응용 프로그램에서 수신 응용 프로그램으로 메시지가 전송되게 합니다. [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]는 MSMQ(Microsoft Message Queuing)를 전송으로 사용하여 큐에 대한 지원을 제공합니다.  
  
 대기 중인 채널 기능은 메시지에 헤더를 추가하지 않습니다. 대신 적절한 메시지 큐 메시지 속성이 설정된 메시지 큐 메시지를 만들고 메시지 큐 메서드를 호출하여 메시지를 메시지 큐의 큐에 보관합니다. 메시지 큐는 Windows에 포함된 선택적 구성 요소입니다.  
  
 대기 중인 채널 기능은 메시지 큐를 큐 인프라로 사용하므로 최종 사용자의 컴퓨터에 정보를 보관하지 않습니다.  
  
## <a name="com-integration"></a>COM+ 통합  
 이 기능은 기존의 COM 및 COM+ 기능을 포함하여 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스와 호환되는 서비스를 만듭니다. 이 기능은 특정 헤더를 사용하지 않으며 최종 사용자의 컴퓨터에 데이터를 보관하지 않습니다.  
  
## <a name="com-service-moniker"></a>COM 서비스 모니커  
 표준 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 클라이언트에 관리되지 않는 래퍼를 제공합니다. 이 기능은 통신 중에 특정 헤더를 사용하지 않으며 최종 사용자의 컴퓨터에 데이터를 보관하지도 않습니다.  
  
## <a name="peer-channel"></a>피어 채널  
 피어 채널은 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]를 사용한 다중 상대방 응용 프로그램의 개발을 가능하게 합니다. 다중 상대방 메시징은 메시 컨텍스트에서 발생합니다. 노드가 참여할 수 있는 메시는 이름으로 식별됩니다. 피어 채널의 각 노드는 사용자 지정 포트에 TCP 수신기를 만들고 메시의 다른 노드와 연결을 설정하여 복원력을 보장합니다. 메시의 다른 노드에 연결하기 위해 노드는 수신기 주소와 컴퓨터의 IP 주소를 비롯한 일부 데이터도 메시의 다른 노드와 교환합니다. 메시에서 전송되는 메시지에는 메시지 스푸핑과 변조를 방지하기 위해 보낸 사람과 관련된 보안 정보가 들어 있을 수 있습니다.  
  
 최종 사용자의 컴퓨터에는 개인 정보가 저장되지 않습니다.  
  
## <a name="it-professional-experience"></a>IT 전문가 경험  
  
### <a name="tracing"></a>추적  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 인프라의 진단 기능은 전송 및 서비스 모델 계층을 통과하는 메시지 및 이러한 메시지와 연결된 동작 및 이벤트를 기록합니다. 이 기능은 기본적으로 해제되어 있습니다. 응용 프로그램의 구성 파일을 사용하여 기능을 활성화하며 런타임에 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] WMI 공급자를 사용하여 추적 동작을 수정할 수 있습니다. 활성화되면 추적 인프라는 메시지, 동작 및 처리 이벤트가 포함된 진단 추적을 구성된 수신기로 내보냅니다. 출력 형식과 위치는 관리자가 선택한 수신기 구성에 의해 결정되지만 일반적으로 XML 형식 파일입니다. 관리자는 추적 파일에 대해 ACL(액세스 제어 목록)을 설정하는 작업을 담당합니다. 특히 WAS(Windows Activation System)에서 호스트할 때 관리자는 원하지 않을 경우 공용 가상 루트 디렉터리에서 파일이 제공되지 않도록 해야 합니다.  
  
 메시지 로깅과 서비스 모델 진단 추적의 두 가지 추적 형식이 있으며, 이에 대해서는 다음 단원에서 설명합니다. 각 형식은 해당 추적 소스인 <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A> 및 <xref:System.ServiceModel>을 통해 구성됩니다. 이러한 로깅 추적 소스는 모두 응용 프로그램의 로컬 데이터를 캡처합니다.  
  
### <a name="message-logging"></a>메시지 로깅  
 메시지 로깅 추적 소스(<xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>)를 사용하면 관리자가 시스템을 통과하는 메시지를 기록할 수 있습니다. 구성을 통해 사용자는 전체 메시지 또는 메시지 헤더만 기록할지, 전송 및/또는 서비스 모델 계층에 기록할지 여부 및 잘못된 형식의 메시지를 포함할지 여부를 결정할 수 있습니다. 또한 사용자는 필터링을 구성하여 기록할 메시지를 제한할 수 있습니다.  
  
 기본적으로 메시지 로깅은 사용되지 않습니다. 로컬 컴퓨터 관리자는 응용 프로그램 수준 관리자가 메시지 로깅을 설정하지 않도록 차단할 수 있습니다.  
  
#### <a name="encrypted-and-decrypted-message-logging"></a>암호화 및 해독된 메시지 로깅  
 메시지는 다음 용어에 설명된 대로 기록, 암호화 또는 해독됩니다.  
  
 전송 로깅  
 전송 수준에서 수신 및 전송된 메시지를 기록합니다. 이 메시지에는 모든 헤더가 들어 있으며, 통신 중에 전송하기 전과 수신할 때 암호화할 수 있습니다.  
  
 통신 중에 전송하기 전과 수신할 때 메시지가 암호화되는 경우 암호화된 상태로도 기록됩니다. 단, 보안 프로토콜(https)을 사용하는 경우는 예외입니다. 메시지가 통신 중에 암호화되는 경우에도 전송되기 전과 수신된 후 해독되어 기록됩니다.  
  
 서비스 로깅  
 채널 헤더 처리가 발생한 후, 사용자 코드를 입력하기 직전과 그 후에 서비스 모델 수준에서 수신 또는 전송된 메시지를 기록합니다.  
  
 이 수준에서 기록된 메시지는 통신 중에 보안 및 암호화된 경우에도 해독됩니다.  
  
 잘못된 형식의 메시지 로깅  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 인프라에서 이해할 수 없거나 처리할 수 없는 메시지를 기록합니다.  
  
 메시지는 있는 그대로, 즉 암호화된 상태나 암호화되지 않은 상태로 기록됩니다.  
  
 메시지가 해독된 형태나 암호화되지 않은 형태로 기록되는 경우 기본적으로 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]는 메시지를 기록하기 전에 보안 키와 잠재적 개인 정보를 메시지에서 제거합니다. 다음 단원에서는 제거되는 정보와 시기에 대해 설명합니다. 키와 잠재적 개인 정보를 기록하려면 컴퓨터 관리자와 응용 프로그램 배포자가 모두 특정 구성 작업을 수행하여 기본 동작을 변경해야 합니다.  
  
#### <a name="information-removed-from-message-headers-when-logging-decryptedunencrypted-messages"></a>해독/암호화되지 않은 메시지를 기록할 때 메시지 헤더에서 제거되는 정보  
 메시지가 해독/암호화되지 않은 형태로 기록되는 경우 기본적으로 메시지를 기록하기 전에 보안 키와 잠재적 개인 정보가 메시지 헤더와 메시지 본문에서 제거됩니다. 다음 목록에서는 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]에서 키와 잠재적 개인 정보로 간주하는 항목을 보여 줍니다.  
  
 제거되는 키  
  
 \-Xmlns: wst = "http://schemas.xmlsoap.org/ws/2004/04/trust" 및 xmlns: wst = "http://schemas.xmlsoap.org/ws/2005/02/trust"  
  
 wst:BinarySecret  
  
 wst:Entropy  
  
 \-Xmlns:wsse "http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.1.xsd" 및 xmlns:wsse = = "http://docs.oasis-open.org/wss/2005/xx/oasis-2005xx-wss-wssecurity-secext-1.1.xsd"  
  
 wsse:Password  
  
 wsse:Nonce  
  
 제거되는 잠재적 개인 정보  
  
 \-Xmlns:wsse "http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.1.xsd" 및 xmlns:wsse = = "http://docs.oasis-open.org/wss/2005/xx/oasis-2005xx-wss-wssecurity-secext-1.1.xsd"  
  
 wsse:Username  
  
 wsse:BinarySecurityToken  
  
 \-Xmlns: saml = "urn: oasis: 이름: tc: SAML:1.0:assertion" 항목 굵게 (아래 참조)이 제거 됩니다.  
  
 \<어설션  
  
 MajorVersion="1"  
  
 MinorVersion="1"  
  
 AssertionId="[ID]"  
  
 Issuer="[string]"  
  
 IssueInstant="[dateTime]"  
  
 >  
  
 \<조건 NotBefore "[dateTime]" NotOnOrAfter = = "[dateTime]" >  
  
 \<AudienceRestrictionCondition >  
  
 \<대상 그룹 > [uri]\</Audience > +  
  
 \</ AudienceRestrictionCondition > *  
  
 \<DoNotCacheCondition / > *  
  
 <\!-기본 형식이 추상  
  
 \<조건 / > *  
  
 -->  
  
 \</ 조건 >?  
  
 \<조언 >  
  
 \<AssertionIDReference > [ID]\</AssertionIDReference > *  
  
 \<어설션 > [어설션]\</Assertion > *  
  
 [any]*  
  
 \</ 통지 >?  
  
 <\!-추상 기본 유형  
  
 \<문 / > *  
  
 \<SubjectStatement >  
  
 \<제목 >  
  
 `<NameIdentifier`  
  
 `NameQualifier="[string]"?`  
  
 `Format="[uri]"?`  
  
 `>`  
  
 `[string]`  
  
 `</NameIdentifier>?`  
  
 \<SubjectConfirmation >  
  
 \<ConfirmationMethod > [anyUri]\</ConfirmationMethod > +  
  
 \<SubjectConfirmationData > [모두]\</SubjectConfirmationData >?  
  
 \<ds:KeyInfo >... \</ds:KeyInfo >?  
  
 \</ SubjectConfirmation >?  
  
 \</ 제목이 >  
  
 \</ SubjectStatement > *  
  
 -->  
  
 \<AuthenticationStatement  
  
 AuthenticationMethod="[uri]"  
  
 AuthenticationInstant="[dateTime]"  
  
 >  
  
 [Subject]  
  
 `<SubjectLocality`  
  
 `IPAddress="[string]"?`  
  
 `DNSAddress="[string]"?`  
  
 `/>?`  
  
 <AuthorityBinding  
  
 AuthorityKind="[QName]"  
  
 Location="[uri]"  
  
 Binding="[uri]"  
  
 />*  
  
 \</ AuthenticationStatement > *  
  
 \<요소의 AttributeStatement >  
  
 [Subject]  
  
 \<특성  
  
 AttributeName="[string]"  
  
 AttributeNamespace="[uri]"  
  
 >  
  
 `<AttributeValue>[any]</AttributeValue>+`  
  
 \</ 특성 > +  
  
 \</ 요소의 AttributeStatement > *  
  
 \<AuthorizationDecisionStatement  
  
 Resource="[uri]"  
  
 의사 결정 = "[허용 &#124; 거부 &#124; 비활성화]"  
  
 >  
  
 [Subject]  
  
 \<작업 Namespace = "[uri]" > [string]\</Action > +  
  
 \<증명 정보 >  
  
 \<AssertionIDReference > [ID]\</AssertionIDReference > +  
  
 \<어설션 > [어설션]\</Assertion > +  
  
 \</ 증명 정보 >?  
  
 \</ AuthorizationDecisionStatement > *  
  
 \</ 어설션 >  
  
#### <a name="information-removed-from-message-bodies-when-logging-decryptedunencrypted-messages"></a>해독/암호화되지 않은 메시지를 기록할 때 메시지 본문에서 제거되는 정보  
 앞에서 설명했듯이 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]는 기록된 해독/암호화되지 않은 메시지에 대해 키와 알려진 잠재적 개인 정보를 메시지에서 제거합니다. 또한 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]는 키 교환과 관련된 보안 메시지를 설명하는 다음 목록의 본문 요소와 작업에 대해 키와 알려진 잠재적 개인 정보를 메시지 본문에서 제거합니다.  
  
 다음 네임스페이스의 경우  
  
 xmlns:wst="http://schemas.xmlsoap.org/ws/2004/04/trust" 및 xmlns:wst="http://schemas.xmlsoap.org/ws/2005/02/trust"(예를 들어 사용 가능한 작업이 없는 경우)  
  
 키 교환과 관련된 다음 본문 요소에서 정보가 제거됩니다.  
  
 wst:RequestSecurityToken  
  
 wst:RequestSecurityTokenResponse  
  
 wst:RequestSecurityTokenResponseCollection  
  
 다음 각 작업에서도 정보가 제거됩니다.  
  
 http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Issue  
  
 http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Issue  
  
 http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Renew  
  
 http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Renew  
  
 http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Cancel  
  
 http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Cancel  
  
 http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Validate  
  
 http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Validate  
  
 http://schemas.xmlsoap.org/ws/2005/02/trust/RST/SCT  
  
 http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/SCT  
  
 http://schemas.xmlsoap.org/ws/2005/02/trust/RST/SCT/Amend  
  
 http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/SCT/Amend  
  
 http://schemas.xmlsoap.org/ws/2005/02/trust/RST/SCT/Renew  
  
 http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/SCT/Renew  
  
 http://schemas.xmlsoap.org/ws/2005/02/trust/RST/SCT/Cancel  
  
 http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/SCT/Cancel  
  
 http://schemas.xmlsoap.org/ws/2004/04/security/trust/RST/SCT  
  
 http://schemas.xmlsoap.org/ws/2004/04/security/trust/RSTR/SCT  
  
 http://schemas.xmlsoap.org/ws/2004/04/security/trust/RST/SCT-Amend  
  
 http://schemas.xmlsoap.org/ws/2004/04/security/trust/RSTR/SCT-Amend  
  
#### <a name="no-information-is-removed-from-application-specific-headers-and-body-data"></a>응용 프로그램별 헤더 및 본문 데이터의 정보는 제거되지 않음  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]에서는 응용 프로그램별 헤더(예: 쿼리 문자열) 또는 본문 데이터(예: 신용 카드 번호)의 개인 정보를 추적하지 않습니다.  
  
 메시지 로깅을 설정하면 응용 프로그램별 헤더와 본문 정보의 개인 정보가 로그에 표시될 수 있습니다. 응용 프로그램 배포자는 구성 및 로그 파일에 ACL을 설정하는 작업을 담당합니다. 또한 이 정보를 표시하지 않으려면 로깅을 해제할 수 있으며 이 정보가 기록된 후 로그 파일에서 필터링할 수도 있습니다.  
  
### <a name="service-model-tracing"></a>서비스 모델 추적  
 서비스 모델 추적 소스(<xref:System.ServiceModel>)는 메시지 처리와 관련된 동작 및 이벤트 추적을 가능하게 합니다. 이 기능은 <xref:System.Diagnostics>의 .NET Framework 진단 기능을 사용합니다. <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A> 속성과 마찬가지로 사용자가 .NET Framework 응용 프로그램 구성 파일을 사용하여 위치와 해당 ACL을 구성할 수 있습니다. 메시지 로깅과 마찬가지로 파일 위치는 항상 관리자가 추적을 활성화할 때 구성되므로 관리자가 ACL을 제어합니다.  
  
 메시지가 범위 내에 있으면 추적에 메시지 헤더가 포함됩니다. 이전 단원에서 메시지 헤더에서 잠재적 개인 정보를 숨기는 경우에 대한 것과 동일한 규칙이 적용됩니다. 기본적으로 이전에 식별된 개인 정보가 추적 중인 헤더에서 제거됩니다. 잠재적 개인 정보를 기록하려면 컴퓨터 관리자와 응용 프로그램 배포자가 모두 구성을 수정해야 합니다. 그러나 응용 프로그램별 헤더에 포함된 개인 정보는 추적에 기록됩니다. 응용 프로그램 배포자는 구성 및 추적 파일에 ACL을 설정하는 작업을 담당합니다. 또한 이 정보를 표시하지 않으려면 추적을 해제할 수 있으며 이 정보가 기록된 후 추적 파일에서 필터링할 수도 있습니다.  
  
 ServiceModel 추적의 일부로 고유 ID(동작 ID라고 하며 일반적으로 GUID임)는 메시지가 인프라의 여러 부분을 통과할 때 여러 동작을 함께 연결합니다.  
  
#### <a name="custom-trace-listeners"></a>사용자 지정 추적 수신기  
 메시지 로깅 및 추적에 대해 통신 중에 추적과 메시지를 원격 데이터베이스 등에 보낼 수 있는 사용자 지정 추적 수신기를 구성할 수 있습니다. 응용 프로그램 배포자는 사용자 지정 수신기를 구성하거나 사용자가 구성할 수 있게 하는 작업을 담당합니다. 또한 원격 위치에 노출되는 모든 개인 정보에 대한 책임이 있으며 이 위치에 ACL을 적절하게 적용하는 작업을 담당합니다.  
  
### <a name="other-features-for-it-professionals"></a>IT 전문가용 기타 기능  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]에는 Windows에 포함된 WMI를 통해 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 인프라 구성 정보를 노출하는 WMI 공급자가 있습니다. 기본적으로 관리자는 WMI 인터페이스를 사용할 수 있습니다.  
  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 구성은 .NET Framework 구성 메커니즘을 사용합니다. 구성 파일은 컴퓨터에 저장됩니다. 응용 프로그램 개발자와 관리자는 응용 프로그램의 각 요구 사항에 대한 구성 파일과 ACL을 만듭니다. 구성 파일에는 끝점 주소와 인증서 저장소의 인증서에 대한 링크가 포함될 수 있습니다. 인증서는 응용 프로그램에서 사용하는 기능의 다양한 속성을 구성하기 위해 응용 프로그램 데이터를 제공하는 데 사용될 수 있습니다.  
  
 또한 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]에서는 <xref:System.Environment.FailFast%2A> 메서드를 사용하여 .NET Framework 프로세스 덤프 기능을 사용합니다.  
  
### <a name="it-pro-tools"></a>IT 전문가 도구  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]에서는 Windows SDK에 포함된 다음 IT 전문가 도구를 제공합니다.  
  
#### <a name="svctraceviewerexe"></a>SvcTraceViewer.exe  
 뷰어는 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 추적 파일을 표시합니다. 뷰어는 추적에 포함된 모든 정보를 보여 줍니다.  
  
#### <a name="svcconfigeditorexe"></a>SvcConfigEditor.exe  
 이 편집기를 통해 사용자는 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 구성 파일을 만들고 편집할 수 있습니다. 편집기는 구성 파일에 포함된 모든 정보를 보여 줍니다. 텍스트 편집기를 사용하여 동일한 작업을 수행할 수 있습니다.  
  
#### <a name="servicemodelreg"></a>ServiceModel_Reg  
 이 도구를 통해 사용자는 컴퓨터의 ServiceModel 설치를 관리할 수 있습니다. 이 도구는 실행될 때 콘솔 창에 상태 메시지를 표시하며, 처리 중에 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 설치의 구성에 대한 정보를 표시할 수 있습니다.  
  
#### <a name="wsatconfigexe-and-wsatuidll"></a>WSATConfig.exe 및 WSATUI.dll  
 이 도구를 통해 IT 전문가는 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]에서 상호 운용 가능한 WS-AtomicTransaction 네트워크 지원을 구성할 수 있습니다. 이 도구는 레지스트리에 저장된 가장 일반적으로 사용되는 WS-AtomicTransaction 설정의 값을 표시하고 사용자가 변경할 수 있게 합니다.  
  
## <a name="cross-cutting-features"></a>교차 편집 기능  
 다음 기능은 교차 편집 기능입니다. 즉, 앞의 기능을 임의로 조합하여 구성될 수 있습니다.  
  
### <a name="service-framework"></a>서비스 프레임워크  
 메시지를 CLR 클래스의 인스턴스와 연결하는 GUID인 인스턴스 ID가 헤더에 들어 있습니다.  
  
 WSDL(웹 서비스 기술 언어)에는 포트 정의가 들어 있습니다. 각 포트에는 끝점 주소와 응용 프로그램에서 사용하는 서비스를 나타내는 바인딩이 있습니다. 구성을 사용하여 WSDL 노출을 해제할 수 있습니다. 컴퓨터에는 정보가 보관되지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [Windows Communication Foundation](http://msdn.microsoft.com/en-us/fd327ade-0260-4c40-adbe-b74645ba3277)  
 [보안](../../../docs/framework/wcf/feature-details/security.md)
