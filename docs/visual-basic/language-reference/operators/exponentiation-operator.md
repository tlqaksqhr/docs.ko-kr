---
title: "^ Operator (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.^"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "raising numbers to powers"
  - "^ operator [Visual Basic], exponention"
  - "square operator"
  - "^ operator [Visual Basic]"
  - "exponentiation operator [Visual Basic]"
  - "exponent"
  - "numbers, rasing"
  - "powers"
  - "arithmetic operators, exponentiation"
ms.assetid: d89a1ca8-83da-4784-a87b-a9d7dceb3f62
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# ^ Operator (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

특정 숫자를 다른 숫자의 승수로 거듭제곱합니다.  
  
## 구문  
  
```  
  
number ^ exponent  
```  
  
## 요소  
 `number`  
 필수 요소.  임의의 숫자 식입니다.  
  
 `exponent`  
 필수 요소.  임의의 숫자 식입니다.  
  
## 결과  
 결과는 `exponent`를 승수로 `number`를 거듭제곱한 값으로, 항상 `Double` 값입니다.  
  
## 지원 형식  
 `Double`.  다른 형식의 피연산자는 `Double`로 변환됩니다.  
  
## 설명  
 Visual Basic에서는 지수 연산이 항상 [Double Data Type](../../../visual-basic/language-reference/data-types/double-data-type.md)으로 수행됩니다.  
  
 `exponent`의 값은 소수나 음수 또는 음의 소수가 될 수 있습니다.  
  
 단일 식에서 두 번 이상 지수 연산을 수행하는 경우 `^` 연산자는 왼쪽에서 오른쪽으로 계산됩니다.  
  
> [!NOTE]
>  `^` 연산자는 필요에 따라 *오버로드*할 수 있습니다. 즉, 피연산자의 형식이 특정 클래스 또는 구조체인 경우 해당 클래스나 구조체에서 이 연산자의 동작을 다시 정의할 수 있습니다.  코드에서 이러한 클래스나 구조체에 대해 이 연산자를 사용할 때는 다시 정의된 동작을 알고 있어야 합니다.  자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)를 참조하십시오.  
  
## 예제  
 다음 예제에서는 `^` 연산자를 사용하여 숫자를 지수만큼 거듭제곱합니다.  즉, 첫째 피연산자가 둘째 피연산자의 승수로 거듭제곱됩니다.  
  
 [!code-vb[VbVbalrOperators#20](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/exponentiation-operator_1.vb)]  
  
 위 예제의 결과는 다음과 같습니다.  
  
 `exp1`은 4\(2의 제곱\)로 설정됩니다.  
  
 `exp2`는 19683\(3을 3제곱한 후 결과 값을 3제곱\)으로 설정됩니다.  
  
 `exp3`은 \-125\(\-5의 3제곱\)로 설정됩니다.  
  
 `exp4`는 625\(\-5의 4제곱\)로 설정됩니다.  
  
 `exp5`는 2\(8의 3제곱근\)로 설정됩니다.  
  
 `exp6`은 0.5\(1.0 나누기 8의 3제곱근\)로 설정됩니다.  
  
 위 예제의 식에서는 괄호가 중요한 역할을 합니다.  *연산자 우선 순위* 때문에 Visual Basic에서는 `^` 연산자가 다른 어떤 연산자보다 먼저 수행되며, 단항 `–` 연산자보다도 먼저 수행됩니다.  `exp4`와 `exp6`을 괄호 없이 계산한다면 다음과 같은 결과가 생성됩니다.  
  
 `exp4 = -5 ^ 4`\(5\-제곱\)를 계산 하는\-625에서 발생 합니다.  
  
 `exp6 = 8 ^ -1.0 / 3.0`은 \(8의 –1제곱, 즉 0.125\) 나누기 3.0, 즉 0.041666666666666666666666666666667로 계산됩니다.  
  
## 참고 항목  
 [^\= Operator](../../../visual-basic/language-reference/operators/exponentiation-assignment-operator.md)   
 [Arithmetic Operators](../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Arithmetic Operators in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)