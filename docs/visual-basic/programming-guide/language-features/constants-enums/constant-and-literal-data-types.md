---
title: 상수 및 리터럴 데이터 형식(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declaring constants [Visual Basic], literal data types
- data types [Visual Basic], declaring
- constants [Visual Basic], declaring
- explicit declarations
- literals [Visual Basic], coercing data type
- declarations [Visual Basic], data types
ms.assetid: 057206d2-3a5b-40b9-b3af-57446f9b52fa
ms.openlocfilehash: 8d110ec17bcdb03f339d779b2950ba56d77957cc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649850"
---
# <a name="constant-and-literal-data-types-visual-basic"></a>상수 및 리터럴 데이터 형식(Visual Basic)
리터럴은 변수의 값 또는 3 숫자 또는 문자열 "Hello"와 같은 식의 결과가 아닌 자체로 표시 되는 값입니다. 상수는 리터럴 대신 하며 값 변경 될 수 있습니다 변수와 달리 프로그램 전체이 동일한 값을 유지 하는 의미 있는 이름을.  
  
 때 [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) 은 `Off` 및 [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) 은 `On`, 데이터 형식으로 모든 상수를 명시적으로 선언 해야 합니다. 다음 예제에서는 데이터의 형식 `MyByte` 데이터 형식으로 명시적 선언 된 `Byte`:  
  
 [!code-vb[VbVbalrConstants#1](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_1.vb)]  
  
 때 `Option Infer` 은 `On` 또는 `Option Strict` 은 `Off`, 데이터 형식으로 지정 하지 않고 상수를 선언할 수 있습니다는 `As` 절. 컴파일러에는 상수 식의 형식에서의 유형을 결정합니다. 기본적으로 숫자 정수 리터럴은 캐스팅 되는 `Integer` 데이터 형식입니다. 부동 소수점 숫자 기본 데이터 형식 `Double`, 키워드 및 `True` 및 `False` 지정는 `Boolean` 상수입니다.  
  
## <a name="literals-and-type-coercion"></a>리터럴 및 형식 강제 변환  
 특정 데이터 형식; 리터럴을 적용 하려는 경우에 따라 예를 들어 매우 큰 정수 리터럴 값 형식의 변수에 할당할 때 `Decimal`합니다. 다음 예에서는 오류가 발생 합니다.  
  
```  
Dim myDecimal as Decimal  
myDecimal = 100000000000000000000   ' This causes a compiler error.  
```  
  
 리터럴 표현에서 오류가 발생 합니다. `Decimal` 데이터 형식을 큰 값을 보유할 수 있지만 리터럴으로 암시적으로 표시 되는 `Long`, 수는 없습니다.  
  
 두 가지 방법으로 특정 데이터 형식에는 리터럴 강제 변환할 수 있습니다: 형식 문자를를 추가 하거나 묶기 문자 안에 배치 하 여 합니다. 형식 문자 또는 문자를 포함 해야 즉시 리터럴 앞 이나 뒤에서, 공백이 나 어떤 종류의 문자 없이 합니다.  
  
 이전 예제가 제대로 실행 되도록 하려면 추가 하는 `D` 형식으로 나타낼 수를 발생 시키는 리터럴 문자는 `Decimal`:  
  
 [!code-vb[VbVbalrConstants#2](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_2.vb)]  
  
 다음 예제에서는 형식 문자와 바깥쪽 변수의 올바른 사용법을 보여 줍니다.  
  
 [!code-vb[VbVbalrConstants#3](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_3.vb)]  
  
 다음 표에 나와 바깥쪽 문자 및 Visual Basic에서 사용할 수 있는 형식 문자.  
  
|데이터 형식|구분 기호|추가 된 형식 문자|  
|---|---|---|  
|`Boolean`|(없음)|(없음)|  
|`Byte`|(없음)|(없음)|  
|`Char`|"|C|  
|`Date`|#|(없음)|  
|`Decimal`|(없음)|D 또는 @|  
|`Double`|(없음)|R 또는 #|  
|`Integer`|(없음)|I 또는 %|  
|`Long`|(없음)|L 또는 &|  
|`Short`|(없음)|S|  
|`Single`|(없음)|F 또는!|  
|`String`|"|(없음)|  
  
## <a name="see-also"></a>참고 항목  
 [사용자 정의 상수](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md)  
 [방법: 상수 선언](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)  
 [상수 개요](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)  
 [Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [Option Explicit 문](../../../../visual-basic/language-reference/statements/option-explicit-statement.md)  
 [열거형 개요](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)  
 [방법: 열거형 선언](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)  
 [열거형 및 이름 한정](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)  
 [데이터 형식](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [상수 및 열거형](../../../../visual-basic/language-reference/constants-and-enumerations.md)
