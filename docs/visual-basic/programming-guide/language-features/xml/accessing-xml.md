---
title: "Accessing XML in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "LINQ to XML [Visual Basic], accessing XML"
  - "Visual Basic code, XML"
  - "accessing XML [Visual Basic], axis properties"
  - "XML [Visual Basic], axis properties"
  - "XML [Visual Basic], accessing"
ms.assetid: c47f88b2-3cbc-4bb1-b4b9-be60f71ffc6a
caps.latest.revision: 18
caps.handback.revision: 18
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Accessing XML in Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서는 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 구조에 액세스하고 탐색하기 위한 XML 축 속성을 제공합니다.  이러한 속성에서는 XML 이름을 지정하여 요소 및 특성에 액세스할 수 있는 특수 구문을 사용합니다.  
  
 다음 표에서는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서 XML 요소와 특성에 액세스할 수 있는 언어 기능을 보여 줍니다.  
  
### XML 축 속성  
  
|속성 설명|예제|설명|  
|-----------|--------|--------|  
|*자식 축*|`contact.<phone>`|`contact` 요소의 자식 요소인 모든 `phone` 요소를 가져옵니다.|  
|*특성 축*|`phone.@type`|`phone` 요소의 모든 `type` 특성을 가져옵니다.|  
|*하위 항목 축*|`contacts...<name>`|계층 구조 내에서의 위치와 상관없이 `contacts` 요소의 모든 `name` 요소를 가져옵니다.|  
|*확장 인덱서*|`contacts...<name>(0)`|시퀀스의 첫 번째 `name` 요소를 가져옵니다.|  
|*value*|`contacts...<name>.Value`|시퀀스의 첫 번째 개체에 대한 문자열 표현을 가져오거나 시퀀스가 비어 있는 경우에는 `Nothing`을 가져옵니다.|  
  
## 단원 내용  
 [How to: Access XML Descendant Elements](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-descendant-elements.md)  
 하위 항목 축 속성을 사용하여 지정된 이름이 있는 지정된 XML 요소 아래에 포함된 모든 XML 요소에 액세스하는 방법을 보여 줍니다.  
  
 [How to: Access XML Child Elements](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-child-elements.md)  
 자식 축 속성을 사용하여 XML 요소에 지정된 이름이 있는 모든 XML 자식 요소에 액세스하는 방법을 보여 줍니다.  
  
 [How to: Access XML Attributes](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-attributes.md)  
 특성 축 속성을 사용하여 XML 요소에 지정된 이름이 있는 모든 XML 특성에 액세스하는 방법을 보여 줍니다.  
  
 [How to: Declare and Use XML Namespace Prefixes](../../../../visual-basic/programming-guide/language-features/xml/how-to-declare-and-use-xml-namespace-prefixes.md)  
 XML 네임스페이스 접두사를 선언하고 해당 접두사를 사용하여 XML 요소를 만들고 액세스하는 방법을 보여 줍니다.  
  
## 관련 단원  
 [XML Axis Properties](../../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 다양한 XML 액세스 속성을 설명하는 단원에 대한 링크를 제공합니다.  
  
 [Overview of LINQ to XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)  
 Visual Basic에서의 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 사용에 대한 개요를 제공합니다.  
  
 [Creating XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 Visual Basic에서의 XML 리터럴 사용에 대한 개요를 제공합니다.  
  
 [Manipulating XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)  
 Visual Basic에서 XML을 로드하고 수정하는 방법을 설명하는 단원에 대한 링크를 제공합니다.  
  
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 Visual Basic에서 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]을 사용하는 방법을 설명하는 단원에 대한 링크를 제공합니다.