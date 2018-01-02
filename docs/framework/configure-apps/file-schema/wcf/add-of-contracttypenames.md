---
title: "&lt;contractTypeNames&gt;의 &lt;add&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 03aff6be-5dfb-4a64-ada3-e36227cd43c7
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 191e3e221ae42e5c046f8df324989aae7ab0dc1c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt-of-ltcontracttypenamesgt"></a>&lt;contractTypeNames&gt;의 &lt;add&gt;
검색할 서비스의 계약 이름 및 서비스를 검색할 때 일반적으로 사용되는 기준을 지정하는 구성 요소입니다. 둘 이상의 계약 이름이 지정되면 모든 계약과 일치하는 서비스 끝점만 응답합니다. [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]에서는 하나의 끝점이 하나의 계약만 지원할 수 있습니다.  
  
 \<시스템입니다. ServiceModel >  
\<d a r d >  
  
## <a name="syntax"></a>구문  
  
```xml  
<system.serviceModel>  
    <standardEndpoints>       <dynamicEndpoint>           <standardEndpoint>             <discoveryClientSettings discoveryEndpoint="String" >               <findCriteria duration="TimeSpan"                  maxResults="Integer"                   scopeMatchBy="Uri" >                  <contractTypeNames>                     <add name="String" namespace="String" />                  <contractTypeNames>                  <extensions />                  <scopes>                    <add scope="URI"/>                  </scopes>               </findCriteria>             </discoveryClientSettings>          <standardEndpoint>       </dynamicEndpoint>            </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|name|계약 형식의 이름을 지정하는 문자열입니다.|  
|namespace|계약 형식의 네임스페이스를 지정하는 문자열입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<contractTypeNames >](../../../../../docs/framework/configure-apps/file-schema/wcf/contracttypenames.md)|계약 형식 이름의 컬렉션입니다.|  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Discovery.FindCriteria>  
 <xref:System.ServiceModel.Discovery.Configuration.FindCriteriaElement>  
 <xref:System.ServiceModel.Discovery.Configuration.ContractTypeNameElement>
