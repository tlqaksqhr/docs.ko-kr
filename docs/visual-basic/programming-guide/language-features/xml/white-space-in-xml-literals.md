---
title: "White Space in XML Literals (Visual Basic) | Microsoft Docs"
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
  - "white space [XML in Visual Basic]"
  - "XML literals [Visual Basic], white space"
ms.assetid: dfe3a9ff-d69a-418e-a6b5-476f4ed84219
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# White Space in XML Literals (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 컴파일러에서는 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)] 개체를 만들 때 XML 리터럴의 유효 공백 문자만 포함합니다.  유효하지 않은 공백 문자는 포함되지 않습니다.  
  
## 유효 및 유효하지 않은 공백 문자  
 XML 리터럴의 공백 문자는 다음과 같은 세 가지 영역에 있는 경우에만 유효합니다.  
  
-   공백 문자가 특성 값에 있는 경우  
  
-   공백 문자가 요소의 텍스트 내용에 포함되어 있고 텍스트도 다른 문자를 포함하는 경우  
  
-   공백 문자가 요소의 텍스트 내용에 대한 포함 식에 있는 경우  
  
 위의 경우에 해당하지 않으면 컴파일러에서는 공백 문자를 유효하지 않은 것으로 처리하고 리터럴의 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)] 개체에 포함하지 않습니다.  
  
 유효하지 않은 공백 문자를 XML 리터럴에 포함하려면 공백 문자가 있는 문자열 리터럴이 들어 있는 포함 식을 사용합니다.  
  
> [!NOTE]
>  `xml:space` 특성이 XML 요소 리터럴에 나타나는 경우 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 컴파일러에서는 <xref:System.Xml.Linq.XElement> 개체에 해당 특성을 포함하지만 이 특성을 추가해도 컴파일러에서 공백을 처리하는 방법이 변경되지 않습니다.  
  
## 예제  
 다음 예제에는 두 가지 XML 요소인 외부 요소와 내부 요소가 있습니다.  두 요소의 텍스트 내용에 공백이 포함되어 있습니다.  외부 요소에는 공백과 XML 요소만 포함되어 있기 때문에 외부 요소의 공백은 유효하지 않습니다.  내부 요소에는 공백과 텍스트가 포함되어 있기 때문에 내부 요소의 공백은 유효합니다.  
  
 [!code-vb[VbXMLSamples#29](../../../../visual-basic/language-reference/operators/codesnippet/visualbasic/white-space-in-xml-liter_1.vb)]  
  
 이 코드를 실행하면 표시되는 텍스트는 다음과 같습니다.  
  
```  
<outer>  
  <inner>  
                                          Inner text  
                                      </inner>  
</outer>  
```  
  
## 참고 항목  
 [Creating XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)