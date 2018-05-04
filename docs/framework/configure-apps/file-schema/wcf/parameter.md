---
title: '&lt;parameter&gt;'
ms.date: 03/30/2017
ms.assetid: 0fb41e2d-64f7-44ab-993e-05892eac6d82
ms.openlocfilehash: b9cccfe37e7658afbf2e49555e6c505497598fbb
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="ltparametergt"></a>&lt;parameter&gt;
선언된 형식이 제네릭 형식이면 제네릭 매개 변수를 지정합니다.  
  
 \<system.runtime.serialization >  
\<dataContractSerializer >  
\<declaredTypes > 요소  
\<추가 > 요소에 대 한 \<declaredTypes >  
\<knownType > 요소  
\<매개 변수 > 요소  
  
## <a name="syntax"></a>구문  
  
```xml  
<parameter index="integer"  
                      type=String" />  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|인덱스입니다.|선언된 형식이 제네릭 형식이면 알려진 형식을 반환하는 제네릭 매개 변수를 지정합니다.|  
|형식|serialization 및 deserialization에 사용되는 알려진 형식을 설명하는 문자열입니다.|  
  
## <a name="index-attribute"></a>index 특성  
  
|값|설명|  
|-----------|-----------------|  
|"0"|제네릭 형식의 첫 번째 매개 변수입니다. 예를 들어, <xref:System.Collections.Generic.List%601>에는 하나의 매개 변수만 있습니다. 이 형식이 선언된 형식으로 사용되면 index가 "0"으로 설정됩니다.|  
|"1"|제네릭 형식의 두 번째 매개 변수입니다. 예를 들어, <xref:System.Collections.Generic.Dictionary%602>에는 두 개의 매개 변수가 있습니다. 이 알려진 형식이 두 번째 매개 변수에서 반환되면 index 특성을 "1"로 설정합니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<knownType >](../../../../../docs/framework/configure-apps/file-schema/wcf/knowntype.md)|선언된 형식의 필드 또는 속성에서 반환될 수 있는 알려진 형식을 지정합니다.|  
  
## <a name="remarks"></a>설명  
 알려진된 형식에 대 한 자세한 내용은 참조 [데이터 계약 알려진 형식을](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) 및 <xref:System.Runtime.Serialization.DataContractSerializer>합니다.  
  
 참조는 [ \<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md) 이 요소를 사용 하는 예제에 대 한 합니다.  
  
 이 구성 요소는 두 가지 특성을 동시에 가질 수 없습니다. 두 가지 특성이 모두 설정되면 <xref:System.Configuration.ConfigurationErrorsException>이 발생합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 [데이터 계약 알려진 형식](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [\<dataContractSerializer >](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)  
 [\<add>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)
