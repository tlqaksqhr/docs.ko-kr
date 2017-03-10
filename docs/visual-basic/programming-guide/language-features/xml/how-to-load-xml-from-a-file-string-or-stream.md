---
title: "How to: Load XML from a File, String, or Stream (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "XML [Visual Basic], loading"
  - "LINQ to XML [Visual Basic], loading XML from files"
ms.assetid: 2b02dcec-4cca-4575-b4ad-89ceb87b984c
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# How to: Load XML from a File, String, or Stream (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

[XML Literals](../../../../visual-basic/language-reference/xml-literals/index.md)을 만들어 여러 가지 메서드를 사용하여 파일, 문자열 또는 스트림과 같은 외부 소스의 내용으로 채울 수 있습니다.  이러한 메서드는 다음 예제에 나와 있습니다.  
  
 [!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note-settings-general-md.md)]  
  
### 파일에서 XML을 로드하려면  
  
-   파일에서 <xref:System.Xml.Linq.XElement> 또는 <xref:System.Xml.Linq.XDocument> 개체와 같은 XML 리터럴을 채우려면 `Load` 메서드를 사용합니다.  이 메서드에서는 파일 경로, 텍스트 스트림 또는 XML 스트림을 입력으로 사용할 수 있습니다.  
  
     다음 코드 예제에서는 <xref:System.Xml.Linq.XDocument.Load%28System.String%29> 메서드를 사용하여 <xref:System.Xml.Linq.XDocument> 개체를 텍스트 파일의 XML로 채우는 방법을 보여 줍니다.  
  
     [!code-vb[VbXMLSamples#43](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/how-to-load-xml-from-a-f_1.vb)]  
  
### 문자열에서 XML을 로드하려면  
  
-   문자열에서 <xref:System.Xml.Linq.XElement> 또는 <xref:System.Xml.Linq.XDocument> 개체와 같은 XML 리터럴을 채우려면 `Parse` 메서드를 사용할 수 있습니다.  
  
     다음 코드 예제에서는 <xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=fullName> 메서드를 사용하여 <xref:System.Xml.Linq.XDocument> 개체를 문자열의 XML로 채우는 방법을 보여 줍니다.  
  
     [!code-vb[VbXMLSamples#47](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/how-to-load-xml-from-a-f_2.vb)]  
  
### 스트림에서 XML을 로드하려면  
  
-   스트림에서 <xref:System.Xml.Linq.XElement> 또는 <xref:System.Xml.Linq.XDocument> 개체와 같은 XML 리터럴을 채우려면 `Load` 메서드 또는 <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=fullName> 메서드를 사용할 수 있습니다.  
  
 다음 코드 예제에서는 <xref:System.Xml.Linq.XNode.ReadFrom%2A> 메서드를 사용하여 <xref:System.Xml.Linq.XDocument> 개체를 XML 스트림의 XML로 채우는 방법을 보여 줍니다.  
  
 [!code-vb[VbXMLSamples#46](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/how-to-load-xml-from-a-f_3.vb)]  
  
## 참고 항목  
 <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName>   
 <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName>   
 <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>   
 <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName>   
 <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=fullName>   
 [XML Literals](../../../../visual-basic/language-reference/xml-literals/index.md)   
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)   
 [Manipulating XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)