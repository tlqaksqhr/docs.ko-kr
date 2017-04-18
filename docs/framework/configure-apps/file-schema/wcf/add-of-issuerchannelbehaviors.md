---
title: "&lt;issuerChannelBehaviors&gt;의 &lt;add&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 50710506-e28f-45dd-ab7e-bff6f44173db
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# &lt;issuerChannelBehaviors&gt;의 &lt;add&gt;
STS와 통신할 때 사용할 끝점 동작을 추가합니다.  
  
> [!NOTE]
>  끝점 동작에 [\<clientCredentials\>](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) 요소가 포함되면 예외가 throw됩니다.  
  
## 구문  
  
```  
  
<add issuerAddress="string"  
     behaviorConfiguraton="string" />  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|issuerAddress|통신할 보안 토큰 발급자의 URI입니다.|  
|behaviorConfiguration|동일한 구성 파일에 정의된 끝점 동작 이름입니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<issuerChannelBehaviors\>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)|지정한 서비스 토큰 서비스와 통신할 때 사용할 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 클라이언트 끝점 동작 컬렉션을 포함합니다.|  
  
## 설명  
 `issuerAddress`는 클라이언트가 통신하려는 보안 토큰 서비스의 URI를 포함합니다.  `behaviorConfiguration`은 발급된 토큰을 보안 토큰 서비스에서 가져오기 위해 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]가 만든 채널에서 응용 프로그램이 사용하는 끝점 동작을 가리킵니다.  
  
## 참고 항목  
 <xref:System.ServiceModel.Configuration.IssuedTokenClientElement.IssuerChannelBehaviors%2A>   
 <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElement>   
 <xref:System.ServiceModel.Configuration.IssuedTokenClientBehaviorsElementCollection>   
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential.IssuerChannelBehaviors%2A>   
 [서비스 ID 및 인증](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)   
 [보안 동작](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)   
 [페더레이션 및 발급된 토큰](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)   
 [서비스 및 클라이언트에 보안 설정](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [클라이언트에 보안 설정](../../../../../docs/framework/wcf/securing-clients.md)   
 [방법: 페더레이션 클라이언트 만들기](../../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)   
 [방법: 로컬 발급자 구성](../../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)   
 [페더레이션 및 발급된 토큰](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)   
 [\<issuerChannelBehaviors\>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)