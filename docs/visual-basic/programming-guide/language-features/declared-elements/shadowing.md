---
title: Visual Basic의 숨김 기능
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], shadowing
- overriding, and shadowing
- shadowing
- duplicate names [Visual Basic]
- shadowing, by inheritance
- declared elements [Visual Basic], referencing
- shadowing, by scope
- declared elements [Visual Basic], hiding
- naming conflicts, shadowing
- declared elements [Visual Basic], shadowing
- shadowing, and overriding
- scope [Visual Basic], shadowing
- Shadows keyword [Visual Basic], about
- objects [Visual Basic], names
- names [Visual Basic], shadowing
ms.assetid: 54bb4c25-12c4-4181-b4a0-93546053964e
ms.openlocfilehash: fde6259b67a8d963ed8c30b87c94029fb2658664
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="shadowing-in-visual-basic"></a>Visual Basic의 숨김 기능
두 개의 프로그래밍 요소가 동일한 이름을 공유 하는 경우 그 중 하나가 숨길 수, 또는 *그림자*, 다른 하나 있습니다. 이러한 상황에서 숨겨진된 요소는 참조용; 수 대신, 코드에서 요소 이름, Visual Basic 컴파일러 숨기는 요소 확인 합니다.  
  
## <a name="purpose"></a>용도  
 섀도잉의 주요 목적은 클래스 멤버의 정의 보호 하는 것입니다. 기본 클래스를 이미 정의한 하나로 동일한 이름을 가진 요소를 만드는 경우가 있을 수 있습니다. 이런 경우는 `Shadows` 한정자를 사용 하면 클래스 멤버로 확인 수를 통한 참조가 이미 정의한 대신 새 기본 클래스 요소입니다.  
  
## <a name="types-of-shadowing"></a>숨김 형식  
 요소는 두 가지 방법으로 다른 요소를 숨길 수 있습니다. 숨기는 요소는 섀도잉 경우 이루어집니다 그림자가 있는 요소를 포함 하는 영역의 하위 영역 안에 선언할 수 있습니다 *범위를 통한*합니다. 파생 클래스는 대/소문자는 섀도잉은 수행 하는 기본 클래스의 멤버를 재정의할 수 또는 *상속을 통해*합니다.  
  
### <a name="shadowing-through-scope"></a>범위를 통한 숨김  
 프로그래밍에서 동일한 모듈, 클래스 또는 구조체에 이름은 같지만 다른 범위에 있는 요소에 대 한 것 같습니다. 더 좁은 범위를 갖는 요소가 다른 요소를 숨기면이 방식으로 두 개의 요소가 선언 된 경우 공유 이름으로 참조 하는 코드 (블록 범위는 가장 좁은 임).  
  
 예를 들어 모듈 정의할 수는 `Public` 라는 변수 `temp`, 모듈 내에서 프로시저도 라는 지역 변수를 선언할 수 `temp`합니다. 에 대 한 참조 `temp` 내에서 프로시저 액세스에 대 한 참조 하는 동안 지역 변수 `temp` 에서 외부 프로시저 액세스는 `Public` 변수입니다. 이 경우, 프로시저 변수 `temp` 모듈 변수를 숨깁니다 `temp`합니다.  
  
 다음 그림에서는 두 개의 변수를 보여 줍니다. 이라는 `temp`합니다. 지역 변수 `temp` 멤버 변수를 숨깁니다 `temp` 자체 프로시저 내에서 액세스할 때 `p`합니다. 그러나는 `MyClass` 키워드는 숨기기를 무시 하 고 멤버 변수에 액세스 합니다.  
  
 ![범위를 통한 숨기기 그래픽 다이어그램](../../../../visual-basic/programming-guide/language-features/declared-elements/media/shadowscope.gif "ShadowScope")  
범위를 통한 숨김  
  
 범위를 통한 숨기기의 예제를 보려면 [하는 방법: 사용자 변수로 이름이 같은 변수 숨기기](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)합니다.  
  
