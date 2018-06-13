---
title: '방법: Visual Basic에서 프로시저에 다른 프로시저 전달'
ms.date: 07/20/2015
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- delegates [Visual Basic], passing procedures
ms.assetid: 5adbba15-5a1d-413f-ab3e-3ff6cc0a4669
ms.openlocfilehash: c28ac7a640ec863b37bd7407d0273a1918964ac4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647240"
---
# <a name="how-to-pass-procedures-to-another-procedure-in-visual-basic"></a>방법: Visual Basic에서 프로시저에 다른 프로시저 전달
이 예제에서는 대리자를 사용 하는 프로시저를 다른 프로시저에 전달 하는 방법을 보여 줍니다.  
  
 대리자 형식이 Visual Basic에서 다른 형식 처럼 사용할 수 있습니다. `AddressOf` 연산자 프로시저 이름에 적용 될 때 대리자 개체를 반환 합니다.  
  
 이 예제에 다른 프로시저를 사용 하 여 얻은에 대 한 참조를 사용할 수 있는 대리자 매개 변수가 있는 프로시저는 `AddressOf` 연산자입니다.  
  
### <a name="create-the-delegate-and-matching-procedures"></a>대리자와 일치 하는 프로시저 만들기  
  
1.  라는 대리자를 만들 `MathOperator`합니다.  
  
     [!code-vb[VbVbalrDelegates#1](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_1.vb)]  
  
2.  라는 프로시저를 만들어 `AddNumbers` 매개 변수와 일치 하는 반환 값 `MathOperator`서명이 일치 되도록 합니다.  
  
     [!code-vb[VbVbalrDelegates#2](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_2.vb)]  
  
3.  라는 프로시저를 만들어 `SubtractNumbers` 일치 하는 서명이 `MathOperator`합니다.  
  
     [!code-vb[VbVbalrDelegates#3](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_3.vb)]  
  
4.  라는 프로시저를 만들어 `DelegateTest` 대리자를 매개 변수로 사용 합니다.  
  
     이 절차에 대 한 참조를 허용할 수 `AddNumbers` 또는 `SubtractNumbers`에서는는 `MathOperator` 서명 합니다.  
  
     [!code-vb[VbVbalrDelegates#4](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_4.vb)]  
  
5.  라는 프로시저를 만들어 `Test` 를 호출 하 `DelegateTest` 한 번에 대 한 대리자와 `AddNumbers` 을 매개 변수로 사용 하 고 다시에 대 한 대리자와 `SubtractNumbers` 매개 변수로 합니다.  
  
     [!code-vb[VbVbalrDelegates#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_5.vb)]  
  
     때 `Test` 은 호출 먼저 표시의 결과 `AddNumbers` 실행 `5` 및 `3`, 하는 8입니다. 결과 `SubtractNumbers` 작업할 `9` 및 `3` 표시 되 면 6이 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [대리자](../../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [AddressOf 연산자](../../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [Delegate 문](../../../../visual-basic/language-reference/statements/delegate-statement.md)  
 [방법: 대리자 메서드 호출](../../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
