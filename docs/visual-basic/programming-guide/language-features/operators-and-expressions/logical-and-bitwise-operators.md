---
title: "Logical and Bitwise Operators in Visual Basic | Microsoft Docs"
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
  - "short-circuiting"
  - "Boolean expressions"
  - "logical operators, Boolean expressions"
  - "operators [Visual Basic], logical"
  - "AndAlso operator"
  - "Not operator [Visual Basic], Boolean expressions"
  - "Xor operator [Visual Basic], Boolean expressions"
  - "And operator [Visual Basic], logical operators"
  - "logical operators"
  - "expressions [Visual Basic], Boolean"
  - "Or operator, logical operators"
  - "Visual Basic code, operators"
  - "short-circuiting, logical operators"
  - "logical operators, short-circuiting"
  - "Visual Basic code, expressions"
  - "logical operators, binary"
  - "OrElse operator [Visual Basic]"
  - "logical operators, unary"
ms.assetid: ca474e13-567d-4b1d-a18b-301433705e57
caps.latest.revision: 22
caps.handback.revision: 22
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Logical and Bitwise Operators in Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

논리 연산자는 `Boolean` 식을 비교하여 `Boolean` 결과를 반환합니다.  `And`, `Or`, `AndAlso`, `OrElse` 및 `Xor` 연산자는 두 개의 피연산자를 사용하므로 *이항* 연산자이고 `Not` 연산자는 단일 피연산자를 사용하므로 *단항* 연산자입니다.  이러한 연산자 중 일부는 정수 계열 값에 대해 비트 논리 연산을 수행할 수도 있습니다.  
  
