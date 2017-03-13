---
title: "Arithmetic Operators in Visual Basic | Microsoft Docs"
ms.custom: ""
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
  - "type safety"
  - "operators [Visual Basic], bitwise"
  - "operators [Visual Basic], bit-shift"
  - "bitwise operators"
  - "bit-shift operators"
  - "zero, division by zero"
  - "operators [Visual Basic], arithmetic"
  - "division, by zero"
  - "Visual Basic code, operators"
  - "arithmetic operators, about arithmetic operators"
ms.assetid: 325dac7a-ea4f-41d5-8b48-f6e904211569
caps.latest.revision: 20
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 20
---
# Arithmetic Operators in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

산술 연산자는 리터럴, 변수, 기타 식, 함수 및 속성 호출, 상수 등으로 나타내는 숫자 값 계산을 포함하여 여러 가지 친숙한 산술 연산을 수행하는 데 사용됩니다.  또한 피연산자의 개별 비트 수준에서 수행되고 비트 패턴을 왼쪽이나 오른쪽으로 이동하는 비트 시프트 연산자도 산술 연산자로 분류됩니다.  
  
## 산술 연산  
 다음 예제와 같이 식에서 [\+ Operator](../../../../visual-basic/language-reference/operators/addition-operator.md)를 사용하여 두 값을 서로 더하거나 [\- Operator](../../../../visual-basic/language-reference/operators/subtraction-operator.md)를 사용하여 한 값에서 다른 값을 뺄 수 있습니다.  
  
 [!code-vb[VbVbalrOperators#57](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_1.vb)]  
  
 다음 예제에서와 같이 부정 연산에서도 [\- Operator](../../../../visual-basic/language-reference/operators/subtraction-operator.md)를 사용하지만 피연산자는 하나만 사용됩니다.  
  
 [!code-vb[VbVbalrOperators#58](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_2.vb)]  
  
 다음 예제에서와 같이 곱하기 연산에는 [\* Operator](../../../../visual-basic/language-reference/operators/multiplication-operator.md)를, 나누기 연산에는 [\/ Operator](../../../../visual-basic/language-reference/operators/floating-point-division-operator.md)를 사용합니다.  
  
 [!code-vb[VbVbalrOperators#59](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_3.vb)]  
  
 다음 예제에서와 같이 지수 연산에서는 [^ Operator](../../../../visual-basic/language-reference/operators/exponentiation-operator.md)를 사용합니다.  
  
 [!code-vb[VbVbalrOperators#60](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_4.vb)]  
  
 정수 나누기는 [\\ Operator](../../../../visual-basic/language-reference/operators/integer-division-operator.md)를 사용하여 실행됩니다.  정수 나누기는 몫을 반환합니다. 즉, 이 몫은 나머지에 관계없이 제수를 피제수로 나눌 수 있는 횟수를 나타내는 정수입니다.  제수 및 피제수 모두 이 연산자에 대한 정수 계열 형식\(`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`\)이어야 합니다.  다른 모든 형식은 먼저 정수 계열 형식으로 변환해야 합니다.  다음 예제에서는 정수 나누기를 보여 줍니다.  
  
 [!code-vb[VbVbalrOperators#61](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_5.vb)]  
  
 나머지 연산은 [Mod 연산자](../../../../visual-basic/language-reference/operators/mod-operator.md)를 사용하여 수행됩니다.  이 연산자는 제수를 피제수로 나눈 후 나머지를 반환합니다.  제수와 피제수가 모두 정수 계열 형식이면 반환된 값도 정수이고  제수와 피제수가 부동 소수점 형식이면 반환된 값도 부동 소수점입니다.  다음 예제에서는 이 동작에 대해 설명합니다.  
  
 [!code-vb[VbVbalrOperators#62](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_6.vb)]  
  
 [!code-vb[VbVbalrOperators#63](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_7.vb)]  
  
### 0으로 나누기 수행  
 0으로 나누기의 결과는 관련된 데이터 형식에 따라 달라집니다.  정수 계열\(`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`\)을 0으로 나누면 [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort-md.md)]에서 <xref:System.DivideByZeroException> 예외를 throw합니다.  `Decimal` 또는 `Single` 데이터 형식에 대해 나누기 연산을 수행해도 [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort-md.md)]에서 <xref:System.DivideByZeroException> 예외를 throw합니다.  
  
 그러나 `Double` 데이터 형식으로 부동 소수점 나누기를 수행하는 경우 예외가 throw되지 않으며 피제수에 따라 각각 <xref:System.Double.NaN>, <xref:System.Double.PositiveInfinity> 또는 <xref:System.Double.NegativeInfinity>를 나타내는 클래스 멤버가 반환됩니다.  다음 표에서는 `Double` 값을 0으로 나누기의 다양한 결과를 요약하여 설명합니다.  
  
|||||  
|-|-|-|-|  
|피제수 데이터 형식|제수 데이터 형식|피제수 값|결과|  
|`Double`|`Double`|0|<xref:System.Double.NaN>\(수학적으로 정의된 숫자가 아님\)|  
|`Double`|`Double`|\> 0|<xref:System.Double.PositiveInfinity>|  
|`Double`|`Double`|\< 0|<xref:System.Double.NegativeInfinity>|  
  
 <xref:System.DivideByZeroException> 예외를 catch하는 경우 해당 멤버를 사용하여 이 예외를 처리할 수 있습니다.  예를 들어, <xref:System.Exception.Message%2A> 속성은 예외에 대한 메시지 텍스트를 저장합니다.  자세한 내용은 [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)을 참조하십시오.  
  
## 비트 시프트 연산  
 비트 시프트 연산은 비트 패턴에 대해 산술 시프트 연산을 수행합니다.  패턴은 왼쪽의 피연산자에 들어 있으며 오른쪽의 피연산자는 패턴을 이동할 위치 수를 지정합니다.  [\>\> Operator](../../../../visual-basic/language-reference/operators/right-shift-operator.md)를 사용하여 패턴을 오른쪽으로 이동하고 [\<\< Operator](../../../../visual-basic/language-reference/operators/left-shift-operator.md)를 사용하여 패턴을 왼쪽으로 이동합니다.  
  
 패턴 피연산자의 데이터 형식은 `SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long` 또는 `ULong`이어야 합니다.  시프트 횟수 피연산자의 데이터 형식은 `Integer`이거나 `Integer`로 확대 변환되어야 합니다.  
  
 산술 시프트 연산은 순환되지 않습니다. 즉, 한 쪽 끝에서 이동하여 빠져나가는 비트가 다른 쪽 끝으로 다시 들어가지 않습니다.  이동 후 비워진 비트 위치는 다음과 같이 설정됩니다.  
  
-   산술 왼쪽 시프트인 경우 0으로 설정됩니다.  
  
-   양수의 산술 오른쪽 시프트인 경우 0으로 설정됩니다.  
  
-   부호 없는 데이터 형식\(`Byte`, `UShort`, `UInteger`, `ULong`\)의 산술 오른쪽 시프트인 경우 0으로 설정됩니다.  
  
-   음수\(`SByte`, `Short`, `Integer` `Long`\)의 산술 오른쪽 시프트인 경우 1로 설정됩니다.  
  
 다음 예제에서는 `Integer` 값을 왼쪽 및 오른쪽으로 시프트합니다.  
  
 [!code-vb[VbVbalrOperators#64](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_8.vb)]  
  
 산술 시프트 연산에서는 오버플로 예외가 생성되지 않습니다.  
  
## 비트 연산  
 `Not`, `Or`, `And` 및 `Xor`는 논리 연산자로 사용될 뿐만 아니라 숫자 값에서 사용되는 경우 비트 연산도 수행합니다.  자세한 내용은 [Logical and Bitwise Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)에서 "비트 연산"을 참조하십시오.  
  
## 형식 안전성  
 일반적으로 피연산자의 형식은 같아야 합니다.  예를 들어, `Integer` 변수를 추가하는 경우 이를 다른 `Integer` 변수에 추가해야 하고 결과도 `Integer` 형식의 변수에 할당해야 합니다.  
  
 형식이 안전한 코딩을 보장하는 한 가지 방법은 [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)을 사용하는 것입니다.  `Option Strict On`을 설정하면 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 *형식 안전* 변환을 자동으로 수행합니다.  예를 들어, `Integer` 변수를 `Double` 변수에 추가하고 값을 `Double` 변수에 할당하려는 경우 `Integer` 값은 데이터 손실 없이 `Double`로 변환될 수 있으므로 연산이 정상적으로 수행됩니다.  안전하지 않은 형식 변환을 수행하면 `Option Strict On` 컴파일러 오류가 발생할 수 있습니다.  예를 들어, `Integer` 변수를 `Double` 변수에 추가하고 값을 `Integer` 변수에 할당하려고 하면 `Double` 변수를 `Integer` 형식으로 암시적으로 변환할 수 없으므로 컴파일러 오류가 발생합니다.  
  
 `Option Strict Off`를 설정한 경우 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 암시적 축소 변환을 수행할 수는 있지만 예기치 않은 데이터 손실 또는 정밀도 손상이 발생할 수 있습니다.  이런 이유로 프로덕션 코드를 작성할 때는 `Option Strict On`을 사용하는 것이 좋습니다.  자세한 내용은 [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)을 참조하십시오.  
  
## 참고 항목  
 [Arithmetic Operators](../../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Bit Shift Operators](../../../../visual-basic/language-reference/operators/bit-shift-operators.md)   
 [Comparison Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)   
 [Concatenation Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)   
 [Logical and Bitwise Operators in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)   
 [Efficient Combination of Operators](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)