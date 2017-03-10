---
title: "Data Types of Operator Results (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "data types [Visual Basic], operator result data types"
  - "result data types"
  - "operator result data types"
  - "operators [Visual Basic], data types"
  - "data types [Visual Basic], ranges"
  - "operators [Visual Basic], result data types"
ms.assetid: 9d524533-e1a1-4aa8-b1b8-622068173d06
caps.latest.revision: 27
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 27
---
# Data Types of Operator Results (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]은 피연산자의 데이터 형식에 기반하여 연산의 결과 데이터 형식을 결정합니다.  경우에 따라 이 데이터 형식의 범위는 두 피연산자의 데이터 형식 범위보다 클 수 있습니다.  
  
## 데이터 형식 범위  
 관련 데이터 형식의 범위를 가장 작은 것부터 순서대로 나열하면 다음과 같습니다.  
  
-   [Boolean](../../../visual-basic/language-reference/data-types/boolean-data-type.md) — 두 개의 값 사용 가능  
  
-   [SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md) — 256개의 정수 계열 값 사용 가능  
  
-   [Short](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md) — 65,536\(6.5...E\+4\)개의 정수 계열 값 사용 가능  
  
-   [Integer](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md) — 4,294,967,296\(4.2...E\+9\)개의 정수 계열 값 사용 가능  
  
-   [Long](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md) — 18,446,744,073,709,551,615\(1.8...E\+19\)개의 정수 계열 값 사용 가능  
  
-   [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md) — 최대 범위 7.9...E\+28\(절대 값\)의 1.5...E\+29개 정수 계열 값 사용 가능  
  
-   [Single](../../../visual-basic/language-reference/data-types/single-data-type.md) — 최대 범위 3.4...E\+38\(절대 값\)  
  
-   [Double](../../../visual-basic/language-reference/data-types/double-data-type.md) — 최대 범위 1.7...E\+308\(절대 값\)  
  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 데이터 형식에 대한 자세한 내용은 [Data Types](../../../visual-basic/language-reference/data-types/data-type-summary.md)을 참조하십시오.  
  
 피연산자가 [Nothing](../../../visual-basic/language-reference/nothing.md)이면 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 산술 연산자는 이를 0으로 처리합니다.  
  
## 10진수 산술 연산  
 [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md) 데이터 형식은 부동 소수점이나 정수가 아닙니다.  
  
 `+`, `–`, `*`, `/` 또는 `Mod` 연산의 피연산자 중 하나가 `Decimal`이고 다른 피연산자가 `Single`이나 `Double`일 경우 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 다른 피연산자를 `Decimal`로 확장합니다.  그런 다음 연산을 `Decimal`로 수행하며 결과 데이터 형식은 `Decimal`이 됩니다.  
  
## 부동 소수점 산술 연산  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 대부분의 부동 소수점 산술 연산을 [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)로 수행하며 이는 이러한 연산에 가장 효율적인 데이터 형식입니다.  그러나 피연산자 중 하나가 [Single](../../../visual-basic/language-reference/data-types/single-data-type.md)이고 다른 하나가 `Double`이 아닌 경우 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 해당 연산을 `Single`로 수행합니다.  Visual Basic에서는 연산 전에 각 피연산자를 필요에 따라 적절한 데이터 형식으로 확장하며 결과 데이터 형식은 해당 형식이 됩니다.  
  
### \/ 및 ^ 연산자  
 `/` 연산자는 [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md), [Single](../../../visual-basic/language-reference/data-types/single-data-type.md) 및 [Double](../../../visual-basic/language-reference/data-types/double-data-type.md) 데이터 형식에 대해서만 정의됩니다.  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 연산 전에 각 피연산자를 필요에 따라 적절한 데이터 형식으로 확장하며 결과 데이터 형식은 해당 형식이 됩니다.  
  
 다음 표에서는 `/` 연산자에 대한 결과 데이터 형식을 보여 줍니다.  이 표는 대칭적입니다. 즉 피연산자 데이터 형식의 특정 조합에 대한 결과 데이터 형식은 피연산자의 순서에 상관없이 동일합니다.  
  
