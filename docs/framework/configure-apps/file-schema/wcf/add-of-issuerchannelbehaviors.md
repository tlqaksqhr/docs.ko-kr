---
title: "&lt;issuerChannelBehaviors&gt;의 &lt;add&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 50710506-e28f-45dd-ab7e-bff6f44173db
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bf66b3d3b531ae41329aade6a416c330957d83c6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt-of-ltissuerchannelbehaviorsgt"></a>&lt;issuerChannelBehaviors&gt;의 &lt;add&gt;
STS와 통신할 때 사용할 끝점 동작을 추가합니다.  
  
> [!NOTE]
>  어떤 끝점 동작을 포함 하는 경우는 [ \<clientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md) 요소에서 예외가 throw 됩니다.  
  
 \<시스템입니다. ServiceModel >  
\<동작 >  
endpointBehaviors 섹션  
\<동작 >  
\<clientCredentials >  
\<issuedToken >  
\<issuerChannelBehaviors > 요소  
\<add>  
  
## <a name="syntax"></a>구문  
  
```xml  
<add issuerAddress="string"  
     behaviorConfiguraton="string" />  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|issuerAddress|통신할 보안 토큰 발급자의 URI입니다.|  
|behaviorConfiguration|동일한 구성 파일에 정의된 끝점 동작 이름입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<issuerChannelBehaviors >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)|지정한 서비스 토큰 서비스와 통신할 때 사용할 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 클라이언트 끝점 동작 컬렉션을 포함합니다.|  
  
## <a name="remarks"></a>설명  
 `issuerAddress`는 클라이언트가 통신하려는 보안 토큰 서비스의 URI를 포함합니다. `behaviorConfiguration`은 발급된 토큰을 보안 토큰 서비스에서 가져오기 위해 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]가 만든 채널에서 응용 프로그램이 사용하는 끝점 동작을 가리킵니다.  
  
## <a name="see-also"></a>참고 항목  
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
 [\<issuerChannelBehaviors >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuerchannelbehaviors-element.md)
