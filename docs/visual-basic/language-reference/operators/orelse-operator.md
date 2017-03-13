---
title: "OrElse Operator (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "OrElse"
  - "vb.OrElse"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "short-circuiting"
  - "operators [Visual Basic], short-circuiting"
  - "operators [Visual Basic], disjunction"
  - "short-circuit evaluation"
  - "OrElse operator [Visual Basic]"
ms.assetid: 253803d8-05b0-47d7-b213-abd222847779
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# OrElse Operator (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

두 식의 단락\(short circuit\) 논리합 연산을 수행합니다.  
  
## 구문  
  
```  
  
result = expression1 OrElse expression2  
```  
  
## 요소  
 `result`  
 필수 요소.  `Boolean` 식입니다.  
  
 `expression1`  
 필수 요소.  `Boolean` 식입니다.  
  
 `expression2`  
 필수 요소.  `Boolean` 식입니다.  
  
## 설명  
 컴파일된 코드가 다른 식의 결과에 따라 한 식의 계산을 건너뛸 수 있는 경우의 논리 연산을 *단락\(short circuit\)*이라고 합니다.  계산된 첫째 식의 결과가 연산의 최종 결과를 결정하는 경우에는 둘째 식을 계산해도 최종 결과가 변경되지 않으므로 둘째 식을 계산할 필요가 없습니다.  단락\(short circuit\)을 사용하면 건너뛸 식이 복잡하거나 식에 프로시저 호출이 포함된 경우 성능을 향상시킬 수 있습니다.  
  
 두 식 중 하나 또는 둘 모두가 `True`이면 `result`는 `True`입니다.  다음 표에서는 `result`가 결정되는 방식을 보여 줍니다.  
  
|`expression1`의 값|`expression2`의 값|`result`의 값|  
|----------------------|----------------------|-----------------|  
|`True`|\(계산되지 않음\)|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
## 데이터 형식  
 `OrElse` 연산자는 [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md)에 대해서만 정의됩니다.  Visual Basic에서는 각 피연산자를 필요에 따라 `Boolean`으로 변환하고 연산을 완전 `Boolean` 형식으로 수행합니다.  결과를 숫자 형식에 할당하면 Visual Basic에서 결과 형식이 `Boolean`에서 해당 형식으로 변환됩니다.  이렇게 되면 예기치 않은 동작이 발생할 수 있습니다.  예를 들어, `5 OrElse 12`를 `Integer`로 변환하면 `–1`이 됩니다.  
  
## 오버로딩  
 [Or Operator](../../../visual-basic/language-reference/operators/or-operator.md) 및 [IsTrue Operator](../../../visual-basic/language-reference/operators/istrue-operator.md)는 *오버로드*할 수 있습니다. 즉, 피연산자의 형식이 특정 클래스 또는 구조인 경우 해당 클래스나 구조에서 이 연산자의 동작을 다시 정의할 수 있습니다.  `Or` 및 `IsTrue` 연산자를 오버로드하면 `OrElse` 연산자의 동작이 영향을 받습니다.  코드에서 `Or` 및 `IsTrue`를 오버로드하는 클래스나 구조에 대해 `OrElse`을 사용할 때는 다시 정의된 동작을 알고 있어야 합니다.  자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)를 참조하십시오.  
  
## 예제  
 다음 예제에서는 `OrElse` 연산자를 사용하여 두 식의 논리합 연산을 수행합니다.  결과는 두 식 중 하나가 True인지 여부를 나타내는 `Boolean` 값입니다.  첫째 식이 `True`이면 둘째 식은 계산되지 않습니다.  
  
 [!code-vb[VbVbalrOperators#37](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/orelse-operator_1.vb)]  
  
 위 예제의 결과는 각각 `True`, `True`, `False`가 됩니다.  `firstCheck` 계산에서 첫째 식이 `True`이므로 둘째 식은 계산되지 않습니다.  그러나 `secondCheck` 계산에서는 둘째 식이 계산됩니다.  
  
## 예제  
 다음 예제에서는 두 개의 프로시저 호출을 포함하는 `If`...`Then` 문을 보여 줍니다.  첫째 호출은 `True`를 반환하고 둘째 프로시저는 호출되지 않습니다.  이러한 방식은 코드의 이 섹션을 실행할 때 항상 수행되어야 할 중요한 작업을 둘째 프로시저가 수행하는 경우에 예기치 않은 동작을 발생시킬 수 있습니다.  
  
 [!code-vb[VbVbalrOperators#38](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/orelse-operator_2.vb)]  
  
## 참고 항목  
 [Logical\/Bitwise Operators](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)   
 [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Or Operator](../../../visual-basic/language-reference/operators/or-operator.md)   
 [IsTrue Operator](../../../visual-basic/language-reference/operators/istrue-operator.md)   
 [Logical and Bitwise Operators in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)