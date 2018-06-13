---
title: dataContractSerializer
ms.date: 03/30/2017
ms.assetid: a47513a4-a96c-4350-8586-daacb05dee71
ms.openlocfilehash: 0528ae823db500da3c3a1efc6934951c4e41cea7
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32748017"
---
# <a name="datacontractserializer"></a>dataContractSerializer
<xref:System.Runtime.Serialization.DataContractSerializer>에 대한 구성 데이터를 포함합니다.  
  
 \<system.ServiceModel>  
\<동작 >  
\<endpointBehaviors>  
\<동작 >  
\<dataContractSerializer >  
  
## <a name="syntax"></a>구문  
  
```xml  
<dataContractSerializer ignoreExtensionDataObject="Boolean"  
      maxItemsInObjectGraph="Integer" />  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|요소|설명|  
|-------------|-----------------|  
|ignoreExtensionDataObject|끝점이 serialize되거나 deserialize될 때 해당 끝점에서 제공하는 데이터를 무시할지 여부를 지정하는 부울 값입니다.|  
|maxItemsInObjectGraph|serialize 또는 deserialize할 항목의 최대 수를 지정하는 정수입니다.|  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<동작 >](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|끝점 동작을 지정합니다.|  
  
## <a name="remarks"></a>설명  
 알려진 형식에 대한 자세한 내용은 <xref:System.Runtime.Serialization.DataContractSerializer> 설명서를 참조하세요.  
  
> [!CAUTION]
>  `<dataContractSerializer>` 동작 요소(있는 경우)는 항상 구성 파일에서 `<enableWebScript>` 동작 요소 앞에 나와야 합니다. 그렇지 않으면 결과 동작이 정의되지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior>  
 <xref:System.ServiceModel.Configuration.DataContractSerializerElement>  
 [데이터 계약 알려진 형식](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [데이터 전송 및 Serialization](../../../../../docs/framework/wcf/feature-details/data-transfer-and-serialization.md)
