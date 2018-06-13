---
title: '방법: 열거형 멤버 참조(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- enumerations [Visual Basic], referring to
- values [Visual Basic], associating constant values with names
- enumeration members
- constants [Visual Basic], enumerated
ms.assetid: bbb5c3cc-7cdb-4814-8d6a-a6d91546ed1e
ms.openlocfilehash: f995a0ef69c503360a5d709551a7f0ccfd67ce40
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33646319"
---
# <a name="how-to-refer-to-an-enumeration-member-visual-basic"></a>방법: 열거형 멤버 참조(Visual Basic)
열거형에는 서로 관련된 있는 상수 집합으로 작업 하 고 이름의 상수 값을 연결 하는 편리한 방법을 제공 합니다. 예를 들어 요일과 연결된 정수 상수에 대한 열거형을 선언한 다음, 코드에 정수 값 대신 요일 이름을 사용할 수 있습니다.  
  
 정규화 된 이름을 사용 하 여 방지할 수 있습니다는 `Imports` 문. 자세한 내용은 참조 [열거형 및 이름 한정](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)합니다.  
  
### <a name="to-refer-to-an-enumeration-member"></a>열거형 멤버를 참조 하려면  
  
-   열거 된 멤버 이름을 한정 합니다. 다음 예제에서는 할당 하는 예를 들어는 `Saturday` 의 멤버는 `FirstDayOfWeek` 변수에 열거형 `DayValue`합니다.  
  
     [!code-vb[VbEnumsTask#19](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/how-to-refer-to-an-enumeration-member_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [방법: 열거형 선언](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)  
 [열거형 및 이름 한정](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [방법: Visual Basic에서 열거형 반복](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-iterate-through-an-enumeration.md)  
 [방법: 열거형 값과 연결된 문자열 확인](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-determine-the-string-associated-with-an-enumeration-value.md)  
 [열거형을 사용하는 경우](../../../../visual-basic/programming-guide/language-features/constants-enums/when-to-use-an-enumeration.md)
