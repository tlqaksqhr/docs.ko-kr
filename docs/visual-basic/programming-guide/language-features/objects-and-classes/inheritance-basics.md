---
title: "Inheritance Basics (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "derived classes, inheritance"
  - "MyClass keyword, using"
  - "MyBase keyword, using"
  - "Inherits statement, inheritance"
  - "overriding, Overridable keyword"
  - "MustInherit keyword, using"
  - "Overrides keyword, using"
  - "inheritance"
  - "MustInherit classes"
  - "MustOverride keyword, using"
  - "classes [Visual Basic], derived"
  - "NotInheritable keyword, using"
  - "base classes, extending properties and methods"
  - "NotOverridable keyword, using"
  - "base classes, inheritance"
  - "abstract classes, inheritance"
  - "overriding, Overrides keyword"
ms.assetid: dfc8deba-f5b3-4d1d-a937-7cb826446fc5
caps.latest.revision: 23
caps.handback.revision: 23
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Inheritance Basics (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

`Inherits` 문은 *기본 클래스*라는 기존 클래스를 기초로 *파생 클래스*라는 새 클래스를 선언하는 데 사용됩니다.  파생 클래스는 기본 클래스에 정의된 속성, 메서드, 이벤트, 필드 및 상수를 상속하고 확장할 수 있습니다.  다음 단원에서는 상속의 몇 가지 규칙과 클래스가 상속하거나 상속되는 방식을 변경하는 데 사용할 수 있는 한정자에 대해 설명합니다.  
  
-   기본적으로 모든 클래스는 `NotInheritable` 키워드로 표시되어 있지 않는 한 상속 가능합니다.  클래스는 프로젝트의 다른 클래스 또는 프로젝트가 참조하는 다른 어셈블리의 클래스에서 상속할 수 있습니다.  
  
-   다중 상속을 허용하는 언어와 달리 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서는 클래스의 단일 상속만 허용합니다. 즉, 파생 클래스는 하나의 기본 클래스만 가질 수 있습니다.  클래스에서는 다중 상속이 허용되지 않지만 같은 결과를 효과적으로 얻을 수 있도록 여러 인터페이스를 구현할 수 있습니다.  
  
-   기본 클래스의 제한된 항목을 노출시키지 않으려는 경우 파생 클래스의 액세스 형식이 해당 기본 클래스와 동일하거나 해당 기본 클래스보다 더 제한적이어야 합니다.  예를 들어, `Public` 클래스는 `Friend` 또는 `Private` 클래스를 상속할 수 없으며, `Friend` 클래스는 `Private` 클래스를 상속할 수 없습니다.  
  
## 상속 한정자  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서는 클래스에 다음과 같은 클래스 수준 문과 한정자를 제공하여 상속을 지원합니다.  
  
-   `Inherits` 문 — 기본 클래스를 지정합니다.  
  
-   `NotInheritable` 한정자 — 프로그래머가 해당 클래스를 기본 클래스로 사용하지 못하게 합니다.  
  
-   `MustInherit` 한정자 — 해당 클래스가 기본 클래스로만 사용되도록 지정합니다.  `MustInherit` 클래스의 인스턴스는 직접 만들 수 없으며 기본 클래스로서 파생 클래스의 인스턴스만 만들 수 있습니다.  C\+\+ 및 C\#과 같은 다른 프로그래밍 언어에서는 이러한 클래스를 *추상 클래스*라고 합니다.  
  
## 파생 클래스의 속성 및 메서드 재정의  
 기본적으로 파생 클래스는 해당 기본 클래스에서 속성과 메서드를 상속합니다.  상속된 속성이나 메서드가 파생 클래스에서 다르게 동작해야 하는 경우 해당 속성이나 메서드를 *재정의*할 수 있습니다.  즉, 파생 클래스에 해당 메서드의 새로운 구현을 정의할 수 있습니다.  다음 한정자는 속성 및 메서드가 재정의되는 방식을 제어하는 데 사용됩니다.  
  
-   `Overridable` — 클래스의 속성 또는 메서드가 파생 클래스에서 재정의될 수 있습니다.  
  
-   `Overrides` — 기본 클래스에 정의되어 있는 `Overridable` 속성 또는 메서드를 재정의합니다.  
  
-   `NotOverridable` — 속성 또는 메서드가 상속 클래스에서 재정의되지 않도록 합니다.  기본적으로 `Public` 메서드는 `NotOverridable`입니다.  
  
-   `MustOverride` — 파생 클래스에서 속성 또는 메서드를 재정의해야 합니다.  `MustOverride` 키워드가 사용되는 경우 메서드 정의는 `Sub`, `Function` 또는 `Property` 문으로만 구성됩니다.  `End Sub` 또는 `End Function` 문을 포함하여 다른 문은 허용되지 않습니다.  `MustOverride` 메서드는 `MustInherit` 클래스에 선언되어야 합니다.  
  
 급료를 처리하는 클래스를 정의하려 한다고 가정합니다.  이 경우 주급을 계산하는 `RunPayroll` 메서드를 포함하는 일반 `Payroll` 클래스를 정의할 수 있습니다.  그런 다음 직원에게 보너스를 지불할 때 사용할 수 있는 좀 더 구체적인 `BonusPayroll` 클래스에 대한 기본 클래스로 `Payroll`을 사용할 수 있습니다.  
  
 `BonusPayroll` 클래스는 기본 `Payroll` 클래스에 정의되어 있는 `PayEmployee` 메서드를 상속하고 재정의할 수 있습니다.  
  
 다음 예제에서는 기본 클래스 `Payroll`과 파생 클래스 `BonusPayroll`을 정의하며 이 클래스는 상속된 메서드 `PayEmployee`를 재정의합니다.  `RunPayroll` 프로시저는 `Payroll` 개체와 `BonusPayroll` 개체를 만든 다음 두 개체의 `PayEmployee` 메서드를 실행하는 함수 `Pay`에 전달합니다.  
  
 [!code-vb[VbVbalrOOP#28](../../../../visual-basic/misc/codesnippet/VisualBasic/inheritance-basics_1.vb)]  
  
## MyBase 키워드  
 `MyBase` 키워드는 현재 클래스 인스턴스의 기본 클래스를 참조하는 개체 변수처럼 동작합니다.  `MyBase`는 파생 클래스에서 재정의되거나 숨겨진 기본 클래스 멤버에 액세스하는 데 많이 사용됩니다.  특히 `MyBase.New`는 파생 클래스 생성자에서 명시적으로 기본 클래스 생성자를 호출하는 데 사용됩니다.  
  
 예를 들어, 기본 클래스에서 상속된 메서드를 재정의하는 파생 클래스를 디자인하고 있다고 가정합니다.  재정의된 메서드는 다음 코드 부분에서와 같이 기본 클래스의 메서드를 호출하고 반환 값을 수정할 수 있습니다.  
  
 [!code-vb[VbVbalrOOP#109](../../../../visual-basic/misc/codesnippet/VisualBasic/inheritance-basics_2.vb)]  
  
 다음은 `MyBase` 사용 시 적용되는 제한 사항에 대한 설명입니다.  
  
-   `MyBase`는 직접적인 기본 클래스와 이에 대한 상속된 멤버를 나타냅니다.  클래스의 `Private` 멤버에 액세스하는 데에는 사용할 수 없습니다.  
  
-   `MyBase`는 실제 개체가 아니라 키워드입니다.  `MyBase`는 변수에 할당하거나, 프로시저에 전달하거나, `Is` 비교에 사용할 수 없습니다.  
  
-   `MyBase`에서 지정하는 메서드는 직접 기본 클래스에 정의할 필요가 없습니다. 대신 간접적으로 상속된 기본 클래스에 정의할 수 있습니다.  `MyBase`에서 지정한 참조가 제대로 컴파일되려면 특정 기본 클래스는 호출에 나타나는 매개 변수의 이름 및 형식과 일치하는 메서드를 포함해야 합니다.  
  
-   `MyBase`를 사용하여 `MustOverride` 기본 클래스 메서드를 호출할 수 없습니다.  
  
-   `MyBase`는 스스로를 한정하는 데 사용될 수 없습니다.  따라서 다음 코드는 올바르지 않습니다.  
  
     `MyBase.MyBase.BtnOK_Click()`  
  
-   `MyBase`는 모듈에서 사용할 수 없습니다.  
  
-   기본 클래스가 다른 어셈블리에 있는 경우 `Friend`로 표시된 기본 클래스 멤버에 액세스하는 데는 `MyBase`를 사용할 수 없습니다.  
  
 자세한 내용 및 다른 예제를 보려면 [How to: Access a Variable Hidden by a Derived Class](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)를 참조하십시오.  
  
## MyClass 키워드  
 `MyClass` 키워드는 원래 구현된 상태의 현재 클래스 인스턴스를 참조하는 개체 변수처럼 동작합니다.  `MyClass`는 `Me`와 비슷하지만 `MyClass`에 대한 모든 메서드와 속성 호출은 해당 메서드나 속성이 [NotOverridable](../../../../visual-basic/language-reference/modifiers/notoverridable.md)인 것처럼 처리됩니다.  따라서 메서드나 속성은 파생 클래스에서 재정의하더라도 영향을 받지 않습니다.  
  
-   `MyClass`는 실제 개체가 아니라 키워드입니다.  `MyClass`는 변수에 할당하거나, 프로시저에 전달하거나, `Is` 비교에 사용할 수 없습니다.  
  
-   `MyClass`는 포함 클래스와 그에 대한 상속된 멤버를 나타냅니다.  
  
-   `MyClass`는 `Shared` 멤버에 대한 한정자로 사용할 수 있습니다.  
  
-   `MyClass`는 `Shared` 메서드 내에서 사용할 수 없지만 인스턴스 메서드 내에서 사용하여 클래스의 공유 멤버에 액세스할 수 있습니다.  
  
-   `MyClass`는 표준 모듈에서 사용할 수 없습니다.  
  
-   `MyClass`는 기본 클래스에 정의되어 있지만 구현 부분은 없는 메서드를 지정하는 데 사용할 수 있습니다.  이러한 참조는 `MyBase.`*Method*와 같은 의미를 갖습니다.  
  
 다음 예제는 `Me`와 `MyClass`를 비교합니다.  
  
```  
Class baseClass  
    Public Overridable Sub testMethod()  
        MsgBox("Base class string")  
    End Sub  
    Public Sub useMe()  
        ' The following call uses the calling class's method, even if   
        ' that method is an override.  
        Me.testMethod()  
    End Sub  
    Public Sub useMyClass()  
        ' The following call uses this instance's method and not any  
        ' override.  
        MyClass.testMethod()  
    End Sub  
End Class  
Class derivedClass : Inherits baseClass  
    Public Overrides Sub testMethod()  
        MsgBox("Derived class string")  
    End Sub  
End Class  
Class testClasses  
    Sub startHere()  
        Dim testObj As derivedClass = New derivedClass()  
        ' The following call displays "Derived class string".  
        testObj.useMe()  
        ' The following call displays "Base class string".  
        testObj.useMyClass()  
    End Sub  
End Class  
```  
  
 `derivedClass`가 `testMethod`를 재정의하더라도 `useMyClass`의 `MyClass` 키워드가 재정의한 결과를 취소하고 컴파일러는 이 호출을 `testMethod`의 기본 클래스 버전으로 연결합니다.  
  
## 참고 항목  
 [Inherits Statement](../../../../visual-basic/language-reference/statements/inherits-statement.md)   
 [Me, My, MyBase, and MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)