### <a name="shadowing-through-inheritance"></a>상속을 통한 숨김  
 프로그래밍 요소가 기본 클래스에서 상속 되며, 다시 정의 하는 파생된 클래스를 재정의 하는 요소를 원본 요소를 숨깁니다. 다른 형식으로 모든 종류의 선언 된 요소 또는 오버 로드 된 요소 집합을 숨길 수 있습니다. 예를 들어는 `Integer` 변수 섀도잉할 수는 `Function` 프로시저입니다. 다른 프로시저를 사용 하 여 프로시저를 숨길 경우에 다른 매개 변수 목록 및 다른 반환 형식을 사용할 수 있습니다.  
  
 다음 그림은 기본 클래스를 보여 줍니다. `b` 및 파생된 클래스가 `d` 에서 상속 되는 `b`합니다. 기본 클래스 라는 프로시저를 정의 `proc`, 파생된 클래스는이 동일한 이름의 다른 절차를 숨깁니다. 첫 번째 `Call` 문에서 액세스는 섀도잉 `proc` 파생된 클래스에서 합니다. 그러나는 `MyBase` 키워드는 숨기기를 무시 하 고 섀도 처리 된 프로시저는 기본 클래스에 액세스 합니다.  
  
 ![상속을 통한 숨기기 그래픽 다이어그램](../../../../visual-basic/programming-guide/language-features/declared-elements/media/shadowinherit.gif "ShadowInherit")  
상속을 통한 숨김  
  
 상속을 통한 숨김의 예제를 보려면 [하는 방법: 사용자 변수로 이름이 같은 변수 숨기기](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md) 및 [하는 방법:는 상속 된 변수 숨기기](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)합니다.  
  
#### <a name="shadowing-and-access-level"></a>숨김 및 액세스 수준  
 섀도잉 요소 항상 파생된 클래스를 사용 하 여 코드에서 액세스할 수 있는 것은 아닙니다. 예를 들어 선언할 수 있습니다 `Private`합니다. 이 경우 않으며 컴파일러 했을 때 같은 요소에 대 한 참조를 확인 섀도잉 되지 않은 것입니다. 이 이전 파생 단계의 숨기는 클래스에서 액세스할 수 있는 요소가입니다. 숨겨진된 요소 프로시저 이면 해상도으로 같은 이름의 매개 변수 목록에 액세스할 수 있는 가장 가까운 버전 및 형식을 반환 합니다.  
  
 다음 예제에서는 세 가지 클래스의 상속 계층 구조를 보여 줍니다. 각 클래스 정의 `Sub` 프로시저 `display`, 각 파생 클래스 그림자 및는 `display` 기본 클래스에서 프로시저입니다.  
  
```  
Public Class firstClass  
    Public Sub display()  
        MsgBox("This is firstClass")  
    End Sub  
End Class  
Public Class secondClass  
    Inherits firstClass  
    Private Shadows Sub display()  
        MsgBox("This is secondClass")  
    End Sub  
End Class  
Public Class thirdClass  
    Inherits secondClass  
    Public Shadows Sub display()  
        MsgBox("This is thirdClass")  
    End Sub  
End Class  
Module callDisplay  
    Dim first As New firstClass  
    Dim second As New secondClass  
    Dim third As New thirdClass  
    Public Sub callDisplayProcedures()  
        ' The following statement displays "This is firstClass".  
        first.display()  
        ' The following statement displays "This is firstClass".  
        second.display()  
        ' The following statement displays "This is thirdClass".  
        third.display()  
    End Sub  
End Module  
```  
  
 위의 예제에서는 파생된 클래스에서에서 `secondClass` 그림자 `display` 와 `Private` 프로시저입니다. 때 모듈 `callDisplay` 호출 `display` 에 `secondClass`, 호출 코드를 벗어납니다 `secondClass` 따라서 액세스할 수 없습니다. 사설 `display` 프로시저입니다. 않으며 컴파일러는 기본 클래스에 대 한 참조를 확인 `display` 프로시저입니다.  
  
 그러나 추가 파생 클래스 `thirdClass` 선언 `display` 으로 `Public`하므로의 코드 `callDisplay` 에 액세스할 수 있습니다.  
  
