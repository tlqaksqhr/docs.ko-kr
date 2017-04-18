---
title: "&lt;custom&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a6f65a00-bd1a-4d4a-955a-fe009ec02ab8
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# &lt;custom&gt;
사용자 지정 피어 확인자 서비스의 설정을 지정합니다.  
  
## 구문  
  
```  
  
<custom address="Uri"  
   resolverType="String">  
      <headers/>  
   <identity/>  
</peerResolver>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`address`|사용자 지정 피어 확인자 서비스를 호스트하는 피어 노드의 끝점 주소를 지정하는 URI입니다.|  
|`resolverType`|사용자 지정 피어 확인자 서비스의 형식을 지정하는 문자열입니다.|  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[\<identity\>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|이 요소로 구성된 사용자 지정 피어 확인자의 ID를 지정합니다.  이 요소는 <xref:System.ServiceModel.Configuration.IdentityElement> 형식입니다.|  
|[\<headers\>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|사용자 지정 피어 확인자에서 처리하는 SOAP 메시지에 사용되는 주소 헤더 컬렉션입니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<resolver\>](../../../../../docs/framework/configure-apps/file-schema/wcf/resolver.md)|메시에 참여하는 몇 개의 노드를 나타내는 피어 노드 주소 집합에 대한 피어 메시 ID를 확인하는 데 사용되는 피어 확인자입니다.|  
  
## 설명  
 이 요소는 서비스를 호스트하는 피어의 끝점 주소 및 모든 특정 바인딩 설정을 포함하여 사용자 지정 피어 확인자 서비스에 대한 기본 설정을 정의합니다.  사용자 지정 확인자를 만드는 방법에 대한 자세한 내용은 [Adding a Custom Resolver to a PeerChannel Application](http://msdn.microsoft.com/ko-kr/12aa3787-2962-439c-ad27-46523c8b0419)를 참조하세요.  
  
## 참고 항목  
 <xref:System.Servicemodel.PeerResolvers.CustomPeerResolverService>   
 <xref:System.ServiceModel.PeerResolvers.PeerCustomResolverSettings>   
 <xref:System.ServiceModel.Configuration.PeerResolverElement.Custom%2A>   
 <xref:System.ServiceModel.Configuration.PeerCustomResolverElement>   
 [피어 확인자](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)   
 [Adding a Custom Resolver to a PeerChannel Application](http://msdn.microsoft.com/ko-kr/12aa3787-2962-439c-ad27-46523c8b0419)