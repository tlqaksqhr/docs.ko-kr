---
title: "How to: Access a Variable Hidden by a Derived Class (Visual Basic) | Microsoft Docs"
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
  - "base classes, accessing elements"
  - "element names, qualification"
  - "references, declared elements"
  - "declared elements, referencing"
  - "variables [Visual Basic], accessing hidden"
ms.assetid: ae21a8ac-9cd4-4fba-a3ec-ecc4321ef93c
caps.latest.revision: 20
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 20
---
# How to: Access a Variable Hidden by a Derived Class (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

파생 클래스의 코드에서 변수에 액세스할 때 컴파일러에서는 일반적으로 해당 참조를 가장 가까운 위치에 있는 액세스 가능 버전, 즉 액세스하는 클래스에서 바로 이전 파생 단계의 액세스 가능 버전으로 확인합니다.  변수가 파생 클래스에 정의되었으면 코드에서는 일반적으로 이 정의에 액세스합니다.  
  
 파생 클래스 변수가 기본 클래스의 변수를 숨기는 경우 기본 클래스 버전은 숨겨집니다.  하지만 `MyBase` 키워드로 변수를 한정하면 기본 클래스 변수에 액세스할 수 있습니다.  
  
### 파생 클래스에 의해 숨겨진 기본 클래스 변수에 액세스하려면  
  
-   식 또는 대입문에서 변수 이름 앞에 `MyBase` 키워드와 마침표\(`.`\)를 차례로 붙입니다.  
  
     컴파일러에서 해당 참조가 기본 클래스 버전의 변수로 확인됩니다.  
  
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
  
     위 예제에서는 기본 클래스에 `shadowString` 변수를 선언하고 파생 클래스에서 이를 숨깁니다.  파생 클래스의 `showStrings` 프로시저는 `shadowString`이라는 이름이 한정되지 않은 경우 해당 문자열의 숨김 버전을 표시합니다.  그런 다음 `shadowString`이 `MyBase`  키워드로 한정되면 숨겨진 버전을 표시합니다.  
  
## 강력한 프로그래밍  
 숨겨진 변수의 원하지 않는 버전을 참조하게 될 가능성을 줄이려면 숨겨진 변수에 대한 모든 참조를 완전히 한정합니다.  변수를 숨기면 이름이 동일한 변수 버전을 두 가지 이상 사용할 수 있습니다.  코드 문이 변수 이름을 참조할 때 컴파일러에서 이 참조에 해당하는 것으로 확인하는 버전은 코드 문의 위치, 한정 문자열이 있는지 여부 등의 요소에 따라 달라집니다.  따라서 잘못된 버전의 변수를 참조하게 될 가능성이 늘어납니다.  
  
## 참고 항목  
 [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [Shadowing in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)   
 [Differences Between Shadowing and Overriding](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)   
 [How to: Hide a Variable with the Same Name as Your Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)   
 [How to: Hide an Inherited Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)   
 [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)   
 [Overrides](../../../../visual-basic/language-reference/modifiers/overrides.md)   
 [Me, My, MyBase, and MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)   
 [Inheritance Basics](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)