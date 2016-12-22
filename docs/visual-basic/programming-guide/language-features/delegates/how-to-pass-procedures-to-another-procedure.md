---
title: "How to: Pass Procedures to Another Procedure in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "AddressOf operator"
  - "delegates [Visual Basic], passing procedures"
ms.assetid: 5adbba15-5a1d-413f-ab3e-3ff6cc0a4669
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Pass Procedures to Another Procedure in Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

이 예제에서는 대리자를 사용하여 한 프로시저를 다른 프로시저에 전달하는 방법을 보여 줍니다.  
  
 대리자는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]의 다른 형식처럼 사용할 수 있는 형식입니다.  `AddressOf` 연산자를 프로시저 이름에 적용하면 대리자 개체가 반환됩니다.  
  
 이 예제의 프로시저에는 `AddressOf` 연산자를 통해 얻은 다른 프로시저에 대한 참조를 사용할 수 있는 대리자 매개 변수가 있습니다.  
  
### 대리자 및 일치하는 프로시저 만들기  
  
1.  `MathOperator`라는 대리자를 만듭니다.  
  
     [!code-vb[VbVbalrDelegates#1](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_1.vb)]  
  
2.  시그니처가 일치하도록 매개 변수 및 반환 값이 `MathOperator`와 일치하는 `AddNumbers`라는 프로시저를 만듭니다.  
  
     [!code-vb[VbVbalrDelegates#2](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_2.vb)]  
  
3.  `MathOperator`와 시그니처가 일치하는 `SubtractNumbers`라는 프로시저를 만듭니다.  
  
     [!code-vb[VbVbalrDelegates#3](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_3.vb)]  
  
4.  대리자를 매개 변수로 사용하는 `DelegateTest`라는 프로시저를 만듭니다.  
  
     이 프로시저에서는 `AddNumbers` 또는 `SubtractNumbers`에 대한 참조를 사용할 수 있습니다. 이는 두 프로시저의 시그니처가 `MathOperator` 시그니처와 일치하기 때문입니다.  
  
     [!code-vb[VbVbalrDelegates#4](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_4.vb)]  
  
5.  한 번은 `AddNumbers`에 대한 대리자를 매개 변수로 사용하고 또 한 번은 `SubtractNumbers`에 대한 대리자를 매개 변수로 사용하여 `DelegateTest`를 호출하는 `Test`라는 프로시저를 만듭니다.  
  
     [!code-vb[VbVbalrDelegates#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-pass-procedures-to-another-procedure_5.vb)]  
  
     `Test`를 호출하면 먼저 `5`와 `3`에 대해 `AddNumbers`를 실행한 결과인 8이 표시되고,  그런 다음 `9`와 `3`에 대해 `SubtractNumbers`를 실행한 결과인 6이 표시됩니다.  
  
## 참고 항목  
 [Delegates](../../../../visual-basic/programming-guide/language-features/delegates/delegates.md)   
 [AddressOf Operator](../../../../visual-basic/language-reference/operators/addressof-operator.md)   
 [Delegate Statement](../../../../visual-basic/language-reference/statements/delegate-statement.md)   
 [How to: Invoke a Delegate Method](../../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)