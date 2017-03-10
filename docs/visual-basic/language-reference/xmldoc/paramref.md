---
title: "&lt;paramref&gt; (Visual Basic) | Microsoft Docs"
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
  - "paramref XML tag"
  - "<paramref> XML tag"
ms.assetid: 8979d53b-beb1-41b7-b41e-6bbea1c17a03
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# &lt;paramref&gt; (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

단어에 매개 변수 서식을 지정합니다.  
  
## 구문  
  
```  
<paramref name="name"/>  
```  
  
#### 매개 변수  
 `name`  
 참조할 매개 변수의 이름입니다.  name은 큰따옴표\(" "\)로 묶습니다.  
  
## 설명  
 `<paramref>` 태그를 사용하면 특정 단어가 매개 변수임을 나타낼 수 있습니다.  이제 XML 파일을 처리하여 이 매개 변수를 다른 방식으로 서식화할 수 있습니다.  
  
 [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 저장합니다.  
  
## 예제  
 다음 예제에서는 `<paramref>` 태그를 사용하여 `id` 매개 변수를 참조합니다.  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/visualbasic/paramref_1.vb)]  
  
## 참고 항목  
 [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)