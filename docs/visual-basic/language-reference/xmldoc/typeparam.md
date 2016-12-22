---
title: "&lt;typeparam&gt; (Visual Basic) | Microsoft Docs"
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
  - "typeparam XML tag"
  - "<typeparam> XML tag"
ms.assetid: 1bb5ba78-f060-478c-905c-77a2e43639af
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;typeparam&gt; (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

형식 매개 변수 이름과 설명을 정의합니다.  
  
## 구문  
  
```  
<typeparam name="name">description</typeparam>  
```  
  
#### 매개 변수  
 `name`  
 형식 매개 변수의 이름입니다.  name은 큰따옴표\(" "\)로 묶습니다.  
  
 `description`  
 형식 매개 변수에 대한 설명입니다.  
  
## 설명  
 제네릭 형식 또는 제네릭 멤버 선언에 대한 주석에서 `<typeparam>` 태그를 사용하여 형식 매개 변수 중 하나를 설명합니다.  
  
 [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 저장합니다.  
  
## 예제  
 다음 예제에서는 `<typeparam>` 태그를 사용하여 `id` 매개 변수를 설명합니다.  
  
 [!code-vb[VbVbcnXmlDocComments#8](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/typeparam_1.vb)]  
  
## 참고 항목  
 [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)