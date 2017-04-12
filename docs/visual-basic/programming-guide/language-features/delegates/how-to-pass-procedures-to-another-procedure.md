---
title: "방법: 프로시저에 Visual Basic에서 다른 프로시저 전달 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- AddressOf operator
- delegates [Visual Basic], passing procedures
ms.assetid: 5adbba15-5a1d-413f-ab3e-3ff6cc0a4669
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 9865e2d7d3786d289add3fa63b3db777317facdf
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-pass-procedures-to-another-procedure-in-visual-basic"></a>방법: Visual Basic에서 프로시저에 다른 프로시저 전달
이 예제에서는 대리자를 사용 하 여 프로시저에 다른 프로시저 전달 하는 방법을 보여 줍니다.  
  
 대리자는 형식에서 다른 형식 처럼 사용할 수 있는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]합니다. `AddressOf` 연산자 프로시저 이름에 적용 될 때 대리자 개체를 반환 합니다.  
  
 이 예제에 다른 프로시저를 사용 하 여 얻은에 대 한 참조를 사용할 수 있는 대리자 매개 변수가 있는 프로시저는 `AddressOf` 연산자입니다.  
  
### <a name="create-the-delegate-and-matching-procedures"></a>대리자 및 일치 하는 프로시저 만들기  
  
1.  명명 된 대리자를 만들고 `MathOperator`합니다.  
  
     [!code-vb[VbVbalrDelegates #&1;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_1.vb)]  
  
2.  라는 프로시저를 만들어 `AddNumbers` 매개 변수 및 반환 값의 일치 하는 `MathOperator`서명이 일치 되도록 합니다.  
  
     [!code-vb[VbVbalrDelegates #&2;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_2.vb)]  
  
3.  라는 프로시저를 만들어 `SubtractNumbers` 일치 하는 서명을 사용 하 여 `MathOperator`합니다.  
  
     [!code-vb[VbVbalrDelegates #&3;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_3.vb)]  
  
4.  라는 프로시저를 만들어 `DelegateTest` 대리자를 매개 변수로 사용 합니다.  
  
     이 절차에 대 한 참조를 수락할 수 있는 `AddNumbers` 또는 `SubtractNumbers`해당 서명이 일치 하기 때문에는 `MathOperator` 서명 합니다.  
  
     [!code-vb[VbVbalrDelegates #&4;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_4.vb)]  
  
5.  라는 프로시저를 만듭니다 `Test` 호출 하는 `DelegateTest` 에 대 한 대리자를 두 번 `AddNumbers` 및 다시에 대 한 대리자를 매개 변수로 `SubtractNumbers` 매개 변수로 합니다.  
  
     [!code-vb[VbVbalrDelegates #&5;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_5.vb)]  
  
     때 `Test` 은 호출 먼저 표시의 결과 `AddNumbers` 실행 `5` 및 `3`은 8입니다. 결과 `SubtractNumbers` 작업할 `9` 및 `3` 표시 되 면 6이 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [대리자](../../../../visual-basic/programming-guide/language-features/delegates/index.md)   
 [AddressOf 연산자](../../../../visual-basic/language-reference/operators/addressof-operator.md)   
 [Delegate 문](../../../../visual-basic/language-reference/statements/delegate-statement.md)   
 [방법: 대리자 메서드 호출](../../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)
