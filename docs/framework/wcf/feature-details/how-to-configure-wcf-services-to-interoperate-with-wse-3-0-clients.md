---
title: "방법: WSE 3.0 클라이언트와 상호 운용하도록 WCF 서비스 구성 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0f38c4a0-49a6-437c-bdde-ad1d138d3c4a
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# 방법: WSE 3.0 클라이언트와 상호 운용하도록 WCF 서비스 구성
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 서비스는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스가 2004년 8월 버전의 WS\-Addressing 사양을 사용하도록 구성된 경우 Microsoft .NET 클라이언트용 WSE\(Web Services Enhancements\) 3.0과 유선 수준으로 호환됩니다.  
  
### WCF 서비스가 WSE 3.0 클라이언트와 상호 운용하도록 하려면  
  
1.  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스의 사용자 지정 바인딩을 정의합니다.  
  
     2004년 8월 버전의 WS\-Addressing 사양을 메시지 인코딩에 사용하도록 지정하려면 사용자 지정 바인딩을 만들어야 합니다.  
  
    1.  [\<customBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) 자식을 서비스 구성 파일의 [\<bindings\>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)에 추가합니다.  
  
    2.  [\<binding\>](../../../../docs/framework/misc/binding.md)를 [\<customBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)에 추가하고 `name` 특성을 설정하여 바인딩의 이름을 지정합니다.  
  
    3.  [\<security\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) 자식을 [\<binding\>](../../../../docs/framework/misc/binding.md)에 추가하여, 인증 모드와 메시지 보안에 사용되는 WS\-Security 사양 버전\(WSE 3.0과 호환 가능\)을 지정합니다.  
  
         인증 모드를 설정하려면 [\<security\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)의 `authenicationMode` 특성을 설정합니다.인증 모드는 대체로 WSE 3.0의 턴키 보안 어설션에 해당합니다.다음 표에는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 인증 모드와 WSE 3.0 턴키 보안 어설션이 매핑되어 있습니다.  
  
        |WCF 인증 모드|WSE 3.0 턴키 보안 어설션|  
        |---------------|-----------------------|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode>|`anonymousForCertificateSecurity`|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode>|`kerberosSecurity`|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode>|`mutualCertificate10Security`\*|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode>|`mutualCertificate11Security`\*|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode>|`usernameOverTransportSecurity`|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode>|`usernameForCertificateSecurity`|  
  
         \* `mutualCertificate10Security`와 `mutualCertificate11Security` 턴키 보안 어설션 간의 주요 차이점은 SOAP 메시지 보안을 위해 WSE에서 사용하는 WS\-Security 사양 버전입니다.`mutualCertificate10Security`에는 WS\-Security 1.0이 사용되는 반면, `mutualCertificate11Security`에는 WS\-Security 1.1이 사용됩니다.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서는 WS\-Security 사양 버전이 [\<security\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)의 `messageSecurityVersion` 특성에 지정됩니다.  
  
         SOAP 메시지 보안에 사용할 WS\-Security 사양 버전을 설정하려면 [\<security\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)의 `messageSecurityVersion` 특성을 설정합니다.WSE 3.0과 상호 운용하려면 `messageSecurityVersion` 특성의 값을 <xref:System.ServiceModel.MessageSecurityVersion.WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10%2A>으로 설정합니다.  
  
    4.  [\<textMessageEncoding\>](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md)를 추가하여 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 2004년 8월 버전의 WS\-Addressing 사양을 사용하도록 지정하고 해당 값에 대한 `messageVersion`을 <xref:System.ServiceModel.Channels.MessageVersion.Soap11WSAddressingAugust2004%2A>로 설정합니다.  
  
        > [!NOTE]
        >  SOAP 1.2를 사용할 경우에는 `messageVersion` 특성을 <xref:System.ServiceModel.Channels.MessageVersion.Soap12WSAddressingAugust2004%2A>로 변경합니다.  
  
2.  서비스에서 사용자 지정 바인딩이 사용되도록 지정합니다.  
  
    1.  [\<endpoint\>](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) 요소의 `binding` 특성을 `customBinding`으로 설정합니다.  
  
    2.  [\<endpoint\>](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) 요소의 `bindingConfiguration` 특성을 사용자 지정 바인딩을 위해 [\<binding\>](../../../../docs/framework/misc/binding.md)의 `name` 특성에 지정된 값으로 설정합니다.  
  
## 예제  
 다음은 `Service.HelloWorldService`에서 사용자 지정 바인딩을 사용하여 WSE 3.0 클라이언트와 상호 운용하도록 지정하는 코드 예제입니다.사용자 지정 바인딩에서는 교환되는 메시지를 인코딩하는 데 2004년 8월 버전의 WS\-Addressing과 WS\-Security 1.1을 사용하도록 지정합니다.메시지 보안은 <xref:System.ServiceModel.Configuration.AuthenticationMode> 인증 모드를 통해 이루어집니다.  
  
```  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service   
        behaviorConfiguration="ServiceBehavior"   
        name="Service.HelloWorldService">  
        <endpoint binding="customBinding" address=""  
          bindingConfiguration="ServiceBinding"  
          contract="Service.IHelloWorld"></endpoint>  
      </service>  
    </services>  
  
    <bindings>  
      <customBinding>  
        <binding name="ServiceBinding">  
          <security authenticationMode="AnonymousForCertificate"  
                  messageProtectionOrder="SignBeforeEncrypt"  
                  messageSecurityVersion="WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10"  
                  requireDerivedKeys="false">  
          </security>  
          <textMessageEncoding messageVersion ="Soap11WSAddressingAugust2004"></textMessageEncoding>  
          <httpTransport/>  
        </binding>  
      </customBinding>  
    </bindings>  
    <behaviors>  
      <behavior name="ServiceBehavior" returnUnknownExceptionsAsFaults="true">  
        <serviceCredentials>  
          <serviceCertificate findValue="CN=WCFQuickstartServer" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectDistinguishedName"/>  
        </serviceCredentials>  
      </behavior>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
## 참고 항목  
 [방법: 시스템 제공 바인딩 사용자 지정](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md)