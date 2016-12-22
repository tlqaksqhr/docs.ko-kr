---
title: "Relaxed Delegate Conversion (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
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
  - "relaxed delegate conversion [Visual Basic]"
  - "delegates [Visual Basic], relaxed conversion"
  - "conversions, relaxed delegate"
ms.assetid: 64f371d0-5416-4f65-b23b-adcbf556e81c
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Relaxed Delegate Conversion (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

완화된 대리자 변환을 사용하면 시그니처가 동일하지 않은 경우에도 대리자나 처리기에 sub 및 함수를 할당할 수 있습니다. 따라서 대리자에 대한 바인딩이 메서드 호출에 대해 이미 허용된 기존 바인딩과 동일해집니다.  
  
## 매개 변수 및 반환 형식  
 완화된 변환은 완전히 일치하는 시그니처 대신 `Option Strict`가 `On`으로 설정된 경우 다음과 같은 조건만 충족되면 됩니다.  
  
-   각 대리자 매개 변수의 데이터 형식에서 할당된 함수 또는 `Sub`의 해당 매개 변수의 데이터 형식으로 확대 변환이 가능해야 합니다.  다음 예제에서 대리자 `Del1`은 `Integer` 형식의 매개 변수 한 개를 사용합니다.  할당된 람다 식의 `m` 매개 변수는 `Integer`에서 확대 변환 가능한 데이터 형식\(예: `Long` 또는 `Double`\)이어야 합니다.  
  
     [!code-vb[VbVbalrRelaxedDelegates#1](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_1.vb)]  
  
     [!code-vb[VbVbalrRelaxedDelegates#2](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_2.vb)]  
  
     축소 변환은 `Option Strict`가 `Off`로 설정된 경우에만 허용됩니다.  
  
     [!code-vb[VbVbalrRelaxedDelegates#8](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_3.vb)]  
  
-   할당된 함수 또는 `Sub`의 반환 형식에서 대리자의 반환 형식으로도 확대 변환이 가능해야 합니다.  다음 예제에서 `del1`의 반환 형식은 `Integer`이므로 할당된 각 람다 식의 본문은 `Integer`로 확대 변환되는 데이터 형식으로 계산되어야 합니다.  
  
     [!code-vb[VbVbalrRelaxedDelegates#3](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_4.vb)]  
  
 `Option Strict`가 `Off`로 설정된 경우에는 양방향 모두에서 확대 변환 제한이 적용되지 않습니다.  
  
 [!code-vb[VbVbalrRelaxedDelegates#4](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_5.vb)]  
  
## 매개 변수 사양 생략  
 완화된 대리자를 사용하면 할당된 메서드에서 매개 변수 사양을 아예 생략할 수도 있습니다.  
  
 [!code-vb[VbVbalrRelaxedDelegates#5](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_6.vb)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#6](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_7.vb)]  
  
 일부 매개 변수는 지정할 수 없고 일부 매개 변수는 생략할 수 없습니다.  
  
 [!code-vb[VbVbalrRelaxedDelegates#15](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_8.vb)]  
  
 여러 개의 복잡한 매개 변수가 관련된 이벤트 처리기를 정의하는 경우에 매개 변수를 생략하면 유용합니다.  일부 이벤트 처리기의 인수는 사용되지 않습니다.  대신 처리기는 이벤트가 등록되어 있는 컨트롤의 상태에 직접 액세스하고 인수를 무시합니다.  완화된 대리자를 사용하면 모호성이 없는 선언에서 인수를 생략할 수 있습니다.  다음 예제에서는 완전하게 지정된 `OnClick` 메서드를 `RelaxedOnClick`으로 다시 작성할 수 있습니다.  
  
```vb#  
Sub OnClick(ByVal sender As Object, ByVal e As EventArgs) Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
  
Sub RelaxedOnClick() Handles b.Click  
    MessageBox.Show("Hello World from" + b.Text)  
End Sub  
```  
  
## AddressOf 예제  
 위의 예제에서는 형식 관계를 쉽게 볼 수 있도록 람다 식을 사용했습니다.  그러나 `AddressOf`, `Handles` 또는 `AddHandler`를 사용하는 대리자 할당에도 이와 같은 완화 기능을 사용할 수 있습니다.  
  
 다음 예제에서는 `f1`, `f2`, `f3` 및 `f4` 함수 모두 `Del1`에 할당할 수 있습니다.  
  
 [!code-vb[VbVbalrRelaxedDelegates#1](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_1.vb)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#7](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_9.vb)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#9](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_10.vb)]  
  
 다음 예제는 `Option Strict`가 `Off`로 설정된 경우에만 유효합니다.  
  
 [!code-vb[VbVbalrRelaxedDelegates#14](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_11.vb)]  
  
## 함수 반환 값 삭제  
 완화된 대리자 변환을 사용하면 `Sub` 대리자에 함수를 할당하여 함수의 반환 값을 효율적으로 무시할 수 있습니다.  그러나 `Sub`를 함수 대리자에 할당할 수는 없습니다.  다음 예제에서는 `doubler` 함수의 주소를 `Sub` 대리자 `Del3`에 할당합니다.  
  
 [!code-vb[VbVbalrRelaxedDelegates#10](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_12.vb)]  
  
 [!code-vb[VbVbalrRelaxedDelegates#11](../../../../visual-basic/programming-guide/language-features/delegates/codesnippet/VisualBasic/relaxed-delegate-conversion_13.vb)]  
  
## 참고 항목  
 [Lambda Expressions](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)   
 [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)   
 [Delegates](../../../../visual-basic/programming-guide/language-features/delegates/delegates.md)   
 [How to: Pass Procedures to Another Procedure in Visual Basic](../../../../visual-basic/programming-guide/language-features/delegates/how-to-pass-procedures-to-another-procedure.md)   
 [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)