---
title: "&lt;client&gt;의 &lt;endpoint&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
ms.assetid: de6238ae-bbf8-48e9-a1b5-e24c0bea8afa
caps.latest.revision: 22
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 22
---
# &lt;client&gt;의 &lt;endpoint&gt;
클라이언트에서 서버의 서비스 끝점과 연결하는 데 사용하는 채널 끝점의 contract, binding 및 address 속성을 지정합니다.  
  
## 구문  
  
```  
  
<endpoint address="String"  
   behaviorConfiguration="String"  
   binding="String"  
   bindingConfiguration="String"  
   contract="String"  
   endpointConfiguration=”String”  
   kind=”String”  
   name="String"  
</endpoint>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|address|필수 문자열 특성입니다.<br /><br /> 끝점의 주소를 지정합니다.  기본값은 빈 문자열입니다.  주소는 절대 URI이어야 합니다.|  
|behaviorConfiguration|서비스를 인스턴스화할 때 사용할 동작의 이름을 포함하는 문자열입니다.  동작 이름은 서비스가 정의된 지점의 범위에 속해야 합니다.  기본값은 빈 문자열입니다.|  
|바인딩|필수 문자열 특성입니다.<br /><br /> 사용할 바인딩의 형식을 나타내는 문자열입니다.  형식에 등록된 구성 섹션이 있어야 형식을 참조할 수 있습니다.  이 형식은 바인딩의 형식 이름 대신 섹션 이름으로 등록됩니다.|  
|bindingConfiguration|선택 사항입니다.  끝점이 인스턴스화될 때 사용할 바인딩 구성의 이름을 포함하는 문자열입니다.  바인딩 구성은 끝점이 정의된 지점의 범위에 속해야 합니다.  기본값은 빈 문자열입니다.<br /><br /> 이 특성은 구성 파일에서 특정 바인딩 구성을 참조하기 위해 `binding`과 함께 사용됩니다.  사용자 지정 바인딩을 사용하려는 경우 이 특성을 설정하세요.  그렇지 않으면 예외가 throw될 수 있습니다.|  
|계약\(contract\)|필수 문자열 특성입니다.<br /><br /> 이 끝점이 공개하는 계약을 나타내는 문자열입니다.  어셈블리는 계약 형식을 구현해야 합니다.|  
|endpointConfiguration|이 표준 끝점의 추가 구성 정보를 참조하는 `kind` 특성에 의해 설정되는 표준 끝점의 이름을 지정하는 문자열입니다.  이와 동일한 이름이 `<standardEndpoints>` 섹션에서 정의되어야 합니다.|  
|kind|적용되는 표준 끝점의 형식을 지정하는 문자열입니다.  이 형식이 `<extensions>` 섹션 또는 machine.config에 등록되어야 합니다.  지정하지 않으면 일반 채널 끝점이 만들어집니다.|  
|name|선택적 문자열 특성입니다.  이 특성은 지정된 계약의 끝점을 고유하게 식별합니다.  지정한 계약 형식에 대해 여러 클라이언트를 정의할 수 있습니다.  각 정의는 고유한 구성 이름으로 식별됩니다.  이 특성을 생략하면 해당하는 끝점이 지정된 계약 형식과 연결된 기본 끝점으로 사용됩니다.  기본값은 빈 문자열입니다.<br /><br /> 바인딩의 `name` 특성은 WSDL을 통해 정의를 내보내는 데 사용됩니다.|  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[\<headers\>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)|주소 헤더 컬렉션입니다.|  
|[\<identity\>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|한 끝점에서 다른 끝점과 메시지를 교환할 때 상대 끝점을 인증할 수 있도록 하는 ID입니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<client\>](../../../../../docs/framework/configure-apps/file-schema/wcf/client.md)|클라이언트가 연결할 수 있는 끝점의 목록을 정의하는 구성 섹션입니다.|  
  
## 예제  
 이것은 채널 끝점 구성의 예제입니다.  
  
```  
<endpoint address="/HelloWorld/"  
    bindingConfiguration="usingDefaults"  
    name="MyBinding"  
    binding="customBinding"  
    contract="HelloWorld">  
</endpoint>  
```  
  
## 참고 항목  
 <xref:System.ServiceModel.Configuration.ChannelEndpointElement>   
 <xref:System.ServiceModel.Configuration.ClientSection>   
 <xref:System.ServiceModel.Configuration.ChannelEndpointElementCollection>   
 <xref:System.ServiceModel.Configuration.ClientSection.Endpoints%2A>   
 <xref:System.ServiceModel.Configuration.ChannelEndpointElement>   
 [WCF 클라이언트 구성](../../../../../docs/framework/wcf/feature-details/client-configuration.md)   
 [클라이언트](../../../../../docs/framework/wcf/feature-details/clients.md)