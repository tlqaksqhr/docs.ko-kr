---
title: "&lt;system.xml.serialization&gt; 요소"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- system.xml.serialization element
- XML serialization, configuration
- <system.xml.serialization> element
ms.assetid: 3ce45919-388a-418c-8968-6df0372c73ec
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: d673c76e57ffb8315e97b1695dbcbc1f4fe0aab9
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="ltsystemxmlserializationgt-element"></a>&lt;system.xml.serialization&gt; 요소
XML serialization을 제어하기 위한 최상위 요소입니다. 구성 파일에 대한 자세한 내용은 [구성 파일 스키마](../../../docs/framework/configure-apps/file-schema/index.md)를 참조하세요.  
  
 \<configuration>  
\<system.xml.serialization>  
  
## <a name="syntax"></a>구문  
  
```xml  
<system.xml.serialization>  
</system.xml.serialization>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
 없음  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<dateTimeSerialization> 요소](../../../docs/standard/serialization/datetimeserialization-element.md)|<xref:System.DateTime> 개체의 serialization 모드를 결정합니다.|  
|[\<schemaImporterExtensions> 요소](../../../docs/standard/serialization/schemaimporterextensions-element.md)|<xref:System.Xml.Serialization.XmlSchemaImporter>에서 XSD 형식을 .NET Framework 형식으로 매핑하는 데 사용되는 형식을 포함합니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[\<configuration> 요소](../../../docs/framework/configure-apps/file-schema/configuration-element.md)|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
  
## <a name="example"></a>예  
 다음 코드 예제에서는 <xref:System.DateTime> 개체의 serialization 모드를 지정하는 방법과 <xref:System.Xml.Serialization.XmlSchemaImporter>에서 XSD 형식을 .NET Framework 형식으로 매핑할 때 사용되는 형식을 추가하는 방법을 보여 줍니다.  
  
```xml  
<system.xml.serialization>  
    <xmlSerializer checkDeserializeAdvances="false" />  
    <dateTimeSerialization mode = "Local" />  
    <schemaImporterExtensions>  
        <add   
        name = "MobileCapabilities"   
        type = "System.Web.Mobile.MobileCapabilities,   
        System.Web.Mobile, Version - 2.0.0.0, Culture = neuutral,   
        PublicKeyToken = b03f5f6f11d40a3a" />  
    </schemaImporterExtensions>  
</system.sxml.serialization>  
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Xml.Serialization.XmlSchemaImporter>  
 <xref:System.Xml.Serialization.Configuration.DateTimeSerializationSection.DateTimeSerializationMode>  
 [구성 파일 스키마](../../../docs/framework/configure-apps/file-schema/index.md)  
 [\<dateTimeSerialization> 요소](../../../docs/standard/serialization/datetimeserialization-element.md)  
 [\<schemaImporterExtensions> 요소](../../../docs/standard/serialization/schemaimporterextensions-element.md)  
 [\<xmlSchemaImporterExtensions>에 대한 \<add> 요소](../../../docs/standard/serialization/add-element-for-xmlschemaimporterextensions.md)
