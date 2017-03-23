---
title: "How to: Hide a Variable with the Same Name as Your Variable (Visual Basic) | Microsoft Docs"
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
  - "qualification, of element names"
  - "declarations, elements"
  - "element names, qualification"
  - "references, declared elements"
  - "declaration statements, declared elements"
  - "declaring elements"
  - "referencing declared elements"
  - "declared elements, referencing"
  - "declared elements, about declared elements"
ms.assetid: e39c0752-f19f-4d2e-a453-00df1b5fc7ee
caps.latest.revision: 25
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 25
---
# How to: Hide a Variable with the Same Name as Your Variable (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

*숨김* 기능을 사용하여, 즉 변수를 같은 이름의 변수로 다시 정의하여 원래 변수를 숨길 수 있습니다.  다음 두 가지 방법으로 변수를 숨길 수 있습니다.  
  
-   **범위를 통한 숨김.** 숨기려는 변수가 들어 있는 영역의 하위 영역 안에서 해당 변수를 다시 선언하여 범위를 통해 변수를 숨길 수 있습니다.  
  
-   **상속을 통한 숨김.** 숨기려는 변수가 클래스 수준에서 정의된 경우 파생 클래스에서 해당 변수를 [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) 키워드로 다시 선언하면 상속을 통해 변수를 숨길 수 있습니다.  
  
## 변수를 숨기는 두 가지 방법  
  
#### 범위를 통해 변수를 숨기려면  
  
1.  숨기려는 변수를 정의하는 영역을 결정하고 사용자의 변수로 다시 정의할 하위 영역을 결정합니다.  
  
    |변수의 영역|변수를 다시 정의할 수 있는 하위 영역|  
    |------------|---------------------------|  
    |모듈|해당 모듈 내의 클래스|  
    |클래스|해당 클래스 내의 서브클래스<br /><br /> 해당 클래스 내의 프로시저|  
  
     프로시저 변수는 해당 프로시저 내에 있는 `If`...`End If` 구문이나 `For` 루프 등의 블록에서 다시 정의할 수 없습니다.  
  
2.  하위 영역이 없으면 만듭니다.  
  
3.  하위 영역 안에서, 숨기는 변수를 선언하는 [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md)을 작성합니다.  
  
     하위 영역 내의 코드가 변수 이름을 참조할 때 컴파일러에서는 해당 참조를 숨기는 변수에 정의된 변수로 확인합니다.  
  
     다음 예제에서는 범위를 통한 숨김과 숨김이 적용되지 않는 참조를 보여 줍니다.  
  
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
  
     위 예제에서는 모듈 수준과 `show` 프로시저의 프로시저 수준 모두에서 `num` 변수를 선언합니다.  `show` 내에서 지역 변수 `num`은 모듈 수준 변수 `num`을 숨기므로 지역 변수가 2로 설정됩니다.  그러나 `useModuleLevelNum` 프로시저에서 `num`을 숨기는 지역 변수는 없습니다.  따라서 `useModuleLevelNum`은 모듈 수준 변수의 값을 1로 설정합니다.  
  
     `show` 내의 `MsgBox` 호출에서는 `num`을 모듈 이름으로 한정하여 숨김 메커니즘을 적용하지 않습니다.  따라서 지역 변수 대신 모듈 수준 변수가 표시됩니다.  
  
#### 상속을 통해 변수를 숨기려면  
  
1.  숨길 변수가 클래스에서 클래스 수준으로, 즉 프로시저 외부에 선언되어 있는지 확인합니다.  그렇지 않으면 상속을 통해 변수를 숨길 수 없습니다.  
  
2.  변수의 클래스에서 파생된 클래스가 아직 없으면 파생 클래스를 정의합니다.  
  
3.  파생 클래스에서, 사용할 변수를 선언하는 `Dim` 문을 작성합니다.  선언에 [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) 키워드를 포함합니다.  
  
     파생 클래스의 코드가 변수 이름을 참조할 때 컴파일러에서는 해당 참조를 파생 클래스에 정의된 변수로 확인합니다.  
  
     다음 예제에서는 상속을 통해 숨기는 방법을 보여 줍니다.  예제에서 만드는 두 개의 참조 중 하나는 숨기는 변수에 액세스하고 다른 하나는 숨기기를 무시합니다.  
  
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
  
     위 예제에서는 기본 클래스에 `shadowString` 변수를 선언하고 파생 클래스에서 이를 숨깁니다.  파생 클래스의 `showStrings` 프로시저는 `shadowString`이라는 이름이 한정되지 않은 경우 해당 문자열의 숨김 버전을 표시합니다.  그런 다음 `shadowString`이 `MyBase`키워드로 한정되면 숨겨진 버전을 표시합니다.  
  
## 강력한 프로그래밍  
 변수를 숨기면 이름이 동일한 변수 버전을 두 가지 이상 사용할 수 있습니다.  코드 문이 변수 이름을 참조할 때 컴파일러에서 이 참조에 해당하는 것으로 확인하는 버전은 코드 문의 위치, 한정 문자열이 있는지 여부 등의 요소에 따라 달라집니다.  따라서 숨겨진 변수의 원하지 않는 버전을 참조하게 될 위험이 높아집니다.  숨겨진 변수에 대한 모든 참조를 정규화하면 이러한 위험을 줄일 수 있습니다.  
  
## 참고 항목  
 [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [Shadowing in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)   
 [Differences Between Shadowing and Overriding](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)   
 [How to: Hide an Inherited Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)   
 [How to: Access a Variable Hidden by a Derived Class](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)   
 [Overrides](../../../../visual-basic/language-reference/modifiers/overrides.md)   
 [Me, My, MyBase, and MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)   
 [Inheritance Basics](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)