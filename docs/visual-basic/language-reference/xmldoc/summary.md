---
title: "&lt;summary&gt; (Visual Basic) | Microsoft Docs"
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
  - "<summary> XML tag"
  - "summary XML tag"
ms.assetid: 861c847d-dd94-478a-aa23-bf4899cdc848
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# &lt;summary&gt; (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

멤버에 대한 요약을 지정합니다.  
  
## 구문  
  
```  
<summary>description</summary>  
```  
  
#### 매개 변수  
 `description`  
 개체에 대한 요약입니다.  
  
## 설명  
 `<summary>` 태그를 사용하여 형식 또는 형식 멤버를 설명합니다.  형식에 대한 설명을 보충하는 정보를 추가하려면 [\<remarks\>](../../../visual-basic/language-reference/xmldoc/remarks.md)를 사용합니다.  
  
 에 대 한 텍스트를 `<summary>` 태그 IntelliSense 입력 하는 방법에 대 한 정보의 유일한 소스가 고 또한 개체 브라우저에 표시 됩니다.  개체 브라우저에 대 한 내용은 [코드 구조 보기](/visual-studio/ide/viewing-the-structure-of-code).  
  
 [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 저장합니다.  
  
## 예제  
 다음 예제에서는 `<summary>` 태그를 사용하여 `ResetCounter` 메서드와 `Counter` 속성을 설명합니다.  
  
 [!code-vb[VbVbcnXmlDocComments#1](../../../visual-basic/language-reference/xmldoc/codesnippet/visualbasic/summary_1.vb)]  
  
## 참고 항목  
 [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)