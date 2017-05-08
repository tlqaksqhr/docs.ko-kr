---
title: "스키마 노드 형식 및 구조 유추 규칙 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: d74ce896-717d-4871-8fd9-b070e2f53cb0
caps.latest.revision: 2
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 2
---
# 스키마 노드 형식 및 구조 유추 규칙
이 항목에서는 스키마 유추 과정에서 XML 문서의 노드 형식을 XSD\(XML 스키마 정의 언어\) 구조로 변환하는 방법을 설명합니다.  
  
## 요소 유추 규칙  
 이 단원에서는 요소 선언의 유추 규칙에 대해 설명합니다.  유추되는 8개의 요소 선언 구조는 다음과 같습니다.  
  
1.  단순 형식 요소  
  
2.  빈 요소  
  
3.  특성을 가진 빈 요소  
  
4.  특성 및 단순 내용을 가진 요소  
  
5.  자식 요소 시퀀스를 가진 요소  
  
6.  자식 요소 시퀀스와 특성을 가진 요소  
  
7.  자식 요소 선택 시퀀스를 가진 요소  
  
8.  자식 요소 선택 시퀀스와 특성을 가진 요소  
  
> [!NOTE]
>  모든 `complexType` 선언은 익명 형식으로 유추됩니다.  유추되는 요소 중 루트 요소만이 전역 요소이며, 기타 모든 요소는 로컬 요소입니다.  
  
 스키마 유추 과정에 대한 자세한 내용은 [XML 문서에서 스키마 유추](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md)를 참조하세요.  
  
### 단순 형식 요소  
 다음 표에서는 <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> 메서드에 대한 XML 입력 및 생성된 XML 스키마를 보여 줍니다.  굵게 표시된 요소는 단순 형식 요소에 대해 유추된 스키마를 나타냅니다.  
  
 스키마 유추 과정에 대한 자세한 내용은 [XML 문서에서 스키마 유추](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md)를 참조하세요.  
  
|XML|스키마|  
|---------|---------|  
|`<?xml version="1.0"?>`<br /><br /> `<root>text</root>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> ``   `\<xs:element name="root" type="xs:string" />`<br /><br /> `\</xs:schema>`|  
  
### 빈 요소  
 다음 표에서는 <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> 메서드에 대한 XML 입력 및 생성된 XML 스키마를 보여 줍니다.  굵게 표시된 요소는 빈 요소에 대해 유추된 스키마를 나타냅니다.  
  
 스키마 유추 과정에 대한 자세한 내용은 [XML 문서에서 스키마 유추](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md)를 참조하세요.  
  
|XML|스키마|  
|---------|---------|  
|`<?xml version="1.0"?>`<br /><br /> `<empty/>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> ``   `\<xs:element name="empty" />`<br /><br /> `\</xs:schema>`|  
  
### 특성을 가진 빈 요소  
 다음 표에서는 <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> 메서드에 대한 XML 입력 및 생성된 XML 스키마를 보여 줍니다.  굵게 표시된 요소는 특성을 가진 빈 요소에 대해 유추된 스키마를 나타냅니다.  
  
 스키마 유추 과정에 대한 자세한 내용은 [XML 문서에서 스키마 유추](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md)를 참조하세요.  
  
|XML|스키마|  
|---------|---------|  
|`<?xml version="1.0"?>`<br /><br /> `<empty attribute1="text"/>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> ``   `\<xs:element name="empty">`<br /><br /> `\<xs:complexType>`<br /><br /> `\<xs:attribute name="attribute1" type="xs:string" use="required" />`<br /><br /> `\</xs:complexType>`<br /><br /> `\</xs:element>`<br /><br /> `\</xs:schema>`|  
  
### 특성 및 단순 내용을 가진 요소  
 다음 표에서는 <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> 메서드에 대한 XML 입력 및 생성된 XML 스키마를 보여 줍니다.  굵게 표시된 요소는 특성 및 단순 내용을 가진 요소에 대해 유추된 스키마를 나타냅니다.  
  
 스키마 유추 과정에 대한 자세한 내용은 [XML 문서에서 스키마 유추](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md)를 참조하세요.  
  
|XML|스키마|  
|---------|---------|  
|`<?xml version="1.0"?>`<br /><br /> `<root attribute1="text">value</root>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> ``   `\<xs:element name="root">`<br /><br /> `\<xs:complexType>`<br /><br /> `\<xs:simpleContent>`<br /><br /> `\<xs:extension base="xs:string">`<br /><br /> `\<xs:attribute name="attribute1" type="xs:string" use="required" />`<br /><br /> `\</xs:extension>`<br /><br /> `\</xs:simpleContent>`<br /><br /> `\</xs:complexType>`<br /><br /> `\</xs:element>`<br /><br /> `\</xs:schema>`|  
  
