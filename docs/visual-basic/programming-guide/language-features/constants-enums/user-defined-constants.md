---
title: "사용자 정의 상수 (Visual Basic) | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- constants, circular references
- Const statement [Visual Basic], user-defined constants
- user-defined constants
- scope, constants
- constants, user-defined
- circular references between constants
ms.assetid: a1206d5c-c45e-4ac2-970a-4a0be6a05fdd
caps.latest.revision: 19
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: e5942d8663a8866b2f9794a86756f2bf25660ba5
ms.lasthandoff: 03/13/2017

---
# <a name="user-defined-constants-visual-basic"></a>사용자 정의 상수(Visual Basic)
상수는 숫자 또는 변경 되지 않는 문자열의 발생 하는 의미 있는 이름입니다. 상수 이름에서 알 수 있듯이 응용 프로그램의 실행 하는 동안 일정 하 게 유지 하는 값을 저장 합니다. 컨트롤이 나 함께 작업 하는 구성 요소에 의해 정의 된 상수를 사용할 수 또는 직접 만들 수 있습니다. 사용자가 직접 만든 상수 상수 라고 *사용자 정의*합니다.  
  
 상수를 선언에서 `Const` 문을, 변수 이름을 만들 때와 동일한 방법 사용 합니다. 경우 `Option Strict` 는 `On`, 상수 형식을 명시적으로 선언 해야 합니다.  
  
## <a name="const-statement-usage"></a>Const 문 사용  
 A `Const` 문 수 수치 나타낼 또는 날짜/시간 값:  
  
 [!code-vb[VbEnumsTask #&10;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_1.vb)]  
  
 정의할 수도 있습니다 `String` 상수:  
  
 [!code-vb[VbEnumsTask #&13;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_2.vb)]  
  
 등호 오른쪽에 있는 식 ( `=` )는 대개 숫자 또는 리터럴 문자열 하지만 결과 숫자 또는 문자열 (식에 함수 호출이 포함 될 수 없습니다) 식일 수 있습니다. 이전에 정의 된 상수를 기준으로 상수를 정의할 수도 있습니다.  
  
 [!code-vb[VbEnumsTask #&15;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_3.vb)]  
  
## <a name="scope-of-user-defined-constants"></a>사용자 정의 상수의 범위  
 A `Const` 문의 범위는 같은 위치에 선언 된 변수에 동일 합니다. 다음 방법 중 하나에서 범위를 지정할 수 있습니다.  
  
-   프로시저 내에 존재 하는 상수를 만들려면 해당 프로시저 내에서 선언 합니다.  
  
-   클래스 내의 모든 프로시저에 있지만 해당 모듈 외부 코드에 사용할 수 있는 상수를 만들려면 클래스의 선언 섹션에서 선언 합니다.  
  
-   사용 하 여 선언 된 어셈블리의 클라이언트 외부 아니라 어셈블리의 모든 구성원에 사용할 수 있는 상수를 만들려면는 `Friend` 키워드는 클래스의 선언 섹션에 있습니다.  
  
-   응용 프로그램에 걸쳐 사용할 수 있는 상수를 만들려면 사용 하 여 선언 된 `Public` 키워드는 선언에는 클래스를 섹션입니다.  
  
 자세한 내용은 참조 [하는 방법: A 상수 선언](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)합니다.  
  
### <a name="avoiding-circular-references"></a>순환 참조를 방지합니다.  
 실수로 만들 수는 다른 상수를 기준으로 상수를 정의할 수는 *주기*, 또는 두 개 이상의 상수 간의 순환 참조입니다. 주기는 다음 예제와 같이 다른 측면에서 정의 된 각 두 개 이상의 공용 상수 있을 때 발생 합니다.  
  
 [!code-vb[VbEnumsTask #&16;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_4.vb)]  
[!code-vb[VbEnumsTask #&17;](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/user-defined-constants_5.vb)]  
  
 주기가 발생 하는 경우 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 컴파일러 오류를 생성 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Const 문](../../../../visual-basic/language-reference/statements/const-statement.md)   
 [상수 및 리터럴 데이터 형식](../../../../visual-basic/programming-guide/language-features/constants-enums/constant-and-literal-data-types.md)   
 [상수 및 열거형](../../../../visual-basic/programming-guide/language-features/constants-enums/index.md)   
 [상수 및 열거형](../../../../visual-basic/language-reference/constants-and-enumerations.md)   
 [열거형 개요](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)   
 [상수 개요](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)   
 [방법: 열거형 선언](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)   
 [열거형 및 이름 한정](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)   
 [Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
