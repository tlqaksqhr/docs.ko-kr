---
title: "상속 기본 사항 (Visual Basic) | Microsoft 문서"
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
- derived classes, inheritance
- MyClass keyword, using
- MyBase keyword, using
- Inherits statement, inheritance
- overriding, Overridable keyword
- MustInherit keyword, using
- Overrides keyword, using
- inheritance
- MustInherit classes
- MustOverride keyword, using
- classes [Visual Basic], derived
- NotInheritable keyword, using
- base classes, extending properties and methods
- NotOverridable keyword, using
- base classes, inheritance
- abstract classes, inheritance
- overriding, Overrides keyword
ms.assetid: dfc8deba-f5b3-4d1d-a937-7cb826446fc5
caps.latest.revision: 23
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: 58aee9f8c348eb06daec2b8c9e332f3f2775bcb6
ms.lasthandoff: 03/13/2017

---
# <a name="inheritance-basics-visual-basic"></a>상속 기본 사항(Visual Basic)
`Inherits` 문을 사용 하 라는 새 클래스를 선언 하는 *파생 클래스*라고 하는 기존 클래스에 따라 한 *기본 클래스*합니다. 파생된 클래스는 상속 하 고 속성, 메서드, 이벤트, 필드 및 기본 클래스에 정의 된 상수 확장할 수 있습니다. 상속에 대 한 규칙 중 일부는 다음 섹션에서는 및 방식으로 클래스를 변경 하는 데 한정자 상속 하거나 상속 됩니다.  
  
-   기본적으로 모든 클래스는 상속할 수로 표시 하지 않는 한는 `NotInheritable` 키워드입니다. 클래스는 프로젝트의 다른 클래스 또는 프로젝트가 참조 하는 다른 어셈블리의 클래스에서 상속할 수 있습니다.  
  
-   다중 상속을 허용 하는 언어와 달리 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 클래스;에 단일 상속을 사용 하면 파생 된 클래스 즉, 하나의 기본 클래스를 가질 수 있습니다. 다중 상속 클래스에 허용 되지 않습니다 하지만 클래스에는 같은 결과 효과적으로 얻을 수 있는 여러 인터페이스를 구현할 수 있습니다.  
  
-   기본 클래스의 제한 된 항목을 공개를 방지 하려면 파생된 클래스의 액세스 형식을 같은 경우 또는 기본 클래스 보다 더 제한적인 이어야 합니다. 예를 들어 한 `Public` 클래스에서 상속할 수 없습니다는 `Friend` 또는 `Private` 클래스 및 `Friend` 클래스에서 상속할 수 없습니다는 `Private` 클래스.  
  
## <a name="inheritance-modifiers"></a>상속 한정자  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서는 다음 클래스 수준의 문과 한정자를 상속을 지원 합니다.  
  
-   `Inherits`문-기본 클래스를 지정 합니다.  
  
-   `NotInheritable`한정자-프로그래머를 기본 클래스로 클래스를 사용 하는 것을 금지 합니다.  
  
