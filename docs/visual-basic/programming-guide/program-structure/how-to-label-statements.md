---
title: '방법: Label 문(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- colons (:)
- statements [Visual Basic], labels
- ': separator character'
- Visual Basic code, labeling statements
ms.assetid: 38f1ff43-2054-42cb-963b-1998e60c6ed4
ms.openlocfilehash: df368bdba73ca35dd70bdd2f4e88cc10af894b5a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-label-statements-visual-basic"></a>방법: Label 문(Visual Basic)
문 블록은 콜론으로 구분 된 코드 줄 구성 됩니다. 확인 문자열 또는 정수 뒤에 오는 코드의 줄에 있다고 *레이블이*합니다. 문 레이블은 사용 하기 위해 문 같은 식별 하는 코드 줄을 표시 하는 데 사용 됩니다 `On Error Goto`합니다.  
  
 레이블은 유효한 Visual Basic 식별자 중 하나가 될 수 있습니다-프로그래밍 요소를 식별 하는 것과 같은-또는 정수 리터럴입니다. 소스 코드 줄의 시작 부분에 표시 되어야 합니다 레이블과 같은 줄에서 문에 의해 뒤 여부에 관계 없이 콜론을 따라야 합니다.  
  
 컴파일러는 줄의 시작 모든 미리 정의 된 식별자와 일치 하는지 여부를 확인 하 여 레이블을 식별 합니다. 그렇지 않은 경우 컴파일러는 레이블을 것으로 간주 합니다.  
  
 레이블 자신의 선언 공간 있고 다른 식별자를 방해 하지 않습니다. 레이블의 범위는 메서드의 본문입니다. 레이블 선언 모호한 상황에서는 우선 적용 됩니다.  
  
> [!NOTE]
>  레이블을은 실행문 메서드 내 에서만 사용할 수 있습니다.  
  
### <a name="to-label-a-line-of-code"></a>에는 코드 줄 레이블을 지정 하려면  
  
-   식별자 뒤에 콜론 소스 코드 줄의 시작 부분에 배치 합니다.  
  
     로 다음 코드 줄을 표시 하는 예를 들어 `Jump` 및 `120`각각:  
  
     [!code-vb[VbVbalrStatements#708](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/how-to-label-statements_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [문](../../../visual-basic/programming-guide/language-features/statements.md)  
 [선언 요소 이름](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [프로그램 구조 및 코드 규칙](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)
