---
title: "&lt;param&gt; (Visual Basic) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- param XML tag
- <param> XML tag
ms.assetid: 4e32e86f-f6f3-4301-b7fc-2f321fb54368
caps.latest.revision: 14
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 41852a7fc41595050940d87f9e741df5cb23361c
ms.lasthandoff: 03/13/2017

---
# <a name="ltparamgt-visual-basic"></a>&lt;param&gt; (Visual Basic)
매개 변수 이름 및 설명을 정의합니다.  
  
## <a name="syntax"></a>구문  
  
```  
<param name="name">description</param>  
```  
  
#### <a name="parameters"></a>매개 변수  
 `name`  
 메서드 매개 변수의 이름입니다. 큰따옴표로 이름을 묶습니다 ("").  
  
 `description`  
 매개 변수에 대해 설명 합니다.  
  
## <a name="remarks"></a>주의  
 `<param>` 태그를 메서드에 대 한 매개 변수 중 하나를 설명 하는 메서드 선언에 대 한 설명에 사용 해야 합니다.  
  
 에 대 한 텍스트는 `<param>` 태그는 다음 위치에 표시 됩니다.  
  
-   IntelliSense의 매개 변수 정보입니다. 자세한 내용은 [IntelliSense 사용](https://docs.microsoft.com/visualstudio/ide/using-intellisense)을 참조하세요.  
  
-   개체 브라우저입니다. 자세한 내용은 [코드 구조 보기](https://docs.microsoft.com/visualstudio/ide/viewing-the-structure-of-code)를 참조하세요.  
  
 사용 하 여 컴파일하면 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) 문서 주석을 파일에 있습니다.  
  
## <a name="example"></a>예제  
 사용 하 여이 예제는 `<param>` 태그를 설명 하는 `id` 매개 변수입니다.  
  
 [!code-vb[VbVbcnXmlDocComments #&6;](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/param_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [XML 주석 태그](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
