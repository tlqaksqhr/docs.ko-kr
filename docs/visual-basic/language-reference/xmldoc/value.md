---
title: "&lt;value&gt; (Visual Basic) | Microsoft Docs"
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
  - "<value> XML tag"
  - "value XML tag"
ms.assetid: 0b84b02e-9e6d-41b5-a926-0d5dc76dacb5
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;value&gt; (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

속성에 대한 설명을 지정합니다.  
  
## 구문  
  
```  
<value>property-description</value>  
```  
  
#### 매개 변수  
 `property-description`  
 속성에 대한 설명입니다.  
  
## 설명  
 `<value>` 태그를 사용하여 속성을 설명합니다.  Visual Studio 개발 환경의 코드 마법사를 사용하여 속성을 추가하면 새 속성에 대한  [\<summary\>](../Topic/%3Csummary%3E%20\(Visual%20Basic\).md) 태그도 추가됩니다.  그러면 사용자는 직접 `<value>` 태그를 추가하여 속성이 나타내는 값을 설명해야 합니다.  
  
 [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 저장합니다.  
  
## 예제  
 다음 예제에서는 `<value>` 태그를 사용하여 `Counter` 속성에 저장되는 값에 대해 설명합니다.  
  
 [!code-vb[VbVbcnXmlDocComments#1](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/value_1.vb)]  
  
## 참고 항목  
 [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)