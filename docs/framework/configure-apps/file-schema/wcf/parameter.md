---
title: "&lt;parameter&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0fb41e2d-64f7-44ab-993e-05892eac6d82
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# &lt;parameter&gt;
선언된 형식이 제네릭 형식이면 제네릭 매개 변수를 지정합니다.  
  
## 구문  
  
```  
  
<parameter index="integer"  
                      type=String" />  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|인덱스입니다.|선언된 형식이 제네릭 형식이면 알려진 형식을 반환하는 제네릭 매개 변수를 지정합니다.|  
|형식|serialization 및 deserialization에 사용되는 알려진 형식을 설명하는 문자열입니다.|  
  
## index 특성  
  
|값|설명|  
|-------|--------|  
|"0"|제네릭 형식의 첫 번째 매개 변수입니다.  예를 들어, <xref:System.Collections.Generic.List%601>에는 하나의 매개 변수만 있습니다.  이 형식이 선언된 형식으로 사용되면 index가 "0"으로 설정됩니다.|  
|"1"|제네릭 형식의 두 번째 매개 변수입니다.  예를 들어, <xref:System.Collections.Generic.Dictionary%602>에는 두 개의 매개 변수가 있습니다.  이 알려진 형식이 두 번째 매개 변수에서 반환되면 index 특성을 "1"로 설정합니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<knownType\>](../../../../../docs/framework/configure-apps/file-schema/wcf/knowntype.md)|선언된 형식의 필드 또는 속성에서 반환될 수 있는 알려진 형식을 지정합니다.|  
  
## 설명  
 알려진 형식[!INCLUDE[crabout](../../../../../includes/crabout-md.md)] [데이터 계약 알려진 형식](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md) 및 <xref:System.Runtime.Serialization.DataContractSerializer>를 참조하세요.  
  
 이 요소의 사용 예제는 [\<dataContractSerializer\>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)를 참조하세요.  
  
 이 구성 요소는 두 가지 특성을 동시에 가질 수 없습니다.  두 가지 특성이 모두 설정되면 <xref:System.Configuration.ConfigurationErrorsException>이 발생합니다.  
  
## 참고 항목  
 <xref:System.Runtime.Serialization.DataContractSerializer>   
 [데이터 계약 알려진 형식](../../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)   
 [\<dataContractSerializer\>](../../../../../docs/framework/configure-apps/file-schema/wcf/datacontractserializer-element.md)   
 [\<add\>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-declaredtypes-element.md)