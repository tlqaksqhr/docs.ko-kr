---
title: "SecurityBindingElement 인증 모드 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 12300bf4-c730-4405-9f65-d286f68b5a43
caps.latest.revision: 13
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 13
---
# SecurityBindingElement 인증 모드
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]에는 클라이언트와 서버가 서로를 인증하는 데 사용되는 모드가 몇 가지 있습니다.<xref:System.ServiceModel.Channels.SecurityBindingElement> 클래스에 정적 메서드를 사용하거나 구성을 통해 이러한 인증 모드의 보안 바인딩 요소를 만들 수 있습니다.이 항목에서는 18가지의 인증 모드에 대해 간단히 설명합니다.  
  
 특정 인증 모드 요소의 사용에 대한 예제는 [방법: 지정된 인증 모드에 대한 SecurityBindingElement 만들기](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)를 참조하십시오.  
  
## 기본 구성 프로그래밍  
 다음 절차에서는 구성 파일에 인증 모드를 설정하는 방법을 설명합니다.  
  
#### 구성 파일에 인증 모드를 설정하려면  
  
1.  [\<bindings\>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) 요소에 [\<customBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)를 추가합니다.  
  
2.  [\<binding\>](../../../../docs/framework/misc/binding.md) 요소를 자식 요소로 `<customBinding>` 요소에 추가합니다.  
  
3.  `<security>` 요소를 `<binding>` 요소에 추가합니다.  
  
4.  `authenticationMode` 특성을 아래 설명된 값 중 하나로 설정합니다.예를 들어 다음 코드에서는 모드를 `AnonymousForCertificate`로 설정합니다.  
  
    ```  
    <bindings>  
      <customBinding>  
        <binding name="SecureCustomBinding">  
         <security authenticationMode ="AnonymousForCertificate" />  
        </binding>  
      </customBinding>  
    </bindings>  
    ```  
  
#### 프로그래밍 방식으로 모드를 설정하려면  
  
1.  반환 형식을<xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>, <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>, <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> 또는 <xref:System.ServiceModel.Channels.SecurityBindingElement> 중에서 선택합니다.  
  