### 자식 요소 시퀀스를 가진 요소  
 다음 표에서는 <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> 메서드에 대한 XML 입력 및 생성된 XML 스키마를 보여 줍니다.  굵게 표시된 요소는 자식 요소 시퀀스를 가진 요소에 대해 유추된 스키마를 나타냅니다.  
  
> [!NOTE]
>  요소에 자식 요소가 한 개만 있더라도 여전히 시퀀스로 간주됩니다.  
  
 스키마 유추 과정에 대한 자세한 내용은 [XML 문서에서 스키마 유추](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md)를 참조하세요.  
  
|XML|스키마|  
|---------|---------|  
|`<?xml version="1.0"?>`<br /><br /> `<root>`<br /><br /> `<subElement/>`<br /><br /> `</root>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> ``   `\<xs:element name="root">`<br /><br /> `\<xs:complexType>`<br /><br /> `\<xs:sequence>`<br /><br /> `\<xs:element name="subElement" />`<br /><br /> `\</xs:sequence>`<br /><br /> `\</xs:complexType>`<br /><br /> `\</xs:element>`<br /><br /> `\</xs:schema>`|  
  
### 자식 요소 시퀀스와 특성을 가진 요소  
 다음 표에서는 <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> 메서드에 대한 XML 입력 및 생성된 XML 스키마를 보여 줍니다.  굵게 표시된 요소는 자식 요소 시퀀스 및 특성을 가진 요소에 대해 유추된 스키마를 나타냅니다.  
  
> [!NOTE]
>  요소에 자식 요소가 한 개만 있더라도 여전히 시퀀스로 간주됩니다.  
  
 스키마 유추 과정에 대한 자세한 내용은 [XML 문서에서 스키마 유추](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md)를 참조하세요.  
  
|XML|스키마|  
|---------|---------|  
|`<?xml version="1.0"?>`<br /><br /> `<root attribute1="text">`<br /><br /> `<subElement1/>`<br /><br /> `<subElement2/>`<br /><br /> `</root>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> ``   `\<xs:element name="root">`<br /><br /> `\<xs:complexType>`<br /><br /> `\<xs:sequence>`<br /><br /> `\<xs:element name="subElement1" />`<br /><br /> `\<xs:element name="subElement2" />`<br /><br /> `\</xs:sequence>`<br /><br /> `\<xs:attribute name="attribute1" type="xs:string" use="required" />`<br /><br /> `\</xs:complexType>`<br /><br /> `\</xs:element>`<br /><br /> `\</xs:schema>`|  
  
### 자식 요소 시퀀스 및 선택 항목을 가진 요소  
 다음 표에서는 <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> 메서드에 대한 XML 입력 및 생성된 XML 스키마를 보여 줍니다.  굵게 표시된 요소는 자식 요소 시퀀스 및 선택 항목을 가진 요소에 대해 유추된 스키마를 나타냅니다.  
  
> [!NOTE]
>  `xs:choice` 요소의 `maxOccurs` 특성은 유추된 스키마에서 `"unbounded"`로 설정됩니다.  
  
 스키마 유추 과정에 대한 자세한 내용은 [XML 문서에서 스키마 유추](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md)를 참조하세요.  
  
