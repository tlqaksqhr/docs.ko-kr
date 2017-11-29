---
title: "연산자 결과의 데이터 형식(Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- data types [Visual Basic], operator result data types
- result data types [Visual Basic]
- operator result data types [Visual Basic]
- operators [Visual Basic], data types
- data types [Visual Basic], ranges
- operators [Visual Basic], result data types
ms.assetid: 9d524533-e1a1-4aa8-b1b8-622068173d06
caps.latest.revision: "27"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 61e8fb785830152acfd7e8e2e1784294053ac66e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="data-types-of-operator-results-visual-basic"></a>연산자 결과의 데이터 형식(Visual Basic)
[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]피연산자의 데이터 형식을 기반으로 하는 작업의 결과 데이터 형식을 결정 합니다. 경우에 따라이 데이터 형식으로 범위는 두 피연산자의 보다 클 수 있습니다.  
  
## <a name="data-type-ranges"></a>데이터 형식 범위  
 순서에서 가장 작은 가장 큰, 관련 데이터 형식의 범위는 다음과 같습니다.  
  
-   [부울](../../../visual-basic/language-reference/data-types/boolean-data-type.md) -두 개의 가능한 값  
  
-   [SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [바이트](../../../visual-basic/language-reference/data-types/byte-data-type.md) -256 개 정수 계열 값  
  
-   [짧은](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md) -65536 (6.5 … E + 4) 가능한 정수 계열 값  
  
-   [정수](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md) -4294967296 (4.2 … E + 9) 가능한 정수 계열 값  
  
-   [긴](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md) -18446744073709551615 (1.8 … E + 19) 가능한 정수 계열 값  
  
-   [10 진수](../../../visual-basic/language-reference/data-types/decimal-data-type.md) -1.5 … E + 29 가능한 정수 계열 값을 최대 범위 7.9... + 28 (절대 값)  
  
-   [단일](../../../visual-basic/language-reference/data-types/single-data-type.md) -최대 범위 3.4 … E + 38 (절대 값)  
  
-   [이중](../../../visual-basic/language-reference/data-types/double-data-type.md) -최대 범위 1.7-E + 308 (절대 값)  
  
 대 한 자세한 내용은 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 데이터 형식을 참조 [데이터 형식](../../../visual-basic/language-reference/data-types/data-type-summary.md)합니다.  
  
 피연산자를 [Nothing](../../../visual-basic/language-reference/nothing.md), [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 산술 연산자 0으로 처리 합니다.  
  
## <a name="decimal-arithmetic"></a>10 진수 산술 연산  
 [10 진수](../../../visual-basic/language-reference/data-types/decimal-data-type.md) 데이터 형식이 부동 소수점 또는 정수입니다.  
  
 하는 경우의 피연산자는 `+`, `–`, `*`, `/`, 또는 `Mod` 작업이 `Decimal` 하나도 및 `Single` 또는 `Double`, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 에다른피연산자확장`Decimal`. 동작을 수행 `Decimal`, 고 결과 데이터 형식이 `Decimal`합니다.  
  
## <a name="floating-point-arithmetic"></a>부동 소수점 산술 연산  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]대부분 부동 소수점 산술 연산 수행 [Double](../../../visual-basic/language-reference/data-types/double-data-type.md), 이러한 연산에 입력 하는 가장 효율적인 데이터 인 합니다. 그러나 한 피연산자가 [단일](../../../visual-basic/language-reference/data-types/single-data-type.md) 하나도 및 `Double`, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 에 작업을 수행 `Single`합니다. 적절 한 데이터 형식 작업 전에 필요에 따라 각 피연산자를 확장 하며 결과 데이터 형식에 해당 합니다.  
  
### <a name="-and--operators"></a>/ 및 ^ 연산자  
 `/` 연산자에 대해서만 정의 되는 [10 진수](../../../visual-basic/language-reference/data-types/decimal-data-type.md), [단일](../../../visual-basic/language-reference/data-types/single-data-type.md), 및 [Double](../../../visual-basic/language-reference/data-types/double-data-type.md) 데이터 형식입니다. [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]연산 및 결과 해당 데이터 형식을 적절 한 데이터 형식으로 필요에 따라 각 피연산자를 확장 합니다.  
  
 다음 표에서 결과 대 한 데이터 형식에서 `/` 연산자입니다. 이 테이블은 대칭; 조합은 피연산자 데이터 형식에 대 한 결과 데이터 형식은 피연산자의 순서에 관계 없이 같습니다.  
  
||||||  
|---|---|---|---|---|  
||`Decimal`|`Single`|`Double`|정수 계열 형식|  
|`Decimal`|Decimal|Single|Double|Decimal|  
|`Single`|Single|Single|Double|Single|  
|`Double`|Double|Double|Double|Double|  
|정수 계열 형식|Decimal|Single|Double|Double|  
  
 `^` 연산자에 대해서만 정의 되는 `Double` 데이터 형식입니다. [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]필요에 따라 각 피연산자 확장 `Double` 작업과 데이터 형식이 항상 결과 하기 전에 `Double`합니다.  
  
## <a name="integer-arithmetic"></a>정수 연산  
 정수 연산 결과 데이터 형식 피연산자의 데이터 형식에 따라 달라 집니다. 일반적으로 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 결과 데이터 형식을 결정 하기 위해 다음 정책을 사용 하 여:  
  
-   이항 연산자의 피연산자가 모두 같으면 결과 데이터 형식, 해당 데이터 형식입니다. 예외는 `Boolean`를 강제 적용할 `Short`합니다.  
  
-   부호 있는 피연산자와 함께 참여 하는 부호 없는 피연산자 인 경우 결과 부호 있는 형식으로 큰 이상 범위 피연산자 중 하나가으로.  
  
-   그렇지 않으면 결과 일반적으로 두 개의 피연산자 데이터 형식 중 더 큰 숫자를 있습니다.  
  
 Note 결과 데이터 형식은 두 피연산자 데이터 형식으로 동일할 수 없습니다 있습니다.  
  
> [!NOTE]
>  결과 데이터 형식은 항상 작업에서으로 인해 발생 하는 모든 가능한 값을 보유할 수 있을 만큼 큰 것은 아닙니다. <xref:System.OverflowException> 값이 너무 커서 결과 데이터 형식에 대 한 예외가 발생할 수 있습니다.  
  
### <a name="unary--and--operators"></a>단항 + 및-연산자  
 다음 표에서 결과 데이터 형식을 보여 줍니다 단항 연산자에 대 한 `+` 및 `–`합니다.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|단항`+`|Short|SByte|Byte|Short|UShort|정수|UInteger|Long|ULong|  
|단항`–`|Short|SByte|Short|Short|정수|정수|Long|Long|Decimal|  
  
### <a name="-and--operators"></a><\<및 >> 연산자  
 다음 표에서 결과 데이터 형식을 보여 줍니다 두 비트 시프트 연산자에 대 한 `<<` 및 `>>`합니다. [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]각 비트 시프트 연산자의 왼쪽된 피연산자 (이동 비트 패턴)에 단항 연산자 구조체로 처리 합니다.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`<<`, `>>`|Short|SByte|Byte|Short|UShort|정수|UInteger|Long|ULong|  
  
 왼쪽된 피연산자가 `Decimal`, `Single`, `Double`, 또는 `String`, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 를 변환 하기 `Long` 작업과 데이터 형식이 결과 하기 전에 `Long`합니다. 오른쪽 피연산자 (이동할 비트 위치 수) `Integer` 또는로 확대 되는 형식의 `Integer`합니다.  
  
### <a name="binary----and-mod-operators"></a>이진 +,-, *, 및 Mod 연산자  
 다음 표에 나와 결과 이진에 대 한 데이터 형식을 `+` 및 `–` 연산자와 `*` 및 `Mod` 연산자입니다. 이 테이블은 대칭; 조합은 피연산자 데이터 형식에 대 한 결과 데이터 형식은 피연산자의 순서에 관계 없이 같습니다.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Boolean`|Short|SByte|Short|Short|정수|정수|Long|Long|Decimal|  
|`SByte`|SByte|SByte|Short|Short|정수|정수|Long|Long|Decimal|  
|`Byte`|Short|Short|Byte|Short|UShort|정수|UInteger|Long|ULong|  
|`Short`|Short|Short|Short|Short|정수|정수|Long|Long|Decimal|  
|`UShort`|정수|정수|UShort|정수|UShort|정수|UInteger|Long|ULong|  
|`Integer`|정수|정수|정수|정수|정수|정수|Long|Long|Decimal|  
|`UInteger`|Long|Long|UInteger|Long|UInteger|Long|UInteger|Long|ULong|  
|`Long`|Long|Long|Long|Long|Long|Long|Long|Long|Decimal|  
|`ULong`|Decimal|Decimal|ULong|Decimal|ULong|Decimal|ULong|Decimal|ULong|  
  
### <a name="-operator"></a>\ 연산자  
 다음 표에서 결과 대 한 데이터 형식에서 `\` 연산자입니다. 이 테이블은 대칭; 조합은 피연산자 데이터 형식에 대 한 결과 데이터 형식은 피연산자의 순서에 관계 없이 같습니다.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Boolean`|Short|SByte|Short|Short|정수|정수|Long|Long|Long|  
|`SByte`|SByte|SByte|Short|Short|정수|정수|Long|Long|Long|  
|`Byte`|Short|Short|Byte|Short|UShort|정수|UInteger|Long|ULong|  
|`Short`|Short|Short|Short|Short|정수|정수|Long|Long|Long|  
|`UShort`|정수|정수|UShort|정수|UShort|정수|UInteger|Long|ULong|  
|`Integer`|정수|정수|정수|정수|정수|정수|Long|Long|Long|  
|`UInteger`|Long|Long|UInteger|Long|UInteger|Long|UInteger|Long|ULong|  
|`Long`|Long|Long|Long|Long|Long|Long|Long|Long|Long|  
|`ULong`|Long|Long|ULong|Long|ULong|Long|ULong|Long|ULong|  
  
 하는 경우의 피연산자는 `\` 연산자는 [10 진수](../../../visual-basic/language-reference/data-types/decimal-data-type.md), [단일](../../../visual-basic/language-reference/data-types/single-data-type.md), 또는 [Double](../../../visual-basic/language-reference/data-types/double-data-type.md), [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 를 변환 하기 [장기](../../../visual-basic/language-reference/data-types/long-data-type.md) 작업과 데이터 형식이 결과 하기 전에 `Long`합니다.  
  
## <a name="relational-and-bitwise-comparisons"></a>관계 및 비트 비교  
 관계형 작업의 결과 데이터 형식 (`=`, `<>`, `<`, `>`, `<=`, `>=`)은 항상 `Boolean` [Boolean 데이터 형식](../../../visual-basic/language-reference/data-types/boolean-data-type.md)합니다. 논리 연산자에도 마찬가지입니다 (`And`, `AndAlso`, `Not`, `Or`, `OrElse`, `Xor`)에 `Boolean` 피연산자.  
  
 비트 논리 작업의 결과 데이터 형식 피연산자의 데이터 형식에 따라 달라 집니다. `AndAlso` 및 `OrElse` 에 대해서만 정의 `Boolean`, 및 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 필요에 따라 각 피연산자를 변환 `Boolean` 작업을 수행 하기 전에.  
  
### <a name="-----and--operators"></a>=, <>, \<, >, \<= 및 > = 연산자  
 피연산자가 모두 경우 `Boolean`, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 고려 `True` 되도록 미만 `False`합니다. 숫자 형식을와 비교 하는 경우는 `String`, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 변환 하려고 시도 `String` 를 `Double` 작업 전에 합니다. A `Char` 또는 `Date` 피연산자는 동일한 데이터 형식이 다른 피연산자와만 비교할 수 있습니다. 결과 데이터 형식이 항상 `Boolean`합니다.  
  
### <a name="bitwise-not-operator"></a>비트 Not 연산자  
 다음 표에 나와 결과 데이터 형식에 대 한 비트 `Not` 연산자입니다.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Not`|부울|SByte|Byte|Short|UShort|정수|UInteger|Long|ULong|  
  
 피연산자가 `Decimal`, `Single`, `Double`, 또는 `String`, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 를 변환 하기 `Long` 작업과 데이터 형식이 결과 하기 전에 `Long`합니다.  
  
### <a name="bitwise-and-or-and-xor-operators"></a>비트를 또는 및 Xor 연산자  
 다음 표에 나와 결과 데이터 형식에 대 한 비트 `And`, `Or`, 및 `Xor` 연산자입니다. 이 테이블은 대칭; 조합은 피연산자 데이터 형식에 대 한 결과 데이터 형식은 피연산자의 순서에 관계 없이 같습니다.  
  
|||||||||||  
|---|---|---|---|---|---|---|---|---|---|  
||`Boolean`|`SByte`|`Byte`|`Short`|`UShort`|`Integer`|`UInteger`|`Long`|`ULong`|  
|`Boolean`|부울|SByte|Short|Short|정수|정수|Long|Long|Long|  
|`SByte`|SByte|SByte|Short|Short|정수|정수|Long|Long|Long|  
|`Byte`|Short|Short|Byte|Short|UShort|정수|UInteger|Long|ULong|  
|`Short`|Short|Short|Short|Short|정수|정수|Long|Long|Long|  
|`UShort`|정수|정수|UShort|정수|UShort|정수|UInteger|Long|ULong|  
|`Integer`|정수|정수|정수|정수|정수|정수|Long|Long|Long|  
|`UInteger`|Long|Long|UInteger|Long|UInteger|Long|UInteger|Long|ULong|  
|`Long`|Long|Long|Long|Long|Long|Long|Long|Long|Long|  
|`ULong`|Long|Long|ULong|Long|ULong|Long|ULong|Long|ULong|  
  
 한 피연산자가 `Decimal`, `Single`, `Double`, 또는 `String`, [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 를 변환 하기 `Long` 하기 전에 작업을 하 고 결과 데이터 형식이 동일 해당 피연산자가 이미 마치 `Long`합니다.  
  
## <a name="miscellaneous-operators"></a>기타 연산자  
 `&` 의 연결에 대 한 연산자가 정의 `String` 피연산자. [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]필요에 따라 각 피연산자를 변환 `String` 작업과 데이터 형식이 항상 결과 하기 전에 `String`합니다. 목적에 대 한는 `&` 연산자, 모든 변환을 `String` 확장 될 것으로 간주 됩니다 경우에 `Option Strict` 은 `On`합니다.  
  
 `Is` 및 `IsNot` 연산자는 두 피연산자는 참조 형식이 되도록 해야 합니다. `TypeOf`... `Is` 식에서는 첫 번째 피연산자는 참조 형식 이어야 하 고 데이터 형식의 이름으로 두 번째 피연산자에 필요 합니다. 이러한 모든 경우의 결과 데이터 형식이 `Boolean`합니다.  
  
 `Like` 의 패턴 일치에 대해서만 연산자가 정의 `String` 피연산자. [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]필요에 따라 각 피연산자를 변환 하려고 `String` 작업 전에 합니다. 결과 데이터 형식이 항상 `Boolean`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [데이터 형식](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [연산자 및 식](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)  
 [Visual Basic의 산술 연산자](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)  
 [Visual Basic의 비교 연산자](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)  
 [연산자](../../../visual-basic/language-reference/operators/index.md)  
 [Visual Basic에서의 연산자 우선 순위](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [기능별 연산자 목록](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [산술 연산자](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [비교 연산자](../../../visual-basic/language-reference/operators/comparison-operators.md)  
 [Option Strict 문](../../../visual-basic/language-reference/statements/option-strict-statement.md)
