---
title: "&lt;permission&gt; (Visual Basic) | Microsoft Docs"
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
  - "<permission> XML tag"
  - "permission XML tag"
ms.assetid: 0edf0500-5cd7-49c0-9255-64c48f972b77
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# &lt;permission&gt; (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

멤버에게 필요한 권한을 지정합니다.  
  
## 구문  
  
```  
<permission cref="member">description</permission>  
```  
  
#### 매개 변수  
 `member`  
 현재 컴파일 환경에서 호출될 수 있는 멤버 또는 필드에 대한 참조입니다.  컴파일러는 지정된 코드 요소가 있는지 확인한 다음 `member`를 출력 XML의 정식 요소 이름으로 변환합니다.  `member`를 따옴표\(" "\)로 묶습니다.  
  
 `description`  
 멤버 액세스에 대한 설명입니다.  
  
## 설명  
 `<permission>` 태그를 사용하여 멤버의 액세스를 설명합니다.  <xref:System.Security.PermissionSet> 클래스를 사용하여 멤버에 대한 액세스를 지정합니다.  
  
 [\/doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 저장합니다.  
  
## 예제  
 다음 예제에서는 `<permission>` 태그를 사용하여 `ReadFile` 메서드에 <xref:System.Security.Permissions.FileIOPermission>이 필요함을 설명합니다.  
  
 [!code-vb[VbVbcnXmlDocComments#7](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/permission_1.vb)]  
  
## 참고 항목  
 [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)