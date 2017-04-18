---
title: "&lt;servicePrincipalName&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3f3b85d3-20f2-4cd8-8a6a-ee18befbd165
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# &lt;servicePrincipalName&gt;
SPN\(서비스 사용자 이름\)으로 서비스 ID를 지정합니다.  
  
 SPN 설정에 대한 자세한 내용은 [서비스 ID 및 인증](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)을 참조하세요.  
  
## 구문  
  
```  
  
<servicePrincipalName value = "String" />  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|값|클라이언트에서 서비스의 인스턴스를 고유하게 식별하는 이름입니다.  포리스트를 통해 컴퓨터에 여러 서비스 인스턴스를 설치하는 경우 각 인스턴스에 고유한 SPN이 있어야 합니다.  클라이언트에서 인증에 사용할 수 있는 이름이 여러 개인 경우 지정한 서비스 인스턴스에 여러 개의 SPN이 있을 수 있습니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<identity\>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|클라이언트에서 인증할 서비스의 ID를 지정합니다.|  
  
## 설명  
 이 ID를 가진 끝점과 연결되는 보안 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 클라이언트는 이 끝점에 대해 SSPI 인증을 수행할 때 SPN을 사용합니다.  
  
## 참고 항목  
 <xref:System.ServiceModel.Configuration.IdentityElement>   
 <xref:System.ServiceModel.EndpointAddress>   
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>   
 <xref:System.ServiceModel.SpnEndpointIdentity>   
 [서비스 ID 및 인증](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)   
 [\<identity\>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)