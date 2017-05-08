---
title: "분산 응용 프로그램 보안 | Microsoft Docs"
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
helpviewer_keywords: 
  - "분산 응용 프로그램 보안 [WCF]"
  - "보안 [WCF], 전송"
ms.assetid: 53928a10-e474-46d0-ab90-5f98f8d7b668
caps.latest.revision: 32
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 32
---
# 분산 응용 프로그램 보안
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 보안은 전송 보안, 액세스 제어 및 감사의 세 가지 주 기능 영역으로 분류됩니다.전송 보안은 무결성, 기밀성 및 인증을 제공합니다.전송 보안은 전송 보안, 메시지 보안, `TransportWithMessageCredential` 중 하나를 통해 제공됩니다.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 메시지 보안의 개요는 [보안 개요](../../../../docs/framework/wcf/feature-details/security-overview.md)를 참조하십시오.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 보안의 다른 두 영역[!INCLUDE[crabout](../../../../includes/crabout-md.md)][권한 부여](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md) 및 [감사](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)를 참조하십시오.  
  
## 전송 보안 시나리오  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 전송 보안을 사용하는 일반적인 시나리오는 다음과 같습니다.  
  
-   Windows를 사용하여 전송을 보안합니다.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트와 서비스는 Windows 도메인 또는 Windows 포리스트에 배포됩니다.메시지에 개인 데이터가 포함되므로 클라이언트와 서비스 간의 상호 인증, 메시지 무결성 및 메시지 기밀성이 요구됩니다.또한 특정 트랜잭션이 발생했다는 증명이 필요합니다. 예를 들어 메시지 수신자가 서명 정보를 기록해야 합니다.  
  
-   `UserName` 및 HTTPS를 사용하여 전송을 보안합니다.인터넷을 통해 작업하려면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트와 서비스를 개발해야 합니다.클라이언트 자격 증명은 사용자 이름\/암호 쌍 데이터베이스를 기준으로 인증합니다.서비스는 신뢰할 수 있는 SSL\(Secure Sockets Layer\) 인증서를 사용하여 HTTPS 주소에 배포됩니다.메시지가 인터넷을 통해 이동하기 때문에 클라이언트와 서비스를 상호 인증하고 전송 중에 메시지의 기밀성과 무결성을 유지해야 합니다.  
  
-   인증서를 사용하여 전송을 보안합니다.공용 인터넷을 통해 작업하려면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트와 서비스를 개발해야 합니다.클라이언트와 서비스에는 모두 메시지를 보안하는 데 사용되는 인증서가 있습니다.클라이언트와 서비스는 인터넷을 사용하여 서로 통신하고 메시지 무결성, 기밀성 및 상호 인증을 필요로 하는 높은 가치의 트랜잭션을 수행합니다.  
  
## 무결성, 기밀성 및 인증  
 세 함수\(무결성, 기밀성, 인증\)를 총칭하여 전송 보안이라고 합니다.전송 보안은 분산 응용 프로그램에 대한 위협을 줄이는 데 도움이 되는 함수를 제공합니다.다음 표에서는 전송 보안을 구성하는 세 함수에 대해 간략하게 설명합니다.  
  
|함수|설명|  
|--------|--------|  
|무결성|*무결성*은 특히, 데이터가 한 지점에서 다른 지점으로 이동되고 여러 행위자가 읽은 후에도 완전하고 정확하다는 보장입니다.무결성은 데이터 변조 방지를 위해 유지되어야 하며, 일반적으로 메시지에 대한 디지털 서명을 통해 수행됩니다.|  
|기밀성|*기밀성*은 대상 사용자 이외의 다른 사용자가 메시지를 읽지 않는다는 보장입니다.예를 들어, 인터넷을 통해 전송되는 신용 카드 번호를 기밀로 유지해야 합니다.기밀성은 대개 공개 키\/개인 키 스키마를 사용하는 데이터 암호화를 통해 제공됩니다.|  
|인증|*인증*은 클레임 ID에 대한 확인입니다.예를 들어 은행 계좌를 사용할 때는 계좌의 실제 소유자만 예금을 인출할 수 있도록 해야 합니다.인증은 다양한 방법으로 제공될 수 있습니다.가장 널리 사용되는 방법은 사용자\/암호 시스템입니다.또한 타사에서 제공하는 X.509 인증서를 사용하는 방법도 있습니다.|  
  
## 보안 모드  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에는 다양한 전송 보안 모드가 있습니다. 각 전송 보안 모드에 대해서는 다음 표에 설명되어 있습니다.  
  
