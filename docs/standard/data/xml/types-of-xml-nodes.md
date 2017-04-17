---
title: "XML 노드 형식 | Microsoft Docs"
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
ms.assetid: 71d03b78-6898-4ce7-b0fc-1282573f31f7
caps.latest.revision: 4
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 3
---
# XML 노드 형식
XML 문서를 노드 트리로 메모리에 읽어올 경우 노드의 형식은 노드가 만들어질 때 결정됩니다.  XML DOM\(문서 개체 모델\)에는 다양한 노드 형식이 있습니다. 이러한 노드 형식은 W3C\(World Wide Web 컨소시엄\)에서 결정하며 1.1.1단원 The DOM Structure Model에 목록이 제공됩니다.  다음 표에서는 노드 형식, 해당 노드 형식에 지정된 개체 및 각각에 대한 간략한 설명의 목록을 보여 줍니다.  
  
|DOM 노드 형식|개체|설명|  
|---------------|--------|--------|  
|문서|[XmlDocument 클래스](frlrfSystemXmlXmlDocumentClassTopic)|트리에 있는 모든 노드의 컨테이너입니다.  Document 루트라고도 하지만 루트 요소와 항상 동일하지는 않습니다.|  
|DocumentFragment|[XmlDocumentFragment 클래스](frlrfSystemXmlXmlDocumentFragmentClassTopic)|트리 구조 없이 하나 이상의 노드를 포함하는 임시 노드입니다.|  
|DocumentType|[XmlDocumentType 클래스](frlrfSystemXmlXmlDocumentTypeClassTopic)|`<!DOCTYPE >` 노드를 나타냅니다.|  
|EntityReference|[XmlEntityReference 클래스](frlrfSystemXmlXmlEntityReferenceClassTopic)|확장되지 않는 엔터티 참조 텍스트를 나타냅니다.|  
|요소|[XmlElement 클래스](frlrfSystemXmlXmlElementClassTopic)|요소 노드를 나타냅니다.|  
|Attr|[XmlAttribute 클래스](frlrfSystemXmlXmlAttributeClassTopic)|요소의 특성입니다.|  
|ProcessingInstruction|[XmlProcessingInstruction 클래스](frlrfSystemXmlXmlProcessingInstructionClassTopic)|처리 명령 노드입니다.|  
|주석|[XmlComment 클래스](frlrfSystemXmlXmlCommentClassTopic)|comment 노드입니다.|  
|Text|[XmlText 클래스](frlrfSystemXmlXmlTextClassTopic)|요소 또는 특성에 속한 텍스트입니다.|  
|CDATASection|[XmlCDataSection 클래스](frlrfSystemXmlXmlCDataSectionClassTopic)|CDATA를 나타냅니다.|  
|엔터티|[XmlEntity 클래스](frlrfSystemXmlXmlEntityClassTopic)|XML 문서에서 내부 DTD\(문서 종류 정의\) 하위 집합 또는 외부 DTD 및 매개 변수 엔터티의 `<!ENTITY >` 선언을 나타냅니다.|  
|Notation|[XmlNotation 클래스](frlrfSystemXmlXmlNotationClassTopic)|DTD에 선언된 노테이션을 나타냅니다.|  
  
 W3C DOM Level 1의 1.2단원 Fundamental Interfaces에는 특성\(*attr*\)이 노드로 나열되지만 다른 요소 노드의 자식으로 간주되지는 않습니다.  
  
 다음 표에서는 W3C에서 정의하지 않은 노드로 Microsoft .NET Framework 개체 모델에서 **XmlNodeType** 열거형으로 사용할 수 있는 추가 노드 형식을 보여 줍니다.  따라서 이러한 노드 형식에는 해당하는 DOM 노드 형식 열이 없습니다.  
  
|노드 형식|설명|  
|-----------|--------|  
|<xref:System.Xml.XmlDeclaration>|`<?xml version="1.0" >` 선언 노드를 나타냅니다.|  
|<xref:System.Xml.XmlSignificantWhitespace>|혼합 내용의 공백인 유효 공백을 나타냅니다.|  
|<xref:System.Xml.XmlWhitespace>|요소 내용의 공백을 나타냅니다.|  
|EndElement|**XmlReader**가 요소의 끝에 도달하면 반환됩니다.<br /><br /> XML 예: **\<\/item\>**<br /><br /> 자세한 내용은 [XmlNodeType 열거형](frlrfSystemXmlXmlNodeTypeClassTopic)을 참조하세요.|  
|EndEntity|<xref:System.Xml.XmlReader.ResolveEntity%2A> 호출 결과 **XmlReader**가 엔터티 대체의 끝에 이르면 반환됩니다.  자세한 내용은 [XmlNodeType 열거형](frlrfSystemXmlXmlNodeTypeClassTopic)을 참조하세요.|  
  
 XML을 읽고 case 구문을 사용하여 노드 형식에 따라 노드와 해당 내용에 대한 정보를 출력하는 코드 예제를 보려면 [XmlSignificantWhitespace.NodeType 속성](frlrfSystemXmlXmlSignificantWhitespaceClassNodeTypeTopic)을 참조하세요.  
  
 노드 형식의 개체 계층 구조와 해당 개체 이름에 대한 자세한 내용은 [XML DOM\(문서 개체 모델\) 계층 구조](../../../../docs/standard/data/xml/xml-document-object-model-dom-hierarchy.md)를 참조하세요.  노드 트리에서 생성되는 개체에 대한 자세한 내용은 [XML 데이터에 개체 계층 구조 매핑](../../../../docs/standard/data/xml/mapping-the-object-hierarchy-to-xml-data.md)을 참조하세요.  
  
## 참고 항목  
 [XML DOM\(문서 개체 모델\)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)