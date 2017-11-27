---
title: '&lt;mexEndpoint&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c9823060-0a5d-4f9d-99d4-4d113b758247
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 75886c08d3e358d4ed6d3d3048594ef28f06a7af
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="ltmexendpointgt"></a>&lt;mexEndpoint&gt;
이 구성 요소는 고정 IMetadataExchange 계약을 사용하여 표준 끝점을 정의합니다. 모든 메타데이터 교환 끝점이 IMetadataExchange를 계약으로 지정하므로 고유의 끝점을 정의하는 대신 이 표준 지점을 사용할 수 있습니다.  
  
 \<시스템입니다. ServiceModel >  
\<d a r d >  
  
## <a name="syntax"></a>구문  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>
    <mexEndpoint>
      <standardEndpoint name="String" />
    </mexEndpoint>
  </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|name|표준 끝점의 구성 이름을 지정하는 문자열입니다. 이 이름은 서비스 끝점의 `endpointConfiguration` 특성에서 표준 끝점을 해당 구성에 연결하기 위해 사용됩니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<d a r d >](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|하나 이상의 속성(주소, 바인딩, 계약)이 고정된 미리 정의된 끝점인 표준 끝점의 컬렉션입니다.|
