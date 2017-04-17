---
title: "DOM에서 새 노드 만들기 | Microsoft Docs"
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
ms.assetid: 6c2b9789-b61a-49f9-b33f-db01a945edf2
caps.latest.revision: 4
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 4
---
# DOM에서 새 노드 만들기
<xref:System.Xml.XmlDocument> 모든 노드 형식에 대 한 create 메서드가 있습니다. 필요에 따라 메서드에 이름을 제공하고, 텍스트 노드처럼 내용이 있는 노드에 대한 내용이나 기타 매개 변수를 지정하면 노드가 생성됩니다. 다음은 적합한 노드를 만들기 위해 이름 및 몇 개의 매개 변수를 제공해야 하는 메서드입니다.  
  
-   <xref:System.Xml.XmlDocument.CreateCDataSection%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateComment%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateDocumentFragment%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateDocumentType%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateElement%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateNode%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateProcessingInstruction%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateSignificantWhitespace%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateTextNode%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateWhitespace%2A>  
  
-   <xref:System.Xml.XmlDocument.CreateXmlDeclaration%2A>  
  
 다른 노드 형식에는 매개 변수에 데이터를 제공하는 것 이상의 요구 사항이 있습니다.  
  
 특성에 대 한 자세한 내용은 [DOM에서 요소의 새 특성 만들기](../../../../docs/standard/data/xml/creating-new-attributes-for-elements-in-the-dom.md)합니다. 요소 및 특성 이름 유효성 검사에 대 한 자세한 내용은 [XML 요소 및 특성 이름 확인을 만들 때 새 노드](../../../../docs/standard/data/xml/xml-element-and-attribute-name-verification-when-creating-new-nodes.md)합니다. 참조 엔터티 참조를 만드는 [새 엔터티 참조 만들기](../../../../docs/standard/data/xml/creating-new-entity-references.md)합니다. 네임 스페이스의 엔터티 참조 확장에 미치는 영향에 대 한 내용은 참조 [Namespace 영향을 줍니다. 새 노드가 포함 된 요소 및 특성에 대 한 엔터티 참조 확장](../../../../docs/standard/data/xml/namespace-affect-on-entity-ref-expansion-for-new-nodes.md)합니다.  
  
 새 노드를 만든 후에 트리에 해당 노드를 삽입하는 데 사용할 수 있는 몇 가지 메서드가 있습니다. 다음 표에는 XML DOM(문서 개체 모델)에서 새 노드가 나타나는 위치에 대한 설명과 함께 해당 메서드가 나열되어 있습니다.  
  
|메서드|노드 배치|  
|------------|--------------------|  
|<xref:System.Xml.XmlNode.InsertBefore%2A>|참조 노드 앞에 삽입됩니다. 예를 들어, 위치 5에 새 노드를 삽입하려면 다음과 같이 입력합니다.<br /><br /> `Dim refChild As XmlNode = node.ChildNodes(4) 'The reference is zero-based.node.InsertBefore(newChild, refChild);`<br /><br /> `XmlNode refChild = node.ChildNodes[4]; //The reference is zero-based. node.InsertBefore(newChild, refChild);`<br /><br /> 자세한 내용은 참조는 <xref:System.Xml.XmlNode.InsertBefore%2A> 메서드.|  
|<xref:System.Xml.XmlNode.InsertAfter%2A>|참조 노드 다음에 삽입됩니다. 예를 들면 다음과 같습니다.<br /><br /> `node.InsertAfter(newChild, refChild)`<br /><br /> `node.InsertAfter(newChild, refChild);`<br /><br /> 자세한 내용은 참조는 <xref:System.Xml.XmlNode.InsertAfter%2A> 메서드.|  
|<xref:System.Xml.XmlNode.AppendChild%2A>|노드를 지정된 노드의 자식 노드 목록 끝에 추가합니다. 추가 되 고 있는 노드는 <xref:System.Xml.XmlDocumentFragment>, 문서 조각의 전체 내용이이 노드의 자식 목록으로 이동 합니다. 자세한 내용은 참조는 <xref:System.Xml.XmlNode.AppendChild%2A> 메서드.|  
|<xref:System.Xml.XmlNode.PrependChild%2A>|노드를 지정된 노드의 자식 노드 목록 시작 부분에 추가합니다. 추가 되 고 있는 노드는 <xref:System.Xml.XmlDocumentFragment>, 문서 조각의 전체 내용이이 노드의 자식 목록으로 이동 합니다. 자세한 내용은 참조는 <xref:System.Xml.XmlNode.PrependChild%2A> 메서드.|  
|<xref:System.Xml.XmlAttributeCollection.Append%2A>|추가 <xref:System.Xml.XmlAttribute> 노드는 요소와 연결 된 특성 컬렉션의 끝에 있습니다. 자세한 내용은 참조는 <xref:System.Xml.XmlAttributeCollection.Append%2A> 메서드.|  
  
## <a name="see-also"></a>참고 항목  
 [XML 문서 개체 모델 (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)