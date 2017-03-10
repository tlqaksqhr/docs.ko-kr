---
title: "/= Operator (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb./="
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "assignment statements, compound"
  - "statements [Visual Basic], compound assignment"
  - "/= operator [Visual Basic]"
  - "operator /="
  - "compound assignment statements"
ms.assetid: a1e22d0e-8380-4761-9da1-84fb51c34821
caps.latest.revision: 23
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 23
---
# /= Operator (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

변수 또는 속성 값을 식의 값으로 나누고 부동 소수점 결과를 변수 또는 속성에 할당합니다.  
  
## 구문  
  
```  
  
variableorproperty /= expression  
```  
  
## 요소  
 `variableorproperty`  
 필수 요소.  임의의 숫자 변수 또는 속성입니다.  
  
 `expression`  
 필수 요소.  임의의 숫자 식입니다.  
  
## 설명  
 `/=` 연산자의 왼쪽 요소는 단순 스칼라 변수, 속성 또는 배열 요소가 될 수 있습니다.  변수나 속성은 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)가 될 수 없습니다.  
  
 `/=`연산자우선 나눕니다변수또는속성\(왼쪽에 있는연산자\)의 값 \(오른쪽에 있는연산자의\) 식의 값입니다.   다음연산자는변수또는속성에 부동 소수점 연산의 결과는 해당 할당합니다.  
  
 이명세서은 할당는 `Double` 값의변수또는속성왼쪽으로.  `Option Strict`가 `On`이면 `variableorproperty`는 `Double`이어야 합니다.  `Option Strict`가 `Off`이면 Visual Basic에서 암시적인 변환을 수행하고 결과 값을 `variableorproperty`에 할당합니다. 이 경우 런타임에 오류가 발생할 수 있습니다.  자세한 내용은 [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) 및 [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md)을 참조하십시오.  
  
## 오버로딩  
 [\/ Operator](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)는 필요에 따라 *오버로드*할 수 있습니다. 즉, 피연산자의 형식이 특정 클래스 또는 구조체인 경우 해당 클래스나 구조체에서 이 연산자의 동작을 다시 정의할 수 있습니다.  `/` 연산자를 오버로드하면 `/=` 연산자의 동작이 영향을 받습니다.  코드에서 `/`를 오버로드하는 클래스나 구조체에 대해 `/=`을 사용할 때는 다시 정의된 동작을 알고 있어야 합니다.  자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)를 참조하십시오.  
  
## 예제  
 다음 예제에서는 `/=` 연산자를 사용하여 첫째 `Integer` 변수의 값을 둘째 변수의 값으로 나누고 몫을 첫째 변수에 할당합니다.  
  
 [!code-vb[VbVbalrOperators#17](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/floating-point-division-_0_1.vb)]  
  
## 참고 항목  
 [\/ Operator](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)   
 [\\\= Operator](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)   
 [Assignment Operators](../../../visual-basic/language-reference/operators/assignment-operators.md)   
 [Arithmetic Operators](../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Statements](../../../visual-basic/programming-guide/language-features/statements.md)