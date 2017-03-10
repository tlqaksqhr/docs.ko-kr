---
title: "GetXmlNamespace Operator (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.GetXmlNamespace"
  - "GetXmlNamespace"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "GetXmlNamespace operator"
  - "GetXmlNamespace keyword"
ms.assetid: d0d28cfd-0755-4896-ae0b-4981aa35517c
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# GetXmlNamespace Operator (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

지정된 XML 네임스페이스 접두사에 해당하는 <xref:System.Xml.Linq.XNamespace> 개체를 가져옵니다.  
  
## 구문  
  
```  
GetXmlNamespace(xmlNamespacePrefix)  
```  
  
## 요소  
 `xmlNamespacePrefix`  
 선택적 요소.  XML 네임스페이스 접두사를 식별하는 문자열입니다.  지정된 경우 이 문자열은 유효한 XML 식별자여야 합니다.  자세한 내용은 [Names of Declared XML Elements and Attributes](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)를 참조하십시오.  지정된 접두사가 없으면 기본 네임스페이스가 반환됩니다.  지정된 기본 네임스페이스가 없으면 빈 네임스페이스가 반환됩니다.  
  
## 반환 값  
 XML 네임스페이스 접두사에 해당하는 <xref:System.Xml.Linq.XNamespace> 개체입니다.  
  
## 설명  
 `GetXmlNamespace` 연산자는 XML 네임스페이스 접두사 `xmlNamespacePrefix`에 해당하는 <xref:System.Xml.Linq.XNamespace> 개체를 가져옵니다.  
  
 XML 네임스페이스 접두사를 XML 리터럴 및 XML 축 속성에 직접 사용할 수 있습니다.  그러나 네임스페이스 접두사를 코드에 사용하기 전에 `GetXmlNamespace` 연산자를 사용하여 네임스페이스 접두사를 <xref:System.Xml.Linq.XNamespace> 개체로 변환해야 합니다.  정규화되지 않은 요소 이름을 <xref:System.Xml.Linq.XNamespace> 개체에 추가하여 많은 [!INCLUDE[sqltecxlinq](../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)] 메서드에서 필요로 하는 정규화된 <xref:System.Xml.Linq.XName> 개체를 가져올 수 있습니다.  
  
## 예제  
 다음 예제에서는 `ns`를 XML 네임스페이스 접두사로 가져옵니다.  그런 다음 네임스페이스의 접두사를 사용하여 XML 리터럴을 만들고 정규화된 이름이 `ns:phone`인 첫 번째 자식 노드에 액세스합니다.  그런 다음 해당 자식 노드를 `GetXmlNamespace` 연산자를 사용하여 정규화된 이름을 생성하는 `ShowName` 서브루틴으로 전달합니다.  그런 다음 `ShowName` 서브루틴에서는 정규화된 이름을 <xref:System.Xml.Linq.XNode.Ancestors%2A> 메서드로 전달하여 부모 `ns:contact` 노드를 가져옵니다.  
  
 [!code-vb[VbXMLSamples#38](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/getxmlnamespace-operator_1.vb)]  
  
 `TestGetXmlNamespace.RunSample()`을 호출하면 다음 텍스트가 포함된 메시지 상자가 표시됩니다.  
  
 `Name: Patrick Hines`  
  
## 참고 항목  
 [Imports Statement \(XML Namespace\)](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)   
 [Accessing XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)