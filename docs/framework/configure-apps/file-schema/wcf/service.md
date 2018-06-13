---
title: '&lt;서비스&gt;'
ms.date: 03/30/2017
ms.assetid: 13123dd6-c4a9-4a04-a984-df184b851788
ms.openlocfilehash: 6e83e988920d24c6fe7615e40334919caf21652e
ms.sourcegitcommit: ff1d40507b3eb6e2185478e37c66c66be6de46f1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2018
ms.locfileid: "34059032"
---
# <a name="ltservicegt"></a>&lt;서비스&gt;
`service` 요소에는 WCF(Windows Communication Foundation) 서비스 설정이 포함되어 있습니다. 이 요소에는 서비스를 공개하는 끝점도 포함되어 있습니다.  
  
 \<system.ServiceModel>  
\<services>  
\<서비스 >  
  
## <a name="syntax"></a>구문  
  
```xml  
<service behaviorConfiguration=String"  
        name="String">  
</service>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|behaviorConfiguration|서비스 인스턴스화에 사용할 동작의 동작 이름을 포함하는 문자열입니다. 동작 이름은 서비스가 정의된 지점의 범위에 속해야 합니다. 기본값은 빈 문자열입니다.|  
|name|인스턴스화할 서비스 형식을 지정하는 필수 문자열 특성입니다. 이 설정은 유효한 형식을 사용해야 하며, Namespace.Class`Namespace.Class.` 형식이어야 합니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<endpoint>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md)|이 서비스를 공개하는 `endpoint` 요소의 컬렉션입니다.|  
|[\<호스트 >](../../../../../docs/framework/configure-apps/file-schema/wcf/host.md)|이 서비스 인스턴스의 호스트를 지정합니다. 이 요소는 <xref:System.ServiceModel.Configuration.HostElement> 형식입니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<services>](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md)|모든 WCF 구성 요소의 루트 요소입니다.|  
  
## <a name="remarks"></a>설명  
 서비스는 구성 파일의 `services` 섹션에 정의됩니다. 어셈블리에는 여러 개의 서비스가 포함될 수 있습니다. 서비스별로 해당 `service` 구성 섹션이 있습니다. 이 단원 및 내용에서는 특정 서비스의 서비스 계약, 동작 및 끝점을 정의합니다.  
  
 `behaviorConfiguration` 요소도 선택적 항목입니다. 서비스가 사용하는 동작을 식별합니다. 이 특성에 지정된 동작은 동일한 구성 파일의 범위에 있는 동작에 연결되어야 합니다.  
  
 각 서비스는 하나 이상의 끝점을 노출하는데, 여기에는 자체 주소 및 바인딩이 있습니다. 구성 파일 내에서 사용되는 모든 바인딩은 파일 범위 내에서 정의되어야 합니다. 바인딩은 `name` 및 `bindingConfiguration` 특성 조합을 통해 끝점에 연결됩니다. `name` 특성은 바인딩이 정의된 섹션에 대해 설명합니다. `bindingConfiguration` 특성은 바인딩 섹션 내에서 사용되는 구성을 정의합니다. 바인딩 섹션에서는 여러 개의 구성을 정의할 수 있습니다.  
  
## <a name="example"></a>예제  
 서비스 구성의 예제입니다.  
  
```xml  
<service behaviorConfiguration="testChannelBehavior"   
     name="HelloWorld">  
     <endpoint   
        address="/HelloWorld2/"  
        name="test"  
        bindingNamespace="http://www.cohowinery.com/"  
        binding="basicHttpBinding"  
        contract="IHelloWorld" />  
</service>  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Configuration.ServiceElement>  
 [서비스 구성](../../../../../docs/framework/wcf/configuring-services.md)