||||||  
|-|-|-|-|-|  
||`Decimal`|`Single`|`Double`|임의의 정수 형식|  
|`Decimal`|Decimal|Single|Double|Decimal|  
|`Single`|Single|Single|Double|Single|  
|`Double`|Double|Double|Double|Double|  
|임의의 정수 형식|Decimal|Single|Double|Double|  
  
 `^` 연산자는 `Double` 데이터 형식에 대해서만 정의됩니다.  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]은 연산 전에 `Double`에 필요한 각 피연산자를 확대 변환하며 결과 데이터 형식은 항상 `Double`입니다.  
  
## 정수 산술 연산  
 정수 연산의 결과 데이터 형식은 피연산자의 데이터 형식에 따라 달라집니다.  일반적으로 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 결과 데이터 형식을 결정하기 위해 다음 정책을 사용합니다.  
  
-   이항 연산자의 두 피연산자가 같은 데이터 형식을 가지는 경우 결과 데이터 형식은 해당 형식이 됩니다.  `Boolean`은 예외로 `Short`가 적용됩니다.  
  
-   부호 없는 피연산자가 부호 있는 피연산자와 함께 사용되는 경우 결과는 부호 있는 형식을 가지며 범위는 적어도 두 피연산자 중 하나보다 크게 됩니다.  
  
-   그렇지 않은 경우 결과는 두 피연산자 데이터 형식 중에서 더 큰 데이터 형식을 가집니다.  
  
 결과 데이터 형식은 두 피연산자 데이터 형식 모두와 다를 수도 있습니다.  
  
> [!NOTE]
>  결과 데이터 형식이 항상 연산 결과로 얻은 모든 가능한 값을 보유할 수 있을 만큼 크지는 않습니다.  값이 결과 데이터 형식에 비해 너무 큰 경우 <xref:System.OverflowException> 예외가 발생할 수 있습니다.  
  
### 단항 \+ 및 – 연산자  
 다음 표에서는 `+` 및 `–` 단항 연산자에 대한 결과 데이터 형식을 보여 줍니다.  
  
|||||||||||  
|-|-|-|-|-|-|-|-|-|-|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|단항 `+`|Short|SByte|Byte|Short|UShort|Integer|UInteger|Long|ULong|  
|단항 `–`|Short|SByte|Short|Short|Integer|Integer|Long|Long|Decimal|  
  
### \<\< 및 \>\> 연산자  
 다음 표에서는 `<<` 및 `>>` 비트 시프트 연산자에 대한 결과 데이터 형식을 보여 줍니다.  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 각 비트 시프트 연산자를 해당 왼쪽 피연산자\(이동할 비트 패턴\)에서 단항 연산자로 처리합니다.  
  
|||||||||||  
|-|-|-|-|-|-|-|-|-|-|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`<<`, `>>`|Short|SByte|Byte|Short|UShort|Integer|UInteger|Long|ULong|  
  
 왼쪽 피연산자가 `Decimal`, `Single`, `Double` 또는 `String`인 경우 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 연산 전에 이를 `Long`으로 변환하며 결과 데이터 형식은 `Long`이 됩니다.  오른쪽 피연산자\(이동할 비트 위치의 수\)는 `Integer` 또는 `Integer`로 확장되는 형식이어야 합니다.  
  
### 이항 \+, –, \* 및 Mod 연산자  
 다음 표에서는 이항 `+` 및 `–`연산자와 `*`및  `Mod` 연산자에 대한 결과 데이터 형식을 보여 줍니다.  이 표는 대칭적입니다. 즉 피연산자 데이터 형식의 특정 조합에 대한 결과 데이터 형식은 피연산자의 순서에 상관없이 동일합니다.  
  
