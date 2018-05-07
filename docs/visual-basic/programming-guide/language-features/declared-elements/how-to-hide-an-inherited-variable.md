---
title: '방법: 상속된 변수 숨기기(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- qualification [Visual Basic], of element names
- element names [Visual Basic], qualification
- references [Visual Basic], declared elements
- declaration statements [Visual Basic], declared elements
- referencing declared elements [Visual Basic]
- declared elements [Visual Basic], referencing
- declared elements [Visual Basic], about declared elements
- variables [Visual Basic], hiding inherited
ms.assetid: 765728d9-7351-4a30-999d-b5f34f024412
ms.openlocfilehash: c59fdd8c6c6d2444b8d687c78c61f4e0d4bf9a52
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-hide-an-inherited-variable-visual-basic"></a>방법: 상속된 변수 숨기기(Visual Basic)
파생된 클래스는 기본 클래스의 모든 정의 상속합니다. 기본 클래스의 요소와 동일한 이름을 사용 하는 변수를 정의 하려는 경우 숨길 수 있습니다, 또는 *그림자*, 파생된 클래스에서 변수를 정의할 때 해당 기본 클래스 요소입니다. 이 작업을 수행 하는 경우 파생된 클래스에서 코드 숨김 메커니즘을 명시적으로 무시 하지 않는 한 변수를 액세스 합니다.  
  
 기본 클래스가 수정 으로부터 보호 하기 위해 상속된 된 변수 숨기기 하려는 하는 다른 이유가입니다. 기본 클래스를 상속 하는 요소를 변경 하는 변경을 받을 수 있습니다. 이런 경우는 `Shadows` 한정자를 사용 하면 기본 클래스 요소 대신으로 변수를 확인 하려면 파생된 클래스에서 참조 합니다.  
  
### <a name="to-hide-an-inherited-variable"></a>상속된 된 변수를 숨기려면  
  
1.  숨기려는 변수가 프로시저) (외부 클래스 수준에서 선언 해야 합니다. 그렇지 않으면 머리글과 바닥글을 숨길 필요가 없습니다.  
  
2.  파생된 클래스 안에 작성 한 [Dim 문](../../../../visual-basic/language-reference/statements/dim-statement.md) 변수를 선언 합니다. 상속 된 변수의 것과 동일한 이름을 사용 합니다.  
  
3.  포함 된 [그림자](../../../../visual-basic/language-reference/modifiers/shadows.md) 키워드를 선언에 있습니다.  
  
     변수 이름에도 다른 여러 가지 파생된 클래스에서 코드를 참조 하는 경우 컴파일러에서 사용자 변수에 대 한 참조를 확인 합니다.  
  
     다음 예제에서는 상속 된 변수 숨기기  
  
    ```  
    Public Class shadowBaseClass  
        Public shadowString As String = "This is the base class string."  
    End Class  
    Public Class shadowDerivedClass  
        Inherits shadowBaseClass  
        Public Shadows shadowString As String = "This is the derived class string."  
        Public Sub showStrings()  
            Dim s As String = "Unqualified shadowString: " & shadowString &  
                vbCrLf & "MyBase.shadowString: " & MyBase.shadowString  
            MsgBox(s)  
        End Sub  
    End Class  
    ```  
  
     위 예제에서는 변수를 선언 `shadowString` 기본 클래스에서 파생된 클래스에서이 숨깁니다. 프로시저 `showStrings` 파생된 클래스에서 문자열의 숨김 버전을 표시 때 이름 `shadowString` 한정 되지 않습니다. 다음 숨겨진된 버전을 표시 때 `shadowString` 으로 한정 되는 `MyBase` 키워드입니다.  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 섀도잉 동일한 이름 가진 변수 둘 이상의 버전을 도입 되었습니다. 코드 문이 변수 이름에는 참조, 컴파일러 참조를 확인 하는 버전 문 코드의 위치 및 한정 문자열이 있는지 여부 등의 요인에 따라 달라 집니다. 의도 하지 않은 버전의 숨겨진된 변수에 참조 위험이 높아질 수 있습니다이 합니다. 숨겨진된 변수에 대 한 모든 참조를 정규화 하 여 위험을 줄일 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [선언된 요소 참조](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [Visual Basic의 숨김 기능](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)  
 [숨기기와 재정의의 차이점](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)  
 [방법: 이름이 같은 변수 숨기기](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)  
 [방법: 파생 클래스에 의해 숨겨진 변수에 액세스](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)  
 [재정의](../../../../visual-basic/language-reference/modifiers/overrides.md)  
 [Me, My, MyBase 및 MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 [상속 기본 사항](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
