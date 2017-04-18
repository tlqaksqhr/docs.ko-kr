---
title: "&lt;transportConfigurationType&gt;의 &lt;add&gt; | Microsoft Docs"
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
ms.assetid: 03d79db9-571d-4534-acef-d05e5467b257
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# &lt;transportConfigurationType&gt;의 &lt;add&gt;
이 요소는 특정 전송 형식을 식별하는 키\/값 쌍입니다.  
  
## 구문  
  
```  
  
<serviceHostingEnvironment>   
   <transportConfigurationTypes>  
      <add name="String"  
               transportConfigurationType="String"/>   
   </transportConfigurationTypes>  
</serviceHostingEnvironment>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|name|필수 문자열 특성입니다.<br /><br /> 전송 형식을 고유하게 식별하는 사용자 정의 키를 포함합니다.|  
|transportConfigurationType|특정 전송을 구현하는 형식을 포함하는 문자열입니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<transportConfigurationTypes\>](../../../../../docs/framework/configure-apps/file-schema/wcf/transportconfigurationtypes.md)|특정 전송을 구현하는 형식의 컬렉션입니다.|  
  
## 예제  
  
```  
<serviceHostingEnvironment>   
   <transportConfigurationTypes>  
      <add name="net.udp"  
      transportConfigurationType="Microsoft.ServiceModel.Samples.Hosting.HostedUdpTransportConfiguration, UdpActivation, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6fa904d2da1848d6" />   
   </transportConfigurationTypes>  
</serviceHostingEnvironment>  
```  
  
## 참고 항목  
 <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElement>   
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>   
 <xref:System.ServiceModel.ServiceHostingEnvironment>   
 [호스팅](../../../../../docs/framework/wcf/feature-details/hosting.md)