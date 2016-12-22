---
title: "XML Comment Literal (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.XmlLiteralComment"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "comment literal [Visual Basic]"
  - "XML comments, adding [Visual Basic]"
  - "XML comment literal [Visual Basic]"
  - "XML literals [Visual Basic], comment"
ms.assetid: 634c1cee-5e01-48d0-88d7-2dd55e4a9e52
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# XML Comment Literal (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

<xref:System.Xml.Linq.XComment> 개체를 나타내는 리터럴입니다.  
  
## 구문  
  
```  
<!-- content -->  
```  
  
## 요소  
  
|||  
|-|-|  
|용어|정의|  
|`<!--`|필수 요소.  XML 주석의 시작을 나타냅니다.|  
|`content`|필수 요소.  XML 주석에 표시할 텍스트입니다.  일련의 두 개의 하이픈\(\-\-\)을 포함하거나 닫는 태그에 인접한 하이픈으로 끝날 수 없습니다.|  
|`-->`|필수 요소.  XML 주석의 끝을 나타냅니다.|  
  
## 반환 값  
 <xref:System.Xml.Linq.XComment> 개체  
  
## 설명  
 XML 주석 리터럴에는 문서 내용이 포함되지 않으며 문서에 대한 정보가 포함됩니다.  XML 주석 섹션은 시퀀스 "\-\-\>"로 끝납니다.  이는 다음 사항을 의미합니다.  
  
-   포함 식 구분 기호는 유효한 XML 주석 내용이 아니므로 XML 주석 리터럴에서 포함 식을 사용할 수 없습니다.  
  
-   `content`는 "\-\-\>" 값을 포함할 수 없으므로 XML 주석 섹션은 중첩될 수 없습니다.  
  
 XML 주석 리터럴을 변수에 할당하거나 XML 요소 리터럴에 포함할 수 있습니다.  
  
> [!NOTE]
>  XML 리터럴은 줄 연속 문자를 사용하지 않고 여러 줄로 나타날 수 있습니다.  이 기능을 사용하여 XML 문서의 내용을 복사하고 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 프로그램에 직접 붙여넣을 수 있습니다.  
  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 컴파일러에서는 XML 주석 리터럴을 <xref:System.Xml.Linq.XComment.%23ctor%2A> 생성자에 대한 호출로 변환합니다.  
  
## 예제  
 다음 예제에서는 "This is a comment" 텍스트를 포함하는 XML 주석을 만듭니다.  
  
 [!CODE [VbXMLSamples#9](../CodeSnippet/VS_Snippets_VBCSharp/VbXMLSamples#9)]  
  
## 참고 항목  
 <xref:System.Xml.Linq.XComment>   
 [XML Element Literal](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)   
 [XML Literals](../../../visual-basic/language-reference/xml-literals/index.md)   
 [Creating XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)