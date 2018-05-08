---
title: '&lt;값&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- <value> XML tag
- value XML tag
ms.assetid: 0b84b02e-9e6d-41b5-a926-0d5dc76dacb5
ms.openlocfilehash: f33a4ec32b45d8996bd39f0cc49097b5fd9252e4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="ltvaluegt-visual-basic"></a>&lt;값&gt; (Visual Basic)
속성의 설명을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```xml  
<value>property-description</value>  
```  
  
#### <a name="parameters"></a>매개 변수  
 `property-description`  
 속성에 대한 설명입니다.  
  
## <a name="remarks"></a>설명  
 사용 하 여는 `<value>` 속성을 설명 하는 태그입니다. 참고는 Visual Studio 개발 환경에서 코드 마법사를 사용 하는 속성을 추가할 때 추가 되는 [ \<요약 >](../../../visual-basic/language-reference/xmldoc/summary.md) 새 속성에 대 한 태그입니다. 수동으로 추가 해야 합니다는 `<value>` 속성을 나타내는 값을 설명 하는 태그입니다.  
  
 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.  
  
## <a name="example"></a>예제  
 사용 하 여이 예제는 `<value>` 태그 값에 대해 설명 하는 `Counter` 속성에 저장 합니다.  
  
 [!code-vb[VbVbcnXmlDocComments#1](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/value_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [XML 주석 태그](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
