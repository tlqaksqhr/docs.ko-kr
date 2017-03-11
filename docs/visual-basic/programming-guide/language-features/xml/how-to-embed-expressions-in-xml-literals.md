---
title: "How to: Embed Expressions in XML Literals (Visual Basic) | Microsoft Docs"
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
  - "embedded expressions [Visual Basic]"
  - "XML literals [Visual Basic], embedded expressions"
ms.assetid: 75016fad-0141-42de-8564-5051be29487e
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# How to: Embed Expressions in XML Literals (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

XML 리터럴을 포함 식과 결합하여 런타임에 생성된 내용을 포함하는 XML 문서, 조각 또는 요소를 만들 수 있습니다.  다음 예제에서는 포함 식을 사용하여 요소 내용, 특성 및 요소 이름을 런타임에 채우는 방법을 보여 줍니다.  
  
 포함 식의 구문은 `<%=` `exp` `%>`이며 [!INCLUDE[vstecasp](../../../../csharp/language-reference/preprocessor-directives/includes/vstecasp-md.md)]에서 사용하는 구문과 같습니다. 자세한 내용은 [Embedded Expressions in XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)을 참조하십시오.  
  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)] API를 사용하여 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)] 개체를 만들 수도 있습니다.  자세한 내용은 <xref:System.Xml.Linq.XElement>를 참조하십시오.  
  
## 절차  
  
#### 텍스트를 요소 내용으로 삽입하려면  
  
-   다음 예제에서는 `contactName` 변수에 포함된 텍스트를 여는 이름 요소와 닫는 이름 요소 사이에 삽입하는 방법을 보여 줍니다.  
  
     [!code-vb[VbXMLSamples#39](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/how-to-embed-expressions_1.vb)]  
  
     이 예제의 결과는 다음과 같습니다.  
  
    ```  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
#### 텍스트를 특성 값으로 삽입하려면  
  
-   다음 예제에서는 `phoneType` 변수에 포함된 텍스트를 `type` 특성의 값으로 삽입하는 방법을 보여 줍니다.  
  
     [!code-vb[VbXMLSamples#40](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/how-to-embed-expressions_2.vb)]  
  
     이 예제의 결과는 다음과 같습니다.  
  
    ```  
    <contact>  
      <phone type="home">206-555-0144</phone>  
    </contact>  
    ```  
  
#### 요소 이름에 대해 텍스트를 삽입하려면  
  
-   다음 예제에서는 `elementName` 변수에 포함된 텍스트를 요소의 이름으로 삽입하는 방법을 보여 줍니다.  
  
     이 방법을 사용하여 요소를 만들 때 해당 요소를 \<\/\> 태그로 닫아야 합니다.  
  
     [!code-vb[VbXMLSamples#41](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/how-to-embed-expressions_3.vb)]  
  
     이 예제의 결과는 다음과 같습니다.  
  
    ```  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
## 참고 항목  
 [How to: Create XML Literals](../../../../visual-basic/programming-guide/language-features/xml/how-to-create-xml-literals.md)   
 [Embedded Expressions in XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)   
 [Creating XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)