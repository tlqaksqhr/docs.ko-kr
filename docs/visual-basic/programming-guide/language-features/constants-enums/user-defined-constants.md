---
title: "User-Defined Constants (Visual Basic) | Microsoft Docs"
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
  - "constants, circular references"
  - "Const statement [Visual Basic], user-defined constants"
  - "user-defined constants"
  - "scope, constants"
  - "constants, user-defined"
  - "circular references between constants"
ms.assetid: a1206d5c-c45e-4ac2-970a-4a0be6a05fdd
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# User-Defined Constants (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

상수는 숫자나 문자열 대신 사용되며 변경되지 않는 의미 있는 이름입니다.  상수는 이름이 의미하는 것처럼 응용 프로그램을 실행하는 동안 일정하게 유지되는 값을 저장합니다.  작업하는 컨트롤 또는 구성 요소에 의해 정의되는 상수를 사용하거나 직접 상수를 만들 수 있습니다.  사용자가 직접 만든 상수를 *사용자 정의* 상수라고 합니다.  
  
 변수 이름을 만들 때와 같은 방법으로 `Const` 문을 사용하여 상수를 선언합니다.  `Option Strict`가 `On`이면 상수 형식을 명시적으로 선언해야 합니다.  
  
## Const 문 사용법  
 `Const` 문은 수치 또는 날짜\/시간 값을 나타낼 수 있습니다.  
  
 [!code-vb[VbEnumsTask#10](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_1.vb)]  
  
 `String` 상수를 정의할 수도 있습니다.  
  
 [!code-vb[VbEnumsTask#13](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_2.vb)]  
  
 등호\(`=`\)의 오른쪽에 있는 식은 종종 숫자 또는 리터럴 문자열이지만 결과 값이 숫자나 문자열인 식이 될 수도 있습니다\(식에 함수 호출이 포함될 수는 없음\).  이전에 정의한 상수로 상수를 정의할 수도 있습니다.  
  
 [!code-vb[VbEnumsTask#15](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_3.vb)]  
  
## 사용자 정의 상수의 범위  
 `Const` 문의 범위는 동일한 위치에 선언된 변수의 범위와 같습니다.  다음과 같은 방법으로 상수의 범위를 지정할 수 있습니다.  
  
-   프로시저 내에만 존재하는 상수를 만들려면 해당 프로시저 내에 상수를 선언합니다.  
  
-   클래스 내의 모든 프로시저에 사용할 수 있지만 해당 모듈 외부의 코드에는 사용할 수 없는 상수를 만들려면 클래스의 선언 섹션에서 상수를 선언합니다.  
  
-   어셈블리의 모든 멤버에 사용할 수 있지만 해당 어셈블리의 클라이언트 외부에는 사용할 수 없는 상수를 만들려면 클래스의 선언 섹션에서 `Friend` 키워드를 사용하여 상수를 선언합니다.  
  
-   응용 프로그램 전체에서 사용할 수 있는 상수를 만들려면 클래스의 선언 섹션에서 `Public` 키워드를 사용하여 상수를 선언합니다.  
  
 자세한 내용은 [How to: Declare A Constant](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)을 참조하십시오.  
  
### 순환 참조 방지  
 다른 상수에 의해 상수를 정의할 수 있으므로 둘 이상의 상수 사이에 실수로 *주기* 또는 순환 참조를 만들 수 있습니다.  주기는 다음 예제와 같이 각각 서로에 의해 정의되는 둘 이상의 공용 상수를 사용하는 경우 일어납니다.  
  
 [!code-vb[VbEnumsTask#16](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_4.vb)]  
[!code-vb[VbEnumsTask#17](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_5.vb)]  
  
 주기가 발생하면 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서 컴파일러 오류를 생성합니다.  
  
## 참고 항목  
 [Const Statement](../../../../visual-basic/language-reference/statements/const-statement.md)   
 [Constant and Literal Data Types](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)   
 [Constants and Enumerations](../../../../visual-basic/programming-guide/language-features/constants-enums/index.md)   
 [Constants and Enumerations](../../../../visual-basic/language-reference/constants-and-enumerations.md)   
 [Enumerations Overview](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)   
 [Constants Overview](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)   
 [How to: Declare an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)   
 [Enumerations and Name Qualification](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)   
 [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)