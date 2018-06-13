---
title: '방법: 코드에서 문 분리 및 결합(Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb._
helpviewer_keywords:
- colons (:)
- line continuation
- _ line-continuation character
- ': line separator character'
- Visual Basic code, line breaks in
- Visual Basic code, line breaks
- Visual Basic code, line continuation
- long lines of code
- line terminator
- line-continuation sequence
- underscores [Visual Basic], in code
- statements [Visual Basic], line continuation in
- line breaks [Visual Basic], in code
- line-continuation character [Visual Basic]
- Visual Basic code, line continuation in
- statements [Visual Basic], line breaks in
ms.assetid: dea01dad-a8ac-484a-bb3a-8c45a1b1eccc
ms.openlocfilehash: 6bca3d62cb3e886ee08b9169d63d4c3a38247f3f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33651020"
---
# <a name="how-to-break-and-combine-statements-in-code-visual-basic"></a>방법: 코드에서 문 분리 및 결합(Visual Basic)
코드를 작성할 시간에 가로 스크롤 코드 편집기에서 볼 수 있는 긴 문을 만들 수 있습니다. 방식에 영향을 주지 않지만 코드를 실행, 하기 쉽게 없는 사용자나 다른 사람이 모니터에 표시 된 대로 코드를 읽을 수에 대 한 합니다. 이러한 경우 긴 문은 여러 줄으로 분리를 고려해 야 합니다.  
  
### <a name="to-break-a-single-statement-into-multiple-lines"></a>단일 문에 여러 선으로 분할 하려면  
  
-   밑줄 줄 연속 문자를 사용 하 여 (`_`), 줄을 원하는 위치에 있습니다. 밑줄 바로 앞에는 공백이 오고 바로 뒤에는 줄 종결자(캐리지 리턴)가 와야 합니다.  
  
    > [!NOTE]
    >  경우에 따라 줄 연속 문자를 생략 하면 Visual Basic 컴파일러는 암시적으로 문을 계속 코드의 다음 줄에 있습니다. "암시적 줄 연속" 목록이 줄 연속 문자를 생략할 수 있는 구문 요소에 대 한 참조 [문을](../../../visual-basic/programming-guide/language-features/statements.md)합니다.  
  
     다음 예에서 문의 마지막 줄을 제외한 모든 줄 연속 문자로 네 줄으로 나뉘어집니다.  
  
     [!code-vb[VbVbcnConventions#20](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/how-to-break-and-combine-statements-in-code_1.vb)]  
  
     이 시퀀스를 사용 하면 온라인 및 시기 인쇄 코드를 쉽게 읽을 수 있습니다.  
  
     줄 연속 문자는 줄에서 마지막 문자 여야 합니다. 같은 줄에 다른 문자로 올 수 없습니다.  
  
     줄 연속 문자를 사용할 수 있는 대 한 몇 가지 제한 사항이 예를 들어 인수 이름 중에 사용할 수 없습니다. 인수 목록이 줄 연속 문자를 중단할 수 있지만 개별 인수 이름에는 있어야 합니다.  
  
     줄 연속 문자를 사용 하 여 메모를 계속할 수 없습니다. 컴파일러 특별 한 의미에 대 한 설명의 문자를 검사 하지 않습니다. 주석이 여러 행에 대 한 반복 주석 기호 (`'`) 각 줄에 있습니다.  
  
 있지만 별도 줄에 각 문을 배치 하는 것이 좋지만, Visual Basic에서는 같은 줄에 여러 개의 문을 배치할 수 있습니다.  
  
### <a name="to-place-multiple-statements-on-the-same-line"></a>같은 줄에 여러 개의 문을 배치 하려면  
  
-   문을 콜론으로 분리 (`:`) 다음 예제와 같이, 합니다.  
  
     [!code-vb[VbVbcnConventions#10](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/how-to-break-and-combine-statements-in-code_2.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [프로그램 구조 및 코드 규칙](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)  
 [문](../../../visual-basic/programming-guide/language-features/statements.md)
