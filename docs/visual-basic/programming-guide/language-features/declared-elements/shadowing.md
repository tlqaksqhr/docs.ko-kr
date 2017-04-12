---
title: "Visual Basic의 숨김 기능 | Microsoft 문서"
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
- inheritance, shadowing
- overriding, and shadowing
- shadowing
- duplicate names
- shadowing, by inheritance
- declared elements, referencing
- shadowing, by scope
- declared elements, hiding
- naming conflicts, shadowing
- declared elements, shadowing
- shadowing, and overriding
- scope, shadowing
- Shadows keyword, about
- objects [Visual Basic], names
- names, shadowing
ms.assetid: 54bb4c25-12c4-4181-b4a0-93546053964e
caps.latest.revision: 24
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: 5f4053de05f0a7a42fccdade1714e08f8eb172e6
ms.lasthandoff: 03/13/2017

---
# <a name="shadowing-in-visual-basic"></a>Visual Basic의 숨김 기능
동일한 이름을 공유 하는 두 가지 프로그래밍 요소를 숨길 수 중 하나, 또는 *섀도*, 다른 하나입니다. 이러한 상황에서 숨겨진된 요소는 참조;에 사용할 수 대신, 코드 요소 이름에서의 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 컴파일러 숨기는 요소를 확인 합니다.  
  
## <a name="purpose"></a>용도  
 그림자의 주요 목적은 클래스 멤버의 정의 보호 하는 것입니다. 기본 클래스를 이미 정의한 하나는 동일한 이름을 갖는 요소를 만드는 경우가 있을 수 있습니다. 이 경우는 `Shadows` 한정자를 사용 하면 클래스 멤버를 확인할 수를 통한 참조가 새 기본 클래스 요소 대신 이미 정의한 합니다.  
  
## <a name="types-of-shadowing"></a>숨김 형식  
 요소는 두 가지 방법으로 다른 요소를 숨길 수 있습니다. 숨기는 요소를 숨기는 경우 수행 됩니다는 숨겨진된 요소가 포함 된 영역의 하위 영역 안에 선언할 수 *범위를 통한*합니다. 파생 클래스를 숨기는 경우가 작업을 수행 하는 기본 클래스의 멤버를 재정의할 수 또는 *상속을 통해*합니다.  
  
### <a name="shadowing-through-scope"></a>범위를 통한 숨김  
 프로그래밍에서 동일한 모듈, 클래스 또는 구조체에 이름은 같지만 다른 범위에 있는 요소에 대 한 것 같습니다. 두 요소는이 방식으로 선언 된 공유 이름으로 참조 하는 코드를 더 좁은 범위를 갖는 요소가 다른 요소를 숨기 (블록 범위는 좁음).  
  
 예를 들어 모듈을 정의할 수는 `Public` 라는 변수 `temp`, 모듈 내에서 프로시저도 라는 지역 변수를 선언할 수 `temp`합니다. 에 대 한 참조 `temp` 내에서 프로시저에 대 한 참조 하는 동안 지역 변수를 액세스 `temp` 에서 프로시저 액세스 외부에서 `Public` 변수입니다. 이 예제의 프로시저 변수 `temp` 모듈 변수를 숨기는 `temp`합니다.  
  
 다음 그림에서는 두 개의 변수를 보여 줍니다. 이라는 `temp`합니다. 지역 변수 `temp` 멤버 변수를 숨기는 `temp` 자체 프로시저 내에서 액세스할 때 `p`합니다. 그러나는 `MyClass` 키워드는 숨기기를 무시 하 고 멤버 변수에 액세스 합니다.  
  
 ![범위를 통한 숨기기 그래픽 다이어그램](../../../../visual-basic/programming-guide/language-features/declared-elements/media/shadowscope.gif "ShadowScope")  
범위를 통한 숨김  
  
 범위를 통한 숨김의 예제를 참조 하십시오. [하는 방법: 이름이 같은 변수를 사용 하 여 변수를 숨기려면](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)합니다.  
  
### <a name="shadowing-through-inheritance"></a>상속을 통한 숨김  
 기본 클래스에서 상속 하는 프로그래밍 요소를 다시 정의 하는 파생된 클래스를 재정의 하는 요소를 원본 요소를 숨깁니다. 모든 형식의 선언 된 요소 또는 오버 로드 된 요소 집합을 다른 형식을 사용 하 여 숨길 수 있습니다. 예를 들어는 `Integer` 변수 숨길 수는 `Function` 프로시저입니다. 다른 프로시저는 프로시저를 숨길 경우 다른 매개 변수 목록 및 다른 반환 형식을 사용할 수 있습니다.  
  
 다음 그림에서는 기본 클래스 `b` 및 파생된 클래스가 `d` 에서 상속 되는 `b`합니다. 라는 프로시저를 정의 하는 기본 클래스 `proc`, 파생된 클래스는이 동일한 이름의 다른 절차를 숨깁니다. 첫 번째 `Call` 는 숨기기 액세스 하는 문을 `proc` 파생된 된 클래스에 있습니다. 그러나는 `MyBase` 키워드는 숨기기를 무시 하 고 섀도 처리 된 프로시저는 기본 클래스에 액세스 합니다.  
  
 ![상속을 통한 숨기기 그래픽 다이어그램](../../../../visual-basic/programming-guide/language-features/declared-elements/media/shadowinherit.gif "ShadowInherit")  