|||||||||||  
|-|-|-|-|-|-|-|-|-|-|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Boolean`|Short|SByte|Short|Short|Integer|Integer|Long|Long|Decimal|  
|`SByte`|SByte|SByte|Short|Short|Integer|Integer|Long|Long|Decimal|  
|`Byte`|Short|Short|Byte|Short|UShort|Integer|UInteger|Long|ULong|  
|`Short`|Short|Short|Short|Short|Integer|Integer|Long|Long|Decimal|  
|`UShort`|Integer|Integer|UShort|Integer|UShort|Integer|UInteger|Long|ULong|  
|`Integer`|Integer|Integer|Integer|Integer|Integer|Integer|Long|Long|Decimal|  
|`UInteger`|Long|Long|UInteger|Long|UInteger|Long|UInteger|Long|ULong|  
|`Long`|Long|Long|Long|Long|Long|Long|Long|Long|Decimal|  
|`ULong`|Decimal|Decimal|ULong|Decimal|ULong|Decimal|ULong|Decimal|ULong|  
  
### \\ 연산자  
 다음 표에서는 `\` 연산자에 대한 결과 데이터 형식을 보여 줍니다.  이 표는 대칭적입니다. 즉 피연산자 데이터 형식의 특정 조합에 대한 결과 데이터 형식은 피연산자의 순서에 상관없이 동일합니다.  
  
|||||||||||  
|-|-|-|-|-|-|-|-|-|-|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Boolean`|Short|SByte|Short|Short|Integer|Integer|Long|Long|Long|  
|`SByte`|SByte|SByte|Short|Short|Integer|Integer|Long|Long|Long|  
|`Byte`|Short|Short|Byte|Short|UShort|Integer|UInteger|Long|ULong|  
|`Short`|Short|Short|Short|Short|Integer|Integer|Long|Long|Long|  
|`UShort`|Integer|Integer|UShort|Integer|UShort|Integer|UInteger|Long|ULong|  
|`Integer`|Integer|Integer|Integer|Integer|Integer|Integer|Long|Long|Long|  
|`UInteger`|Long|Long|UInteger|Long|UInteger|Long|UInteger|Long|ULong|  
|`Long`|Long|Long|Long|Long|Long|Long|Long|Long|Long|  
|`ULong`|Long|Long|ULong|Long|ULong|Long|ULong|Long|ULong|  
  
 `\`연산자의 피연산자 중 하나가 [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md), [Single](../../../visual-basic/language-reference/data-types/single-data-type.md) 또는 [Double](../../../visual-basic/language-reference/data-types/double-data-type.md)인 경우 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 연산 전에 이를 [Long](../../../visual-basic/language-reference/data-types/long-data-type.md)으로 변환하며 결과 데이터 형식은 `Long`이 됩니다.  
  
## 관계 및 비트 비교  
 관계 연산\(`=`, `<>`, `<`, `>`, `<=`, `>=`\)의 결과 데이터 형식은 항상 `Boolean`[Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md)입니다.  `Boolean` 피연산자에 대한 논리 연산\(`And`, `AndAlso`, `Not`, `Or`, `OrElse`, `Xor`\)의 경우도 마찬가지입니다.  
  
 비트 논리 연산의 결과 데이터 형식은 피연산자의 데이터 형식에 따라 달라집니다.  `AndAlso` 및 `OrElse`는 `Boolean`에 대해서만 정의되어 있으며 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 연산을 수행하기 전에 필요에 따라 각 피연산자를 `Boolean`로 변환합니다.  
  
### \=, \<\>, \<, \>, \<\= 및 \>\= 연산자  
 두 피연산자가 모두 `Boolean`인 경우 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 `True`가 `False`보다 작은 것으로 간주합니다.  숫자 형식을 `String`과 비교하는 경우 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 연산 전에 `String`을 `Double`로 변환합니다.  `Char` 또는 `Date` 피연산자는 데이터 형식이 동일한 다른 피연산자와만 비교될 수 있습니다.  결과 데이터 형식은 항상 `Boolean`입니다.  
  
### 비트 Not 연산자  
 다음 표에서는 비트 `Not` 연산자에 대한 결과 데이터 형식을 보여 줍니다.  
  
|||||||||||  
|-|-|-|-|-|-|-|-|-|-|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Not`|Boolean|SByte|Byte|Short|UShort|Integer|UInteger|Long|ULong|  
  
 피연산자가 `Decimal`, `Single`, `Double` 또는 `String`인 경우 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 연산 전에 이를 `Long`으로 변환하며 결과 데이터 형식은 `Long`이 됩니다.  
  
