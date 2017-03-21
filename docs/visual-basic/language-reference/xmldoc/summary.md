---
title: "&lt;요약&gt; (Visual Basic) | Microsoft 문서"
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
- <summary> XML tag
- summary XML tag
ms.assetid: 861c847d-dd94-478a-aa23-bf4899cdc848
caps.latest.revision: 12
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
ms.openlocfilehash: ad2053e21e58c49205fe869a484cb2dffd2169ee
ms.lasthandoff: 03/13/2017

---
# <a name="ltsummarygt-visual-basic"></a>&lt;요약&gt; (Visual Basic)
멤버의 요약을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
<summary>description</summary>  
```  
  
#### <a name="parameters"></a>매개 변수  
 `description`  
 개체의 요약입니다.  
  
## <a name="remarks"></a>주의  
 사용 된 `<summary>` 형식 또는 형식 멤버를 설명 하는 태그입니다. 사용 하 여 [ \<설명 >](../../../visual-basic/language-reference/xmldoc/remarks.md) 유형 설명에 추가 정보를 추가 합니다.  
  
 에 대 한 텍스트는 `<summary>` 태그는 IntelliSense에는 형식에 대 한 정보의 유일 하는 소스 및 개체 브라우저에도 표시 됩니다. 개체 브라우저에 대 한 정보를 참조 하십시오. [코드 구조 보기](https://docs.microsoft.com/visualstudio/ide/viewing-the-structure-of-code)합니다.  
  
 사용 하 여 컴파일하면 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) 문서 주석을 파일에 있습니다.  
  
## <a name="example"></a>예제  
 사용 하 여이 예제는 `<summary>` 태그를 설명 하는 `ResetCounter` 메서드 및 `Counter` 속성입니다.  
  
 [!code-vb[VbVbcnXmlDocComments #&1;](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/summary_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [XML 주석 태그](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
