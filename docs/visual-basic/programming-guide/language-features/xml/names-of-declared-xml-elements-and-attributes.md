---
title: 선언된 XML 요소 및 특성의 이름(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [XML in Visual Basic]
- element names [XML in Visual Basic]
- names in XML literals [Visual Basic]
- attribute names [XML in Visual Basic]
- XML literals [Visual Basic], element names
ms.assetid: cc110118-b6cf-4ff9-a4e4-6233c90c9fbf
ms.openlocfilehash: 9b586936281bfbf2dcace7cf2892bebf305fc842
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="names-of-declared-xml-elements-and-attributes-visual-basic"></a>선언된 XML 요소 및 특성의 이름(Visual Basic)
이 항목에서는 XML 리터럴의 XML 요소 및 특성 이름 지정에 대 한 Visual Basic 지침을 제공 합니다.  Xml 리터럴, 로컬 이름 또는 정규화 된 이름을 지정할 수 있습니다. 정규화 된 이름은 XML 네임 스페이스 접두사, 콜론 및 로컬 이름으로 구성 됩니다. XML 네임 스페이스 접두사에 대 한 자세한 내용은 참조 [XML 요소 리터럴](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)합니다.  
  
## <a name="rules"></a>규칙  
 요소 또는 Visual Basic의 특성의 로컬 이름은 다음 규칙을 준수 해야 합니다.  
  
-   네임 스페이스로 시작할 수 있습니다. 알파벳 문자 또는 밑줄로 시작 해야 합니다 (`_`).  
  
-   영문자, 10 진수 숫자, 밑줄, 마침표 (.) 및 하이픈만 포함 해야 합니다 (-).  
  
-   1, 024 개 이상의 자 않아야 합니다.  
  
-   이름에 나타나는 콜론 네임 스페이스 구분을 나타냅니다. 따라서 특정 이름에 대 한 XML 네임 스페이스 지정에 콜론을 사용할 수 있습니다.  
  
 또한 다음 지침을 따라야 합니다.  
  
-   XML 1.0 사양에 문자열 "xml" 모든 대문자 변형으로 시작 하는 모든 이름을 예약 합니다. 따라서 해당 프로그램 요소에 대 한 이름 및 특성 이름을 사용 하지 마십시오.  
  
### <a name="name-length-guidelines"></a>이름 길이 지침  
 명확히 요소의 특성을 식별 하는 동안 한 이름은 최대한 단축 해야 합니다. 이 코드의 가독성을 높일 수 및 줄 길이 소스 파일 크기를 줄입니다.  
  
 그러나 사용자 이름이 너무 짧아서는 설명 하지는 않습니다 적절 하 게 요소 또는 코드에서 어떻게 되지 않아야 합니다. 이 코드의 가독성을 위해 중요 합니다. 다른 사람을 이해 하려고 하거나 자신을 원하는 경우에 쓰고 이때 후 오랫동안 적절 한 요소 이름을 시간을 절약할 수 있습니다.  
  
## <a name="case-sensitivity-in-names"></a>이름에서 대/소문자 구분  
 XML 요소 이름은 대/소문자를 구분 합니다. 이 Visual Basic 컴파일러 알파벳 소문자만 다르고 이름은 동일한 두 개의 비교 하 여 해석 다른 이름으로 의미 합니다. 예를 들어 해석 `ABC` 및 `abc` 각각 별도 요소를 참조 합니다.  
  
## <a name="xml-namespaces"></a>XML 네임스페이스  
 XML 요소 리터럴를 만들 때 요소 이름에 대 한 XML 네임 스페이스 접두사를 지정할 수 있습니다. 자세한 내용은 참조 [XML 요소 리터럴](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic에서 XML 만들기](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [XML 요소 리터럴](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
