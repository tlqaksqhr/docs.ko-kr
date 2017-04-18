---
title: "XPathNavigator를 사용하여 노드 일치시키기 | Microsoft Docs"
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
ms.assetid: e6848c47-ee5d-401a-89a5-50b5eed40f30
caps.latest.revision: 2
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 2
---
# XPathNavigator를 사용하여 노드 일치시키기
<xref:System.Xml.XPath.XPathNavigator> 클래스는 노드가 XPath 식과 일치하는지 결정하는 <xref:System.Xml.XPath.XPathNavigator.Matches%2A> 메서드를 제공합니다.  <xref:System.Xml.XPath.XPathNavigator.Matches%2A> 메서드는 XPath 식을 입력으로 사용하며 현재 노드가 지정된 XPath 식 또는 지정된 컴파일된 <xref:System.Xml.XPath.XPathExpression> 개체와 일치하는지를 나타내는 <xref:System.Boolean>을 반환합니다.  
  
## 노드 일치시키기  
 현재 노드가 지정된 XPath 식과 일치하는 경우 <xref:System.Xml.XPath.XPathNavigator.Matches%2A> 메서드는 `true`를 반환합니다.  예를 들어, 다음 코드 예제에서 현재 노드가 `b` 요소이고 `b` 요소에 `c` 특성이 있을 경우 <xref:System.Xml.XPath.XPathNavigator.Matches%2A> 메서드는 `true`를 반환합니다.  
  
> [!NOTE]
>  <xref:System.Xml.XPath.XPathNavigator.Matches%2A> 메서드는 <xref:System.Xml.XPath.XPathNavigator> 상태를 변경하지 않습니다.  
  
```vb  
Dim document as XPathDocument = New XPathDocument("input.xml")  
Dim navigator as XPathNavigator = document.CreateNavigator()  
  
navigator.Matches("b[@c]")  
```  
  
```csharp  
XPathDocument document = new XPathDocument("input.xml");  
XPathNavigator navigator = document.CreateNavigator();  
  
navigator.Matches("b[@c]");  
```  
  
## 참고 항목  
 <xref:System.Xml.XmlDocument>   
 <xref:System.Xml.XPath.XPathDocument>   
 <xref:System.Xml.XPath.XPathNavigator>   
 [XPath 데이터 모델을 사용하여 XML 데이터 처리](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)   
 [XPathNavigator를 사용하여 XML 데이터 선택](../../../../docs/standard/data/xml/select-xml-data-using-xpathnavigator.md)   
 [XPathNavigator를 사용하여 XPath 식 계산](../../../../docs/standard/data/xml/evaluate-xpath-expressions-using-xpathnavigator.md)   
 [XPath 쿼리에서 인식하는 노드 형식](../../../../docs/standard/data/xml/node-types-recognized-with-xpath-queries.md)   
 [XPath 쿼리 및 네임스페이스](../../../../docs/standard/data/xml/xpath-queries-and-namespaces.md)   
 [컴파일된 XPath 식](../../../../docs/standard/data/xml/compiled-xpath-expressions.md)