---
title: "&lt;para&gt; (Visual Basic) | Microsoft Docs"
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
  - "<para> XML tag"
  - "para XML tag"
ms.assetid: a3a18b6c-6416-4358-94ec-37b22675fd37
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# &lt;para&gt; (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

단락 서식을 지정합니다.  
  
## 구문  
  
```  
<para>content</para>  
```  
  
#### 매개 변수  
 `content`  
 단락 텍스트입니다.  
  
## 설명  
 `<para>` 태그는 [\<summary\>](../../../visual-basic/language-reference/xmldoc/summary.md), [\<remarks\>](../../../visual-basic/language-reference/xmldoc/remarks.md) 또는 [\<returns\>](../../../visual-basic/language-reference/xmldoc/returns.md)처럼 태그 안에 사용하는 태그로 텍스트에 구조를 추가할 수 있습니다.  
  
 [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 저장합니다.  
  
## 예제  
 다음 예제에서는 `<para>` 태그를 사용하여 `UpdateRecord` 메서드의 설명 부분을 두 단락으로 나눕니다.  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/visualbasic/para_1.vb)]  
  
## 참고 항목  
 [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)