---
title: "&lt;dateTimeSerialization&gt; 요소 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "<dateTimeSerialization> 요소"
  - "dateTimeSerialization 요소"
  - "XML serialization, configuration"
ms.assetid: 90fda55c-7730-41e9-bc4b-6423a4b920af
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# &lt;dateTimeSerialization&gt; 요소
<xref:System.DateTime> 개체의 serialization 모드를 결정합니다.  
  
## 구문  
  
```  
  
<dateTimeSerialization  
    mode = "Roundtrip" | "Local"  
/>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|`mode`|선택 사항입니다.  serialization 모드를 지정합니다.  <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode> 값 중 하나로 설정합니다.  기본값은 **RoundTrip**입니다.|  
  
### 자식 요소  
 없음  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|system.xml.serialization|XML serialization을 제어하기 위한 최상위 요소입니다.|  
  
## 설명  
 .NET Framework의 버전 1.0, 1.1 및 2.0 이상 버전에서 이 속성을 **Local**로 설정하면 <xref:System.DateTime> 개체의 형식이 항상 현지 시간으로 지정됩니다.  따라서 현지 시간대 정보가 serialize된 데이터에 항상 포함됩니다.  .NET Framework의 이전 버전과 호환되도록 하려면 이 속성을 **Local**로 설정합니다.  
  
 이 특성이 **Roundtrip**으로 설정된 .NET Framework의 2.0 이상 버전에서는 <xref:System.DateTime> 개체를 검사하여 해당 개체가 현지, UTC 또는 지정되지 않은 시간대 중 무엇인지 결정합니다.  그런 다음 <xref:System.DateTime> 개체는 이 정보를 유지할 수 있는 방식으로 serialize됩니다.  이 동작이 기본 동작이며 이전 버전의 framework와 통신하지 않는 모든 새 응용 프로그램에 대해 이를 사용하는 것이 좋습니다.  
  
## 참고 항목  
 <xref:System.DateTime>   
 <xref:System.Xml.Serialization.XmlSchemaImporter>   
 <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>   
 [구성 파일 스키마](../../../docs/framework/configure-apps/file-schema/index.md)   
 [\<schemaImporterExtensions\> 요소](../../../docs/framework/serialization/schemaimporterextensions-element.md)   
 [\<xmlSchemaImporterExtensions\>의 요소 \<add\>](../../../docs/framework/serialization/add-element-for-xmlschemaimporterextensions.md)   
 [\<system.xml.serialization\> 요소](../../../docs/framework/serialization/system-xml-serialization-element.md)