-   `MustInherit`한정자-하는 클래스 사용 하기 위한 기본 클래스로 지정 합니다. 인스턴스 `MustInherit` 클래스를 직접 만들 수 없습니다; 만들 수 있습니다만 파생된 클래스의 클래스 인스턴스를 기본으로 합니다. (이라는 용어를 사용 하는 c + + 및 C#과 같은 다른 프로그래밍 언어에서는 *추상 클래스* 이러한 클래스를 설명 합니다.)  
  
## <a name="overriding-properties-and-methods-in-derived-classes"></a>파생된 클래스의 속성 및 메서드를 재정의합니다.  
 기본적으로 파생된 클래스는 기본 클래스에서 속성 및 메서드 상속합니다. 상속 된 속성 또는 메서드는 파생된 클래스에서 다르게 동작 하는 경우 일 수 있습니다 *재정의*합니다. 즉, 파생된 클래스에서 메서드의 새로운 구현을 정의할 수 있습니다. 다음 한정자는 속성 및 메서드가 재정의되는 방식을 제어하는 데 사용됩니다.  
  
-   `Overridable`-파생된 클래스에서 재정의 해야 하는 클래스에서 속성 또는 메서드의 수 있습니다.  
  
-   `Overrides`-재정의 `Overridable` 속성이 나 메서드의 기본 클래스에서 정의 합니다.  
  
-   `NotOverridable`-상속 클래스에서 재정의 되는 속성 또는 메서드 수 없습니다. 기본적으로 `Public` 메서드는 `NotOverridable`합니다.  
  
-   `MustOverride`-파생된 클래스에서 속성 또는 메서드를 재정의 필요 합니다. 때는 `MustOverride` 키워드가 사용 되는지, 메서드 정의의 구성만 `Sub`, `Function`, 또는 `Property` 문입니다. 다른 문이 허용 여부와 특별히 없습니다 `End Sub` 또는 `End Function` 문입니다. `MustOverride`메서드를 선언 해야 `MustInherit` 클래스입니다.  
  
 급여를 처리 하는 클래스를 정의 하려고 한다고 가정 합니다. 일반을 정의할 수 있습니다 `Payroll` 클래스를 포함 하는 `RunPayroll` 일반적인 주에 대 한 급여를 계산 하는 방법입니다. 사용 하 여 수 `Payroll` 좀 더 특수 한 작업에 대 한 기본 클래스로 `BonusPayroll` 직원에 게 보너스를 배포 하는 경우 사용할 수 있는 클래스입니다.  
  
 `BonusPayroll` 클래스를 상속 하 고 재정의할 수는 `PayEmployee` 자료에 정의 된 메서드 `Payroll` 클래스입니다.  
  
 다음 예제에서는 기본 클래스를 정의 `Payroll,` 및 파생된 클래스가 `BonusPayroll`, 상속된 된 메서드를 재정의 하 `PayEmployee`합니다. 프로시저 `RunPayroll`을 만들고 다음 전달는 `Payroll` 개체 및 `BonusPayroll` , 함수 개체 `Pay`, 실행 하는 `PayEmployee` 두 개체의 메서드.  
  
 [!code-vb[VbVbalrOOP #&28;](../../../../visual-basic/misc/codesnippet/VisualBasic/inheritance-basics_1.vb)]  
  
## <a name="the-mybase-keyword"></a>MyBase 키워드  
 `MyBase` 키워드는 클래스의 현재 인스턴스는 기본 클래스를 참조 하는 개체 변수 처럼 동작 합니다. `MyBase`재정의 되거나 파생된 클래스에서 숨겨진 하는 기본 클래스 멤버 액세스를 주로 사용 됩니다. 특히, `MyBase.New` 파생된 클래스 생성자에서 기본 클래스 생성자를 명시적으로 호출 하는 데 사용 됩니다.  
  
 예를 들어, 기본 클래스에서 상속 된 메서드를 재정의 하는 파생된 클래스를 디자인 하는 가정 합니다. 재정의 된 메서드는 기본 클래스에서 메서드를 호출 하 고 다음 코드 조각에서와 같이 반환 값을 수정할 수 있습니다.:  
  
 [!code-vb[VbVbalrOOP #&109;](../../../../visual-basic/misc/codesnippet/VisualBasic/inheritance-basics_2.vb)]  
  
 사용 하 여 다음 목록에는 제한이 정리 되어 `MyBase`:  
  
-   `MyBase`직접 기본 클래스와 상속 된 멤버를 나타냅니다. 사용할 수 없습니다에 액세스 하려면 `Private` 클래스의 멤버입니다.  
  
-   `MyBase`실제 개체가 아니라 키워드가입니다. `MyBase`변수에 할당, 프로시저에 전달 하거나 사용할 수 없습니다에 `Is` 비교 합니다.  
  
-   메서드는 `MyBase` 한정;는 직접 기본 클래스에서 정의 하지 않아도 간접적으로 상속된 하는 기본 클래스에서 대신 정의할 수 있습니다. 지정한 참조가 위해 `MyBase` 올바르게 컴파일하기 위해 일부 기본 클래스 이름 및 호출에 나타나는 매개 변수의 형식과 일치 하는 메서드를 포함 해야 합니다.  
  
-   사용할 수 없는 `MyBase` 호출할 `MustOverride` 기본 클래스 메서드.  
  
-   `MyBase`자체를 정하는 데 사용할 수 없습니다. 따라서 다음 코드는 유효 하지 않습니다.  
  
     `MyBase.MyBase.BtnOK_Click()`  
  
-   `MyBase`모듈에서 사용할 수 없습니다.  
  
-   `MyBase`로 표시 된 기본 클래스 멤버 액세스를 사용할 수 없습니다 `Friend` 다른 어셈블리에 기본 클래스는 경우.  
  
 자세한 내용 및 다른 예에 대 한 참조 [하는 방법: 파생 클래스에 의해 변수 숨겨진 액세스](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)합니다.  
  
## <a name="the-myclass-keyword"></a>MyClass 키워드  
 `MyClass` 키워드는 원래 구현 된 클래스의 현재 인스턴스를 참조 하는 개체 변수 처럼 작동 합니다. `MyClass`유사한 `Me`, 모든 메서드 및 속성에 호출 되지만 `MyClass` 메서드 또는 속성 처럼 처리 됩니다 [NotOverridable](../../../../visual-basic/language-reference/modifiers/notoverridable.md)합니다. 따라서 메서드 또는 속성은 영향을 받지 파생된 클래스에서 재정의 하 여.  
  
-   `MyClass`실제 개체가 아니라 키워드가입니다. `MyClass`변수에 할당, 프로시저에 전달 하거나 사용할 수 없습니다에 `Is` 비교 합니다.  
  
-   `MyClass`포함 하는 클래스와 상속 된 멤버를 나타냅니다.  
  
-   `MyClass`에 대 한 한정자로 사용할 수 있습니다 `Shared` 멤버입니다.  
  
-   `MyClass`내에서 사용할 수 없습니다는 `Shared` 메서드를 되지만 인스턴스 메서드 내에서 사용 하는 클래스의 공유 멤버에 액세스할 수 있습니다.  
  
-   `MyClass`표준 모듈에서 사용할 수 없습니다.  
  
-   `MyClass`데 사용할 수는 기본 클래스에 정의 된 해당 클래스에서 제공 하는 메서드의 구현이 없는 메서드. 이러한 참조는 동일한 의미를 갖는 `MyBase.` *메서드*합니다.  
  
 다음 예제에서는 비교 `Me` 및 `MyClass`합니다.  
  
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
  
 경우에 `derivedClass` 재정의 `testMethod`, `MyClass` 키워드 `useMyClass` 재정의 및 컴파일러 확인 한 결과의 기본 클래스 버전에 대 한 호출을 취소 `testMethod`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Inherits 문](../../../../visual-basic/language-reference/statements/inherits-statement.md)   
 [Me, My, MyBase 및 MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
