---
title: "XML 노드 형식"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 71d03b78-6898-4ce7-b0fc-1282573f31f7
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3914a2c5c06a2cc73f14bc473984094b474d537e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="types-of-xml-nodes"></a>XML 노드 형식
XML 문서를 노드 트리로 메모리에 읽어올 경우 노드의 형식은 노드가 만들어질 때 결정됩니다. XML DOM(문서 개체 모델)에는 다양한 노드 형식이 있습니다. 이러한 노드 형식은 W3C(World Wide Web 컨소시엄)에서 결정하며 1.1.1단원 The DOM Structure Model에 목록이 제공됩니다. 다음 표에서는 노드 형식, 해당 노드 형식에 지정된 개체 및 각각에 대한 간략한 설명의 목록을 보여 줍니다.  
  
|DOM 노드 형식|개체|설명|  
|-------------------|------------|-----------------|  
|문서|<xref:System.Xml.XmlDocument>|트리에 있는 모든 노드의 컨테이너입니다. Document 루트라고도 하지만 루트 요소와 항상 동일하지는 않습니다.|  
|DocumentFragment|<xref:System.Xml.XmlDocumentFragment>|트리 구조 없이 하나 이상의 노드를 포함하는 임시 노드입니다.|  
|DocumentType|<xref:System.Xml.XmlDocumentType>|`<!DOCTYPE…>` 노드를 나타냅니다.|  
|EntityReference|<xref:System.Xml.XmlEntityReference>|확장되지 않는 엔터티 참조 텍스트를 나타냅니다.|  
|요소|<xref:System.Xml.XmlElement>|요소 노드를 나타냅니다.|  
|Attr|<xref:System.Xml.XmlAttribute>|요소의 특성입니다.|  
|ProcessingInstruction|<xref:System.Xml.XmlProcessingInstruction>|처리 명령 노드입니다.|  
|주석|<xref:System.Xml.XmlComment>|comment 노드입니다.|  
|텍스트|<xref:System.Xml.XmlText>|요소 또는 특성에 속한 텍스트입니다.|  
|CDATASection|<xref:System.Xml.XmlCDataSection>|CDATA를 나타냅니다.|  
|엔터티|<xref:System.Xml.XmlEntity>|XML 문서에서 내부 DTD(문서 종류 정의) 하위 집합 또는 외부 DTD 및 매개 변수 엔터티의 `<!ENTITY…>` 선언을 나타냅니다.|  
|Notation|<xref:System.Xml.XmlNotation>|DTD에 선언된 노테이션을 나타냅니다.|  
  
 않더라도 특성 (*attr*) 나열 됩니다에 W3C DOM Level 1 1.2 단원 Fundamental Interfaces 노드, 간주 되지 않으며 모든 요소 노드 자식입니다.  
  
 다음 표에서 이지만으로 Microsoft.NET Framework 개체 모델에서 사용 하기 위해 사용할 수는 W3C에서 정의 되지 하는 추가 노드 형식을 보여 줍니다 **XmlNodeType** 열거형입니다. 따라서 이러한 노드 형식에는 해당하는 DOM 노드 형식 열이 없습니다.  
  
|노드 형식|설명|  
|---------------|-----------------|  
|<xref:System.Xml.XmlDeclaration>|`<?xml version="1.0"…>` 선언 노드를 나타냅니다.|  
|<xref:System.Xml.XmlSignificantWhitespace>|혼합 내용의 공백인 유효 공백을 나타냅니다.|  
|<xref:System.Xml.XmlWhitespace>|요소 내용의 공백을 나타냅니다.|  
|EndElement|이 반환 **XmlReader** 요소 끝에 도달 합니다.<br /><br /> XML 예:  **\<항목/>**<br /><br /> 자세한 내용은 <xref:System.Xml.XmlNodeType>을 참조하십시오.|  
|EndEntity|이 반환 **XmlReader** 에 대 한 호출의 결과로 엔터티 대체의 끝에 도달 <xref:System.Xml.XmlReader.ResolveEntity%2A>합니다. 자세한 내용은 <xref:System.Xml.XmlNodeType>을 참조하십시오.|  
  
 XML을 읽고 case 구문을 노드와 해당 내용에 대 한 인쇄 정보 노드 형식에서 사용 하는 코드 예제를 보려면 참조 <xref:System.Xml.XmlSignificantWhitespace.NodeType%2A>합니다.  
  
 노드 형식 및 해당 개체 이름의 개체 계층 구조에 자세한 내용은 참조 하십시오. [XML 문서 개체 모델 (DOM) 계층 구조](../../../../docs/standard/data/xml/xml-document-object-model-dom-hierarchy.md)합니다. 노드 트리에 만들어지는 개체에 대 한 자세한 내용은 참조 하십시오. [XML 데이터에 개체 계층 구조 매핑](../../../../docs/standard/data/xml/mapping-the-object-hierarchy-to-xml-data.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [XML 문서 개체 모델 (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
