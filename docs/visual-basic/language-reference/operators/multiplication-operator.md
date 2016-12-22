---
title: "* Operator (Visual Basic) | Microsoft Docs"
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
  - "vb.*"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "arithmetic operators, multiplication"
  - "operators [Visual Basic], multiplication"
  - "* operator [Visual Basic]"
  - "multiplication operator, syntax"
  - "math operators"
ms.assetid: 2b210382-99da-4195-89ba-b1d06f5e89ad
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# * Operator (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

두 숫자를 곱합니다.  
  
## 구문  
  
```  
  
number1 * number2  
```  
  
## 요소  
  
|||  
|-|-|  
|용어|정의|  
|`number1`|필수 요소.  임의의 숫자 식입니다.|  
|`number2`|필수 요소.  임의의 숫자 식입니다.|  
  
## 결과  
 결과는 `number1`과 `number2`의 곱입니다.  
  
## 지원 형식  
 부호 없는 형식, 부동 소수점 형식 및 `Decimal`을 비롯한 모든 숫자 형식입니다.  
  
## 설명  
 결과의 데이터 형식은 피연산자 형식에 따라 달라집니다.  다음 표에서는 결과의 데이터 형식이 결정되는 방식을 보여 줍니다.  
  
|||  
|-|-|  
|피연산자 데이터 형식|결과 데이터 형식|  
|두 식이 모두 정수 계열 데이터 형식\([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md), [Short](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [Long](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md)\)인 경우|`number1`과 `number2`의 데이터 형식에 적합한 숫자 데이터 형식.  [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)에서 "정수 연산" 표를 참조하십시오.|  
|두 식이 모두 [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md)인 경우|`Decimal`|  
|두 식이 모두 [Single](../../../visual-basic/language-reference/data-types/single-data-type.md)인 경우|`Single`|  
|둘 중 어느 한 식이 부동 소수점 데이터 형식\(`Single` 또는 [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)\)이고 둘 다 `Single`이 아닌 경우\(`Decimal`은 부동 소수점 데이터 형식이 아님\)|`Double`|  
  
 식이 [Nothing](../../../visual-basic/language-reference/nothing.md)이면 0으로 처리됩니다.  
  
## 오버로딩  
 `*` 연산자는 필요에 따라 *오버로드*할 수 있습니다. 즉, 피연산자의 형식이 특정 클래스 또는 구조체인 경우 해당 클래스나 구조체에서 이 연산자의 동작을 다시 정의할 수 있습니다.  코드에서 이러한 클래스나 구조체에 대해 이 연산자를 사용할 때는 다시 정의된 동작을 알고 있어야 합니다.  자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)를 참조하십시오.  
  
## 예제  
 다음 예제에서는 `*` 연산자를 사용하여 두 숫자를 곱합니다.  결과는 두 피연산자의 곱입니다.  
  
 [!CODE [VbVbalrOperators#4](../CodeSnippet/VS_Snippets_VBCSharp/VbVbalrOperators#4)]  
  
## 참고 항목  
 [\*\= Operator](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md)   
 [Arithmetic Operators](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)   
 [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Arithmetic Operators in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)