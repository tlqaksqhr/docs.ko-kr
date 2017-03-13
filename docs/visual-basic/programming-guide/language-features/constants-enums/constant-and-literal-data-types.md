---
title: "Constant and Literal Data Types (Visual Basic) | Microsoft Docs"
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
  - "declaring constants, literal data types"
  - "data types [Visual Basic], declaring"
  - "constants, declaring"
  - "explicit declarations"
  - "literals, coercing data type"
  - "declarations, data types"
ms.assetid: 057206d2-3a5b-40b9-b3af-57446f9b52fa
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# Constant and Literal Data Types (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

리터럴은 변수의 값이나 식의 결과로 표현되는 것이 아니라 숫자 3이나 문자열 "Hello"와 같이 있는 그대로 표현되는 값입니다.  상수는 리터럴 대신 사용되어 프로그램 전체에서 이 동일한 값을 유지하는 의미 있는 이름으로, 변수와 달리 값을 변경할 수 있습니다.  
  
 [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md)가 `Off`이고 [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)가 `On`인 경우 모든 상수를 데이터 형식을 사용하여 명시적으로 선언해야 합니다.  다음 예제에서는 `MyByte`의 데이터 형식이 `Byte` 데이터 형식으로 명시적으로 선언되었습니다.  
  
 [!code-vb[VbVbalrConstants#1](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_1.vb)]  
  
 `Option Infer`가 `On`이거나 `Option Strict`가 `Off`인 경우 `As` 절로 데이터 형식을 지정하지 않고 상수를 선언할 수 있습니다.  컴파일러는 식의 형식에서 상수 형식을 확인합니다.  숫자 정수 리터럴은 기본적으로 `Integer` 데이터 형식으로 캐스팅됩니다.  부동 소수점 숫자의 기본 데이터 형식은 `Double`이고 `True` 및 `False` 키워드는 `Boolean` 상수를 지정합니다.  
  
## 리터럴 및 형식 강제 변환  
 경우에 따라 특정 데이터 형식에 리터럴을 강제로 적용할 수도 있습니다. 예를 들어, 매우 큰 정수 리터럴 값을 `Decimal` 형식의 변수에 할당하는 경우입니다.  다음 예제에서는 오류가 발생합니다.  
  
```  
Dim myDecimal as Decimal  
myDecimal = 100000000000000000000   ' This causes a compiler error.  
```  
  
 리터럴 표현에서 발생하는 오류입니다.  `Decimal` 데이터 형식은 이러한 큰 값을 저장할 수 있지만 리터럴은 암시적으로 큰 값을 저장할 수 없는 `Long` 형식으로 표시됩니다.  
  
 리터럴에 형식 문자를 붙이거나 리터럴을 묶기 문자 안에 넣는 두 가지 방법으로 리터럴을 특정 데이터 형식으로 강제 변환할 수 있습니다.  형식 문자나 묶기 문자는 리터럴 바로 앞이나 뒤에 붙여야 하며 공백이나 기타 문자를 삽입해서는 안 됩니다.  
  
 위 예제가 제대로 실행되도록 하려면 리터럴에 형식 문자 `D`를 추가하여 `Decimal` 형식으로 표시되도록 하십시오.  
  
 [!code-vb[VbVbalrConstants#2](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_2.vb)]  
  
 다음 예제는 형식 문자와 묶기 문자의 올바른 사용법을 보여 줍니다.  
  
 [!code-vb[VbVbalrConstants#3](../../../../visual-basic/programming-guide/language-features/constants-enums/codesnippet/VisualBasic/constant-and-literal-data-types_3.vb)]  
  
 다음 표에서는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서 사용할 수 있는 묶기 문자와 형식 문자를 보여 줍니다.  
  
||||  
|-|-|-|  
|데이터 형식|묶기 문자|추가된 형식 문자|  
|`Boolean`|\(없음\)|\(없음\)|  
|`Byte`|\(없음\)|\(없음\)|  
|`Char`|이때|C|  
|`Date`|\#|\(없음\)|  
|`Decimal`|\(없음\)|D 또는 @|  
|`Double`|\(없음\)|R 또는 \#|  
|`Integer`|\(없음\)|I 또는 %|  
|`Long`|\(없음\)|L 또는 &|  
|`Short`|\(없음\)|S|  
|`Single`|\(없음\)|F 또는 \!|  
|`String`|이때|\(없음\)|  
  
## 참고 항목  
 [User\-Defined Constants](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md)   
 [How to: Declare A Constant](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)   
 [Constants Overview](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)   
 [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [Option Explicit Statement](../../../../visual-basic/language-reference/statements/option-explicit-statement.md)   
 [Enumerations Overview](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)   
 [How to: Declare an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)   
 [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)   
 [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Constants and Enumerations](../../../../visual-basic/language-reference/constants-and-enumerations.md)