---
title: "/ Operator (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb./"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "division operator, floating point"
  - "floating-point numbers, division operator"
  - "slash (/) operator"
  - "zero, division by zero"
  - "operators [Visual Basic], arithmetic"
  - "arithmetic operators, division"
  - "division, by zero"
  - "operators [Visual Basic], division"
  - "division operator, syntax"
  - "/ operator [Visual Basic]"
  - "math operators"
ms.assetid: 335e97f2-c434-439e-9064-76973a051101
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# / Operator (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

두 숫자를 나누고 부동 소수점 결과를 반환합니다.  
  
## 구문  
  
```  
  
expression1 / expression2  
```  
  
## 요소  
 `expression1`  
 필수 요소.  임의의 숫자 식입니다.  
  
 `expression2`  
 필수 요소.  임의의 숫자 식입니다.  
  
## 지원 형식  
 부호 없는 형식, 부동 소수점 형식 및 `Decimal`을 비롯한 모든 숫자 형식입니다.  
  
## 결과  
 결과는 `expression1`을 `expression2`로 나눈 전체 몫\(나머지 포함\)입니다.  
  
 [\\ Operator](../../../visual-basic/language-reference/operators/integer-division-operator.md)는 나머지가 삭제된 정수 몫을 반환합니다.  
  
## 설명  
 결과의 데이터 형식은 피연산자 형식에 따라 달라집니다.  다음 표에서는 결과의 데이터 형식이 결정되는 방식을 보여 줍니다.  
  
|피연산자 데이터 형식|결과 데이터 형식|  
|-----------------|---------------|  
|두 식이 모두 정수 계열 데이터 형식\([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md), [Short](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [Long](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md)\)인 경우|`Double`|  
|한 식은 [Single](../../../visual-basic/language-reference/data-types/single-data-type.md) 데이터 형식이고 다른 식은 [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)이 아닌 경우|`Single`|  
|한 식은 [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md) 데이터 형식이고 다른 식은 [Single](../../../visual-basic/language-reference/data-types/single-data-type.md) 또는 [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)이 아닌 경우|`Decimal`|  
|둘 중 어느 한 식이 [Double](../../../visual-basic/language-reference/data-types/double-data-type.md) 데이터 형식인 경우|`Double`|  
  
 나누기를 수행하기 전에 정수 계열 숫자 식이 모두 `Double`로 확장됩니다.  결과를 정수 계열 데이터 형식에 할당하면 결과는 `Double`에서 해당 형식으로 변환됩니다.  이때 결과가 해당 형식에 맞지 않을 경우 예외가 throw될 수 있습니다.  이 도움말 페이지에서 "0으로 나누기"를 참조하십시오.  
  
 `expression1` 또는 `expression2`가 [Nothing](../../../visual-basic/language-reference/nothing.md)이면 0으로 처리됩니다.  
  
## 0으로 나누기 수행  
 `expression2`가 0이면 `/` 연산자는 여러 가지 피연산자 데이터 형식에 대해 다르게 실행됩니다.  다음 표에서는 가능한 실행 결과를 보여 줍니다.  
  
|피연산자 데이터 형식|`expression2`가 0일 경우|  
|-----------------|--------------------------|  
|부동 소수점\(`Single` 또는 `Double`\)|무한대\(<xref:System.Double.PositiveInfinity> 또는 <xref:System.Double.NegativeInfinity>\)를 반환하거나, `expression1`도 0이면 <xref:System.Double.NaN>\(숫자 아님\)을 반환합니다.|  
|`Decimal`|<xref:System.DivideByZeroException>을 throw합니다.|  
|정수 계열\(부호 있음 또는 부호 없음\)|정수 형식에서 <xref:System.Double.PositiveInfinity>, <xref:System.Double.NegativeInfinity> 또는 <xref:System.Double.NaN>을 받아들일 수 없으므로 정수 형식으로 다시 변환하려고 하면 <xref:System.OverflowException>이 throw됩니다.|  
  
> [!NOTE]
>  `/` 연산자는 필요에 따라 *오버로드*할 수 있습니다. 즉, 피연산자의 형식이 특정 클래스 또는 구조체인 경우 해당 클래스나 구조체에서 이 연산자의 동작을 다시 정의할 수 있습니다.  코드에서 이러한 클래스나 구조체에 대해 이 연산자를 사용할 때는 다시 정의된 동작을 알고 있어야 합니다.  자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)를 참조하십시오.  
  
## 예제  
 다음 예제에서는 `/` 연산자를 사용하여 부동 소수점 나누기를 수행합니다.  결과는 두 피연산자의 몫입니다.  
  
 [!code-vb[VbVbalrOperators#16](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/floating-point-division-_1_1.vb)]  
  
 위 예제의 식에서는 2.5와 3.333333 값이 반환됩니다.  두 피연산자가 모두 정수 상수지만 결과는 항상 부동 소수점\(`Double`\)입니다.  
  
## 참고 항목  
 [\/\= Operator](../../../visual-basic/language-reference/operators/floating-point-division-assignment-operator.md)   
 [\\ Operator](../../../visual-basic/language-reference/operators/integer-division-operator.md)   
 [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)   
 [Arithmetic Operators](../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Arithmetic Operators in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)