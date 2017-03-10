---
title: "- Operator (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Negate"
  - "vb.-"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "- operator [Visual Basic]"
  - "operators [Visual Basic], subtraction"
  - "operators [Visual Basic], difference"
  - "negation operator"
  - "operators [Visual Basic], arithmetic"
  - "subtraction operator, syntax"
  - "arithmetic operators, subtraction"
  - "difference operator"
  - "math operators"
  - "operators [Visual Basic], negation"
  - "minus operator [Visual Basic]"
ms.assetid: bff2c368-662d-4c92-ac87-1d9bdfd3426a
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# - Operator (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

두 숫자 식의 차를 반환하거나 숫자 식의 음의 값을 반환합니다.  
  
## 구문  
  
```  
  
      expression1 – expression2  
- or -  
– expression1  
```  
  
## 요소  
 `expression1`  
 필수 요소.  임의의 숫자 식입니다.  
  
 `expression2`  
 `–` 연산자가 음의 값을 계산하지 않으면 필수적 요소입니다.  임의의 숫자 식입니다.  
  
## 결과  
 결과는 `expression1`과 `expression2`의 차이거나 `expression1`의 음의 값입니다.  
  
 결과 데이터 형식은 `expression1`과 `expression2`의 데이터 형식에 적합한 숫자 형식입니다.  [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)에서 "정수 연산" 표를 참조하십시오.  
  
## 지원 형식  
 모든 숫자 데이터 형식입니다.  여기에는 부호 없는 형식, 부동 소수점 형식 및 `Decimal`이 포함됩니다.  
  
## 설명  
 위 구문에 나오는 첫 번째 사용에서 `–` 연산자는 두 숫자 식의 차에 대한 *이진* 산술 빼기 연산자입니다.  
  
 위 구문에 나오는 두 번째 사용에서는 `–` 연산자가 식의 음의 값에 대한 *단항* 부정 연산자입니다.  따라서 부정은 `expression1`의 부호를 반대로 바꾸는 과정이므로 `expression1`이 음수이면 결과는 양수가 됩니다.  
  
 두 식 중 하나가 [Nothing](../../../visual-basic/language-reference/nothing.md)이면 `–` 연산자는 해당 식을 0으로 처리합니다.  
  
> [!NOTE]
>  `–` 연산자는 필요에 따라 *오버로드*할 수 있습니다. 즉, 피연산자의 형식이 특정 클래스 또는 구조체인 경우 해당 클래스나 구조체에서 이 연산자의 동작을 다시 정의할 수 있습니다.  코드에서 이러한 클래스나 구조체에 대해 이 연산자를 사용할 때는 다시 정의된 동작을 알고 있어야 합니다.  자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)를 참조하십시오.  
  
## 예제  
 다음 예제에서는 `–` 연산자를 사용하여 두 식의 차를 계산하여 반환한 다음 숫자를 부정합니다.  
  
 [!code-vb[VbVbalrOperators#10](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/subtraction-operator_1.vb)]  
  
 이러한 문을 실행한 후 `binaryResult`에는 124.45가 포함되고 `unaryResult`에는 –334.90이 포함됩니다.  
  
## 참고 항목  
 [\-\= Operator](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)   
 [Arithmetic Operators](../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Arithmetic Operators in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)