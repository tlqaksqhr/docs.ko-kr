---
title: "&lt;c&gt; (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
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
  - "c XML tag"
  - "<c> XML tag"
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;c&gt; (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

설명 안의 텍스트가 코드임을 나타냅니다.  
  
## 구문  
  
```  
<c>text</c>  
```  
  
#### 매개 변수  
  
|||  
|-|-|  
|Parameter|설명|  
|`text`|코드로 나타낼 텍스트입니다.|  
  
## 설명  
 `<c>` 태그를 사용하면 설명에 있는 텍스트를 코드로 표시할 수 있습니다.  여러 줄을 코드로 표시하려면 [\<code\>](../../../visual-basic/language-reference/xmldoc/code.md)를 사용합니다.  
  
 [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 저장합니다.  
  
## 예제  
 이 예제에서는 요약 섹션에 `<c>` 태그를 사용하여 `Counter`가 코드임을 나타냅니다.  
  
 [!code-vb[VbVbcnXmlDocComments#1](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/c_1.vb)]  
  
## 참고 항목  
 [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)