---
title: "방법: 보안 세션 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "보안 [WCF], 세션 만들기"
ms.assetid: b6f42b5a-bbf7-45cf-b917-7ec9fa7ae110
caps.latest.revision: 10
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 10
---
# 방법: 보안 세션 만들기
[\<basicHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) 바인딩을 제외하고, [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]에 시스템이 제공하는 바인딩에서는 메시지 보안이 활성화된 경우 자동으로 보안 세션을 사용합니다.  
  
 기본적으로 보안 세션은 재생된 웹 서버에 남지 않습니다.  보안 세션이 설정되면 클라이언트와 서비스에서 보안 세션과 연결된 키를 캐시합니다.  메시지를 교환하면 캐시된 키의 식별자만 교환됩니다.  웹 서버가 재생되면 캐시도 재생되며, 이 때 웹 서버는 식별자의 캐시된 키를 검색할 수 없습니다.  이런 경우가 발생하면 클라이언트로 예외가 throw됩니다.  상태 저장 SCT\(보안 컨텍스트 토큰\)을 사용하는 보안 세션은 웹 서버가 재생되는 동안 보안 세션을 유지할 수 있습니다.  보안 세션에서 상태 저장 SCT 사용에 대한 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]는 [방법: 보안 세션에 대한 보안 컨텍스트 토큰 만들기](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md)를 참조하세요.  
  
### 서비스에서 시스템에서 제공되는 바인딩 중 하나를 사용하여 보안 세션을 사용하도록 지정하려면  
  
-   메시지 보안을 지원하는 시스템 제공 바인딩을 사용하도록 서비스를 구성합니다.  
  
     [\<basicHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) 바인딩을 제외하고, 시스템이 제공하는 바인딩이 메시지 보안을 사용하도록 구성되어 있으면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 자동으로 보안 세션을 사용합니다.  다음 표에는 메시지 보안을 지원하는 시스템 제공 바인딩과 메시지 보안이 기본 보안 메커니즘인지 여부가 표시되어 있습니다.  
  
    |시스템 제공 바인딩|구성 요소|기본적으로 메시지 보안 사용|  
    |----------------|-----------|---------------------|  
    |<xref:System.ServiceModel.BasicHttpBinding>|[\<basicHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)|아니요|  
    |<xref:System.ServiceModel.WSHttpBinding>|[\<wsHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)|예|  
    |<xref:System.ServiceModel.WSDualHttpBinding>|[\<wsDualHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md)|예|  
    |<xref:System.ServiceModel.WSFederationHttpBinding>|[\<wsFederationHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)|예|  
    |<xref:System.ServiceModel.NetTcpBinding>|[\<netTcpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)|아니요|  
    |<xref:System.ServiceModel.NetMsmqBinding>|[\<netMsmqBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md)|아니요|  
  
     다음 코드 예제에서는 구성을 사용하여 이름이 `wsHttpBinding_Calculator`이고 [\<wsHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), 메시지 보안 및 보안 세션을 사용하는 바인딩을 지정합니다.  
  
    ```  
    <bindings>  
      <WSHttpBinding>  
       <binding name = "wsHttpBinding_Calculator">  
         <security mode="Message">  
           <message clientCredentialType="Windows"/>  
         </security>  
        </binding>  
      </WSHttpBinding>  
    </bindings>  
    ```  
  
     다음 코드 예제에서는 [\<wsHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), 메시지 보안 및 보안 세션을 사용하여 `secureCalculator` 서비스를 보호하도록 지정합니다.  
  
     [!code-csharp[c_CreateSecureSession#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_createsecuresession/cs/secureservice.cs#1)]
     [!code-vb[c_CreateSecureSession#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_createsecuresession/vb/secureservice.vb#1)]  
  
    > [!NOTE]
    >  [\<wsHttpBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)의 보안 세션은 `establishSecurityContext` 특성을 `false`로 설정하여 끌 수 있습니다.  다른 시스템 제공 바인딩의 경우 사용자 지정 바인딩을 만들어야만 보안 세션을 끌 수 있습니다.  
  
### 사용자 지정 바인딩을 사용하여 서비스에서 보안 세션을 사용하도록 지정하려면  
  
-   보안 세션을 통해 SOAP 메시지를 보호하도록 지정하는 사용자 지정 바인딩을 만듭니다.  
  
     사용자 지정 바인딩을 만드는 경우에 대한 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]는 [방법: 시스템 제공 바인딩 사용자 지정](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md)을 참조하세요.  
  
     다음 코드 예제에서는 구성을 사용하여 보안 세션을 통해 메시지를 전송하는 사용자 지정 바인딩을 지정합니다.  
  
    ```  
    <bindings>  
      <!-- configure a custom binding -->  
      <customBinding>  
        <binding name="customBinding_Calculator">  
          <security authenticationMode="SecureConversation" />  
          <secureConversationBootstrap authenticationMode="SspiNegotiated" />  
          <textMessageEncoding messageVersion="Soap12WSAddressing10" writeEncoding="utf-8"/>  
          <httpTransport/>  
        </binding>  
      </customBinding>  
    </bindings>  
    ```  
  
     다음 코드 예제에서는 <xref:System.ServiceModel.Configuration.AuthenticationMode> 인증 모드를 사용하여 보안 세션을 부트스트랩하는 사용자 지정 바인딩을 만듭니다.  
  
     [!code-csharp[c_CreateSecureSession#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_createsecuresession/cs/secureservice.cs#2)]
     [!code-vb[c_CreateSecureSession#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_createsecuresession/vb/secureservice.vb#2)]  
  
## 참고 항목  
 [WCF 바인딩 개요](../../../../docs/framework/wcf/bindings-overview.md)