|모드|설명|  
|--------|--------|  
|None|전송 계층 또는 메시지 계층에 보안이 제공되지 않습니다.[\<basicHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) 요소 또는 <xref:System.ServiceModel.BasicHttpBinding> 클래스\(코드를 사용할 경우\)를 제외하고 기본적으로 이 모드를 사용하는 미리 정의된 바인딩이 없습니다.|  
|Transport|무결성, 기밀성 및 상호 인증을 위해 HTTPS와 같은 보안 전송을 사용합니다.|  
|Message|무결성, 기밀성 및 상호 인증을 위해 SOAP 메시지 보안을 사용합니다.SOAP 메시지는 WS\-Security 표준에 따라 보안됩니다.|  
|Mixed Mode|무결성, 기밀성 및 서버 인증을 위해 전송 보안을 사용합니다.클라이언트 인증을 위해 메시지 보안\(WS\-Security 및 다른 표준\)을 사용합니다.<br /><br /> 이 모드에 대한 이 열거형은 `TransportWithMessageCredential`입니다.|  
|Both|두 수준 모두에서 보호 및 인증을 수행합니다.이 모드는 [\<netMsmqBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md) 요소에서만 사용할 수 있습니다.|  
  
## 자격 증명 및 전송 보안  
 *자격 증명*은 클레임 ID 또는 기능을 설정하기 위해 제공되는 데이터입니다.자격 증명을 제공할 때는 데이터와 데이터 소유 증명을 모두 제공해야 합니다.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 전송 보안 수준과 메시지 보안 수준 둘 다에서 다양한 자격 증명 형식을 지원합니다.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 바인딩에 대한 자격 증명 형식을 지정할 수 있습니다.  
  
 많은 국가나 지역의 운전 면허가 자격 증명의 예입니다.라이선스에는 사용자의 신분과 능력을 나타내는 데이터가 들어 있습니다.또한 소유자의 사진 형태로 소유 증명이 포함되어 있습니다.라이선스는 신뢰할 수 있는 기관\(일반적으로 정부 라이선스 부서\)에서 발급됩니다.라이선스에는 날인이 찍히며, 변조 또는 위조되지 않았음을 증명하는 홀로그램이 삽입되어 있을 수 있습니다.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 지원되는 두 가지 자격 증명 형식인 사용자 이름 자격 증명과 \(X.509\) 인증서 자격 증명을 예로 들어 볼 수 있습니다.  
  
 사용자 이름 자격 증명에서 사용자 이름은 클레임 ID를 나타내고 암호는 소유 증명을 나타냅니다.이 경우 신뢰할 수 있는 기관은 사용자 이름과 암호의 유효성을 검사하는 시스템입니다.  
  
 인증서 자격 증명에서는 주체 이름, 주체 대체 이름 또는 인증서 내의 특정 필드를 사용하여 클레임 ID 및\/또는 기능을 나타낼 수 있습니다.자격 증명의 데이터 소유 증명은 연결된 개인 키로 서명을 생성하여 설정됩니다.  
  
 전송 보안 프로그래밍 및 자격 증명 지정[!INCLUDE[crabout](../../../../includes/crabout-md.md)][바인딩 및 보안](../../../../docs/framework/wcf/feature-details/bindings-and-security.md) 및 [보안 동작](../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)을 참조하십시오.  
  
### 전송 클라이언트 자격 증명 형식  
 다음 표에서는 전송 보안을 사용하는 응용 프로그램을 만들 때 사용할 수 있는 값을 보여 줍니다.이러한 값은 코드 또는 바인딩 설정에 사용할 수 있습니다.  
  
|설정|설명|  
|--------|--------|  
|None|클라이언트가 자격 증명을 제공할 필요가 없음을 지정합니다.익명 클라이언트로 변환됩니다.|  
|Basic|기본 인증을 지정합니다.자세한 내용은 RFC2617, "[HTTP Authentication: Basic and Digest Authentication](http://go.microsoft.com/fwlink/?LinkId=88313)"을 참조하십시오.|  
|Digest|다이제스트 인증을 지정합니다.자세한 내용은 RFC2617, "[HTTP Authentication: Basic and Digest Authentication](http://go.microsoft.com/fwlink/?LinkId=88313)"을 참조하십시오.|  
|Ntlm|Windows 도메인에서 SSPI 협상을 사용하여 Windows 인증을 지정합니다.<br /><br /> SSPI 협상은 Kerberos 프로토콜 또는 NTLM\(NT LanMan\)을 사용합니다.|  
|Windows|Windows 도메인에서 SSPI를 사용하여 Windows 인증을 지정합니다.SSPI는 Kerberos 프로토콜 또는 NTLM을 인증 서비스로 선택합니다.<br /><br /> SSPI는 Kerberos 프로토콜을 먼저 시도한 다음 실패하면 NTLM을 사용합니다.|  
|Certificate|인증서\(일반적으로 X.509\)를 사용하여 클라이언트 인증을 수행합니다.|  
  
