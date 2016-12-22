---
title: "Extension Indexer Property (Visual Basic) | Microsoft Docs"
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
  - "vb.XmlPropertyExtensionIndexer"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Visual Basic code, accessing XML"
  - "XML extension indexer [Visual Basic]"
  - "extension indexer [Visual Basic]"
  - "XML [Visual Basic], accessing"
ms.assetid: a16a4b13-54be-432c-82b3-a87091464ada
caps.latest.revision: 22
caps.handback.revision: 22
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Extension Indexer Property (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

컬렉션의 각 요소에 대한 액세스를 제공합니다.  
  
## 구문  
  
```  
  
object(index)  
```  
  
## 요소  
  
|||  
|-|-|  
|용어|정의|  
|`object`|필수 요소.  쿼리 가능한 컬렉션입니다.  즉, <xref:System.Collections.Generic.IEnumerable%601> 또는 <xref:System.Linq.IQueryable%601>을 구현하는 컬렉션입니다.|  
|\(|필수 요소.  인덱서 속성의 시작을 나타냅니다.|  
|`index`|필수 요소.  컬렉션 요소의 위치\(0부터 시작\)를 지정하는 정수 식입니다.|  
|\)|필수 요소.  인덱서 속성의 끝을 나타냅니다.|  
  
## 반환 값  
 컬렉션의 지정된 위치에 있는 개체이며 인덱스가 범위를 벗어난 경우에는 `Nothing`입니다.  
  
## 설명  
 확장 인덱서 속성을 사용하여 컬렉션의 각 요소에 액세스할 수 있습니다.  일반적으로 이 인덱서 속성은 XML 축 속성의 출력에 사용됩니다.  XML 자식 및 XML 하위 항목 축 속성은 <xref:System.Xml.Linq.XElement> 개체의 컬렉션 또는 특성 값을 반환합니다.  
  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 컴파일러가 확장명 인덱서 속성을 `ElementAtOrDefault` 메서드에 대한 호출로 변환합니다. 배열 인덱서와 달리, 인덱스의 범위가 초과될 경우 `ElementAtOrDefault` 메서드는 `Nothing`을 반환합니다.  이러한 동작은 컬렉션의 요소 수를 확인하는 데 매우 유용합니다.  
  
 이 인덱서 속성은 <xref:System.Collections.Generic.IEnumerable%601> 또는 <xref:System.Linq.IQueryable%601>을 구현하는 컬렉션의 확장 속성과 같으며 컬렉션에 인덱서 또는 기본 속성이 없는 경우에만 사용됩니다.  
  
 <xref:System.Xml.Linq.XElement> 또는 <xref:System.Xml.Linq.XAttribute> 개체의 컬렉션에 있는 첫 번째 요소의 값에 액세스하려면 XML `Value` 속성을 사용합니다.  자세한 내용은 [XML Value Property](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)를 참조하십시오.  
  
## 예제  
 다음 예제에서는 확장 인덱서를 사용하여 <xref:System.Xml.Linq.XElement> 개체의 컬렉션에 있는 두 번째 자식 노드에 액세스하는 방법을 보여 줍니다.  컬렉션은 `contact` 개체에서 `phone`이라는 모든 자식 요소를 가져오는 자식 축 속성을 사용하여 액세스합니다.  
  
 [!CODE [VbXMLSamples#24](../CodeSnippet/VS_Snippets_VBCSharp/VbXMLSamples#24)]  
  
 이 코드가 표시하는 텍스트는 다음과 같습니다.  
  
 `Second phone number: 425-555-0145`  
  
## 참고 항목  
 <xref:System.Xml.Linq.XElement>   
 [XML Axis Properties](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)   
 [XML Literals](../../../visual-basic/language-reference/xml-literals/index.md)   
 [Creating XML in Visual Basic](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [XML Value Property](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)