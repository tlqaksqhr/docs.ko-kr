---
title: "&lt;remarks&gt; (Visual Basic) | Microsoft Docs"
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
  - "<remarks> XML tag"
  - "remarks XML tag"
ms.assetid: c6241773-a7ed-41c9-9a8b-9722a0c606a9
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# &lt;remarks&gt; (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

멤버에 대한 설명 부분을 지정합니다.  
  
## 구문  
  
```  
<remarks>description</remarks>  
```  
  
#### 매개 변수  
 `description`  
 멤버에 대한 설명입니다.  
  
## 설명  
 형식에 대한 정보를 추가하여 [\<summary\>](../../../visual-basic/language-reference/xmldoc/summary.md)로 지정된 정보를 보충하려면 `<remarks>` 태그를 사용합니다.  
  
 이 정보는 개체 브라우저에 나타납니다.  개체 브라우저에 대 한 내용은 [코드 구조 보기](/visual-studio/ide/viewing-the-structure-of-code).  
  
 [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 저장합니다.  
  
## 예제  
 다음 예제에서는 `<remarks>` 태그를 사용하여 `UpdateRecord` 메서드의 기능을 설명합니다.  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/remarks_1.vb)]  
  
## 참고 항목  
 [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)