## <a name="shadowing-and-overriding"></a>숨기기와 재정의  
 숨김과 재정의 혼동 하지 마십시오. 둘 다 파생된 클래스는 기본 클래스에서 상속 하 고 다른 하나 선언 된 요소를 다시 정의 둘 다 사용 됩니다. 하지만 두 가지 중요 한 차이점이 있습니다. 비교를 참조 하십시오. [차이점 간의 숨기기와 재정의](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)합니다.  
  
## <a name="shadowing-and-overloading"></a>섀도잉 및 오버 로드  
 파생된 클래스에 둘 이상의 요소와 동일한 기본 클래스 요소를 숨길 경우 숨기는 요소는 해당 요소의 오버 로드 된 버전 됩니다. 자세한 내용은 참조 [프로시저 오버 로드](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)합니다.  
  
## <a name="accessing-a-shadowed-element"></a>섀도잉 된 요소에 액세스  
 파생된 클래스에서 요소를 액세스 하는 경우 일반적으로 이렇게 하면 해당 파생된 클래스의 현재 인스턴스를 통해 해당 요소 이름을 정규화 하 여는 `Me` 키워드입니다. 파생된 클래스의 기본 클래스에 요소를 숨기면 경우 한정 기본 클래스 요소를 액세스할 수 있습니다는 `MyBase` 키워드입니다.  
  
 섀도잉 된 요소에 액세스 하는 예제를 보려면 [하는 방법: 파생 클래스에 의해 변수 숨겨진 액세스](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)합니다.  
  
### <a name="declaration-of-the-object-variable"></a>개체 변수 선언  
 개체 변수를 만드는 방법는 파생된 클래스는 섀도잉 요소 또는 섀도잉 된 요소에 액세스 하는지 여부를 영향을 줄 수 있습니다. 다음 예제에서는 파생된 클래스에서 두 개체 만들지만 한 개체의 기본 클래스 및 파생된 클래스와 기타로 선언 됩니다.  
  
```  
Public Class baseCls  
    ' The following statement declares the element that is to be shadowed.  
    Public z As Integer = 100  
End Class  
Public Class dervCls  
    Inherits baseCls  
    ' The following statement declares the shadowing element.  
    Public Shadows z As String = "*"  
End Class  
Public Class useClasses  
    ' The following statement creates the object declared as the base class.  
    Dim basObj As baseCls = New dervCls()  
    ' Note that dervCls widens to its base class baseCls.  
    ' The following statement creates the object declared as the derived class.  
    Dim derObj As dervCls = New dervCls()  
    Public Sub showZ()   
    ' The following statement outputs 100 (the shadowed element).  
        MsgBox("Accessed through base class: " & basObj.z)  
    ' The following statement outputs "*" (the shadowing element).  
        MsgBox("Accessed through derived class: " & derObj.z)  
    End Sub  
End Class  
```  
  
 위의 예제에서는 변수에서에서 `basObj` 기본 클래스로 선언 합니다. 할당 한 `dervCls` 개체를 확대 변환이 구성 이므로 유효 합니다. 그러나 기본 클래스 변수 숨김 버전에 액세스할 수 없습니다 `z` 파생된 클래스에서 때문에 컴파일러에서는 `basObj.z` 원래 기본 클래스에 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [선언된 요소 참조](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [Visual Basic의 범위](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)  
 [확대 변환과 축소 변환](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)  
 [재정의](../../../../visual-basic/language-reference/modifiers/overrides.md)  
 [Me, My, MyBase 및 MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 [상속 기본 사항](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
