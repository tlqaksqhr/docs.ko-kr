---
title: "&lt;seealso&gt; (Visual Basic) | Microsoft Docs"
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
  - "<seealso> XML tag"
  - "seealso XML tag"
ms.assetid: 36050c95-1af2-4284-b9b6-1a70691ed978
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# &lt;seealso&gt; (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

참고 항목 부분에 나타나는 링크를 지정합니다.  
  
## 구문  
  
```  
<seealso cref="member"/>  
```  
  
#### 매개 변수  
 `member`  
 현재 컴파일 환경에서 호출될 수 있는 멤버 또는 필드에 대한 참조입니다.  컴파일러는 지정된 코드 요소가 있고 출력 XML의 요소 이름에 `member`가 전달되는지 검사합니다.  `member`는 큰따옴표\(" "\)로 묶어야 합니다.  
  
## 설명  
 참고 항목 부분에 표시할 텍스트를 지정하려면 `<seealso>` 태그를 사용하고,  텍스트 내부에서 링크를 지정하려면 [\<see\>](../../../visual-basic/language-reference/xmldoc/see.md)를 사용합니다.  
  
 [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 저장합니다.  
  
## 예제  
 이 예제에서는 `DoesRecordExist` 설명 부분에서 `<seealso>` 태그를 사용하여 `UpdateRecord` 메서드를 참조합니다.  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/visualbasic/seealso_1.vb)]  
  
## 참고 항목  
 [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)