### 비트 And, Or 및 Xor 연산자  
 다음 표에서는 비트 `And`, `Or` 및 `Xor` 연산자에 대한 결과 데이터 형식을 보여 줍니다.  이 표는 대칭적입니다. 즉 피연산자 데이터 형식의 특정 조합에 대한 결과 데이터 형식은 피연산자의 순서에 상관없이 동일합니다.  
  
|||||||||||  
|-|-|-|-|-|-|-|-|-|-|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Boolean`|Boolean|SByte|Short|Short|Integer|Integer|Long|Long|Long|  
|`SByte`|SByte|SByte|Short|Short|Integer|Integer|Long|Long|Long|  
|`Byte`|Short|Short|Byte|Short|UShort|Integer|UInteger|Long|ULong|  
|`Short`|Short|Short|Short|Short|Integer|Integer|Long|Long|Long|  
|`UShort`|Integer|Integer|UShort|Integer|UShort|Integer|UInteger|Long|ULong|  
|`Integer`|Integer|Integer|Integer|Integer|Integer|Integer|Long|Long|Long|  
|`UInteger`|Long|Long|UInteger|Long|UInteger|Long|UInteger|Long|ULong|  
|`Long`|Long|Long|Long|Long|Long|Long|Long|Long|Long|  
|`ULong`|Long|Long|ULong|Long|ULong|Long|ULong|Long|ULong|  
  
 피연산자가 `Decimal`, `Single`, `Double` 또는 `String`인 경우 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 연산 전에 이를 `Long`으로 변환하며 결과 데이터 형식은 해당 피연산자가 이미 이전에 `Long`이었던 것처럼 Long이 됩니다.  
  
## 기타 연산자  
 `&` 연산자는 `String` 피연산자의 연결에 대해서만 정의됩니다.  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]은 연산 전에 `String`에 필요한 각 피연산자를 변환하며 결과 데이터 형식은 항상 `String`입니다.  `&` 연산자의 경우 `Option Strict`가 `On`인 경우에도 `String`으로 변환하면 모두 확장되는 것으로 간주됩니다.  
  
 `Is` 및 `IsNot` 연산자에서는 두 피연산자가 모두 참조 형식이어야 합니다.  `TypeOf`...`Is` 식에서는 첫 번째 피연산자가 참조 형식이고 두 번째 피연산자가 데이터 형식의 이름이어야 합니다.  이러한 모든 경우에 결과 데이터 형식은 `Boolean`이 됩니다.  
  
 `Like` 연산자는 `String` 피연산자의 패턴 일치에 대해서만 정의됩니다.  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 연산 전에 각 연산자를 필요에 따라 `String`으로 변환합니다.  결과 데이터 형식은 항상 `Boolean`입니다.  
  
## 참고 항목  
 [Data Types](../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Operators and Expressions](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)   
 [Arithmetic Operators in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)   
 [Comparison Operators in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)   
 [Operators](../../../visual-basic/language-reference/operators/index.md)   
 [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Arithmetic Operators](../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Comparison Operators](../../../visual-basic/language-reference/operators/comparison-operators.md)   
 [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md)