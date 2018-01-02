---
title: '&lt;contractTypeNames&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5ec5efc6-87f8-4160-9be0-dcd2e01df3df
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e5ac3a4af54d9f470a1cbd50096731b23d28b0c5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltcontracttypenamesgt"></a>&lt;contractTypeNames&gt;
검색할 서비스의 계약 이름인 계약 형식 이름 목록 및 서비스를 검색할 때 일반적으로 사용되는 기준을 지정하는 구성 섹션입니다. 둘 이상의 계약 이름이 지정되면 모든 계약과 일치하는 서비스 끝점만 응답합니다. [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]에서는 하나의 끝점이 하나의 계약만 지원할 수 있습니다.  
  
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
              <add scope="URI"/>
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
|[\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/contracttypenames.md)|계약 형식 이름은 서비스를 검색할 때 일반적으로 사용되는 조건 집합을 나타나는 속성입니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<findCriteria >](../../../../../docs/framework/configure-apps/file-schema/wcf/findcriteria.md)|클라이언트 응용 프로그램에서 검색 서비스를 찾기 위해 사용하는 조건 집합을 제공하는 구성 요소입니다. 기준을 검색 조건 (찾으려는 서비스 지정)으로 그룹화 할 수 및 찾기 종료 조건 (검색 지속 기간).|  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Discovery.FindCriteria>  
 <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>  
 <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElementCollection>
