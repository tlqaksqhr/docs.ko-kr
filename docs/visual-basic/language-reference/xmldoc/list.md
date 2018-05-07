---
title: '&lt;목록&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- listheader XML tag
- <item> XML tag
- <list> XML tag
- <listheader> XML tag
- term XML tag
- list XML tag
- <description> XML tag
- description XML tag
- item XML tag
- <term> XML tag
ms.assetid: ec35fced-d58e-4520-a764-0691256e014b
ms.openlocfilehash: f03924217393e1e909b086b282f1c62ddb471522
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="ltlistgt-visual-basic"></a>&lt;목록&gt; (Visual Basic)
목록 또는 테이블을 정의합니다.  
  
## <a name="syntax"></a>구문  
  
```xml  
<list type="type">  
   <listheader>  
      <term>term</term>  
      <description>description</description>  
   </listheader>  
   <item>  
      <term>term</term>  
      <description>description</description>  
   </item>  
</list>  
```  
  
#### <a name="parameters"></a>매개 변수  
 `type`  
 형식 목록입니다. 글머리 기호 목록, 번호 매기기 목록 또는 두 개의 열 테이블에 대 한 "table"에 대 한 "number"에 대 한 "bullet" 이어야 합니다.  
  
 `term`  
 경우에 사용 `type` "table"은 용어를 정의 하려면 설명 태그에 정의 된입니다.  
  
 `description`  
 때 `type` "bullet" 또는 "number" `description` 이 목록에 항목이 때 `type` "table"은 `description` 의 정의가 `term`합니다.  
  
## <a name="remarks"></a>설명  
 `<listheader>` 블록 목록 정의 또는 테이블의 머리글을 정의 합니다. 테이블을 정의할 때만 제공 해야에 대 한 항목이 `term` 머리글에 있습니다.  
  
 목록의 각 항목으로 지정 된 프로그램 `<item>` 블록입니다. 둘 다 지정 해야 정의 목록을 만들 때 `term` 및 `description`합니다. 그러나 테이블, 글머리 기호 목록 또는 번호 매기기 목록에 대 한 하기만 하면에 대 한 항목을 제공 하려면 `description`합니다.  
  
 목록 또는 테이블 만큼 가질 수 `<item>` 필요에 따라 차단 합니다.  
  
 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.  
  
## <a name="example"></a>예제  
 사용 하 여이 예제는 `<list>` 글머리 기호 목록 주의 섹션에 정의 하는 태그입니다.  
  
 [!code-vb[VbVbcnXmlDocComments#5](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/list_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [XML 주석 태그](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
