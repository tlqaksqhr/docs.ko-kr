---
title: "&lt;endpointExtensions&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 33396e0a-1fae-4616-b822-923584eebfd1
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# &lt;endpointExtensions&gt;
이 섹션에서는 새 표준 끝점을 컴퓨터 또는 응용 프로그램 구성 파일의 extensions 섹션에 등록합니다.  `add` 키워드를 사용하고 요소의 `type` 특성을 해당 끝점 형식으로 설정하고, `name` 특성을 표준 끝점의 이름으로 설정하여 표준 끝점을 이 컬렉션에 추가할 수 있습니다.  
  
 다음 예제에서는 `add` 요소와 `name` 특성을 사용하여 구성 파일의 `<endpointExtensions>` 섹션에 표준 끝점을 추가합니다.  
  
```  
<system.serviceModel>  
    <extensions>  
        <endpointExtensions>  
           <add name="udpDiscoveryEndpoint"  
                type="System.Discovery.UdpEndpointCollectionElement, System.Discovery.dll, Version=1.0.0.0, Culture=neutral, PublicKeyToken=ffffffffffffffff"/>  
        </endpointExtensions>   
    </extensions>  
</system.serviceModel>  
```  
  
 표준 끝점을 등록한 다음 이를 다음 예제와 같이 사용할 수 있습니다.  [\<endpoint\>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) 요소에서는 `kind` 특성이 `<endpointExtensions>` 섹션에 등록된 표준 끝점 형식을 지정합니다.  `endpointConfiguration` 특성은 `<standardEndpoints>`섹션에 있는 표준 끝점 구성 요소의 `name` 특성과 동일합니다.  
  
```  
  
<system.serviceModel>  
    <services>  
      <service name="Service1">  
        <endpoint kind="udpDiscoveryEndpoint"  
                  endpointConfiguration="udpConfig" />  
      </service>  
    </services>  
    <standardEndpoints>  
      <udpDiscoveryEndpoint>  
        <standardEndpoint  
                  name="udpConfig"  
                  multicastAddress="soap.udp://239.255.255.250:3703"  
                  ... />  
      </udpDiscoveryEndpoint>  
    </standardEndpoints>  
  </system.serviceModel>  
  
```