---
title: "Recommended XML Tags for Documentation Comments (Visual Basic) | Microsoft Docs"
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
  - "vb.XmlDocComment"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "tags, XML"
  - "XML comments, recommended tags [Visual Basic]"
  - "comments, recommended XML tags"
ms.assetid: 294e0736-ff1e-498e-af83-6db71ed41a72
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Recommended XML Tags for Documentation Comments (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 컴파일러는 코드의 문서 주석을 XML 파일로 만들 수 있습니다.  추가 도구를 사용하면 XML 파일을 문서로 만들 수도 있습니다.  
  
 XML 주석은 형식, 형식 멤버 등과 같은 코드 구문에서 사용할 수 있습니다.  부분 형식\(Partial Type\)의 경우 해당 멤버의 주석 처리에는 제한이 없어도 형식의 한 부분에만 XML 주석을 사용할 수 있습니다.  
  
> [!NOTE]
>  네임스페이스에는 문서 주석을 적용할 수 없습니다.  그 이유는 한 네임스페이스가 여러 어셈블리에 확장될 수 있으며, 모든 어셈블리를 동시에 로드할 필요가 없기 때문입니다.  
  
 컴파일러는 유효한 XML 태그를 모두 처리합니다.  아래 태그에는 사용자 문서에서 자주 사용하는 기능이 포함되어 있습니다.  
  
||||  
|-|-|-|  
|[\<c\>](../../../visual-basic/language-reference/xmldoc/c.md)|[\<code\>](../../../visual-basic/language-reference/xmldoc/code.md)|[\<example\>](../../../visual-basic/language-reference/xmldoc/example.md)|  
|[\<exception\>](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup>|[\<include\>](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup>|[\<list\>](../../../visual-basic/language-reference/xmldoc/list.md)|  
|[\<para\>](../../../visual-basic/language-reference/xmldoc/para.md)|[\<param\>](../../../visual-basic/language-reference/xmldoc/param.md) <sup>1</sup>|[\<paramref\>](../../../visual-basic/language-reference/xmldoc/paramref.md)|  
|[\<permission\>](../../../visual-basic/language-reference/xmldoc/permission.md) <sup>1</sup>|[\<remarks\>](../Topic/%3Cremarks%3E%20\(Visual%20Basic\).md)|[\<returns\>](../../../visual-basic/language-reference/xmldoc/returns.md)|  
|[\<see\>](../../../visual-basic/language-reference/xmldoc/see.md) <sup>1</sup>|[\<seealso\>](../../../visual-basic/language-reference/xmldoc/seealso.md) <sup>1</sup>|[\<summary\>](../Topic/%3Csummary%3E%20\(Visual%20Basic\).md)|  
|[\<typeparam\>](../../../visual-basic/language-reference/xmldoc/typeparam.md) <sup>1</sup>|[\<value\>](../../../visual-basic/language-reference/xmldoc/value.md)||  
  
 \(<sup>1</sup> 컴파일러가 구문을 확인합니다.\)  
  
> [!NOTE]
>  문서 주석의 텍스트에 꺽쇠괄호를 표시하려면 `<`와 `>`을 사용합니다.  예를 들어, `"<text in angle brackets>"` 문자열은 `<text in angle` `brackets>`으로 표시됩니다.  
  
## 참고 항목  
 [Documenting Your Code with XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)   
 [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md)   
 [How to: Create XML Documentation](../Topic/How%20to:%20Create%20XML%20Documentation%20in%20Visual%20Basic.md)