---
title: '&lt;dynamicEndpoint&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 929f223d-176d-4205-9505-234ddb6dbff4
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e24d340364f126d9cf33295d6d36d1b686065a76
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltdynamicendpointgt"></a>&lt;dynamicEndpoint&gt;
이 구성 요소는 응용 프로그램이 런타임에 끝점 주소를 동적으로 찾을 수 있는 클라이언트 프로그램으로 기능하도록 설정하기 위한 정보를 포함하는 표준 끝점을 정의합니다.  
  
\<시스템입니다. ServiceModel >  
\<d a r d >  
  
## <a name="syntax"></a>구문  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>
    <dynamicEndpoint>
      <standardEndpoint>
      <discoveryClientSettings discoveryEndpoint="String">
        <findCriteria duration="TimeSpan" 
                      maxResults="Integer" 
                      scopeMatchBy="Uri">
          <contractTypeNames>
            <add name="String" namespace="String" />
          <contractTypeNames>
          <extensions />
          <scopes>
            <add scope="URI" />
          </scopes>
        </findCriteria>
      </discoveryClientSettings>
      <standardEndpoint>
    </dynamicEndpoint>
  </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
 없음  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<discoveryClientSettings >](../../../../../docs/framework/configure-apps/file-schema/wcf/discoveryclientsettings.md)|응용 프로그램에서 서비스 검색 프로세스에 클라이언트로 참여하기 위해 필요한 설정이 포함됩니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<d a r d >](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|하나 이상의 속성(주소, 바인딩, 계약)이 고정된 미리 정의된 끝점인 표준 끝점의 컬렉션입니다.|  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Discovery.DynamicEndpoint>  
 <xref:System.ServiceModel.Discovery.Configuration.DynamicEndpointElement>
