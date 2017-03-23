---
title: "&lt;exception&gt; (Visual Basic) | Microsoft Docs"
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
  - "<exception> XML tag"
  - "exception XML tag"
ms.assetid: c0517549-171e-4dae-ab88-a9c1700b6eee
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# &lt;exception&gt; (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

throw될 수 있는 예외를 지정합니다.  
  
## 구문  
  
```  
<exception cref="member">description</exception>  
```  
  
#### 매개 변수  
 `member`  
 현재 컴파일 환경에 있는 예외에 대한 참조.  컴파일러에서는 지정된 예외가 존재하는지를 확인하고 `member`를 출력 XML의 정식 요소 이름으로 변환합니다.  `member`는 큰따옴표\(" "\)로 묶어야 합니다.  
  
 `description`  
 설명.  
  
## 설명  
 throw될 수 있는 예외를 지정하려면 `<exception>` 태그를 사용합니다.  이 태그는 메서드 정의에 적용됩니다.  
  
 [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 저장합니다.  
  
## 예제  
 다음 예제에서는 `<exception>` 태그를 사용하여 `IntDivide` 함수에서 throw될 수 있는 예외를 설명합니다.  
  
 [!code-vb[VbVbcnXmlDocComments#3](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/exception_1.vb)]  
  
## 참고 항목  
 [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)