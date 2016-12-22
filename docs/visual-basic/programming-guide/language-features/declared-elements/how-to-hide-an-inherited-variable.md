---
title: "How to: Hide an Inherited Variable (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "qualification, of element names"
  - "element names, qualification"
  - "references, declared elements"
  - "declaration statements, declared elements"
  - "referencing declared elements"
  - "declared elements, referencing"
  - "declared elements, about declared elements"
  - "variables [Visual Basic], hiding inherited"
ms.assetid: 765728d9-7351-4a30-999d-b5f34f024412
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Hide an Inherited Variable (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

파생 클래스는 기본 클래스의 모든 정의를 상속합니다.  기본 클래스의 요소와 동일한 이름으로 변수를 정의하려는 경우 파생 클래스에 변수를 정의할 때 기본 클래스 요소를 숨길\(*shadow*\) 수 있습니다.  이렇게 하면 숨김 메커니즘을 명시적으로 무시하지 않는 한 파생 클래스의 코드에서는 파생 클래스에 정의된 변수에 액세스하게 됩니다.  
  
 상속된 변수를 숨기는 또 다른 이유는 기본 클래스가 수정되는 것을 방지하기 위해서입니다.  기본 클래스가 변경되면 상속하는 요소도 변경될 수 있습니다.  이 경우 `Shadows` 한정자를 사용하면 파생 클래스에서의 참조는 기본 클래스 요소 대신 파생 클래스에 정의된 변수로 확인됩니다.  
  
### 상속된 변수를 숨기려면  
  
1.  숨길 변수가 클래스 수준, 즉 프로시저 외부에 선언되어 있는지 확인합니다.  그렇지 않으면 변수를 숨기지 않아도 됩니다.  
  
2.  파생 클래스 안에 사용할 변수를 선언하는 [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md)을 작성합니다.  상속된 변수의 이름과 동일한 이름을 사용합니다.  
  
3.  선언에 [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) 키워드를 포함합니다.  
  
     파생 클래스의 코드가 변수 이름을 참조할 때 컴파일러에서는 해당 참조를 파생 클래스에 정의된 변수로 확인합니다.  
  
     다음 예제에서는 상속된 변수를 숨기는 방법을 보여 줍니다.  
  
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
  
     위 예제에서는 기본 클래스에 `shadowString` 변수를 선언하고 파생 클래스에서 이를 숨깁니다.  파생 클래스의 `showStrings` 프로시저는 `shadowString`이라는 이름이 한정되지 않은 경우 해당 문자열의 숨김 버전을 표시합니다.  그런 다음 `shadowString`이 `MyBase` 키워드로 한정되면 숨겨진 버전을 표시합니다.  
  
## 강력한 프로그래밍  
 변수를 숨기면 이름이 동일한 변수 버전을 두 가지 이상 사용할 수 있습니다.  코드 문이 변수 이름을 참조할 때 컴파일러에서 이 참조에 해당하는 것으로 확인하는 버전은 코드 문의 위치, 한정 문자열이 있는지 여부 등의 요소에 따라 달라집니다.  따라서 숨겨진 변수의 원하지 않는 버전을 참조하게 될 위험이 높아집니다.  숨겨진 변수에 대한 모든 참조를 정규화하면 이러한 위험을 줄일 수 있습니다.  
  
## 참고 항목  
 [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [Shadowing in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)   
 [Differences Between Shadowing and Overriding](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)   
 [How to: Hide a Variable with the Same Name as Your Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)   
 [How to: Access a Variable Hidden by a Derived Class](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)   
 [Overrides](../../../../visual-basic/language-reference/modifiers/overrides.md)   
 [Me, My, MyBase, and MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)   
 [Inheritance Basics](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)