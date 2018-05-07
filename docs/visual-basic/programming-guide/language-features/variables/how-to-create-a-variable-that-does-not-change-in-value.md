---
title: '방법: 값이 변경되지 않는 변수 만들기(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], read-only
- variables [Visual Basic], constant value
ms.assetid: 86b59266-25df-4635-ae15-9b59c411d036
ms.openlocfilehash: d63c254abe6d12c094e0d1252c9721f668947f09
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-variable-that-does-not-change-in-value-visual-basic"></a>방법: 값이 변경되지 않는 변수 만들기(Visual Basic)
해당 값이 변경 되지 않는 변수 개념 모순 되 게 나타날 수 있습니다. 하지만 상황이 발생 하는 상수 작업이 불가능 하 고 변수 고정된 값을 사용 하는 것이 유용 합니다. 이러한 경우에 사용 하 여 멤버 변수를 정의할 수 있습니다는 [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) 키워드입니다.  
  
 사용할 수 없습니다는 [Const 문을](../../../../visual-basic/language-reference/statements/const-statement.md) 선언 하 고 다음과 같은 경우 상수 값을 할당 합니다.  
  
-   `Const` 문에서 사용 하려는 데이터 형식을 허용 하지 않는  
  
-   컴파일 타임에 값을 알지 못합니다  
  
-   컴파일 타임에 상수 값을 계산할 수 없습니다  
  
### <a name="to-create-a-variable-that-does-not-change-in-value"></a>값에서 변경 되지 않는 변수를 만들려면  
  
1.  모듈 수준에서 멤버 변수를 선언에서 [Dim 문](../../../../visual-basic/language-reference/statements/dim-statement.md), 포함 하 고는 [ReadOnly](../../../../visual-basic/language-reference/modifiers/readonly.md) 키워드입니다.  
  
    ```  
    Dim ReadOnly timeStarted  
    ```  
  
     지정할 수 있습니다 `ReadOnly` 멤버 변수에 대해서만 합니다. 즉, 기존 프로시저 외부의 모듈 수준에서 변수를 정의 해야 합니다.  
  
2.  컴파일 타임에 하나의 문에서 값을 계산할 수 있으면에 초기화 절을 사용 합니다.는 `Dim` 문. 에 따라는 [으로](../../../../visual-basic/language-reference/statements/as-clause.md) 등호로 절 (`=`) 식 옵니다. 컴파일러에는 상수 값이 식을 계산할 수 있어야 합니다.  
  
    ```  
    Dim ReadOnly timeStarted As Date = Now  
    ```  
  
     값을 할당할 수는 `ReadOnly` 변수 한 번만 합니다. 이렇게 하면 코드가 해당 값을 변경할 수 있습니다.  
  
     컴파일 타임에 값을 알지 못하는 하거나 단일 문에서 컴파일 타임에 계산할 수 없는 경우에 생성자에서 런타임 시 여전히 할당할 수 있습니다. 이 작업을 수행 하려면 해당 선언 해야는 `ReadOnly` 클래스 또는 구조 수준에서 변수입니다. 해당 클래스 또는 구조체에 대 한 생성자에서 변수의 고정된 값을 계산 하 고 생성자에서 반환 하기 전에를 변수에 할당 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [WriteOnly](../../../../visual-basic/language-reference/modifiers/writeonly.md)  
 [Const 문](../../../../visual-basic/language-reference/statements/const-statement.md)
