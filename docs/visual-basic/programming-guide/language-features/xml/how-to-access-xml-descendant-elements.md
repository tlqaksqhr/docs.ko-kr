---
title: "How to: Access XML Descendant Elements (Visual Basic) | Microsoft Docs"
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
  - "XML descendent axis property [Visual Basic]"
  - "XML axis [Visual Basic], descendent"
  - "descendent axis property [Visual Basic]"
  - "XML [Visual Basic], accessing"
ms.assetid: aabfa258-4112-4e7e-bab9-403f96072ef7
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# How to: Access XML Descendant Elements (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

이 예제에서는 하위 항목 축 속성을 사용하여 지정된 이름이 있는 XML 요소 아래에 포함된 모든 XML 요소에 액세스하는 방법을 보여 줍니다.  특히 `Value` 속성을 사용하여 `name` 하위 항목 축 속성에서 반환하는 컬렉션의 첫 번째 요소 값을 가져옵니다.  `name` 하위 항목 축 속성은 `contacts` 개체에 포함된 `name`이라는 모든 요소를 가져옵니다.  또한 이 예제에서는 `phone` 하위 항목 축 속성을 사용하여 `contacts` 개체에 포함된 `phone`이라는 모든 하위 항목에 액세스합니다.  
  
## 예제  
 [!code-vb[VbXMLSamples#31](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-access-xml-descendant-elements_1.vb)]  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   <xref:System.Xml.Linq> 네임스페이스에 대한 참조  
  
## 참고 항목  
 <xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=fullName>   
 [XML Descendant Axis Property](../../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md)   
 [XML Value Property](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)   
 [Accessing XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)   
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)