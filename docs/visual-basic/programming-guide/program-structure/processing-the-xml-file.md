---
title: "Processing the XML File (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "XML comments, parsing [Visual Basic]"
ms.assetid: 78a15cd0-7708-4e79-85d1-c154b7a14a8c
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# Processing the XML File (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

컴파일러는 태그가 있는 코드의 각 구문에 ID 문자열을 생성하여 문서를 만듭니다.  코드에 태그를 지정하는 방법에 대한 자세한 내용은 [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)를 참조하십시오. ID 문자열은 해당 구문을 고유하게 식별합니다.  XML 파일을 처리하는 프로그램에서는 ID 문자열을 사용하여 해당 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] 메타데이터\/리플렉션 항목을 식별할 수 있습니다.  
  
 XML 파일은 코드를 계층 구조로 표현하지 않고 각 요소에 대해 생성된 ID로 단순하게 목록화합니다.  
  
 컴파일러는 아래와 같은 규칙에 따라 ID 문자열을 생성합니다.  
  
-   문자열에 공백 문자를 배치하지 않습니다.  
  
-   ID 문자열의 첫 부분은 식별할 멤버의 종류를 나타내는 단일 문자이며 그 뒤에 콜론이 옵니다.  다음과 같은 멤버 형식을 사용합니다.  
  
|||  
|-|-|  
|문자|설명|  
|N|네임스페이스<br /><br /> 네임스페이스에는 문서 주석을 추가할 수 없지만 지원되는 경우 문서 주석에 대한 CREF 참조를 만들 수 있습니다.|  
|T|형식: `Class`, `Module`, `Interface`, `Structure`, `Enum`, `Delegate`|  
|F|필드: `Dim`|  
|P|속성: `Property`\(기본 속성 포함\)|  
|M|메서드: `Sub`, `Function`, `Declare`, `Operator`|  
|E|이벤트: `Event`|  
|\!|오류 문자열<br /><br /> 나머지 문자열은 오류 정보를 제공합니다.  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 컴파일러는 확인할 수 없는 링크에 대한 오류 정보를 생성합니다.|  
  
-   `String`의 둘째 부분은 네임스페이스의 루트에서 시작하는 항목의 정규화된 이름입니다.  항목의 이름, 해당 바깥쪽 형식 및 네임스페이스는 마침표로 구분합니다.  항목 이름 자체에 마침표가 있는 경우 해당 마침표는 숫자 기호\(\#\)로 바뀝니다.  항목 이름에 직접 숫자 기호를 사용하지 않는 것으로 가정합니다.  예를 들어, `String` 생성자의 정규화된 이름은 `System.String.#ctor`가 될 수 있습니다.  
  
-   속성 및 메서드의 경우, 메서드 인수가 있는 경우 인수 목록을 괄호로 묶어야 합니다.  인수가 없으면 괄호는 필요 없습니다.  인수는 쉼표로 구분합니다.  각 인수의 인코딩은 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] 시그니처에서 인수를 인코딩하는 방법을 그대로 따릅니다.  
  
## 예제  
 다음 코드에서는 클래스와 해당 멤버의 ID 문자열이 생성되는 방식을 보여 줍니다.  
  
 [!code-vb[VbVbcnXmlDocComments#10](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/processing-the-xml-file_1.vb)]  
  
## 참고 항목  
 [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md)   
 [How to: Create XML Documentation](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)