### 메시지 클라이언트 자격 증명 형식  
 다음 표에서는 메시지 보안을 사용하는 응용 프로그램을 만들 때 사용할 수 있는 값을 보여 줍니다.이러한 값은 코드 또는 바인딩 설정에 사용할 수 있습니다.  
  
|설정|설명|  
|--------|--------|  
|None|서비스와 익명 클라이언트가 상호 작용할 수 있습니다.|  
|Windows|Windows 자격 증명의 인증된 컨텍스트에서 SOAP 메시지 교환을 수행할 수 있습니다.SSPI 협상 메커니즘을 사용하여 Kerberos 프로토콜 또는 NTLM을 인증 서비스로 선택합니다.|  
|Username|서비스에서 사용자 이름 자격 증명을 사용하여 클라이언트를 인증하도록 요구할 수 있습니다.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 사용자 이름을 사용하여 서명 생성, 데이터 암호화 등과 같은 암호화 작업을 수행할 수 없습니다.따라서 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 사용자 이름 자격 증명을 사용할 때 전송에 보안을 적용합니다.|  
|Certificate|서비스에서 인증서를 사용하여 클라이언트를 인증하도록 요구할 수 있습니다.|  
|[!INCLUDE[infocard](../../../../includes/infocard-md.md)]|서비스에서 [!INCLUDE[infocard](../../../../includes/infocard-md.md)]를 사용하여 클라이언트를 인증하도록 요구할 수 있습니다.|  
  
### 프로그래밍 자격 증명  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 프로그래밍 모델을 사용하면 서비스 동작과 채널 동작을 사용하여 각 클라이언트 자격 증명 형식에 대해 자격 증명 값과 자격 증명 유효성 검사기를 지정할 수 있습니다.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 보안에는 서비스 자격 증명 동작과 채널 자격 증명 동작의 두 가지 자격 증명 형식이 있습니다.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]의 자격 증명 동작은 실제 데이터 즉, 바인딩을 통해 명시된 보안 요구 사항을 충족시키는 데 사용되는 자격 증명을 지정합니다.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 클라이언트 클래스는 작업 호출과 메시지 간에 변환되는 런타임 구성 요소입니다.모든 클라이언트는 <xref:System.ServiceModel.ClientBase%601> 클래스에서 상속됩니다.기본 클래스의 <xref:System.ServiceModel.ClientBase%601.ClientCredentials%2A> 속성을 사용하면 다양한 클라이언트 자격 증명 값을 지정할 수 있습니다.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 서비스 동작은 서비스를 프로그래밍 방식으로 제어하기 위해 서비스 계약\(인터페이스\)을 구현하는 클래스에 적용되는 특성입니다.<xref:System.ServiceModel.Description.ServiceCredentials> 클래스를 사용하면 서비스 자격 증명에 대한 인증서와 다양한 클라이언트 자격 증명 형식에 대한 클라이언트 유효성 검사 설정을 지정할 수 있습니다.  
  
### 메시지 보안에 대한 협상 모델  
 메시지 보안 모드에서는 대역 외 클라이언트에서 서비스 자격 증명이 구성되도록 전송 보안을 수행할 수 있습니다.예를 들어 Windows 인증서 저장소에 저장된 인증서를 사용할 경우 MMC\(Microsoft Management Console\) 스냅인과 같은 도구를 사용해야 합니다.  
  
 메시지 보안 모드에서는 초기 협상 과정에서 서비스 자격 증명을 클라이언트와 교환하도록 전송 보안을 수행할 수도 있습니다.협상을 사용하도록 설정하려면 <xref:System.ServiceModel.MessageSecurityOverHttp.NegotiateServiceCredential%2A> 속성을 `true`로 설정합니다.  
  
## 참고 항목  
 [끝점 만들기 개요](../../../../docs/framework/wcf/endpoint-creation-overview.md)   
 [시스템 제공 바인딩](../../../../docs/framework/wcf/system-provided-bindings.md)   
 [보안 개요](../../../../docs/framework/wcf/feature-details/security-overview.md)   
 [Windows Server AppFabric 보안 모델](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x412)