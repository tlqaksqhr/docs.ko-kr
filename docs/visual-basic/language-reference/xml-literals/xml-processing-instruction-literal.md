---
title: "XML Processing Instruction Literal (Visual Basic) | Microsoft Docs"
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
  - "vb.XmlLiteralProcessingInstruction"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "XML literals [Visual Basic], processing instruction"
  - "XML processing instruction literal [Visual Basic]"
  - "processing instruction literal [Visual Basic]"
ms.assetid: cef4f7f8-0011-4f64-8602-795077ad4f15
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# XML Processing Instruction Literal (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

<xref:System.Xml.Linq.XProcessingInstruction> 개체를 나타내는 리터럴입니다.  
  
## 구문  
  
```  
<?piName [ = piData ] ?>  
```  
  
## 요소  
 `<?`  
 필수 요소.  XML 처리 명령 리터럴의 시작을 나타냅니다.  
  
 `piName`  
 필수 요소.  처리 명령의 대상 응용 프로그램을 나타내는 이름입니다.  "xml" 또는 "XML"로 시작할 수 없습니다.  
  
 `piData`  
 선택적 요소.  `piName`의 대상 응용 프로그램에서 XML 문서를 처리하는 방법을 나타내는 문자열입니다.  
  
 `?>`  
 필수 요소.  처리 명령의 끝을 나타냅니다.  
  
## 반환 값  
 <xref:System.Xml.Linq.XProcessingInstruction> 개체  
  
## 설명  
 XML 처리 명령 리터럴은 응용 프로그램에서 XML 문서를 처리하는 방법을 나타냅니다.  응용 프로그램에서는 XML 문서를 로드할 때 XML 처리 명령을 검사하여 문서 처리 방법을 결정합니다.  응용 프로그램에서는 `piName` 및 `piData`의 의미를 해석합니다.  
  
 XML 문서 리터럴에서는 XML 처리 명령의 구문과 유사한 구문을 사용합니다.  자세한 내용은 [XML Document Literal](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)을 참조하십시오.  
  
> [!NOTE]
>  XML 1.0 사양에는 문자열 "xml" 또는 "XML"이 예약되어 있기 때문에 `piName` 요소는 이러한 식별자로 시작할 수 없습니다.  
  
 XML 처리 명령 리터럴을 변수에 할당하거나 XML 문서 리터럴에 포함할 수 있습니다.  
  
> [!NOTE]
>  XML 리터럴은 줄 연속 문자를 사용하지 않고 여러 줄로 나타날 수 있습니다.  이 기능을 사용하여 XML 문서의 내용을 복사하여 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 프로그램에 직접 붙여넣을 수 있습니다.  
  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 컴파일러는 XML 처리 명령 리터럴을 <xref:System.Xml.Linq.XProcessingInstruction.%23ctor%2A> 생성자에 대한 호출로 변환합니다.  
  
## 예제  
 다음 예제에서는 XML 문서의 스타일시트를 식별하는 처리 명령을 만듭니다.  
  
 [!CODE [VbXMLSamples#28](../CodeSnippet/VS_Snippets_VBCSharp/VbXMLSamples#28)]  
  
## 참고 항목  
 <xref:System.Xml.Linq.XProcessingInstruction>   
 [XML Document Literal](../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)   
 [XML Literals](../../../visual-basic/language-reference/xml-literals/index.md)   
 [Creating XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)