## 단항 논리 연산자  
 [Not Operator](../../../../visual-basic/language-reference/operators/not-operator.md)는 `Boolean` 식에 대해 논리 *부정*을 수행하며  해당 피연산자의 반대 논리를 생성합니다.  식이 `True`인 경우 `Not`은 `False`를 반환하고 식이 `False`인 경우 `Not`은 `True`를 반환합니다.  다음은 이에 대한 예입니다.  
  
 [!CODE [VbVbalrOperators#77](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOperators#77)]  
  
## 이항 논리 연산자  
 [And Operator](../../../../visual-basic/language-reference/operators/and-operator.md)는 두 `Boolean` 식에 대해 *논리곱*을 수행합니다.  두 식이 모두 `True`인 경우 `And`는 `True`를 반환합니다.  식 중 하나라도 `False`인 경우 `And`는 `False`를 반환합니다.  
  
 [Or Operator](../../../../visual-basic/language-reference/operators/or-operator.md)는 두 `Boolean` 식에 대해 *논리합* 또는 논리 *포함*을 수행합니다.  식 중 하나가 `True`이거나 두 식이 모두 `True`인 경우 `Or`는 `True`를 반환합니다.  두 식이 모두 `True`인 경우 `Or`는 `False`를 반환합니다.  
  
 [Xor Operator](../../../../visual-basic/language-reference/operators/xor-operator.md)는 두 `Boolean` 식에 대해 *배타적 논리합*을 수행합니다.  식 중 하나만 `True`인 경우 `Xor`는 `True`를 반환합니다.  두 식이 모두 `True`이거나 두 식이 모두 `False`인 경우 `Xor`는 `False`를 반환합니다.  
  
 다음 예제에서는 `And`, `Or` 및 `Xor` 연산자를 보여 줍니다.  
  
 [!CODE [VbVbalrOperators#78](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOperators#78)]  
  
## 단락\(short circuit\) 논리 연산  
 [AndAlso Operator](../../../../visual-basic/language-reference/operators/andalso-operator.md)는 두 `Boolean` 식에 대해 논리곱을 수행한다는 점에서 `And` 연산자와 매우 유사합니다.  두 연산자의 주요 차이점은 `AndAlso`가 *단락\(short circuit\)* 동작을 나타낸다는 것입니다.  `AndAlso` 식의 첫 번째 식이 `False`인 경우 최종 결과를 변경할 수 없으므로 두 번째 식을 계산하지 않고 `AndAlso`는 `False`를 반환합니다.  
  
 마찬가지로 [OrElse Operator](../../../../visual-basic/language-reference/operators/orelse-operator.md)는 두 `Boolean` 식에 대해 단락\(short circuit\) 논리합을 수행합니다.  `OrElse` 식의 첫 번째 식이 `True`인 경우 최종 결과를 변경할 수 없으므로 두 번째 식을 계산하지 않고 `OrElse`는 `True`를 반환합니다.  
  
### 단락\(short circuit\)의 장단점  
 단락\(short circuit\)을 사용하면 논리 연산의 결과를 변경할 수 없는 식을 계산하지 않아 성능을 향상시킬 수 있지만  해당 식이 추가 작업을 수행하는 경우 단락\(short circuit\)은 이러한 작업을 건너뜁니다.  예를 들어, 식에 `Function` 프로시저에 대한 호출이 포함되어 있는 경우 식이 단락\(short circuit\)되면 해당 프로시저가 호출되지 않으며 `Function`에 포함된 추가 코드도 실행되지 않습니다.  따라서 함수가 가끔씩만 실행될 수 있으며 제대로 테스트되지 않을 수 있습니다.  또는 프로그램 논리가 `Function`의 코드에 따라 달라질 수 있습니다.  
  
 다음 예제에서는 `And` 및 `Or` 연산자와 단락\(short circuit\) 연산자의 차이점을 보여 줍니다.  
  
 [!CODE [VbVbalrOperators#81](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOperators#81)]  
  
 [!CODE [VbVbalrOperators#80](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOperators#80)]  
  
 [!CODE [VbVbalrOperators#79](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOperators#79)]  
  
 위 예제에서는 호출이 단락\(short circuit\)되는 경우 `checkIfValid()` 내 일부 중요한 코드가 실행되지 않습니다.  `And`가 단락\(short circuit\)하지 않으므로 `12 > 45`가 `False`를 반환하더라도 첫 번째 `If` 문은 `checkIfValid()`를 호출합니다.  `12 > 45`가 `False`를 반환하면 `AndAlso`가 두 번째 식을 단락\(short circuit\)하므로 두 번째 `If` 문은 `checkIfValid()`를 호출하지 않습니다.  `Or`가 단락\(short circuit\)하지 않으므로 `12 < 45`가 `True`를 반환하더라도 세 번째 `If` 문은 `checkIfValid()`를 호출합니다.  `12 < 45`가 `True`를 반환하면 `OrElse`가 두 번째 식을 단락\(short circuit\)하므로 네 번째 `If` 문은 `checkIfValid()`를 호출하지 않습니다.  
  
## 비트 연산  
 비트 연산은 두 정수 계열 값을 이진\(2진법\) 형식으로 계산합니다.  또한 해당 위치의 비트를 비교한 다음 이 비교를 기반으로 값을 할당합니다.  다음 예제에서는 `And` 연산자를 보여 줍니다.  
  
 [!code-vb[VbVbalrConcepts#2](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/codesnippet/VisualBasic/logical-and-bitwise-operators_1.vb)]  
  
 위 예제에서 `x` 값을 1로 설정하는 이유는 다음과  같습니다.  
  
-   값이 이진으로 처리됩니다.  
  
     3의 이진 형식 값 \= 011  
  
     5의 이진 형식 값 \= 101  
  
-   `And` 연산자는 한 번에 하나의 이진 위치\(비트\)에서 이진 표현을 비교합니다.  지정된 위치에서 두 비트가 모두 1이면 해당 위치에는 결과적으로 1이 남습니다.  둘 중 한 비트가 0이면 해당 위치에는 결과적으로 0이 남습니다.  위의 예제 결과는 다음과 같습니다.  
  
     011\(3의 이진 형식\)  
  
     101\(5의 이진 형식\)  
  
     001\(결과, 이진 형식\)  
  
-   결과는 10진수로 처리됩니다.  값 001은 1의 이진 표현이므로 `x` \= 1입니다.  
  
 비교 비트 중 어느 하나라도 1인 경우 결과 비트에 1이 할당된다는 점을 제외하면 비트 `Or` 연산도 비슷합니다.  `Xor`는 비교 비트 중 하나만 1인 경우 결과 비트에 1을 할당합니다.  `Not`은 단일 피연산자를 사용하고 부호 비트를 포함한 모든 비트를 반전하여 해당 값을 결과에 할당합니다.  즉, 부호 있는 양수의 경우 `Not`은 항상 음수를 반환하고 음수의 경우 `Not`은 항상 양수 또는 0을 반환합니다.  
  
 `AndAlso` 및 `OrElse` 연산자에는 비트 연산을 사용할 수 없습니다.  
  
> [!NOTE]
>  비트 연산은 정수 계열 형식에 대해서만 수행할 수 있으므로  비트 연산을 수행하려면 먼저 부동 소수점 값을 정수 계열 형식으로 변환해야 합니다.  
  
## 참고 항목  
 [Logical\/Bitwise Operators](../../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)   
 [Boolean Expressions](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)   
 [Arithmetic Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)   
 [Comparison Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)   
 [Concatenation Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)   
 [Efficient Combination of Operators](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)