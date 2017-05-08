---
title: "&lt;endpointDiscovery&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 70812717-888a-4748-9640-0df6715ff029
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# &lt;endpointDiscovery&gt;
검색 기능, 범위 및 해당 메타데이터에 대한 사용자 지정 확장 등 끝점에 대한 다양한 검색 설정을 지정합니다.  
  
## 구문  
  
```  
  
<behaviors>  
  <endpointBehaviors>  
    <behavior name="String">  
      <endpointDiscovery enabled="Boolean">  
        <scopes>  
          <add scope="URI"/>  
        </scopes>  
        <extensions>  
        </extensions>  
      </endpointDiscovery>  
    </behavior>  
  </endpointBehaviors>  
</behaviors>  
  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|사용|이 끝점에서 검색 기능을 사용하는지 여부를 지정하는 부울 값입니다.  기본값은 `false`입니다.|  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[\<scopes\>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)|끝점에 대한 범위 URI의 컬렉션입니다.  단일 끝점에 둘 이상의 범위 URI를 연결할 수 있습니다.|  
|[\<extensions\>](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md) \[\<endpointDiscovery\>의\]|끝점에 대해 게시되는 사용자 지정 메타데이터를 지정할 수 있는 XML 요소의 컬렉션입니다.|  
|\<types\>|검색할 인터페이스의 컬렉션입니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<behavior\>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|동작 요소를 지정합니다.|  
|||  
  
## 설명  
 끝점의 동작 구성에 추가되고 `enabled` 특성이 `true`로 설정되면 이 구성 요소에 대한 검색 기능을 사용할 수 있습니다.  또한 [\<scopes\>](../../../../../docs/framework/configure-apps/file-schema/wcf/scopes.md)[\<extensions\>](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions.md) 자식 요소를 사용하여 표준 검색 가능 메타데이터\(EPR, ContractTypeName, BindingName, Scope 및 ListenURI\)와 함께 게시되어야 하는 사용자 지정 메타데이터를 지정할 수 있습니다.  
  
 이 구성 요소는 검색 기능의 서비스 수준 제어를 제공하는 [\<serviceDiscovery\>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md) 요소에 종속됩니다.  즉, 구성에 [\<serviceDiscovery\>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicediscovery.md)가 있는 경우 이 요소의 설정이 무시됩니다.  
  
## 예제  
 다음 구성 예제에서는 필터링 범위 및 끝점에 게시되는 확장 메타데이터를 지정합니다.  
  
```  
  
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
  
## 참고 항목  
 <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior>