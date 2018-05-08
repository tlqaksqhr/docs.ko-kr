---
title: '방법: XML 하위 요소 액세스(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- XML descendent axis property [Visual Basic]
- XML axis [Visual Basic], descendent
- descendent axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: aabfa258-4112-4e7e-bab9-403f96072ef7
ms.openlocfilehash: 6d41844b540631df96740ce56818c125cf85e928
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-access-xml-descendant-elements-visual-basic"></a>방법: XML 하위 요소 액세스(Visual Basic)
이 예제는 지정 된 이름이 XML 요소 아래에 포함 된 모든 XML 요소에 액세스 하려면 하위 항목 축 속성을 사용 하는 방법을 보여 줍니다. 사용 하 여 특히는 `Value` 속성을 하는 컬렉션의 첫 번째 요소 값을 가져옵니다는 `name` 하위 축 속성에서 반환 합니다. `name` 하위 항목 축 속성 이라는 모든 요소를 가져옵니다 `name` 에 포함 된는 `contacts` 개체입니다. 또한이 예제에서는 `phone` 이라는 모든 하위 요소를 액세스 하는 하위 항목 축 속성 `phone` 에 포함 된는 `contacts` 개체입니다.  
  
## <a name="example"></a>예제  
 [!code-vb[VbXMLSamples#31](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-access-xml-descendant-elements_1.vb)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   <xref:System.Xml.Linq> 네임스페이스에 대한 참조  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=nameWithType>  
 [XML Descendant 축 속성](../../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md)  
 [XML 값 속성](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)  
 [Visual Basic에서 XML에 액세스](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)  
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
