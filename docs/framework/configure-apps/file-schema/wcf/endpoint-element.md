---
title: '&lt;endpoint&gt; 요소'
ms.date: 03/30/2017
ms.assetid: 2fc8fedc-78d0-4e87-8142-fbfd26c15a4e
ms.openlocfilehash: ef436acca40eaac135a54042b62abd76ec55febf
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltendpointgt-element"></a>&lt;endpoint&gt; 요소
서비스 공개에 사용되는 서비스 끝점에 대한 바인딩, 계약 및 주소 속성을 지정합니다.  
  
 \<system.ServiceModel>  
\<서비스 >  
\<endpoint>  
  
## <a name="syntax"></a>구문  
  
```xml  
<endpoint address="String"  
   behaviorConfiguration="String"  
   binding="String"  
   bindingConfiguration="String"  
   bindingName="String"  
   bindingNamespace="String"  
   contract="String"  
   endpointConfiguration="String"   isSystemEndpoint="Boolean"   kind="String"   listenUriMode="Explicit/Unique"  
   listenUri="Uri"  
</endpoint>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|address|끝점의 주소를 포함하는 문자열입니다. 주소는 절대 주소 또는 상대 주소로 지정할 수 있습니다. 상대 주소가 제공되는 경우 호스트는 바인딩에 사용된 전송 체계에 적합한 기본 주소를 제공합니다. 주소가 구성되지 않으면 해당 끝점의 주소를 기본 주소로 가정합니다.<br /><br /> 기본값은 빈 문자열입니다.|  
|behaviorConfiguration|끝점에 사용할 동작의 이름을 포함하는 문자열입니다.|  
|바인딩|사용할 바인딩 형식을 지정하는 필수 문자열 특성입니다. 형식에 등록된 구성 섹션이 있어야 형식을 참조할 수 있습니다. 이 형식은 바인딩의 형식 이름이 아니라 섹션 이름으로 등록됩니다.|  
|bindingConfiguration|끝점이 인스턴스화될 때 사용하는 바인딩의 바인딩 이름을 지정하는 문자열입니다. 바인딩 이름은 끝점이 정의된 지점의 범위에 속해야 합니다. 기본값은 빈 문자열입니다.<br /><br /> 이 특성은 구성 파일에서 특정 바인딩 구성을 참조하기 위해 `binding`과 함께 사용됩니다. 사용자 지정 바인딩을 사용하려는 경우 이 특성을 설정하세요. 그렇지 않으면 예외가 throw될 수 있습니다.|  
|bindingName|WSDL을 통해 정의를 내보내기 위한 바인딩의 정규화된 고유 이름을 지정하는 문자열입니다. 기본값은 빈 문자열입니다.|  
|bindingNamespace|WSDL을 통해 정의를 내보내기 위한 바인딩 네임스페이스의 정규화된 이름을 지정하는 문자열입니다. 기본값은 빈 문자열입니다.|  
|계약(contract)|이 끝점이 공개하는 계약을 나타내는 문자열입니다. 어셈블리는 계약 형식을 구현해야 합니다. 서비스 구현에서 단일 계약 형식을 구현하는 경우 이 속성을 생략할 수 있습니다. 기본값은 빈 문자열입니다.|  
|endpointConfiguration|이 표준 끝점의 추가 구성 정보를 참조하는 `kind` 특성에 의해 설정되는 표준 끝점의 이름을 지정하는 문자열입니다. 이와 동일한 이름이 `<standardEndpoints>` 섹션에서 정의되어야 합니다.|  
|isSystemEndpoint|끝점이 인프라 끝점인지 여부를 지정하는 부울 값입니다.|  
|kind|적용되는 표준 끝점의 형식을 지정하는 문자열입니다. 이 형식이 `<extensions>` 섹션 또는 machine.config에 등록되어야 합니다. 지정하지 않으면 일반 서비스 끝점이 만들어집니다.|  
|listenUriMode|서비스에서 수신하도록 제공된 `ListenUri`를 전송에서 처리하는 방법을 지정합니다. 유효한 값은 다음과 같습니다.<br /><br /> 명시적<br />고유<br /><br /> 기본값은 Explicit입니다.|  
|listenUri|서비스 끝점이 수신하는 URI를 지정하는 문자열입니다. 기본값은 빈 문자열입니다.|  
|name|선택적 특성입니다. 서비스 끝점의 이름을 지정하는 문자열입니다. 기본값은 바인딩 이름과 계약 설명 이름을 연결한 값입니다. 서비스에 끝점이 여러 개일 수 있으므로 끝점의 `name` 특성은 서비스 이름과 구분됩니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<headers>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)|주소 헤더 컬렉션입니다.|  
|[\<identity>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|한 끝점에서 다른 끝점과 메시지를 교환할 때 상대 끝점을 인증할 수 있도록 하는 ID입니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<service>](../../../../../docs/framework/configure-apps/file-schema/wcf/service.md)|클라이언트가 연결할 수 있는 끝점의 목록을 정의하는 구성 섹션입니다.|  
  
## <a name="example"></a>예제  
 서비스 끝점 구성의 예제입니다.  
  
```xml  
<endpoint   
    address="/HelloWorld/"  
    bindingConfiguration="usingDefaults"  
    bindingName="MyBinding"  
    binding="customBinding"  
    contract="HelloWorld">  
    <Headers>  
       <Region xmlns="http://tempuri.org/">EastCoast</Region>  
       <Member xmlns="http://tempuri.org/">Gold</Member>  
    </Headers>  
</endpoint>  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Configuration.ServiceEndpointElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.Description.ServiceEndpoint>  
 [끝점: 주소, 바인딩 및 계약](../../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)  
 [방법: 구성에서 서비스 끝점 만들기](../../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)
