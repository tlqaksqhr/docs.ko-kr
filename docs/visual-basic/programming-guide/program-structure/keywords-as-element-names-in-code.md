---
title: 코드에서 요소 이름으로 사용되는 키워드(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, naming conventions
- keywords [Visual Basic], in code
- name conflicts [Visual Basic]
- element names [Visual Basic], in code
ms.assetid: 2e4e8e02-23f7-49b9-a1c8-2b0402b6b525
ms.openlocfilehash: 53c3172e8518115d001c23be2430fbc87ae1b60f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="keywords-as-element-names-in-code-visual-basic"></a>코드에서 요소 이름으로 사용되는 키워드(Visual Basic)
모든 프로그램 요소-변수, 클래스 또는 멤버와 같은-제한 된 키워드와 동일한 이름을 가질 수 있습니다. 예를 들어 라는 변수를 만들 수 있습니다 `Loop`합니다. 그러나 구별 참조 하려면-제한 된와 동일한 이름이 있는 `Loop` 키워드-앞에 정규화 문자열 하거나 대괄호로 묶어야 합니다 (`[ ]`) 다음 예제와 같이 합니다.  
  
 [!code-vb[VbVbcnConventions#8](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/keywords-as-element-names-in-code_1.vb)]  
  
 이 중 하나를 수행 하지 않는 경우 Visual Basic은 내장 함수를 사용 한다고 가정 `Loop` 키워드와 다음 예제와 같이 오류를 발생 시킵니다.  
  
 `' The following statement causes a compiler error.`  
  
 `Loop.Visible = True`  
  
 폼과 컨트롤을 나타낼 때와 때 대괄호를 사용할 수 있습니다 변수를 선언 하거나 제한 된 키워드와 같은 이름의 프로시저를 정의 합니다. 이름 한정 포함 대괄호를 하 고 따라서 코드에 오류가 발생 하 고 읽기 하기가 더 어려워지며를 잊기 쉬울 수 있습니다. 이러한 이유로 프로그램 요소 이름으로 제한 된 키워드를 사용 하지는 것이 좋습니다. 그러나 이후 버전의 Visual Basic의 기존 폼 또는 컨트롤 이름 충돌 하는 새로운 키워드를 정의 다음 사용할 수 있습니다이 방법은 코드를 업데이트할 때 새 버전으로 작업 하도록.  
  
> [!NOTE]
>  또한 프로그램 다른 참조 된 어셈블리에서 제공 되는 요소 이름이 포함 될 수 있습니다. 이러한 이름은 제한 된 키워드와 충돌 하는 경우 대괄호로 묶으면 Visual Basic 정의 된 요소를 해석할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic 명명 규칙](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 [프로그램 구조 및 코드 규칙](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 [키워드](../../../visual-basic/language-reference/keywords/index.md)
