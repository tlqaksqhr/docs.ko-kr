---
title: "Value Comparisons (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "variables [Visual Basic], comparing values"
  - "Visual Basic code, operators"
  - "Visual Basic code, expressions"
  - "comparison operators, comparing expressions"
  - "numeric expressions"
  - "operators [Visual Basic], comparison"
  - "expressions [Visual Basic], comparing"
ms.assetid: 60da0c76-9458-4afc-97e9-44a7939c064c
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# Value Comparisons (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

비교 연산자를 사용하여 숫자 변수의 값을 비교하는 식을 구성할 수 있습니다.  이러한 식은 비교 결과가 true인지 아니면 false인지에 따라 `Boolean` 값을 반환합니다.  이러한 식의 예제는 다음과 같습니다.  
  
 `45 > 26`  
  
 `26 > 45`  
  
 첫째 식은 45가 26보다 크므로 `True`가 되고  둘째 식은 26이 45보다 크지 않으므로 `False`가 됩니다.  
  
 또한 이런 방식으로 숫자 식을 비교할 수 있습니다.  비교하는 두 식은 다음 예제와 같이 복잡한 식일 수 있습니다.  
  
 `x / 45 * (y +17) >= System.Math.Sqrt(z) / (p - (x * 16))`  
  
 위의 복합 식은 리터럴, 변수 및 함수 호출을 포함합니다.  비교 연산자의 양쪽에 있는 식을 계산한 다음 `>=` 비교 연산자를 사용하여 결과 값을 비교합니다.  왼쪽 식의 값이 오른쪽 식의 값보다 크거나 같으면 전체 식이 `True`가 되고, 그렇지 않으면 `False`가 됩니다.  
  
 다음 예제와 같이 값을 비교하는 식은 `If...Then` 구문에서 가장 일반적으로 사용됩니다.  
  
 [!code-vb[VbVbalrOperators#84](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/value-comparisons_1.vb)]  
  
 `=` 기호는 할당 연산자뿐만 아니라 비교 연산자입니다.  다음 예제와 같이 비교 연산자로 사용되는 경우에는 왼쪽의 값이 오른쪽의 값과 같은지 여부를 확인합니다.  
  
 [!code-vb[VbVbalrOperators#85](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/value-comparisons_2.vb)]  
  
 또한 `If`, `While`, `Loop` 또는 `ElseIf` 문과 같이 `Boolean` 값이 필요한 모든 경우 또는 `Boolean` 변수에 값을 할당하거나 전달하는 경우 비교 식을 사용할 수 있습니다.  다음 예제에서는 비교 식에서 반환된 값이 `Boolean` 변수에 할당됩니다.  
  
 [!code-vb[VbVbalrOperators#86](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/value-comparisons_3.vb)]  
  
## 참고 항목  
 [Boolean Expressions](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)   
 [Operators and Expressions](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)   
 [Comparison Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)   
 [How to: Calculate Numeric Values](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-calculate-numeric-values.md)   
 [Operator Precedence in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md)