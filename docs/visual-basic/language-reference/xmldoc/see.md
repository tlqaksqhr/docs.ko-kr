---
title: "&lt;see&gt; (Visual Basic) | Microsoft Docs"
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
  - "see XML tag"
  - "<see> XML tag"
ms.assetid: 7e18f60b-ef4a-4678-a797-5eb918635ca9
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;see&gt; (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

다른 멤버에 대한 링크를 지정합니다.  
  
## 구문  
  
```  
<see cref="member"/>  
```  
  
#### 매개 변수  
 `member`  
 현재 컴파일 환경에서 호출될 수 있는 멤버 또는 필드에 대한 참조입니다.  컴파일러는 지정된 코드 요소가 있고 출력 XML의 요소 이름에 `member`가 전달되는지 검사합니다.  `member`는 큰따옴표\(" "\)로 묶어야 합니다.  
  
## 설명  
 텍스트 내부에서 링크를 지정하려면 `<see>` 태그를 사용합니다.  "참고 항목" 부분에 나타나는 텍스트를 지정하려면 [\<seealso\>](../../../visual-basic/language-reference/xmldoc/seealso.md)를 사용합니다.  
  
 [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 저장합니다.  
  
## 예제  
 이 예제에서는 `UpdateRecord` 설명 부분에서 `<see>` 태그를 사용하여 `DoesRecordExist` 메서드를 참조합니다.  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/see_1.vb)]  
  
## 참고 항목  
 [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)