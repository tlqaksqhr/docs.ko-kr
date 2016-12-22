---
title: "&lt;include&gt; (Visual Basic) | Microsoft Docs"
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
  - "include XML tag"
  - "<include> XML tag"
ms.assetid: ba8e9173-82cd-460b-8938-a075a2dfb36d
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;include&gt; (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

소스 코드의 형식과 멤버를 설명하는 다른 파일을 참조합니다.  
  
## 구문  
  
```  
<include file="filename" path="tagpath[@name='id']" />  
```  
  
#### 매개 변수  
 `filename`  
 필수 요소.  문서를 포함할 파일 이름입니다.  파일 이름은 path로 한정될 수 있습니다.  `filename`은 큰따옴표\(" "\)로 묶습니다.  
  
 `tagpath`  
 필수 요소.  태그의 `name`을 찾을 수 있는 `filename`의 태그 경로입니다.  경로는 큰따옴표\(" "\)로 묶습니다.  
  
 `name`  
 필수 요소.  주석 앞에 오는 태그의 이름 지정자입니다.  `Name`에는 `id`가 있어야 합니다.  
  
 `id`  
 필수 요소.  주석 앞에 오는 태그의 ID입니다.  ID는 작은따옴표\(' '\)로 묶습니다.  
  
## 설명  
 소스 코드의 형식과 멤버를 설명하는 다른 파일의 주석을 참조하려면 `<include>` 태그를 사용합니다.  이렇게 하면 소스 코드 파일에 직접 문서 주석을 배치하지 않아도 됩니다.  
  
 `<include>` 태그에는 W3C XPath\(XML Path Language\) 버전 1.0 권장 사항이 적용됩니다.  `<include>`를 사용자 지정하는 방법에 대한 자세한 내용은 http:\/\/www.w3.org\/TR\/xpath를 참조하십시오.  
  
## 예제  
 다음 예제에서는 `<include>` 태그를 사용하여 `commentFile.xml`이라는 파일에서 멤버 설명서 주석을 가져옵니다.  
  
 [!code-vb[VbVbcnXmlDocComments#4](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/include_1.vb)]  
  
 `commentFile.xml`의 형식은 다음과 같습니다.  
  
```  
<Docs>  
<Members name="Open">  
<summary>Opens a file.</summary>  
<param name="filename">File name to open.</param>  
</Members>  
<Members name="Close">  
<summary>Closes a file.</summary>  
<param name="filename">File name to close.</param>  
</Members>  
</Docs>  
```  
  
## 참고 항목  
 [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)