---
title: "Visual Basic의 산술 연산자"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- type safety
- operators [Visual Basic], bitwise
- operators [Visual Basic], bit-shift
- bitwise operators [Visual Basic]
- bit-shift operators [Visual Basic]
- zero, division by zero
- operators [Visual Basic], arithmetic
- division [Visual Basic], by zero
- Visual Basic code, operators
- arithmetic operators [Visual Basic], about arithmetic operators
ms.assetid: 325dac7a-ea4f-41d5-8b48-f6e904211569
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7fec98c38eebc34a0f84e051dc7c0914f537418f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="arithmetic-operators-in-visual-basic"></a>Visual Basic의 산술 연산자
산술 연산자는 많은 리터럴, 변수, 다른 식, 함수 및 속성 호출 및 상수를 나타내는 숫자 값의 계산을 포함 하는 친숙 한 산술 연산을 수행 하는 데 사용 됩니다. 피연산자의 개별 비트 수준에서 작동 하 고 왼쪽 이나 오른쪽으로의 비트 패턴을 이동 하는 비트 시프트 연산자는 산술 연산자를 사용 하 여 분류도 합니다.  
  
## <a name="arithmetic-operations"></a>산술 연산  
 와 함께 식에서 두 개의 값을 추가할 수 있습니다는 [+ 연산자](../../../../visual-basic/language-reference/operators/addition-operator.md), 또는와 다른 빼기는 [-연산자 (Visual Basic)](../../../../visual-basic/language-reference/operators/subtraction-operator.md)다음 예제에서 보여 주듯이, 합니다.  
  
 [!code-vb[VbVbalrOperators#57](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_1.vb)]  
  
 부정 또한 사용 하 여는 [-연산자 (Visual Basic)](../../../../visual-basic/language-reference/operators/subtraction-operator.md), 없지만 하나의 피연산자와 함께 다음 예제와 같이 보여 줍니다.  
  
 [!code-vb[VbVbalrOperators#58](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_2.vb)]  
  
 사용 하 여 곱하기와 나누기는 [* 연산자](../../../../visual-basic/language-reference/operators/multiplication-operator.md) 및 [/ 연산자 (Visual Basic)](../../../../visual-basic/language-reference/operators/floating-point-division-operator.md)다음 예제에서 보여 주듯이 각각.  
  
 [!code-vb[VbVbalrOperators#59](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_3.vb)]  
  
 사용 하 여 지 수는 [^ 연산자](../../../../visual-basic/language-reference/operators/exponentiation-operator.md)다음 예제에서 보여 주듯이, 합니다.  
  
 [!code-vb[VbVbalrOperators#60](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_4.vb)]  
  
 정수 나누기 연산을 수행 하는 사용 하 여 [\ 연산자 (Visual Basic)](../../../../visual-basic/language-reference/operators/integer-division-operator.md)합니다. 즉, 횟수를 나타내는 정수 제도 나눌 수 있으며 나머지를 고려 하지 않고 피제수, 정수 나누기 몫을 반환 합니다. Divisor와 dividend가 모두 정수 계열 형식 이어야 합니다 (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, 및 `ULong`)이이 연산자에 대 한 합니다. 다른 모든 형식은 정수 계열 형식으로 먼저 변환 해야 합니다. 다음 예제에서는 정수 나누기를 보여 줍니다.  
  
 [!code-vb[VbVbalrOperators#61](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_5.vb)]  
  
 모듈러스 산술 사용 하 여 수행 되는 [Mod 연산자](../../../../visual-basic/language-reference/operators/mod-operator.md)합니다. 이 연산자 번을 합한 값으로 하 제 수를 피제수로 나눈 다음 나머지를 반환 합니다. Divisor와 dividend 둘 다 정수 계열 형식인 경우 반환 되는 값은 정수 계열입니다. Divisor와 dividend 부동 소수점 형식인 경우 반환 되는 값도 부동 소수점입니다. 다음 예제에서는이 동작을 보여 줍니다.  
  
 [!code-vb[VbVbalrOperators#62](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_6.vb)]  
  
 [!code-vb[VbVbalrOperators#63](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_7.vb)]  
  
### <a name="attempted-division-by-zero"></a>0으로 나누기  
 0으로 나누기는 관련 된 데이터 형식에 따라 다른 결과입니다. 정수 계열 사업부의 (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, `ULong`), [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] throw 한 <xref:System.DivideByZeroException> 예외입니다. 나누기에 대 한 작업에는 `Decimal` 또는 `Single` 데이터 형식으로는 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] throw는 <xref:System.DivideByZeroException> 예외입니다.  
  
 부동 소수점 나누기에서는 `Double` 데이터 형식 예외가 throw 되지 않으며 결과 나타내는 클래스 멤버는 <xref:System.Double.NaN>, <xref:System.Double.PositiveInfinity>, 또는 <xref:System.Double.NegativeInfinity>피제수에 따라 합니다. 다음 표에서 나누기의 다양 한 결과 요약 한 `Double` 값을 0으로 합니다.  
  
|피제수 데이터 형식|제 수 데이터 형식|피제수 값|결과|  
|---|---|---|---|  
|`Double`|`Double`|0|<xref:System.Double.NaN>(수학적으로 정의 된 숫자가 아님)|  
|`Double`|`Double`|> 0|<xref:System.Double.PositiveInfinity>|  
|`Double`|`Double`|\< 0|<xref:System.Double.NegativeInfinity>|  
  
 Catch 하는 <xref:System.DivideByZeroException> 예외를 처리할 수 있도록 해당 멤버를 사용할 수 있습니다. 예를 들어는 <xref:System.Exception.Message%2A> 속성 예외에 대 한 메시지 텍스트를 저장 합니다. 자세한 내용은 [Try...Catch...Finally 문](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)을 참조하세요.  
  
## <a name="bit-shift-operations"></a>비트 시프트 연산  
 비트 시프트 작업과 비트 패턴에 산술 시프트를 수행 합니다. 오른쪽의 피연산자는 패턴을 이동할 위치 수를 지정 하는 동안 패턴 왼쪽의 피연산자에 포함 되어 있습니다. 오른쪽에는 패턴을 이동할 수 있습니다는 [>> 연산자](../../../../visual-basic/language-reference/operators/right-shift-operator.md) 또는 왼쪽에는 [<< 연산자](../../../../visual-basic/language-reference/operators/left-shift-operator.md)합니다.  
  
 패턴 피연산자의 데이터 형식 이어야 합니다 `SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, 또는 `ULong`합니다. 시프트 횟수 피연산자의 데이터 형식은 이어야 `Integer` 으로 확장 되어야 또는 `Integer`합니다.  
  
 이동 하는 산술 형식 이므로 하지 순환, 결과의 한쪽 끝에서 이동 하는 비트는 다른 쪽 끝에서 다시 도입 되지 않습니다. 이동 후 비워진 비트 위치는 다음과 같이 설정 됩니다.  
  
-   산술 왼쪽된 시프트에 대 한 0  
  
-   양수의 산술 오른쪽 시프트에 대 한 0  
  
-   부호 없는 데이터 형식에 산술 오른쪽 시프트에 대 한 0 (`Byte`, `UShort`, `UInteger`, `ULong`)  
  
-   음수 숫자의 산술 오른쪽 시프트에 대 한 1 (`SByte`, `Short`, `Integer`, 또는 `Long`)  
  
 다음 예제에서는 이동는 `Integer` 값을 왼쪽 및 오른쪽입니다.  
  
 [!code-vb[VbVbalrOperators#64](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/arithmetic-operators_8.vb)]  
  
 이동 하는 산술 오버플로 예외를 생성 하지 않습니다.  
  
## <a name="bitwise-operations"></a>비트 연산  
 논리 연산자로 사용 될 뿐 아니라 `Not`, `Or`, `And`, 및 `Xor` 비트 연산도 숫자 값에 사용할 때 수행 됩니다. 자세한 내용은의 "비트 작업" 참조 [논리 및 비트 Visual Basic의 연산자](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)합니다.  
  
## <a name="type-safety"></a>형식 안전성  
 피연산자는 일반적으로 같은 형식 이어야 합니다. 예를 들어, 추가 하는 경우는 `Integer` 변수를 추가 해야 다른 `Integer` 변수에 결과 형식의 변수를 할당 해야 `Integer` 도 합니다.  
  
 형식이 안전한 되도록 한 가지 방법은 코딩 사례 사용 하는 것은 [Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md)합니다. 설정한 경우 `Option Strict On`, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 자동으로 수행 *형식이 안전한* 변환 합니다. 추가 하려는 경우 등는 `Integer` 변수를 한 `Double` 변수 값을 할당 하 고는 `Double` 변수, 작업을 정상적으로 진행 되므로 `Integer` 값을 변환할 수 `Double` 데이터 손실 없이 합니다. 변환의 형식이 안전 하지 않은 경우에 반면에으로 컴파일러 오류가 발생 `Option Strict On`합니다. 추가 하려는 경우 등는 `Integer` 변수를 `Double` 변수 값을 할당 하 고는 `Integer` 변수, 컴파일러 오류가 발생 한 `Double` 변수 형식으로 암시적으로 변환 될 수 없습니다 `Integer`합니다.  
  
 설정한 경우 `Option Strict Off`그러나 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 암시적 축소 변환을 수행 하면 허용 예기치 않은 데이터 또는 정밀도 손실을 초래할 수 있습니다. 이러한 이유로 사용 하는 권장 `Option Strict On` 프로덕션 코드를 작성할 때. 자세한 내용은 [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [산술 연산자](../../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [비트 시프트 연산자](../../../../visual-basic/language-reference/operators/bit-shift-operators.md)  
 [Visual Basic의 비교 연산자](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)  
 [Visual Basic의 연결 연산자](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)  
 [Visual Basic의 논리 및 비트 연산자](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)  
 [연산자의 효율적 결합](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/efficient-combination-of-operators.md)
