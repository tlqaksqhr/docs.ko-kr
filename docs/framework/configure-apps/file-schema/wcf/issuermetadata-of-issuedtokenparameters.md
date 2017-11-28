---
title: "&lt;issuedTokenParameters&gt;의 &lt;issuerMetadata&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1a85ca37-496d-4fa3-8d44-d6c9383d735c
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 9e8df1ffb74c59bfed2b9fa2f1e87e7669fe3ad9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltissuermetadatagt-of-ltissuedtokenparametersgt"></a>&lt;issuedTokenParameters&gt;의 &lt;issuerMetadata&gt;
\<system.serviceModel >  
\<바인딩 >  
\<customBinding >  
\<바인딩 >  
\<보안 >  
\<r s >  
\<issuerMetadata >  
  
## <a name="syntax"></a>구문  
  
```xml  
<issuerMetaData address=String"/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|address|필수 요소. 끝점의 주소를 지정하는 문자열입니다. 주소는 절대 URI이어야 합니다. 기본값은 빈 문자열입니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<헤더 >](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|주소 헤더 컬렉션입니다.|  
|[\<identity >](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|한 끝점에서 다른 끝점과 메시지를 교환할 때 상대 끝점을 인증할 수 있도록 하는 ID입니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<r s >](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md)|페더레이션 보안 시나리오에서 발급된 보안 토큰에 대한 매개 변수를 지정합니다.|  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>  
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [서비스 Id 및 인증](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [페더레이션 및 발급 된 토큰](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [사용자 지정 바인딩 사용 하는 보안 기능](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [페더레이션 및 발급 된 토큰](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [바인딩](../../../../../docs/framework/wcf/bindings.md)  
 [바인딩 확장](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [사용자 지정 바인딩](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [\<customBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [방법: SecurityBindingElement를 사용 하 여 사용자 지정 바인딩을 만들려면](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [사용자 지정 바인딩 보안](../../../../../docs/framework/wcf/samples/custom-binding-security.md)
