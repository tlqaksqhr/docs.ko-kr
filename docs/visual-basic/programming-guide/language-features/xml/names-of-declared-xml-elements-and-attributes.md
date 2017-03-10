---
title: "Names of Declared XML Elements and Attributes (Visual Basic) | Microsoft Docs"
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
  - "declarations [XML in Visual Basic]"
  - "element names [XML in Visual Basic]"
  - "names in XML literals"
  - "attribute names [XML in Visual Basic]"
  - "XML literals [Visual Basic], element names"
ms.assetid: cc110118-b6cf-4ff9-a4e4-6233c90c9fbf
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# Names of Declared XML Elements and Attributes (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

이 항목에서는 XML 리터럴의 XML 요소 및 특성의 이름을 지정하는 데 필요한 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 지침을 제공합니다. XML 리터럴에는 로컬 이름 또는 정규화된 이름을 지정할 수 있습니다.  정규화된 이름은 XML 네임스페이스 접두사, 콜론 및 로컬 이름으로 구성됩니다.  XML 네임스페이스 접두사에 대한 자세한 내용은 [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)을 참조하십시오.  
  
## 규칙  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서 요소 또는 특성의 로컬 이름은 다음 규칙을 따라야 합니다.  
  
-   네임스페이스로 시작할 수 있습니다.  영문자 또는 밑줄\(`_`\)로 시작해야 합니다.  
  
-   영문자, 10진수, 밑줄, 마침표\(.\) 및 하이픈\(\-\)만으로 이루어져야 합니다.  
  
-   두 개 이상의 1024 자 아니어야 합니다.  
  
-   이름에 나타나는 콜론은 네임스페이스 구분을 의미합니다.  따라서 콜론만 사용하여 특정 이름에 대해 XML 네임스페이스를 지정할 수 있습니다.  
  
 또한 다음 지침을 따라야 합니다.  
  
-   XML 1.0 사양에는 모든 대문자 변형에 대해 문자열 "xml"로 시작하는 모든 이름이 예약되어 있습니다.  따라서 요소 및 특성 이름에 이러한 이름을 사용하지 마십시오.  
  
### 이름 길이 지침  
 실제 적용에 있어서 이름은 요소의 특성을 명확히 나타내면서 가능한 간결하게 지정해야  코드를 읽기가 쉬워지고 줄의 길이와 소스 파일 크기가 줄어듭니다.  
  
 그러나 이름이 요소 또는 코드에서 해당 요소를 사용하는 방법에 대해 충분히 설명하지 못할 정도로 짧아서는 안 됩니다.  이름의 길이는 코드의 가독성에 중요한 영향을 미칩니다.  적합한 요소 이름은 다른 사용자가 이름을 이해하려는 경우 또는 사용자 자신이 이름을 작성하고 나서 한참 뒤에 해당 이름을 보는 경우 시간을 절약할 수 있습니다.  
  
## 이름의 대\/소문자 구분  
 XML 요소 이름은 대\/소문자를 구분합니다.  즉, [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 컴파일러에서는 알파벳은 같고 대\/소문자가 다른 두 이름이 서로 다른 이름으로 해석됩니다.  예를 들어 `ABC`와 `abc`는 각각 별도의 요소를 참조하는 것으로 해석합니다.  
  
## XML 네임스페이스  
 XML 요소 리터럴을 만드는 경우 요소 이름에 대해 XML 네임스페이스 접두사를 지정할 수 있습니다.  자세한 내용은 [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)을 참조하십시오.  
  
## 참고 항목  
 [Creating XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)   
 [XML Element Literal](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)