상속을 통한 숨김  
  
 상속을 통한 숨김의 예제를 참조 하십시오. [하는 방법: 이름이 같은 변수를 사용 하 여 변수를 숨기려면](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md) 및 [하는 방법:는 상속 된 변수 숨기기](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)합니다.  
  
#### <a name="shadowing-and-access-level"></a>숨기기와 액세스 수준  
 숨기는 요소는 항상 파생된 클래스를 사용 하는 코드에서 액세스할 수 있는 것은 아닙니다. 예를 들어 선언할 수 있습니다 `Private`합니다. 이러한 경우 않으며 했을 때 같은 요소에 대 한 참조를 확인 하는 컴파일러 있었다면 숨기기 없습니다. 이 요소는 파생 단계의 뒤로 숨기는 클래스에서 액세스할 수 있는 요소입니다. 그림자가 있는 요소가 프로시저 이면 해상도으로 같은 이름의 매개 변수 목록에 액세스할 수 있는 가장 가까운 버전 및 형식을 반환 합니다.  
  
 다음 예제에서는 세 개의 클래스의 상속 계층 구조를 보여 줍니다. 각 클래스 정의 `Sub` 프로시저 `display`, 고 각 파생 클래스 그림자는 `display` 프로시저는 기본 클래스에 있습니다.  
  
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
  
 위의 예제에서는 파생된 클래스에서에서 `secondClass` 그림자 `display` 와 `Private` 프로시저입니다. 때 모듈 `callDisplay` 호출 `display` 에서 `secondClass`, 외부 호출 하는 코드는 `secondClass` 따라서 액세스할 수 없습니다. 사설 `display` 프로시저입니다. 컴파일러는 기본 클래스에 대 한 참조를 확인 하 고 숨기기 즉, `display` 프로시저입니다.  
  
 그러나 추가 파생 클래스 `thirdClass` 선언 `display` 으로 `Public`하므로 코드 `callDisplay` 에 액세스할 수 있습니다.  
  
## <a name="shadowing-and-overriding"></a>숨기기와 재정의  
 숨김과 재정의 혼동 하지 마십시오. 둘 다에 파생된 클래스는 기본 클래스에서 상속 하 고 다른 한 선언 된 요소를 재정의 하는 둘 다 사용 됩니다. 그러나 두 가지 중요 한 차이점이 있습니다. 비교를 참조 하십시오. [차이 간의 숨기기와 재정의](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)합니다.  
  
## <a name="shadowing-and-overloading"></a>숨기기와 오버 로드  
 파생된 클래스에서 둘 이상의 요소와 동일한 기본 클래스 요소를 숨길 경우 숨기는 요소는 해당 요소의 오버 로드 된 버전이 됩니다. 자세한 내용은 참조 [프로시저 오버 로딩](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)합니다.  
  
## <a name="accessing-a-shadowed-element"></a>숨겨진된 요소 액세스  
 파생된 클래스에서 요소를 액세스 하는 경우 일반적으로 이렇게 하면 해당 파생된 클래스의 현재 인스턴스를 통해 해당 요소 이름을 정규화 하 여는 `Me` 키워드입니다. 파생된 클래스의 기본 클래스에 있는 요소를 숨기면 정하여 기본 클래스 요소에 액세스할 수 있습니다는 `MyBase` 키워드입니다.  
  
 숨겨진된 요소에 액세스 하는 예제를 보려면 [하는 방법: 파생 클래스에 의해 변수 숨겨진 액세스](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)합니다.  
  
### <a name="declaration-of-the-object-variable"></a>개체 변수 선언  
 파생된 클래스를 숨기는 요소 또는 숨겨진된 요소에 액세스 하는지 여부를 개체 변수를 만드는 방법을 달라질 수 있습니다. 다음 예제에서는 파생된 클래스에서 두 개체 만들지만 한 개체의 기본 클래스와 파생된 클래스와 기타로 선언 됩니다.  
  
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
  
 위의 예제에서는 변수에서에서 `basObj` 기본 클래스로 선언 됩니다. 할당 한 `dervCls` 개체를 확대 변환이 구성 이므로 유효 합니다. 하지만, 기본 클래스에서 변수 숨김 버전에 액세스할 수 없습니다 `z` 파생된 클래스에서 때문에 컴파일러에서는 `basObj.z` 원래 기본 클래스에 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [선언 된 요소에 대 한 참조](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [Visual Basic의 범위](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)   
 [확대 변환과 축소 변환](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)   
 [그림자](../../../../visual-basic/language-reference/modifiers/shadows.md)   
 [재정](../../../../visual-basic/language-reference/modifiers/overrides.md)   
 [Me, My, MyBase 및 MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)   
 [상속 기본 사항](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
