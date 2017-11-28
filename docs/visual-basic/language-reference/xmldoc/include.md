---
title: "&lt;포함&gt; (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- include XML tag
- <include> XML tag
ms.assetid: ba8e9173-82cd-460b-8938-a075a2dfb36d
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 22eebaa8da8ef082e132cfdf8cb68498bfe16d73
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="ltincludegt-visual-basic"></a>&lt;포함&gt; (Visual Basic)
형식 및 소스 코드에서 멤버를 설명 하는 다른 파일을 가리킵니다.  
  
## <a name="syntax"></a>구문  
  
```xml  
<include file="filename" path="tagpath[@name='id']" />  
```  
  
#### <a name="parameters"></a>매개 변수  
 `filename`  
 필수 요소. 설명서를 포함 하는 파일의 이름입니다. 경로를 사용하여 파일 이름을 정규화할 수 있습니다. 묶습니다 `filename` 큰따옴표에서 ("").  
  
 `tagpath`  
 필수 요소. `filename`의 태그 경로로, `name` 태그에 연결됩니다. 경로를 큰따옴표로 묶습니다 ("").  
  
 `name`  
 필수 요소. 주석 앞에 태그에 이름 지정자입니다. `Name`갖습니다는 `id`합니다.  
  
 `id`  
 필수 요소. 주석 앞에 오는 태그의 ID입니다. ID를 작은따옴표로 묶습니다 (' ').  
  
## <a name="remarks"></a>설명  
 사용 하 여는 `<include>` 태그의 형식을 설명 하는 다른 파일의 주석에 소스 코드에서 멤버를 참조할 수 있습니다. 소스 코드 파일에 직접 문서 주석을 포함하는 대신 사용되는 대안입니다.  
  
 `<include>` 태그의 W3C XML 경로 언어 (XPath) Version 1.0 권장 사항에 사용 합니다. 사용자 지정 하는 방법에 대 한 자세한 내용은 프로그램 `<include>` 사용은 http://www.w3.org/TR/xpath에서 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 사용 하 여이 예제는 `<include>` 멤버 문서 주석을 라는 파일에서 가져올 태그 `commentFile.xml`합니다.  
  
 [!code-vb[VbVbcnXmlDocComments#4](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/include_1.vb)]  
  
 형식은 `commentFile.xml` 는 다음과 같습니다.  
  
```xml  
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
  
## <a name="see-also"></a>참고 항목  
 [XML 주석 태그](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
