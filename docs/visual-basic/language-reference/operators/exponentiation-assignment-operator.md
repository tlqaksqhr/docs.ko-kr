---
title: "^= Operator (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.^="
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "assignment statements, compound"
  - "statements [Visual Basic], compound assignment"
  - "^= operator [Visual Basic]"
  - "compound assignment statements"
ms.assetid: 397da132-2d96-4a85-a7bc-f7c730a608c9
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# ^= Operator (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

변수나 속성의 값을 식의 값으로 거듭제곱하고 결과를 변수나 속성에 다시 할당합니다.  
  
## 구문  
  
```  
  
variableorproperty ^= expression  
```  
  
## 요소  
 `variableorproperty`  
 필수 요소.  임의의 숫자 변수 또는 속성입니다.  
  
 `expression`  
 필수 요소.  임의의 숫자 식입니다.  
  
## 설명  
 `^=` 연산자의 왼쪽 요소는 단순 스칼라 변수, 속성 또는 배열 요소가 될 수 있습니다.  변수나 속성은 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)가 될 수 없습니다.  
  
 `^=`연산자먼저 발생의변수또는속성\(왼쪽에 있는연산자\)의 값에 전원 식 \(오른쪽에 있는연산자\)의 값입니다.   연산자는 다음 다시변수또는속성에 해당 연산의 결과를 할당합니다.  
  
 Visual Basic에서는 지수 연산이 항상 [Double Data Type](../../../visual-basic/language-reference/data-types/double-data-type.md)으로 수행됩니다.  다른 형식의 피연산자는 `Double` 형식으로 변환되며, 결과는 항상 `Double` 형식입니다.  
  
 `expression`의 값은 소수나 음수 또는 음의 소수가 될 수 있습니다.  
  
## 오버로딩  
 [^ Operator](../../../visual-basic/language-reference/operators/exponentiation-operator.md)는 필요에 따라 *오버로드*할 수 있습니다. 즉, 피연산자의 형식이 특정 클래스 또는 구조체인 경우 해당 클래스나 구조체에서 이 연산자의 동작을 다시 정의할 수 있습니다.  `^` 연산자를 오버로드하면 `^=` 연산자의 동작이 영향을 받습니다.  코드에서 `^`를 오버로드하는 클래스나 구조체에 대해 `^=`을 사용할 때는 다시 정의된 동작을 알고 있어야 합니다.  자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)를 참조하십시오.  
  
## 예제  
 다음 예제에서는 `^=` 연산자를 사용하여 첫째 `Integer` 변수의 값을 둘째 변수의 값으로 거듭제곱하고 결과를 첫째 변수에 할당합니다.  
  
 [!CODE [VbVbalrOperators#21](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOperators#21)]  
  
## 참고 항목  
 [^ Operator](../../../visual-basic/language-reference/operators/exponentiation-operator.md)   
 [Assignment Operators](../../../visual-basic/language-reference/operators/assignment-operators.md)   
 [Arithmetic Operators](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)   
 [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Statements](../../../visual-basic/programming-guide/language-features/statements.md)