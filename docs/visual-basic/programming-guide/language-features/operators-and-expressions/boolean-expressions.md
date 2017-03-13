---
title: "Boolean Expressions (Visual Basic) | Microsoft Docs"
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
  - "short-circuiting"
  - "Boolean expressions"
  - "logical operators, Boolean expressions"
  - "expressions [Visual Basic], Boolean"
  - "expression evaluation, Boolean expressions"
  - "operators [Visual Basic], short-circuiting"
  - "Visual Basic code, operators"
  - "short-circuit evaluation"
  - "logical operators, short-circuiting"
  - "operators [Visual Basic], Boolean"
  - "Visual Basic code, expressions"
ms.assetid: d3d90406-55c8-4404-8143-50fd7f0d0d1a
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# Boolean Expressions (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

*부울 식*은 [Boolean 데이터 형식](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) 값\(`True` 또는 `False`\)으로 계산되는 식입니다.  `Boolean` 식은 여러 가지 형식을 사용할 수 있습니다.  가장 간단한 형식은 다음 예제와 같이 `Boolean` 변수의 값을 `Boolean` 리터럴과 직접 비교하는 것입니다.  
  
 [!code-vb[VbVbalrOperators#87](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/boolean-expressions_1.vb)]  
  
## \= 연산자의 두 가지 의미  
 `newCustomer = True` 할당문은 위의 예제의 식과 같지만 다른 기능을 수행하며 다르게 사용됩니다.  위의 예제에서 `newCustomer = True` 식은 부울 값을 나타내므로 `=` 기호는 비교 연산자로 해석됩니다.  독립 실행형 문에서는 `=` 기호는 할당 연산자로 해석되어 오른쪽의 값을 왼쪽에 있는 변수에 할당합니다.  다음은 이에 대한 예입니다.  
  
 [!code-vb[VbVbalrOperators#88](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/boolean-expressions_2.vb)]  
  
 자세한 내용은 [Value Comparisons](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md) 및 [Statements](../../../../visual-basic/language-reference/statements/index.md)을 참조하십시오.  
  
## 비교 연산자  
 `=`, `<`, `>`, `<>`, `<=`, `>=` 등과 같은 비교 연산자는 연산자의 왼쪽에 있는 식과 연산자의 오른쪽에 있는 식을 비교하고 결과를 `True` 또는 `False`로 평가하여 부울 식을 생성합니다.  다음은 이에 대한 예입니다.  
  
 `42 < 81`  
  
 42는 81보다 작으므로 위의 예제에서 부울 식은 `True`가 됩니다.  이러한 종류의 식에 대한 자세한 내용은 [Value Comparisons](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)를 참조하십시오.  
  
### 논리 연산자와 함께 사용되는 비교 연산자  
 좀 더 복잡한 부울 식을 만들기 위해 논리 연산자를 사용하여 비교 식을 결합할 수 있습니다.  다음 예제에서는 비교 연산자와 논리 연산자를 함께 사용하는 것을 보여 줍니다.  
  
 `x > y And x < 1000`  
  
 위의 예제에서 전체 식의 값은 `And` 연산자의 양쪽에 있는 각 식의 값에 따라 달라집니다.  두 식이 모두 `True`이면 전체 식은 `True`가 되고  둘 중 어느 한 식이 `False`이면 전체 식은 `False`가 됩니다.  
  
## 단락\(Short\-Circuiting\) 연산자  
 논리 연산자 `AndAlso`와 `OrElse`는 *단락\(short circuit\)*으로 알려진 동작을 나타냅니다.  단락\(short circuit\) 연산자는 왼쪽에 있는 피연산자를 먼저 계산합니다.  왼쪽에 있는 피연산자가 전체 식의 값을 결정하는 경우 오른쪽에 있는 식을 계산하지 않고 프로그램 실행이 계속됩니다.  다음은 이에 대한 예입니다.  
  
 [!code-vb[VbVbalrOperators#89](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/boolean-expressions_3.vb)]  
  
 위의 예제에서 연산자는 왼쪽에 있는 식 `45 < 12`를 계산합니다.  왼쪽에 있는 식이 `False`이므로 전체 논리 식은 `False`가 됩니다.  따라서 프로그램은 오른쪽에 있는 식 `testFunction(3)`을 계산하지 않고 `If` 블록 내의 코드 실행을 건너뜁니다.  이 예제에서는 왼쪽에 있는 식이 전체 식을 false로 계산하기 때문에 `testFunction()`을 호출하지 않습니다.  
  
 마찬가지로 `OrElse`를 사용하는 논리 식에서 왼쪽에 있는 식이 `True`가 되면 왼쪽에 있는 식이 이미 전체 식을 true로 계산하기 때문에 오른쪽에 있는 식을 계산하지 않고 다음 코드 줄을 실행합니다.  
  
### 비단락\(short circuit\) 연산자와 비교  
 이와 대조적으로 논리 연산자 `And`와 `Or`가 사용되는 경우에는 논리 연산자의 양쪽을 모두 계산합니다.  다음은 이에 대한 예입니다.  
  
 [!code-vb[VbVbalrOperators#90](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/boolean-expressions_4.vb)]  
  
 위의 예제에서는 왼쪽에 있는 식이 `False`가 되어도 `testFunction()`을 호출합니다.  
  
## 괄호 식  
 괄호를 사용하여 부울 식 계산 순서를 제어할 수 있습니다.  괄호로 묶은 식을 가장 먼저 확인합니다.  여러 번 중첩된 경우에는 가장 안쪽에 있는 식에 우선 순위가 부여됩니다.  괄호 내에서는 연산자 우선 순위 규칙에 따라 확인됩니다.  자세한 내용은 [Operator Precedence in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md)를 참조하십시오.  
  
## 참고 항목  
 [Logical and Bitwise Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)   
 [Value Comparisons](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)   
 [Statements](../../../../visual-basic/programming-guide/language-features/statements.md)   
 [Comparison Operators](../../../../visual-basic/language-reference/operators/comparison-operators.md)   
 [Efficient Combination of Operators](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)   
 [Operator Precedence in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Boolean Data Type](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)