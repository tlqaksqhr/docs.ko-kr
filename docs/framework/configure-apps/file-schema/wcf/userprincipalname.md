---
title: "&lt;userPrincipalName&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 68032f69-149e-4613-bae4-18314d4fd294
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# &lt;userPrincipalName&gt;
클라이언트에서 인증할 서비스의 UPN\(User Principal Name\)을 지정합니다.  
  
 UPN 설정에 대한 자세한 내용은 [서비스 ID 및 인증](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)을 참조하세요.  
  
## 구문  
  
```  
  
<userPrincipalName value = "String" />  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|값|사용자 로그온 이름이라고도 하는 사용자 계정 이름 및 사용자 계정이 있는 도메인을 나타내는 도메인 이름입니다.  Windows 도메인에 로그온하는 표준 사용법입니다.  전자 메일 주소의 경우 someone@example.com 형식입니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<identity\>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|클라이언트에서 인증할 서비스의 ID를 지정합니다.|  
  
## 설명  
 이 ID를 가진 끝점과 연결되는 보안 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 클라이언트는 이 끝점에 대해 SSPI 인증을 사용할 때 UPN을 사용합니다.  
  
## 예제  
 다음 구성 코드는 클라이언트에서 인증할 서비스의 UPN을 지정합니다.  
  
```  
<identity>  
  <userPrincipalName value="someone@cohowinery.com" />  
</identity>  
```  
  
## 참고 항목  
 <xref:System.ServiceModel.Configuration.IdentityElement>   
 <xref:System.ServiceModel.EndpointAddress>   
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>   
 <xref:System.ServiceModel.UpnEndpointIdentity>   
 [서비스 ID 및 인증](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)   
 [\<identity\>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)