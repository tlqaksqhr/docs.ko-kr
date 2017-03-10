---
title: "&amp;= Operator (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.&="
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "operator &="
  - "assignment statements, compound"
  - "statements [Visual Basic], compound assignment"
  - "&= operator [Visual Basic]"
  - "compound assignment statements"
ms.assetid: 0cf262fc-1a05-419a-a503-60013f111c8a
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# &amp;= Operator (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

`String` 변수 또는 속성에 `String` 식을 연결하고 결과를 변수 또는 속성에 할당합니다.  
  
## 구문  
  
```  
  
variableorproperty &= expression  
```  
  
## 요소  
 `variableorproperty`  
 필수 요소.  임의의 `String` 변수 또는 속성입니다.  
  
 `expression`  
 필수 요소.  `String` 식입니다.  
  
## 설명  
 `&=` 연산자의 왼쪽 요소는 단순 스칼라 변수, 속성 또는 배열 요소가 될 수 있습니다.  변수나 속성은 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)가 될 수 없습니다.  `&=` 연산자는 연결의 `String` 식의 오른쪽에는 `String` 변수 또는 속성의 왼쪽에 하 고 결과를 변수 또는 속성의 왼쪽에 할당 합니다.  
  
## 오버로딩  
 [& Operator](../../../visual-basic/language-reference/operators/concatenation-operator.md)는 필요에 따라 *오버로드*할 수 있습니다. 즉, 피연산자의 형식이 특정 클래스 또는 구조체인 경우 해당 클래스나 구조체에서 이 연산자의 동작을 다시 정의할 수 있습니다.  `&` 연산자를 오버로드하면 `&=` 연산자의 동작이 영향을 받습니다.  코드에서 `&`를 오버로드하는 클래스나 구조체에 대해 `&=`를 사용할 때는 다시 정의된 동작을 알고 있어야 합니다.  자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)를 참조하십시오.  
  
## 예제  
 다음 예제에서는 `&=` 연산자를 사용하여 두 `String` 변수를 연결하고 결과를 첫 번째 변수에 할당합니다.  
  
 [!code-vb[VbVbalrOperators#3](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/and-assignment-operator_1.vb)]  
  
## 참고 항목  
 [& Operator](../../../visual-basic/language-reference/operators/concatenation-operator.md)   
 [\+\= Operator](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)   
 [Assignment Operators](../../../visual-basic/language-reference/operators/assignment-operators.md)   
 [Concatenation Operators](../../../visual-basic/language-reference/operators/concatenation-operators.md)   
 [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Statements](../../../visual-basic/programming-guide/language-features/statements.md)