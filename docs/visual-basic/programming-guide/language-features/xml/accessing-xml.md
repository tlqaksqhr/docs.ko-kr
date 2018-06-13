---
title: Visual Basic에서 XML에 액세스
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ to XML [Visual Basic], accessing XML
- Visual Basic code, XML
- accessing XML [Visual Basic], axis properties
- XML [Visual Basic], axis properties
- XML [Visual Basic], accessing
ms.assetid: c47f88b2-3cbc-4bb1-b4b9-be60f71ffc6a
ms.openlocfilehash: b000b3f6846f800b2a96ce10cdd408a355f78a81
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649596"
---
# <a name="accessing-xml-in-visual-basic"></a>Visual Basic에서 XML에 액세스
Visual Basic에서 XML 축 속성에 액세스 하 고 탐색 하기 위한 제공 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 구조입니다. 이러한 속성에는 XML 이름을 지정 하 여 요소 및 특성에 액세스할 수 있도록 특수 한 구문을 사용 합니다.  
  
 다음 표에서 XML 요소 및 Visual Basic의 특성에 액세스할 수 있도록 하는 언어 기능을 보여 줍니다.  
  
### <a name="xml-axis-properties"></a>XML 축 속성  
  
|속성 설명|예제|설명|  
|--------------------------|-------------|-----------------|  
|*자식 축*|`contact.<phone>`|모든 가져옵니다 `phone` 의 자식 요소가 있는 요소는 `contact` 요소입니다.|  
|*특성 축*|`phone.@type`|모든 가져옵니다 `type` 의 특성은 `phone` 요소입니다.|  
|*descendant 축*|`contacts...<name>`|모든 가져옵니다 `name` 의 요소는 `contacts` 요소와 상관 없이 발생 하는 계층 구조에서.|  
|*확장 인덱서*|`contacts...<name>(0)`|첫 번째 `name` 시퀀스의 요소입니다.|  
|*값*|`contacts...<name>.Value`|시퀀스의 첫 번째 개체의 문자열 표현을 가져옵니다 또는 `Nothing` 시퀀스가 비어 있는 경우.|  
  
## <a name="in-this-section"></a>섹션 내용  
 [방법: XML 하위 요소 액세스](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-descendant-elements.md)  
 지정 된 이름이 지정된 된 XML 요소 아래에 포함 된 모든 XML 요소에 액세스 하려면 하위 항목 축 속성을 사용 하는 방법을 보여 줍니다.  
  
 [방법: XML 자식 요소 액세스](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-child-elements.md)  
 축 속성에 지정 된 이름이 XML 요소에 있는 모든 XML 자식 요소를 액세스 하려면 자식을 사용 하는 방법을 보여 줍니다.  
  
 [방법: XML 특성 액세스](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-attributes.md)  
 특성 축 속성을 사용 하 여 XML 요소에 지정 된 이름을 가진 모든 XML 특성에 액세스 하는 방법을 보여 줍니다.  
  
 [방법: XML 네임스페이스 접두사 선언 및 사용](../../../../visual-basic/programming-guide/language-features/xml/how-to-declare-and-use-xml-namespace-prefixes.md)  
 XML 네임 스페이스 접두사를 선언 하 고 사용을 만들고 XML 요소에 액세스 하는 방법을 보여 줍니다.  
  
## <a name="related-sections"></a>관련 단원  
 [XML 축 속성](../../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 다양 한 XML 액세스 속성을 설명 하는 섹션에 대 한 링크를 제공 합니다.  
  
 [Visual Basic의 LINQ to XML 개요](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)  
 사용 하 여 소개 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] Visual Basic의 합니다.  
  
 [Visual Basic에서 XML 만들기](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 Visual Basic의 XML 리터럴을 사용 하 여에 대 한 소개를 제공 합니다.  
  
 [Visual Basic에서 XML 조작](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)  
 로드 하 고 Visual Basic의 XML을 수정 하는 방법에 대 한 섹션에 대 한 링크를 제공 합니다.  
  
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 섹션을 사용 하는 방법을 설명 하는 링크를 제공 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] Visual Basic의 합니다.
