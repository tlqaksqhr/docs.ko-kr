---
title: '방법: 이름이 같은 변수 숨기기(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- qualification [Visual Basic], of element names
- declarations [Visual Basic], elements
- element names [Visual Basic], qualification
- references [Visual Basic], declared elements
- declaration statements [Visual Basic], declared elements
- declaring elements [Visual Basic]
- referencing declared elements [Visual Basic]
- declared elements [Visual Basic], referencing
- declared elements [Visual Basic], about declared elements
ms.assetid: e39c0752-f19f-4d2e-a453-00df1b5fc7ee
ms.openlocfilehash: a7ebc4eb44592800decd5ef943750f0cd845afb4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-hide-a-variable-with-the-same-name-as-your-variable-visual-basic"></a>방법: 이름이 같은 변수 숨기기(Visual Basic)
변수를 숨길 수 *섀도잉* 즉, 같은 이름의 변수로 다시 정의 하 여 합니다. 두 가지 방법으로 숨기려는 변수를 숨길 수 있습니다.  
  
-   **범위를 통한 숨김 합니다.** 숨기려는 변수가 포함 된 지역의 하위 영역 안에 다시 선언 하 여 범위를 통해 숨길 수 있습니다.  
  
-   **상속을 통한 숨김 합니다.** 숨기려는 변수가 클래스 수준에서 정의 하는 경우 숨길 수 있습니다 상속을 통해 변수가 [그림자](../../../../visual-basic/language-reference/modifiers/shadows.md) 파생된 클래스에서 키워드입니다.  
  
## <a name="two-ways-to-hide-a-variable"></a>두 가지 방법으로 변수를 숨기려면  
  
#### <a name="to-hide-a-variable-by-shadowing-it-through-scope"></a>범위를 통해 여 변수를 숨기려면  
  
1.  숨기려는 변수를 정의 하는 영역을 확인 하 고 사용자의 변수로 다시 정의 하는 하위 영역을 결정 합니다.  
  
    |변수의 영역|다시 정의할 수 있는 허용 가능한 부분 영역|  
    |-----------------------|-------------------------------------------|  
    |Module|모듈 내에서 클래스|  
    |클래스|클래스 내의 하위 클래스<br /><br /> 클래스 내의 프로시저|  
  
     예를 들어 해당 프로시저 내에 프로시저 변수를 재정의할 수 없습니다는 `If`... `End If` 생성 또는 `For` 루프입니다.  
  
2.  아직 없는 경우 하위 영역을 만듭니다.  
  
3.  하위 지역 내에서 작성 한 [Dim 문](../../../../visual-basic/language-reference/statements/dim-statement.md) 숨기는 변수를 선언 합니다.  
  
     변수 이름에 하위 지역 내에서 코드 참조, 컴파일러를 숨기는 변수에 대 한 참조를 확인 합니다.  
  
     다음 예제는 숨기기를 무시 하는 참조 뿐만 아니라 범위를 통한 숨김입니다.  
  
    ```  
    Module shadowByScope  
        ' The following statement declares num as a module-level variable.  
        Public num As Integer  
        Sub show()  
            ' The following statement declares num as a local variable.  
            Dim num As Integer  
            ' The following statement sets the value of the local variable.  
            num = 2  
            ' The following statement displays the module-level variable.  
            MsgBox(CStr(shadowByScope.num))  
        End Sub  
        Sub useModuleLevelNum()  
            ' The following statement sets the value of the module-level variable.  
            num = 1  
            show()  
        End Sub  
    End Module  
    ```  
  
     위 예제에서는 변수를 선언 `num` 프로시저 수준 및 모듈 수준 (프로시저에서 `show`). 지역 변수 `num` 모듈 수준 변수를 숨깁니다 `num` 내 `show`이므로 지역 변수가 2로 설정 됩니다. 그러나는 그림자 로컬 변수가 없으면 `num` 에 `useModuleLevelNum` 프로시저입니다. 따라서 `useModuleLevelNum` 모듈 수준 변수 값을 1로 설정 합니다.  
  
     `MsgBox` 내부에서 호출 `show` 정규화 하 여 숨김 메커니즘을 우회 `num` 모듈 이름으로 합니다. 따라서 지역 변수 대신 모듈 수준 변수를 표시 합니다.  
  
#### <a name="to-hide-a-variable-by-shadowing-it-through-inheritance"></a>상속을 통해 하 여 변수를 숨기려면  
  
1.  클래스 및 프로시저) (외부 클래스 수준에서 숨기려는 변수가 선언 해야 합니다. 그렇지 않으면 상속을 통해 숨길 수 없습니다.  
  
2.  아직 없는 경우 해당 변수의 클래스에서 파생 된 클래스를 정의 합니다.  
  
3.  파생된 클래스의 내부 쓰기는 `Dim` 문에 변수를 선언 합니다. 포함 된 [그림자](../../../../visual-basic/language-reference/modifiers/shadows.md) 키워드를 선언에 있습니다.  
  
     변수 이름에도 다른 여러 가지 파생된 클래스에서 코드를 참조 하는 경우 컴파일러에서 사용자 변수에 대 한 참조를 확인 합니다.  
  
     다음 예제에서는 상속을 통한 숨김 예제에서는 두 개의 참조, 숨기는 변수에 액세스 하 고 다른 하나는 숨기기를 무시.  
  
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
 [방법: 상속된 변수 숨기기](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)  
 [방법: 파생 클래스에 의해 숨겨진 변수에 액세스](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)  
 [재정의](../../../../visual-basic/language-reference/modifiers/overrides.md)  
 [Me, My, MyBase 및 MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 [상속 기본 사항](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
