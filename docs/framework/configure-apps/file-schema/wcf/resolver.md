---
title: "&lt;resolver&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0c00200c-f135-4e5c-a024-76b72bcbc021
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# &lt;resolver&gt;
피어 메시 ID를 확인하는 데 사용되는 피어 확인자를 메시에 참여하는 몇 개의 노드를 나타내는 피어 노드 주소 집합에 지정합니다.  
  
## 구문  
  
```  
  
<resolver mode="Auto/Custom/Pnrp"  
   referralPolicy="DoNotShare/Service/Share">  
</resolver>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`mode`|이 서비스와 연결된 피어 확인자 인스턴스가 PNRP 관련 사용자 지정 확인자인지 아니면 자동으로 결정되는지 여부를 지정하는 문자열입니다.  이 특성은 <xref:System.ServiceModel.PeerResolvers.PeerResolverMode> 형식입니다.|  
|`referralPolicy`|피어 간에 조회를 공유하는 방법을 지정하는 문자열입니다.  이 특성은 <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy> 형식입니다.|  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[\<headers\>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)|사용자 지정 피어 확인자 서비스의 설정을 지정합니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<binding\>](../../../../../docs/framework/misc/binding.md)|[\<netPeerTcpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md)의 모든 바인딩 기능을 정의합니다.|  
  
## 설명  
 피어 이름 확인자는 피어 메시에 참여하는 피어 노드를 찾기 위해 피어 채널에서 사용하는 검색 서비스입니다.  또한 이 확인자는 피어 노드가 알려지고 피어 메시에서 사용할 수 있게 되는 메커니즘인 피어 메시를 통해 노드를 "등록"하는 데에도 사용됩니다.  피어 확인자에 대한 자세한 내용은 [피어 확인자](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)를 참조하세요.  
  
## 참고 항목  
 <xref:System.ServiceModel.PeerResolver>   
 <xref:System.ServiceModel.PeerResolvers.PeerResolverSettings>   
 <xref:System.ServiceModel.NetPeerTcpBinding.Resolver%2A>   
 <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Resolver%2A>   
 <xref:System.ServiceModel.Configuration.PeerResolverElement>   
 [피어 확인자](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)   
 [Adding a Custom Resolver to a PeerChannel Application](http://msdn.microsoft.com/ko-kr/12aa3787-2962-439c-ad27-46523c8b0419)