|XML|스키마|  
|---------|---------|  
|`<?xml version="1.0"?>`<br /><br /> `<root>`<br /><br /> `<subElement1/>`<br /><br /> `<subElement2/>`<br /><br /> `<subElement1/>`<br /><br /> `</root>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> ``   `\<xs:element name="root">`<br /><br /> `\<xs:complexType>`<br /><br /> `\<xs:sequence>`<br /><br /> `\<xs:choice maxOccurs="unbounded">`<br /><br /> `\<xs:element name="subElement1" />`<br /><br /> `\<xs:element name="subElement2" />`<br /><br /> `\</xs:choice>`<br /><br /> `\</xs:sequence>`<br /><br /> `\</xs:complexType>`<br /><br /> `\</xs:element>`<br /><br /> `\</xs:schema>`|  
  
### 자식 요소 시퀀스 및 선택 항목과 특성을 가진 요소  
 다음 표에서는 <xref:System.Xml.Schema.XmlSchemaInference.InferSchema%2A> 메서드에 대한 XML 입력 및 생성된 XML 스키마를 보여 줍니다.  굵게 표시된 요소는 자식 요소 시퀀스 및 선택 항목과 특성을 가진 요소에 대해 유추된 스키마를 나타냅니다.  
  
> [!NOTE]
>  `xs:choice` 요소의 `maxOccurs` 특성은 유추된 스키마에서 `"unbounded"`로 설정됩니다.  
  
 스키마 유추 과정에 대한 자세한 내용은 [XML 문서에서 스키마 유추](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md)를 참조하세요.  
  
|XML|스키마|  
|---------|---------|  
|`<?xml version="1.0"?>`<br /><br /> `<root attribute1="text">`<br /><br /> `<subElement1/>`<br /><br /> `<subElement2/>`<br /><br /> `<subElement1/>`<br /><br /> `</root>`|`<?xml version="1.0" encoding="utf-8"?>`<br /><br /> `<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xml`<br /><br /> `ns:xs="http://www.w3.org/2001/XMLSchema">`<br /><br /> ``   `\<xs:element name="root">`<br /><br /> `\<xs:complexType>`<br /><br /> `\<xs:sequence>`<br /><br /> `\<xs:choice maxOccurs="unbounded">`<br /><br /> `\<xs:element name="subElement1" />`<br /><br /> `\<xs:element name="subElement2" />`<br /><br /> `\</xs:choice>`<br /><br /> `\</xs:sequence>`<br /><br /> `\<xs:attribute name="attribute1" type="xs:string" use="required" />`<br /><br /> `\</xs:complexType>`<br /><br /> `\</xs:element>`<br /><br /> `\</xs:schema>`|  
  
### 특성 처리  
 노드에서 새로운 특성이 나타날 때마다 해당 특성은 `use="required"`와 함께 노드의 유추된 정의에 추가됩니다.  인스턴스에서 같은 노드가 다시 나타나면 유추 과정에서 현재 인스턴스의 특성을 이미 유추된 특성과 비교합니다.  인스턴스에 이미 유추된 특성의 일부가 누락되어 있으면 `use="optional"`이 특성 정의에 추가됩니다.  새로운 특성은 `use="optional"`과 함께 기존 선언에 추가됩니다.  
  
### 발생 제약 조건  
 스키마 유추 과정에서는 스키마의 유추된 구성 요소에 대해 `"0"` 또는 `"1"` 및 `"1"` 또는 `"unbounded"`의 값을 갖는 `minOccurs` 및 `maxOccurs` 특성이 생성됩니다.  `"1"` 및 `"unbounded"` 값은 `"0"` 및 `"1"` 값이 XML 문서의 유효성을 검사할 수 없을 경우에만 사용됩니다. 예를 들어, `MinOccurs="0"`이 요소를 정확하게 나타내지 못하면 `minOccurs="1"`이 사용됩니다.  
  
### 혼합 내용  
 요소에 텍스트와 요소가 섞여 있는 것과 같이 혼합 내용이 있으면 유추된 복합 형식 정의에 대해 `mixed="true"` 특성이 생성됩니다.  
  
## 기타 노드 형식 유추 규칙  
 다음 표에서는 처리 명령, 주석, entityreference, CDATA, 문서 형식 및 네임스페이스 노드의 유추 규칙에 대해 설명합니다.  
  
|노드 형식|변환|  
|-----------|--------|  
|처리 명령|무시됩니다.|  
|주석|무시됩니다.|  
|EntityReference|<xref:System.Xml.Schema.XmlSchemaInference> 클래스는 엔터티 참조를 처리하지 않습니다.  XML 문서에 엔터티 참조가 있는 경우 엔터티를 확장하는 판독기를 사용해야 합니다.  예를 들어, 매개 변수로서 <xref:System.Xml.EntityHandling>로 설정된 <xref:System.Xml.XmlTextReader.EntityHandling%2A> 속성과 함께 <xref:System.Xml.XmlTextReader>를 전달할 수 있습니다.  엔터티 참조가 발생할 때 판독기가 엔터티를 확장하지 않으면 예외가 throw됩니다.|  
|CDATA|XML 문서의 모든 `<![CDATA[   ]]` 섹션은 `xs:string`으로 유추됩니다.|  
|문서 형식|무시됩니다.|  
|네임스페이스|무시됩니다.|  
  
 스키마 유추 과정에 대한 자세한 내용은 [XML 문서에서 스키마 유추](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md)를 참조하세요.  
  
## 참고 항목  
 <xref:System.Xml.Schema.XmlSchemaInference>   
 [XML SOM\(스키마 개체 모델\)](../../../../docs/standard/data/xml/xml-schema-object-model-som.md)   
 [XML 스키마 유추](../../../../docs/standard/data/xml/inferring-an-xml-schema.md)   
 [XML 문서에서 스키마 유추](../../../../docs/standard/data/xml/inferring-schemas-from-xml-documents.md)   
 [단순 형식 유추 규칙](../../../../docs/standard/data/xml/rules-for-inferring-simple-types.md)