2.  <xref:System.ServiceModel.Channels.SecurityBindingElement> 클래스의 적절한 정적 메서드를 호출합니다.예를 들어 다음 코드에서는 <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateAnonymousForCertificateBindingElement%2A> 메서드를 호출합니다.  
  
     [!code-csharp[c_CustomBindingsAuthMode#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_custombindingsauthmode/cs/source.cs#3)]
     [!code-vb[c_CustomBindingsAuthMode#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_custombindingsauthmode/vb/source.vb#3)]  
  
3.  바인딩 요소를 사용하여 사용자 지정 바인딩을 만듭니다.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][사용자 지정 바인딩](../../../../docs/framework/wcf/extending/custom-bindings.md).  
  
## 모드 설명  
  
### AnonymousForCertificate  
 이 인증 모드에서 클라이언트는 익명이고 서비스는 X.509 인증서를 사용하여 인증됩니다.보안 바인딩 요소는 <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateAnonymousForCertificateBindingElement%2A> 메서드에서 반환된 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>입니다.또는 \<`security`\> 요소의 `authenticationMode` 특성을 `AnonymousForCertificate`로 설정합니다.  
  
### AnonymousForSslNegotiated  
 이 인증 모드에서 클라이언트는 비대칭이고 서비스는 런타임에 협상되는 X.509 인증서를 사용하여 인증됩니다.보안 바인딩 요소는 첫 번째 매개 변수에 대해 `false` 값이 전달될 때 <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSslNegotiationBindingElement%2A> 메서드에 의해 반환된 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>입니다.또는 `authenticationMode` 특성을 `AnonymousForSslNegotiated`로 설정합니다.  
  
### CertificateOverTransport  
 이 인증 모드에서 클라이언트는 메시지 서명에 서명한 토큰인 보증 지원 토큰으로 SOAP 계층에 표시되는 X.509 인증서를 사용하여 인증합니다.서비스는 전송 계층에서 X.509 인증서를 사용하여 인증됩니다.보안 바인딩 요소는 <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateCertificateOverTransportBindingElement%2A> 메서드에서 반환된 <xref:System.ServiceModel.Channels.TransportSecurityBindingElement>입니다.또는 `authenticationMode` 특성을 `CertificateOverTransport`로 설정합니다.  
  
### IssuedToken  
 이 인증 모드에서는 클라이언트가 서비스를 인증하지 않으므로 대신 클라이언트가 보안 토큰 서비스를 인증하고 SAML 토큰을 수신한 다음 서버에 제공하여 공유 키에 대해 알고 있음을 증명합니다.따라서 서비스가 클라이언트 자체에 인증되지 않지만 보안 토큰 서비스에서 공유 키를 발급된 토큰의 일부로 암호화하여 서비스에서만 키를 해독할 수 있게 합니다.보안 바인딩 요소는 <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateIssuedTokenBindingElement%2A> 메서드에서 반환된 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>입니다.또는 `authenticationMode` 특성을 `IssuedToken`으로 설정합니다.  
  
### IssuedTokenForCertificate  
 이 인증 모드에서는 클라이언트가 서비스를 인증하지 않으므로 대신 클라이언트가 보안 토큰 서비스를 인증하고 SAML 토큰을 수신한 다음 서버에 제공하여 공유 키에 대해 알고 있음을 증명합니다.발급된 토큰은 메시지 서명에 서명한 토큰인 보증 지원 토큰 또는 bearer 토큰으로 SOAP 계층에 표시됩니다.서비스는 X.509 인증서를 사용하여 클라이언트를 인증합니다.보안 바인딩 요소는 <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateIssuedTokenForCertificateBindingElement%2A> 메서드에서 반환된 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>입니다.또는 `authenticationMode` 특성을 `IssuedTokenForCertificate`로 설정합니다.  
  
### IssuedTokenForSslNegotiated  
 이 인증 모드에서는 클라이언트가 서비스를 인증하지 않으므로 대신 클라이언트가 보안 토큰 서비스를 인증하고 SAML 토큰을 수신한 다음 서버에 제공하여 공유 키에 대해 알고 있음을 증명합니다.발급된 토큰은 메시지 서명에 서명한 토큰인 보증 지원 토큰 또는 bearer 토큰으로 SOAP 계층에 표시됩니다.서비스는 X.509 인증서를 사용하여 인증됩니다.보안 바인딩 요소는 <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateIssuedTokenForSslBindingElement%2A> 메서드에서 반환된 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>입니다.또는 `authenticationMode` 특성을 `IssuedTokenForSslnegotiated`로 설정합니다.  
  
### IssuedTokenOverTransport  
 이 인증 모드에서는 클라이언트가 서비스를 인증하지 않으므로 대신 클라이언트가 보안 토큰 서비스를 인증하고 SAML 토큰을 수신한 다음 서버에 제공하여 공유 키에 대해 알고 있음을 증명합니다.발급된 토큰은 메시지 서명에 서명한 토큰인 보증 지원 토큰 또는 bearer 토큰으로 SOAP 계층에 표시됩니다.서비스는 전송 계층에서 X.509 인증서를 사용하여 인증됩니다.보안 바인딩 요소는 <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateIssuedTokenOverTransportBindingElement%2A> 메서드에서 반환된 `TransportSecurityBindingElement`입니다.또는 `authenticationMode` 특성을 `IssuedTokenOverTransport`로 설정합니다.  
  
### Kerberos  
 이 인증 모드에서는 클라이언트가 Kerberos 티켓을 사용하여 서비스를 인증합니다.동일한 티켓에서 서버 인증을 제공합니다.보안 바인딩 요소는 <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateKerberosBindingElement%2A> 메서드에서 반환된 `SymmetricSecurityBindingElement`입니다.또는 `authenticationMode` 특성을 `Kerberos`로 설정합니다.  
  
> [!NOTE]
>  이 인증 모드를 사용하려면 서비스 계정이 SPN\(서비스 사용자 이름\)과 연결되어야 합니다.이 작업을 수행하려면 NETWORK SERVICE 계정이나 LOCAL SYSTEM 계정에서 서비스를 실행합니다.또는 SetSpn.exe 도구를 사용하여 서비스 계정의 SPN을 만듭니다.어떤 경우에든 클라이언트는 [\<servicePrincipalName\>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceprincipalname.md) 요소에서 또는 <xref:System.ServiceModel.EndpointAddress> 생성자를 사용하여 정확한 SPN을 사용해야 합니다.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][서비스 ID 및 인증](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).  
  
> [!NOTE]
>  `Kerberos` 인증 모드를 사용하면 <xref:System.Security.Principal.TokenImpersonationLevel> 및 <xref:System.Security.Principal.TokenImpersonationLevel> 가장 수준이 지원되지 않습니다.  
  
### KerberosOverTransport  
 이 인증 모드에서는 클라이언트가 Kerberos 티켓을 사용하여 서비스를 인증합니다.Kerberos 토큰은 메시지 서명에 서명한 토큰인 보증 지원 토큰으로 SOAP 계층에 표시됩니다.서비스는 전송 계층에서 X.509 인증서를 사용하여 인증됩니다.보안 바인딩 요소는 <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateKerberosOverTransportBindingElement%2A> 메서드에서 반환된 `TransportSecurityBindingElement`입니다.또는 `authenticationMode` 특성을 `KerberosOverTransport`로 설정합니다.  
  
> [!NOTE]
>  이 인증 모드를 사용하려면 서비스 계정이 SPN과 연결되어야 합니다.이 작업을 수행하려면 NETWORK SERVICE 계정이나 LOCAL SYSTEM 계정에서 서비스를 실행합니다.또는 SetSpn.exe 도구를 사용하여 서비스 계정의 SPN을 만듭니다.어떤 경우에든 클라이언트는 [\<servicePrincipalName\>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceprincipalname.md) 요소에서 또는 <xref:System.ServiceModel.EndpointAddress> 생성자를 사용하여 정확한 SPN을 사용해야 합니다.[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][서비스 ID 및 인증](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).  
  
### MutualCertificate  
 이 인증 모드에서 클라이언트는 메시지 서명에 서명한 토큰인 보증 지원 토큰으로 SOAP 계층에 표시되는 X.509 인증서를 사용하여 인증합니다.서비스도 X.509 인증서를 사용하여 인증됩니다.보안 바인딩 요소는 <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateMutualCertificateBindingElement%2A> 메서드에서 반환된 `SymmetricSecurityBindingElement`입니다.또는 `authenticationMode` 특성을 `MutualCertificate`로 설정합니다.  
  
### MutualCertificateDuplex  
 이 인증 모드에서 클라이언트는 메시지 서명에 서명한 토큰인 보증 지원 토큰으로 SOAP 계층에 표시되는 X.509 인증서를 사용하여 인증합니다.서비스도 X.509 인증서를 사용하여 인증됩니다.바인딩은 <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateMutualCertificateDuplexBindingElement%2A> 메서드에서 반환된 `AsymmetricSecurityBindingElement`입니다.또는 `authenticationMode` 특성을 `MutualCertificateDuplex`로 설정합니다.  
  
### MutalSslNegotiation  
 이 인증 모드에서 클라이언트 및 서비스는 X.509 인증서를 사용하여 인증합니다.보안 바인딩 요소는 첫 번째 매개 변수에 대해 `true` 값이 전달될 때 <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSslNegotiationBindingElement%2A> 메서드에 의해 반환된 `SymmetricSecurityBindingElement`입니다.또는 `authenticationMode` 특성을 `MutualSslNegotiated`로 설정합니다.  
  
### SecureConversation  
 보안 바인딩 요소는 <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSecureConversationBindingElement%2A> 메서드에서 반환된 `SymmetricSecurityBindingElement`입니다.이 메서드는 <xref:System.ServiceModel.Channels.SecurityBindingElement>를 초기화 중에 보안 세션 설정에 사용할 매개 변수로 사용합니다.또는 `authenticationMode` 특성을 `SecureConversation`으로 설정합니다.  
  
 부트스트랩 바인딩이 지정되지 않은 경우에는 `SspiNegotiated` 인증 모드가 부트스트랩에 사용됩니다.  
  
### SspiNegotiation  
 이 인증 모드에서는 협상 프로토콜을 사용하여 클라이언트 및 서버 인증을 수행합니다.가능한 경우에는 Kerberos가 사용되며 그 이외에는 NTLM\(NT LanMan\)이 사용됩니다.보안 바인딩 요소는 <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSspiNegotiationBindingElement%2A> 메서드에서 반환된 `SymmetricSecurityBindingElement`입니다.또는 `authenticationMode` 특성을 `SspiNegotiated`로 설정합니다.  
  
### SspiNegotiatedOverTransport  
 이 인증 모드에서는 협상 프로토콜을 사용하여 클라이언트 및 서버 인증을 수행합니다.가능하면 Kerberos 프로토콜이 사용되고, 그렇지 않으면 NTLM이 사용됩니다.결과 토큰은 메시지 서명에 서명한 토큰인 보증 지원 토큰으로 SOAP 계층에 표시됩니다.서비스는 전송 계층에서 X.509 인증서를 사용하여 추가 인증됩니다.보안 바인딩 요소는 <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateSspiNegotiationOverTransportBindingElement%2A> 메서드에서 반환된 `TransportSecurityBindingElement`입니다.또는 `authenticationMode` 특성을 `SspiNegotiatedOverTransport`로 설정합니다.  
  
### UserNameForCertificate  
 이 인증 모드에서 클라이언트는 메시지 서명에 의해 서명된 토큰인 서명된 지원 토큰으로 SOAP 계층에 표시되는 사용자 이름 토큰을 사용하여 서비스를 인증합니다.서비스는 X.509 인증서를 사용하여 클라이언트를 인증합니다.보안 바인딩 요소는 <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateUserNameForCertificateBindingElement%2A> 메서드에서 반환된 `SymmetricSecurityBindingElement`입니다.또는 `authenticationMode` 특성을 `UserNameForCertificate`로 설정합니다.  
  
 `UserNameForCertificate` 인증 모드의 경우 클라이언트와 서비스 모두 WS\-Security 1.1을 사용해야 합니다.  
  
### UserNameForSslNegotiated  
 이 인증 모드에서 클라이언트는 메시지 서명에 의해 서명된 토큰인 서명된 지원 토큰으로 SOAP 계층에 표시되는 사용자 이름 토큰을 사용하여 인증합니다.서비스는 X.509 인증서를 사용하여 인증됩니다.보안 바인딩 요소는 <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateUserNameForSslBindingElement%2A> 메서드에서 반환된 `SymmetricSecurityBindingElement`입니다.또는 `authenticationMode` 특성을 `UserNameForSslNegotiated`로 설정합니다.  
  
### UserNameOverTransport  
 이 인증 모드에서 클라이언트는 메시지 서명에 의해 서명된 토큰인 서명된 지원 토큰으로 SOAP 계층에 표시되는 사용자 이름 토큰을 사용하여 인증합니다.서비스는 전송 계층에서 X.509 인증서를 사용하여 인증됩니다.보안 바인딩 요소는 <xref:System.ServiceModel.Channels.SecurityBindingElement.CreateUserNameOverTransportBindingElement%2A> 메서드에서 반환된 `TransportSecurityBindingElement`입니다.또는 `authenticationMode` 특성을 `UserNameOverTransport`로 설정합니다.  
  
## 참고 항목  
 <xref:System.ServiceModel.Channels.SecurityBindingElement>   
 [방법: 지정된 인증 모드에 대한 SecurityBindingElement 만들기](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)