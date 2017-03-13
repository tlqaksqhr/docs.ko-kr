---
title: "&lt;param&gt; (Visual Basic) | Microsoft Docs"
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
  - "param XML tag"
  - "<param> XML tag"
ms.assetid: 4e32e86f-f6f3-4301-b7fc-2f321fb54368
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# &lt;param&gt; (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

매개 변수 이름과 설명을 정의합니다.  
  
## 구문  
  
```  
<param name="name">description</param>  
```  
  
#### 매개 변수  
 `name`  
 메서드 매개 변수의 이름입니다.  name은 큰따옴표\(" "\)로 묶습니다.  
  
 `description`  
 매개 변수에 대한 설명입니다.  
  
## 설명  
 메서드의 매개 변수 중 하나를 설명하려면 메서드 선언의 주석에서 `<param>` 태그를 사용해야 합니다.  
  
 텍스트는 `<param>` 태그가 다음 위치에 표시 됩니다.  
  
-   IntelliSense의 매개 변수 정보입니다.  자세한 내용은 [IntelliSense 사용](/visual-studio/ide/using-intellisense)을 참조하십시오.  
  
-   개체 브라우저입니다.  자세한 내용은 [코드 구조 보기](/visual-studio/ide/viewing-the-structure-of-code)을 참조하십시오.  
  
 [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 저장합니다.  
  
## 예제  
 다음 예제에서는 `<param>` 태그를 사용하여 `id` 매개 변수를 설명합니다.  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/param_1.vb)]  
  
## 참고 항목  
 [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)