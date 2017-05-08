---
title: "&lt;identity&gt;에 대한 &lt;certificate&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4aeccaf7-8f23-495c-aa5f-5bd8b5d4a10c
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# &lt;identity&gt;에 대한 &lt;certificate&gt;
클라이언트에 서버의 유효성을 검사하는 데 사용되는 X.509 인증서를 지정합니다.  
  
 요소 값 설정에 대한 자세한 내용은 [서비스 ID 및 인증](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)을 참조하세요.  
  
## 구문  
  
```  
  
<certificate encodedValue = "Sring" />  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|encodedValue|인증서의 Base64 인코딩입니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<identity\>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|클라이언트에서 인증할 서비스의 ID를 지정합니다.|  
  
## 예제  
 다음 코드에서는 클라이언트에 서버의 유효성을 검사하는 데 사용되는 인코딩된 인증서 표현을 지정합니다.  
  
```  
<identity>  
  <certificate encodedValue = " MIIBxjCCAXSgAwIBAgIQmXJgyu9tro1M98GifjtuoDAJBgUrDgMCHQUAMBYxFDASBgNVBAMTC1Jvb3QgQWdlbmN5MB4XDTA2MDUxNzIxNDQyNVoXDTM5MTIzMTIzNTk1OVowKTEQMA4GA1UEChMHQ29udG9zbzEVMBMGA1UEAxMMaWRlbnRpdHkuY29tMIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQDBmivcb8hYbh11hqVoDuB7zmJ2y230f" />  
</identity>  
```  
  
## 참고 항목  
 <xref:System.ServiceModel.Configuration.IdentityElement>   
 <xref:System.ServiceModel.EndpointAddress>   
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>   
 <xref:System.ServiceModel.EndpointIdentity>   
 [서비스 ID 및 인증](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)   
 [\<identity\>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)