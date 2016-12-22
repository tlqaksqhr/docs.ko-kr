---
title: "\ Operator (Visual Basic) | Microsoft Docs"
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
  - "vb.\"
  - "\"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "division operator, integer"
  - "integer division operator"
  - "zero, division by zero"
  - "arithmetic operators, division"
  - "division, by zero"
  - "backslash (\) [Visual Basic]"
  - "\ operator [Visual Basic]"
  - "integer quotient"
  - "math operators"
  - "quotients, integer"
  - "truncation, integer division"
ms.assetid: 4b0ee347-950c-45c9-8e23-54bc85df208e
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# \ Operator (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

두 숫자를 나누고 정수 결과를 반환합니다.  
  
## 구문  
  
```  
  
expression1 \ expression2  
```  
  
## 요소  
 `expression1`  
 필수 요소.  임의의 숫자 식입니다.  
  
 `expression2`  
 필수 요소.  임의의 숫자 식입니다.  
  
## 지원 형식  
 부호 없는 형식, 부동 소수점 형식 및 `Decimal`을 비롯한 모든 숫자 형식입니다.  
  
## 결과  
 결과는 `expression1`을 `expression2`로 나눠 나머지는 버리고 정수 부분만 남긴 몫입니다.  이를 *잘림*이라고 합니다.  
  
 결과 데이터 형식은 `expression1`과 `expression2`의 데이터 형식에 적합한 숫자 형식입니다.  [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)에서 "정수 연산" 표를 참조하십시오.  
  
 [\/ Operator](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)는 나머지를 소수 부분으로 유지하여 전체 몫을 반환합니다.  
  
## 설명  
 Visual Basic에서는 나누기 연산을 수행하기 전에 부동 소수점 숫자 식을 `Long`으로 변환합니다.  `Option Strict`가 `On`이면 컴파일러 오류가 발생합니다.  `Option Strict`가 `Off`이면 값이 [Long Data Type](../../../visual-basic/language-reference/data-types/long-data-type.md) 범위를 벗어날 경우 <xref:System.OverflowException>이 발생할 수 있습니다.  `Long`으로 변환할 때는 *은행원 반올림*도 적용됩니다.  자세한 내용은 [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)에서 "소수 부분"을 참조하십시오.  
  
 `expression1` 또는 `expression2`가 [Nothing](../../../visual-basic/language-reference/nothing.md)이면 0으로 처리됩니다.  
  
## 0으로 나누기 수행  
 `expression2`가 0이면 `\` 연산자는 <xref:System.DivideByZeroException> 예외를 throw합니다.  모든 숫자 데이터 형식의 피연산자도 마찬가지입니다.  
  
> [!NOTE]
>  `\` 연산자는 필요에 따라 *오버로드*할 수 있습니다. 즉, 피연산자의 형식이 특정 클래스 또는 구조체인 경우 해당 클래스나 구조체에서 이 연산자의 동작을 다시 정의할 수 있습니다.  코드에서 이러한 클래스나 구조체에 대해 이 연산자를 사용할 때는 다시 정의된 동작을 알고 있어야 합니다.  자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)를 참조하십시오.  
  
## 예제  
 다음 예제에서는 `\` 연산자를 사용하여 정수 나누기 연산을 수행합니다.  결과는 두 피연산자의 정수 몫을 나타내는 정수입니다. 이때 나머지는 버립니다.  
  
 [!CODE [VbVbalrOperators#18](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOperators#18)]  
  
 위 예제의 식에서는 2, 3, 33, \-22 값이 각각 반환됩니다.  
  
## 참고 항목  
 [\\\= Operator](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)   
 [\/ Operator](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)   
 [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [Arithmetic Operators](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)   
 [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Arithmetic Operators in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)