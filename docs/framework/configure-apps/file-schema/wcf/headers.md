---
title: '&lt;헤더&gt;'
ms.date: 03/30/2017
ms.assetid: c79b897d-8ea3-40b5-a8b6-2471941f7ed3
ms.openlocfilehash: 7683b07093719cda6b210a4174d47e5785d4644d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32747153"
---
# <a name="ltheadersgt"></a>&lt;헤더&gt;
하나 이상의 SOAP 헤더와 해당 기본 URI로 끝점에 주소를 지정할 수 있습니다. 이 유용한 하나의 시나리오 집합이 SOAP 매개 시나리오 집합입니다. 이 시나리오 집합에서는 끝점에 매개자를 대상으로 한 SOAP 헤더를 포함할 해당 끝점의 클라이언트가 필요합니다. 이 구성 요소는 그러한 사용자 지정 주소 헤더를 정의하는 데 사용할 수 있습니다. 끝점 헤더 컬렉션의 항목은 사용자 정의 XML 요소입니다. 각 요소는 올바른 형식의 XML이어야 합니다.  
  
 \<system.ServiceModel>  
\<client>  
\<endpoint>  
  
## <a name="syntax"></a>구문  
  
```xml  
<headers>  
    <Region xmlns="Uri">"String"</Region>  
        <Member xmlns="Uri">"String"</Member>  
</headers>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
 없음  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|Region||  
|멤버||  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<endpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-of-client.md)|다양한 형식의 끝점을 구성합니다.|  
  
## <a name="remarks"></a>설명  
 선택적 헤더는 끝점을 확인하거나 상호 작용하는 데 필요한 자세한 주소 지정 정보를 제공합니다. 예를 들어 헤더는 들어오는 메시지를 처리하는 방법, 끝점이 회신 메시지를 보내야 하는 위치 또는 여러 인스턴스를 사용할 수 있는 경우 특정 사용자의 들어오는 메시지를 처리하는 데 사용할 서비스 인스턴스를 나타낼 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Headers%2A>  
 <xref:System.ServiceModel.Channels.AddressHeaderCollection>  
 [끝점: 주소, 바인딩 및 계약](../../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
