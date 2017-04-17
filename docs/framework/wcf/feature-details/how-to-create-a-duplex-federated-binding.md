---
title: "방법: 이중 페더레이션 바인딩 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4331d2bc-5455-492a-9189-634a82597726
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# 방법: 이중 페더레이션 바인딩 만들기
<xref:System.ServiceModel.WSFederationHttpBinding>은 데이터그램 및 요청\/응답 메시지 교환 계약만 지원합니다.이중 메시지 교환 계약을 사용하려면 사용자 지정 바인딩을 만들어야 합니다.다음 절차에서는 HTTP 및 TCP 전송에 대해서는 메시지 모드 보안을 사용하고 TCP 전송에 대해서는 혼합 모드 보안을 사용하여 구성에서 이 작업을 수행하는 방법을 보여 줍니다.3개의 바인딩을 모두 보여 주는 샘플 코드는 이 항목의 끝에 나옵니다.  
  
 코드에서 바인딩을 만들 수도 있습니다.만들 바인딩 요소 스택에 대한 설명은 [방법: SecurityBindingElement를 사용하여 사용자 지정 바인딩 만들기](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)를 참조하십시오.  
  
### HTTP를 사용하여 이중 페더레이션 사용자 지정 바인딩을 만들려면  
  
1.  구성 파일의 [\<bindings\>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)[\<customBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) 요소를 만듭니다.  
  
2.  [\<customBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)요소 안에 `name` 특성이 `FederationDuplexHttpMessageSecurityBinding`으로 설정된 [\<binding\>](../../../../docs/framework/misc/binding.md) 요소를 만듭니다.  
  
3.  [\<binding\>](../../../../docs/framework/misc/binding.md) 요소 안에 `authenticationMode` 특성이 `SecureConversation`으로 설정된 [\<security\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) 요소를 만듭니다.  
  
4.  [\<security\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) [\<secureConversationBootstrap\>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) 요소 안에 `IssuedTokenForCertificate` 특성이 `IssuedTokenForSslNegotiated` 또는 로 설정된 `authenticationMode` 요소를 만듭니다.  
  
5.  [\<security\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) [\<compositeDuplex\>](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) 요소를 만듭니다.  
  
6.  [\<compositeDuplex\>](../../../../docs/framework/configure-apps/file-schema/wcf/compositeduplex.md) [\<oneWay\>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) 요소를 만듭니다.  
  
7.  [\<oneWay\>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) [\<httpTransport\>](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md) 요소를 만듭니다.  
  
### TCP 메시지 보안 모드를 사용하여 이중 페더레이션 사용자 지정 바인딩을 만들려면  
  
1.  구성 파일의 [\<oneWay\>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)[\<oneWay\>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) 요소를 만듭니다.  
  
2.  [\<oneWay\>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) [\<oneWay\>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) 요소 안에 `FederationDuplexTcpMessageSecurityBinding` 특성이 으로 설정된 `name` 요소를 만듭니다.  
  
3.  [\<oneWay\>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) [\<security\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) 요소 안에 `SecureConversation` 특성이 으로 설정된 `authenticationMode` 요소를 만듭니다.  
  
4.  [\<security\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) [\<secureConversationBootstrap\>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)요소 안에 `IssuedTokenForCertificate` 특성이 `IssuedTokenForSslNegotiated` 또는 로 설정된 `authenticationMode` 요소를 만듭니다.  
  
5.  [\<security\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) [\<tcpTransport\>](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) 요소를 만듭니다.  
  
### TCP 혼합 보안 모드를 사용하여 이중 페더레이션 사용자 지정 바인딩을 만들려면  
  
1.  구성 파일의 [\<oneWay\>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md)[\<oneWay\>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) 요소를 만듭니다.  
  
2.  [\<oneWay\>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) [\<oneWay\>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) 요소 안에 `FederationDuplexTcpTransportSecurityWithMessageCredentialBinding` 특성이 으로 설정된 `name` 요소를 만듭니다.  
  
3.  [\<oneWay\>](../../../../docs/framework/configure-apps/file-schema/wcf/oneway.md) [\<security\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) 요소 안에 `SecureConversation` 특성이 으로 설정된 `authenticationMode` 요소를 만듭니다.  
  
4.  [\<security\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) [\<secureConversationBootstrap\>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) 요소 안에 `IssuedTokenForCertificate` 특성이 `IssuedTokenForSslNegotiated` 또는 로 설정된 `authenticationMode` 요소를 만듭니다.  
  
5.  [\<security\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) [\<sslStreamSecurity\>](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) 요소 다음에 빈  요소를 만듭니다.  
  
6.  [\<sslStreamSecurity\>](../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) [\<tcpTransport\>](../../../../docs/framework/configure-apps/file-schema/wcf/tcptransport.md) 요소 다음에 빈 요소를 만듭니다.  
  
## 코드 샘플  
  
#### 3개의 바인딩에 대한 샘플  
  
1.  구성 파일에 다음 코드를 삽입합니다.  
  
## 예제  
  
```  
  
<bindings>  
   <customBinding>  
      <binding name="FederationDuplexHttpMessageSecurityBinding">  
<!-- duplex contract requires secure conversation with require cancellation = true -->  
          <security authenticationMode="SecureConversation">  
              <secureConversationBootstrap authenticationMode="IssuedTokenForSslNegotiated" />  
          </security>  
          <compositeDuplex />  
          <oneWay />  
          <httpTransport />  
       </binding>  
<!-- duplex over https is not supported -->  
       <binding name="FederationDuplexTcpMessageSecurityBinding">  
<!-- duplex contract requires secure conversation with require cancellation = true -->  
          <security authenticationMode="SecureConversation">  
              <secureConversationBootstrap authenticationMode="IssuedTokenForSslNegotiated" />  
          </security>  
          <tcpTransport />  
       </binding>              
       <binding name="FederationDuplexTcpTransportSecurityWithMessageCredentialsBinding">  
<!-- duplex contract requires secure conversation with require cancellation = true -->  
          <security authenticationMode="SecureConversation">  
              <secureConversationBootstrap authenticationMode="IssuedTokenOverTransport" />  
          </security>  
<!-- requireClientCertificate = true or <windowsStreamSecurity /> can be used, but does not make sense for most scenarios -->  
          <sslStreamSecurity />  
          <tcpTransport />  
       </binding>              
    </customBinding>  
</bindings>  
  
```