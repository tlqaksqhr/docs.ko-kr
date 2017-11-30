---
title: "방법: 파생 클래스에 의해 숨겨진 변수에 액세스(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- qualification [Visual Basic], of element names
- base classes [Visual Basic], accessing elements
- element names [Visual Basic], qualification
- references [Visual Basic], declared elements
- declared elements [Visual Basic], referencing
- variables [Visual Basic], accessing hidden
ms.assetid: ae21a8ac-9cd4-4fba-a3ec-ecc4321ef93c
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0f94e45fcb0a26b0d59789e101c37aceba219250
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-access-a-variable-hidden-by-a-derived-class-visual-basic"></a>방법: 파생 클래스에 의해 숨겨진 변수에 액세스(Visual Basic)
변수에 액세스 하는 파생된 클래스에서 코드를 컴파일러는 이전 파생 단계의 액세스 하는 클래스에서 액세스할 수 있는 버전 즉, 가장 가까운 액세스할 수 있는 버전에 대 한 참조에 해결 일반적으로 합니다. 변수를 파생된 클래스에서 정의 하는 경우 코드는 일반적으로 해당 정의 액세스 합니다.  
  
 파생된 클래스 변수는 기본 클래스의 변수를 숨기면 기본 클래스 버전을 숨깁니다. 그러나 기본 클래스 변수를 정규화 하 여 액세스할 수 있습니다는 `MyBase` 키워드입니다.  
  
### <a name="to-access-a-base-class-variable-hidden-by-a-derived-class"></a>파생된 클래스에 의해 숨겨진 기본 클래스 변수에 액세스 하려면  
  
-   식 또는 대입문, 변수 이름 앞에 `MyBase` 키워드와 마침표 (`.`).  
  
     컴파일러는 변수의 기본 클래스 버전에 대 한 참조를 확인 합니다.  
  
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
 위험을 낮추기 위해서는 의도 하지 않은 버전의 숨겨진된 변수에 참조를 완전히 숨겨진된 변수에 대 한 모든 참조를 한정할 수 있습니다. 섀도잉 동일한 이름 가진 변수 둘 이상의 버전을 도입 되었습니다. 코드 문이 변수 이름에는 참조, 컴파일러 참조를 확인 하는 버전 문 코드의 위치 및 한정 문자열이 있는지 여부 등의 요인에 따라 달라 집니다. 잘못 된 버전의 변수를 참조할 위험이 높아질 수 있습니다이 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [선언된 요소 참조](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [Visual Basic의 숨김 기능](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)  
 [숨기기와 재정의의 차이점](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)  
 [방법: 이름이 같은 변수 숨기기](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)  
 [방법: 상속된 변수 숨기기](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)  
 [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)  
 [재정의](../../../../visual-basic/language-reference/modifiers/overrides.md)  
 [Me, My, MyBase 및 MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 [상속 기본 사항](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
