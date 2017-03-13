---
title: "XML CDATA Literal (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.XmlLiteralCdata"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "CDATA literal [Visual Basic]"
  - "XML CDATA literal [Visual Basic]"
  - "XML literals [Visual Basic], CDATA"
ms.assetid: 9eafb6a4-dd9d-4866-85e8-0654c65abc44
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# XML CDATA Literal (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

<xref:System.Xml.Linq.XCData> 개체를 나타내는 리터럴입니다.  
  
## 구문  
  
```  
<![CDATA[content]]>  
```  
  
## 요소  
 `<![CDATA[`  
 필수 요소.  XML CDATA 섹션의 시작을 나타냅니다.  
  
 `content`  
 필수 요소.  XML CDATA 섹션에 표시할 텍스트 내용입니다.  
  
 `]]>`  
 필수 요소.  섹션의 끝을 나타냅니다.  
  
## 반환 값  
 <xref:System.Xml.Linq.XCData> 개체  
  
## 설명  
 XML CDATA 섹션에는 포함되어야 하지만 구문 분석되지 않은 원시 텍스트가 이 텍스트를 포함하는 XML과 함께 들어 있습니다.  XML CDATA 섹션은 모든 텍스트를 포함할 수 있습니다.  예약된 XML 문자도 포함될 수 있습니다.  XML CDATA 섹션은 시퀀스 "\]\]\>"로 끝납니다.  이는 다음 사항을 의미합니다.  
  
-   포함된 식 구분 기호는 유효한 XML CDATA 내용이므로 XML 주석 리터럴에서 포함된 식을 사용할 수 없습니다.  
  
-   `content`는 "\]\]\>" 값을 포함할 수 없으므로 XML CDATA 섹션을 중첩할 수 없습니다.  
  
 XML CDATA 리터럴을 변수에 할당하거나 XML 요소 리터럴에 포함할 수 있습니다.  
  
> [!NOTE]
>  XML 리터럴은 여러 줄로 나타날 수 있지만 줄 연속 문자를 사용하지 않습니다.  이 기능을 사용하여 XML 문서의 내용을 복사하여 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 프로그램에 직접 붙여넣을 수 있습니다.  
  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 컴파일러에서는 XML CDATA 리터럴을 <xref:System.Xml.Linq.XCData.%23ctor%2A> 생성자에 대한 호출로 변환합니다.  
  
## 예제  
 다음 예제에서는 "리터럴 \<XML\> 태그를 포함할 수 있음" 텍스트가 포함된 CDATA 섹션을 만듭니다.  
  
 [!code-vb[VbXMLSamples#23](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-cdata-literal_1.vb)]  
  
## 참고 항목  
 <xref:System.Xml.Linq.XCData>   
 [XML Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)   
 [XML Literals](../../../visual-basic/language-reference/xml-literals/index.md)   
 [Creating XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)