---
title: "&lt;schemaImporterExtensions&gt; 요소 | Microsoft Docs"
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
  - "<schemaImporterExtensions> 요소"
  - "schemaImporterExtensions 요소"
  - "XML serialization, configuration"
ms.assetid: 465ef2a0-f909-4ac1-9a56-0ead5c849698
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# &lt;schemaImporterExtensions&gt; 요소
<xref:System.Xml.Serialization.XmlSchemaImporter>에서 XSD 형식을 .NET Framework 형식으로 매핑하는 데 사용되는 형식을 포함합니다.  구성 파일에 대한 자세한 내용은 [구성 파일 스키마](../../../docs/framework/configure-apps/file-schema/index.md)를 참조하십시오.  
  
## 구문  
  
```  
  
<schemaImporterExtensions>  
    <!-- Add types -->  
</SchemaImporterExtension>  
```  
  
## 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[\<xmlSchemaImporterExtensions\>의 요소 \<add\>](../../../docs/framework/serialization/add-element-for-xmlschemaimporterextensions.md)|<xref:System.Xml.Serialization.XmlSchemaImporter>에서 매핑을 만들기 위해 사용하는 형식을 추가합니다.|  
  
## 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<system.xml.serialization\> 요소](../../../docs/framework/serialization/system-xml-serialization-element.md)|XML serialization을 제어하기 위한 최상위 요소입니다.|  
  
## 예제  
 다음 코드 예제에서는 XSD 형식을 .NET Framework 형식으로 매핑할 때 <xref:System.Xml.Serialization.XmlSchemaImporter>에서 사용하는 형식을 추가하는 방법을 보여 줍니다.  
  
```  
<system.xml.serialization>  
    <schemaImporterExtensions>  
        <add name = "MobileCapabilities" type =   
        "System.Web.Mobile.MobileCapabilities,   
        System.Web.Mobile, Version - 2.0.0.0, Culture = neutral,   
        PublicKeyToken = b03f5f6f11d40a3a" />  
    </schemaImporterExtensions>  
/system.sxml.serializaiton>  
```  
  
## 참고 항목  
 <xref:System.Xml.Serialization.XmlSchemaImporter>   
 <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>   
 [구성 파일 스키마](../../../docs/framework/configure-apps/file-schema/index.md)   
 [\<dateTimeSerialization\> 요소](../../../docs/framework/serialization/datetimeserialization-element.md)   
 [\<xmlSchemaImporterExtensions\>의 요소 \<add\>](../../../docs/framework/serialization/add-element-for-xmlschemaimporterextensions.md)   
 [\<system.xml.serialization\> 요소](../../../docs/framework/serialization/system-xml-serialization-element.md)