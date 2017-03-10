---
title: "Shared (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Shared"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Shared keyword"
  - "members, shared"
  - "shared members"
  - "nonshared"
  - "shared elements"
  - "elements, shared"
ms.assetid: 2bf7cf2c-b0dd-485e-8749-b5d674dab4cd
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# Shared (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

선언된 프로그래밍 요소 하나 이상이 클래스나 구조체의 특정 인스턴스가 아니라 해당 클래스나 구조체 전체에 연결되도록 지정합니다.  
  
## 설명  
  
## Shared를 사용하는 경우  
 클래스나 구조체의 멤버를 공유하면 인스턴스마다 자체 복사본이 유지되는 *비공유* 상태와 달리 해당 멤버를 모든 인스턴스에서 사용할 수 있게 됩니다.  이 기능은 변수 값이 전체 응용 프로그램에 적용될 때와 같은 경우에 유용합니다.  변수를 `Shared`로 선언하면 모든 인스턴스에서 같은 저장소 위치에 액세스하며, 한 인스턴스에서 변수 값을 변경해도 모든 인스턴스에서 업데이트된 값에 액세스할 수 있습니다.  
  
 공유를 통해 멤버의 액세스 수준이 변경되지는 않습니다.  예를 들어 클래스 멤버가 공유이면서 전용\(클래스 내에서만 액세스 가능\)일 수도 있고, 비공유이면서 공용일 수도 있습니다.  자세한 내용은 [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)을 참조하십시오.  
  
## 규칙  
  
-   **선언 컨텍스트.** `Shared` 키워드는 모듈 수준에서만 사용할 수 있습니다.  즉, `Shared` 요소에 대한 선언 컨텍스트는 클래스 또는 구조체여야 하며 소스 파일, 네임스페이스 또는 프로시저가 될 수는 없습니다.  
  
-   **결합 한정자.** 하나의 선언에서 `Shared`를 [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md), [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md), [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md), [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md) 또는 [Static](../../../visual-basic/language-reference/modifiers/static.md)과 함께 지정할 수 없습니다.  
  
-   **액세스.** 클래스나 구조체의 특정 인스턴스의 변수 이름이 아닌 해당 클래스 또는 구조체 이름으로 공유 요소를 한정하여 해당 요소에 액세스합니다.  해당 공유 멤버에 액세스하기 위한 클래스 또는 구조체의 인스턴스도 만들 필요가 없습니다.  
  
     다음 예제에서는 <xref:System.Double> 구조체에 의해 노출되는 공유 프로시저 <xref:System.Double.IsNaN%2A>을 호출합니다.  
  
     `If Double.IsNaN(result) Then MsgBox("Result is mathematically undefined.")`  
  
-   **암시적 공유.** `Shared` 한정자를 [Const Statement](../../../visual-basic/language-reference/statements/const-statement.md)에서 사용할 수 없지만 상수는 암시적으로 공유됩니다.  마찬가지로 모듈 또는 인스턴스의 멤버를 `Shared`로 선언할 수 없어도 암시적으로는 공유됩니다.  
  
## 동작  
  
-   **저장.** 해당 클래스나 구조체에 대해 만드는 인스턴스의 개수에 관계없이 공유 변수 또는 이벤트는 메모리에 한 번만 저장됩니다.  마찬가지로 공유 프로시저 또는 속성에는 지역 변수 집합이 하나만 저장됩니다.  
  
-   **인스턴스 변수를 통한 액세스.** 클래스나 구조체의 특정 인스턴스가 포함된 변수 이름으로 공유 요소를 한정하여 해당 요소에 액세스할 수 있습니다.  이 기능은 대개 예상한 대로 작동하지만 컴파일러에서는 경고 메시지를 생성하고 변수 대신 클래스 또는 구조체 이름을 통해 액세스합니다.  
  
-   **인스턴스 식을 통한 액세스.** 해당 클래스나 구조체의 인스턴스를 반환하는 식을 통해 공유 요소에 액세스하면 컴파일러에서는 식을 계산하지 않고 클래스나 구조체 이름을 통해 액세스합니다.  이때, 식을 통해 인스턴스를 반환함은 물론 다른 작업을 수행하려고 하면 예기치 않은 결과가 발생합니다.  다음은 이에 대한 예입니다.  
  
    ```  
    Sub main()  
        shareTotal.total = 10  
        ' The preceding line is the preferred way to access total.  
        Dim instanceVar As New shareTotal  
        instanceVar.total += 100  
        ' The preceding line generates a compiler warning message and  
        ' accesses total through class shareTotal instead of through  
        ' the variable instanceVar. This works as expected and adds  
        ' 100 to total.  
        returnClass().total += 1000  
        ' The preceding line generates a compiler warning message and  
        ' accesses total through class shareTotal instead of calling  
        ' returnClass(). This adds 1000 to total but does not work as  
        ' expected, because the MsgBox in returnClass() does not run.  
        MsgBox("Value of total is " & CStr(shareTotal.total))  
    End Sub  
    Public Function returnClass() As shareTotal  
        MsgBox("Function returnClass() called")  
        Return New shareTotal  
    End Function  
    Public Class shareTotal  
        Public Shared total As Integer  
    End Class  
    ```  
  
     위 예제에서는 코드에서 인스턴스를 통해 공유 변수 `total`에 액세스할 때마다 컴파일러에서 경고 메시지를 생성합니다.  각 경우마다 `shareTotal` 클래스를 통해 직접 액세스하며 인스턴스는 사용하지 않습니다.  `returnClass` 프로시저 호출을 의도한 경우에는 `returnClass`에 대한 호출도 생성되지 않으므로 "Function returnClass\(\) called"를 표시하는 추가 작업이 수행되지 않습니다.  
  
 `Shared` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.  
  
 [Dim 문](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Event 문](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Operator 문](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [Property 문](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## 참고 항목  
 [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)   
 [Static](../../../visual-basic/language-reference/modifiers/static.md)   
 [Lifetime in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)   
 [Procedures](../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Structures](../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Objects and Classes](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)