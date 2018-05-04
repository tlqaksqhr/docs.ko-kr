---
title: '&lt;endpointDiscovery&gt;'
ms.date: 03/30/2017
ms.assetid: 70812717-888a-4748-9640-0df6715ff029
ms.openlocfilehash: c5971ce79ac2f03fbdc91653d5d282804e98cf8a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltendpointdiscoverygt"></a>&lt;endpointDiscovery&gt;
검색 기능, 범위 및 해당 메타데이터에 대한 사용자 지정 확장명 등 끝점에 대한 다양한 검색 설정을 지정합니다.  
  
\<system.ServiceModel>  
\<동작 >  
\<endpointBehaviors>  
\<동작 >  
\<endpointDiscovery >  
  
## <a name="syntax"></a>구문  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="String">
      <endpointDiscovery enabled="Boolean">
        <scopes>
          <add scope="URI"/>
        </scopes>
        <extensions />
      </endpointDiscovery>
    </behavior>
  </endpointBehaviors>
</behaviors>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|사용|이 끝점에서 검색 기능을 사용하는지 여부를 지정하는 부울 값입니다. 기본값은 `false`입니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<범위 >](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)|끝점에 대한 범위 URI의 컬렉션입니다. 단일 끝점에 둘 이상의 범위 URI를 연결할 수 있습니다.|  
|[\<확장 >](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md) [의 \<endpointDiscovery >]|끝점에 대해 게시되는 사용자 지정 메타데이터를 지정할 수 있는 XML 요소의 컬렉션입니다.|  
|\<유형 >|검색할 인터페이스의 컬렉션입니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<동작 >](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|동작 요소를 지정합니다.|  
|||  
  
## <a name="remarks"></a>설명  
 끝점의 동작 구성에 추가되고 `enabled` 특성이 `true`로 설정되면 이 구성 요소에 대한 검색 기능을 사용할 수 있습니다. 또한 사용할 수 있습니다는 [ \<범위 >](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)자식 요소가 사용자 지정 범위 쿼리 중 서비스 끝점을 필터링 하기 위해 사용할 수 있는 Uri를 지정 하는 것과 같이 [ \<확장 >](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md) 표준 검색 가능 메타 데이터 (EPR, ContractTypeName, BindingName, 범위 및 ListenURI)와 함께 게시 해야 하는 사용자 지정 메타 데이터를 지정 하는 자식 요소입니다.  
  
 이 구성 요소에 따라 달라 집니다.는 [ \<serviceDiscovery >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) 검색 기능의 서비스 수준 제어를 제공 하는 요소입니다. 이 의미 하는 경우이 요소의 설정이 무시 됩니다 [ \<serviceDiscovery >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) 구성에 나타나지 않습니다.  
  
## <a name="example"></a>예제  
 다음 구성 예제에서는 필터링 범위 및 끝점에 게시되는 확장명 메타데이터를 지정합니다.  
  
```xml  
<services>  
  <service name="CalculatorService"  
           behaviorConfiguration="CalculatorServiceBehavior">  
     <endpoint binding="basicHttpBinding"  
              address="calculator"  
              contract="ICalculatorService"  
              behaviorConfiguration="calculatorEndpointBehavior" />  
  </service>  
</services>  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="CalculatorServiceBehavior">  
      <serviceDiscovery />  
    </behavior>  
  </serviceBehaviors>  
  <endpointBehaviors>  
    <behavior name="calculatorEndpointBehavior">  
      <endpointDiscovery enabled="true">  
        <scopes>  
          <add scope="http://contoso/test1"/>  
          <add scope="http://contoso/test2"/>  
        </scopes>  
        <extensions>  
          <e:Publisher xmlns:e="http://example.org">  
            <e:Name>The Example Organization</e:Name>  
            <e:Address>One Example Way, ExampleTown, EX 12345</e:Address>  
            <e:Contact>support@example.org</e:Contact>  
          </e:Publisher>  
          <AnotherCustomMetadata>Custom Metadata</AnotherCustomMetadata>  
        </extensions>  
      </endpointDiscovery>  
    </behavior>  
  </endpointBehaviors>  
</behaviors>  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>
