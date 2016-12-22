---
title: "&lt;list&gt; (Visual Basic) | Microsoft Docs"
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
  - "listheader XML tag"
  - "<item> XML tag"
  - "<list> XML tag"
  - "<listheader> XML tag"
  - "term XML tag"
  - "list XML tag"
  - "<description> XML tag"
  - "description XML tag"
  - "item XML tag"
  - "<term> XML tag"
ms.assetid: ec35fced-d58e-4520-a764-0691256e014b
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;list&gt; (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

목록이나 테이블을 정의합니다.  
  
## 구문  
  
```  
<list type="type">  
   <listheader>  
      <term>term</term>  
      <description>description</description>  
   </listheader>  
   <item>  
      <term>term</term>  
      <description>description</description>  
   </item>  
</list>  
```  
  
#### 매개 변수  
 `type`  
 목록의 형식입니다.  글머리 기호 목록의 경우는 "bullet", 번호 매기기 목록의 경우는 "number", 두 개의 열로 이루어진 테이블의 경우는 "table"이어야 합니다.  
  
 `term`  
 `type`이 "table"일 경우에만 사용됩니다. 정의할 용어로, 설명 태그 안에서 정의됩니다.  
  
 `description`  
 `type`이 "bullet"이거나 "number"이면 `description`은 목록에 있는 항목이며, `type`이 "table"이면 `description`은 `term`에 대한 정의입니다.  
  
## 설명  
 `<listheader>` 블록은 테이블이나 정의 목록의 머리글을 정의합니다.  테이블을 정의할 때는 머리글의 `term`에 대한 엔트리만 제공하면 됩니다.  
  
 목록의 각 항목은 `<item>` 블록으로 지정합니다.  정의 목록을 만들 때는 `term`과 `description`을 모두 지정해야 합니다.  그러나 테이블, 글머리 기호 목록 또는 번호 매기기 목록의 경우에는 `description`의 엔트리만 제공하면 됩니다.  
  
 목록이나 테이블에 사용할 수 있는 `<item>` 블록의 수에는 제한이 없습니다.  
  
 [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 저장합니다.  
  
## 예제  
 다음 예제에서는 `<list>` 태그를 사용하여 설명 섹션에 글머리 기호 목록을 정의합니다.  
  
 [!code-vb[VbVbcnXmlDocComments#5](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/list_1.vb)]  
  
## 참고 항목  
 [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)