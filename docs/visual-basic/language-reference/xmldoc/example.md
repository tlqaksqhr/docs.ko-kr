---
title: "&lt;example&gt; (Visual Basic) | Microsoft Docs"
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
  - "example XML tag"
  - "<example> XML tag"
ms.assetid: 90eeda1c-3fc4-427c-879c-5046d265a97c
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# &lt;example&gt; (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

멤버에 대한 예제를 지정합니다.  
  
## 구문  
  
```  
<example>description</example>  
```  
  
#### 매개 변수  
 `description`  
 코드 예제에 대한 설명입니다.  
  
## 설명  
 `<example>` 태그를 사용하면 메서드나 기타 라이브러리 멤버의 사용 방법에 대한 예제를 지정할 수 있습니다.  이 경우 일반적으로 [\<code\>](../../../visual-basic/language-reference/xmldoc/code.md) 태그가 사용됩니다.  
  
 [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 저장합니다.  
  
## 예제  
 다음 예제에서는 `<example>` 태그를 사용하여 `ID` 필드 사용에 대한 예제를 포함합니다.  
  
 [!code-vb[VbVbcnXmlDocComments#2](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/example_1.vb)]  
  
## 참고 항목  
 [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)