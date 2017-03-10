---
title: "&lt;returns&gt; (Visual Basic) | Microsoft Docs"
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
  - "returns XML tag"
  - "<returns> XML tag"
ms.assetid: a03a6469-d907-425d-882f-083187950e7e
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# &lt;returns&gt; (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

속성이나 함수의 반환 값을 지정합니다.  
  
## 구문  
  
```  
<returns>description</returns>  
```  
  
#### 매개 변수  
 `description`  
 반환 값에 대한 설명입니다.  
  
## 설명  
 반환 값을 설명하려면 메서드 선언의 주석에서 `<returns>` 태그를 사용합니다.  
  
 [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 저장합니다.  
  
## 예제  
 다음 예제에서는 `<returns>` 태그를 사용하여 `DoesRecordExist` 함수에서 반환되는 내용을 설명합니다.  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/visualbasic/returns_1.vb)]  
  
## 참고 항목  
 [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)