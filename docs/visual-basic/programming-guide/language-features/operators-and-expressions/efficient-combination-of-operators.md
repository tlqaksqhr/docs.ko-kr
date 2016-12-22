---
title: "Efficient Combination of Operators (Visual Basic) | Microsoft Docs"
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
  - "expressions [Visual Basic], parentheses"
  - "operators [Visual Basic], associativity"
  - "expressions [Visual Basic], operators"
  - "operators [Visual Basic], precedence"
  - "Visual Basic code, operators"
  - "Visual Basic code, expressions"
  - "operators [Visual Basic], complex expressions"
  - "expressions [Visual Basic], complex"
  - "parentheses, complex expressions"
  - "numeric expressions"
ms.assetid: bd22340e-b5be-458b-8772-3916c02309a4
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Efficient Combination of Operators (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

복합 식에는 여러 가지 다양한 연산자를 사용할 수 있습니다.  다음은 이에 대한 예입니다.  
  
 `x = (45 * (y + z)) ^ (2 / 85) * 5 + z`  
  
 위의 예제와 같은 복합 식을 만들려면 연산자 우선 순위 규칙을 완전히 이해해야 합니다.  자세한 내용은 [Operator Precedence in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md)를 참조하십시오.  
  
## 괄호 식  
 연산자 우선 순위에 의해 결정된 것과 다른 순서로 연산을 실행할 수도 있습니다.  다음 예제를 살펴보십시오.  
  
 `x = z * y + 4`  
  
 위의 예제에서는 `z`를 `y`로 곱한 다음 그 결과에 `4`를 더합니다.  그러나 괄호를 사용하여 일반 연산자 우선 순위를 재정의하면 `y`와 `4`를 더한 다음 그 결과에 `z`를 곱할 수 있습니다.  식을 괄호로 묶으면 연산자 우선 순위에 관계없이 괄호로 묶은 식이 가장 먼저 계산됩니다.  위의 예제에서 더하기를 가장 먼저 수행하려면 다음 예제와 같이 다시 작성합니다.  
  
 `x = z * (y + 4)`  
  
 위의 예제에서는 `y`와 `4`를 더한 값에 `z`를 곱합니다.  
  
### 중첩 괄호 식  
 우선 순위를 추가로 재정의하려면 괄호를 여러 개 사용하여 식을 중첩시킬 수 있습니다.  괄호 내에서 가장 안쪽에 중첩된 식이 가장 먼저 계산되어 가장 바깥쪽에 중첩된 식까지 차례로 계산된 다음 괄호 외부의 식이 마지막으로 계산됩니다.  다음은 이에 대한 예입니다.  
  
 `x = (z * 4) ^ (y * (z + 2))`  
  
 위의 예제에서는 `z + 2`가 가장 먼저 계산된 다음 다른 괄호 식이 계산됩니다.  일반적으로 더하기나 빼기보다 우선 순위가 높은 지수 연산의 경우 다른 식이 괄호로 묶여 있기 때문에 이 예제에서는 마지막에 계산됩니다.  
  
## 참고 항목  
 [Arithmetic Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)   
 [Comparison Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)   
 [Logical and Bitwise Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)   
 [Logical\/Bitwise Operators](../../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)   
 [Boolean Expressions](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)   
 [Value Comparisons](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/value-comparisons.md)   
 [How to: Calculate Numeric Values](../Topic/How%20to:%20Calculate%20Numeric%20Values%20\(Visual%20Basic\).md)   
 [Operator Precedence in Visual Basic](../../../../visual-basic/language-reference/operators/operator-precedence.md)