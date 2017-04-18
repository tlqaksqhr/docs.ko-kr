---
title: "&lt;client&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel/client"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#client"
dev_langs: 
  - "VB"
  - "CSharp"
ms.assetid: bf0f7031-76c8-4e7e-a6c6-9ad9119134be
caps.latest.revision: 18
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 18
---
# &lt;client&gt;
`client` 요소는 클라이언트가 연결할 수 있는 끝점 목록을 정의합니다.  
  
## 구문  
  
```  
  
<system.serviceModel>  
    <client>  
        <endpoint>  
        </endpoint>  
                <metadata>  
        </metadata>  
    </client>  
</system.serviceModel>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
 없음  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[\<endpoint\>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-of-client.md)|이 클라이언트가 연결할 수 있는 끝점을 지정하는 끝점 요소 컬렉션을 포함합니다.|  
|[\<metadata\>](../../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md)|메타데이터 처리를 위한 설정을 포함합니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<system.serviceModel\>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|모든 WCF\(Windows Communication Foundation\) 구성 요소의 루트 요소입니다.|  
  
## 설명  
 `client` 섹션은 클라이언트가 연결할 수 있는 끝점 목록을 정의합니다.  클라이언트 섹션에 나열된 각 끝점은 자체의 바인딩, 동작 및 계약을 정의합니다.  각 끝점은 `name` 및 `contract` 특성 조합에 의해 고유하게 식별됩니다.  클라이언트 코드는 클라이언트가 구현하는 서비스에 대한 끝점에 연결하기 위한 `name`을 지정합니다.  `name` 특성을 생략하면 끝점은 구현하는 계약에 대한 기본 끝점으로 작동합니다.  
  
 또한 이 섹션에서는 메타데이터 처리를 위한 설정도 지정합니다.  
  
## 예제  
  
```  
<client>  
    <endpoint address="/HelloWorld/"  
              bindingConfiguration="usingDefaults"  
              name="MyBinding"  
              binding="customBinding"  
              contract="HelloWorld">  
    <addressProperties actingAs="http://www.microsoft.com/TestActor"  
             identityData="BasicReadWrite" identityType="Spn" isAddressPrivate="false">  
    </endpoint>  
</client>  
```  
  
## 참고 항목  
 <xref:System.ServiceModel.Configuration.ClientSection>   
 <xref:System.ServiceModel.Configuration.MetadataElement>   
 [WCF 클라이언트 구성](../../../../../docs/framework/wcf/feature-details/client-configuration.md)   
 [클라이언트](../../../../../docs/framework/wcf/feature-details/clients.md)