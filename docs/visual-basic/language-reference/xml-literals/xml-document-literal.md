---
title: "XML Document Literal (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.XmlLiteralDocument"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "XML document literal [Visual Basic]"
  - "XML literals [Visual Basic], document"
  - "XML documents [Visual Basic], creating"
  - "document literal [Visual Basic]"
ms.assetid: f7bbee56-0911-41de-b907-96f20450137b
caps.latest.revision: 20
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 20
---
# XML Document Literal (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

<xref:System.Xml.Linq.XDocument> 개체를 나타내는 리터럴입니다.  
  
## 구문  
  
```  
<?xml version="1.0" [encoding="encoding"] [standalone="standalone"] ?>  
[ piCommentList ]  
rootElement  
[ piCommentList ]  
```  
  
## 요소  
  
|||  
|-|-|  
|용어|정의|  
|`encoding`|선택적 요소.  문서에서 사용하는 인코딩을 선언하는 리터럴 텍스트입니다.|  
|`standalone`|선택적 요소.  리터럴 텍스트입니다.  “예” 또는 “아니요”이어야 합니다.|  
|`piCommentList`|선택적 요소.  XML 처리 명령 및 XML 주석 목록입니다.  이 문은 다음과 같은 형식을 사용합니다.<br /><br /> `piComment [` `piComment` `... ]`<br /><br /> 각 `piComment`는 `` 다음 중 하나일 수 있습니다.<br /><br /> -   [XML Processing Instruction Literal](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md).<br />-   [XML Comment Literal](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md).|  
|`rootElement`|필수 요소.  문서의 루트 요소입니다.  형식은 다음 중 하나입니다.<br /><br /> <ul><li>[XML Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md).</li><li>`<%=` `elementExp` `%>` 형식의 포함 식입니다.  `elementExp`에서는 다음 중 하나를 반환합니다.<br /><br /> <ul><li><xref:System.Xml.Linq.XElement> 개체</li><li>한 개의 <xref:System.Xml.Linq.XElement> 개체와 여러 개의 <xref:System.Xml.Linq.XProcessingInstruction> 및 <xref:System.Xml.Linq.XComment> 개체를 포함하고 있는 컬렉션</li></ul></li></ul><br /> 자세한 내용은 [Embedded Expressions in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)을 참조하십시오.|  
  
## 반환 값  
 <xref:System.Xml.Linq.XDocument> 개체  
  
## 설명  
 XML 문서 리터럴은 리터럴의 시작 부분에 있는 XML 선언에 의해 식별됩니다.  각 XML 문서 리터럴에 정확히 하나의 루트 XML 요소가 있더라도 여러 개의 XML 처리 명령과 XML 주석이 있을 수 있습니다.  
  
 XML 문서 리터럴은 XML 요소에 나타날 수 없습니다.  
  
> [!NOTE]
>  XML 리터럴은 줄 연속 문자를 사용하지 않고 여러 줄로 나타날 수 있습니다.  이 기능을 사용하여 XML 문서의 내용을 복사하여 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 프로그램에 직접 붙여넣을 수 있습니다.  
  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 컴파일러는 XML 문서 리터럴을 <xref:System.Xml.Linq.XDocument.%23ctor%2A> 및 <xref:System.Xml.Linq.XDeclaration.%23ctor%2A> 생성자에 대한 호출로 변환합니다.  
  
## 예제  
 다음 예제에서는 XML 선언, 처리 명령, 주석 및 다른 요소를 포함하는 요소가 있는 XML 문서를 만듭니다.  
  
 [!code-vb[VbXMLSamples#30](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/xml-document-literal_1.vb)]  
  
## 참고 항목  
 <xref:System.Xml.Linq.XElement>   
 <xref:System.Xml.Linq.XProcessingInstruction>   
 <xref:System.Xml.Linq.XComment>   
 <xref:System.Xml.Linq.XDocument>   
 [XML Processing Instruction Literal](../../../visual-basic/language-reference/xml-literals/xml-processing-instruction-literal.md)   
 [XML Comment Literal](../../../visual-basic/language-reference/xml-literals/xml-comment-literal.md)   
 [XML Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)   
 [XML Literals](../../../visual-basic/language-reference/xml-literals/index.md)   
 [Creating XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [Embedded Expressions in XML](../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)