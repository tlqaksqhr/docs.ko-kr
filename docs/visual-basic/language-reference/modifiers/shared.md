---
title: Shared(Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Shared
helpviewer_keywords:
- Shared keyword [Visual Basic]
- members [Visual Basic], shared
- shared members
- nonshared
- shared [elements VB]
- elements [Visual Basic], shared
ms.assetid: 2bf7cf2c-b0dd-485e-8749-b5d674dab4cd
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fce13c308a449e63eacc2bc4c94c274c7e25506a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="shared-visual-basic"></a>Shared(Visual Basic)
선언 된 프로그래밍 요소를 하나 이상의 클래스 또는 구조체의 특정 인스턴스가 아닌 클래스 또는 구조체도 연결 되도록 지정 합니다.  
  
## <a name="remarks"></a>설명  
  
## <a name="when-to-use-shared"></a>공유 사용 하는 경우  
 모든 인스턴스를 사용할 수 있도록 클래스 또는 구조체의 멤버를 공유 대신 *비공유*각 인스턴스는 자체 복사본을 유지 합니다. 예를 들어 변수의 값이 전체 응용 프로그램에 적용 경우 유용 합니다. 해당 변수를 선언 하는 경우 `Shared`모든 인스턴스에서 동일한 저장소 위치에 액세스 하 고 하나의 인스턴스만 해당 변수의 값을 변경 해도 모든 인스턴스에서 업데이트 된 값에 액세스 합니다.  
  
 공유 멤버의 액세스 수준을 변경 하지 않습니다. 예를 들어, 클래스 멤버를 공유할 수 있습니다 및 private (내 에서만 액세스할 수는 클래스) 또는 비공유 및 공개 합니다. 자세한 내용은 참조 [액세스 수준을 Visual Basic의](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)합니다.  
  
## <a name="rules"></a>규칙  
  
-   **선언 컨텍스트입니다.** `Shared`는 모듈 수준에서만 사용할 수 있습니다. 즉, 선언 컨텍스트는 `Shared` 요소는 클래스 또는 구조체 이어야 하며 원본 파일, 네임 스페이스 또는 프로시저일 수 없습니다.  
  
-   **결합 된 한정자입니다.** 지정할 수 없습니다 `Shared` 와 함께 [재정의](../../../visual-basic/language-reference/modifiers/overrides.md), [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md), [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md), [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md), 또는 [ 정적](../../../visual-basic/language-reference/modifiers/static.md) 같은 선언에 있습니다.  
  
-   **에 액세스합니다.** 공유 요소에 액세스 하면 해당 클래스 또는 구조체의 특정 인스턴스에의 변수 이름와 아닌에서 클래스나 구조체 이름으로 한정 합니다. 도 클래스 또는 해당 공유 멤버에 액세스 하는 구조체의 인스턴스를 만들 필요가 없습니다.  
  
     공유 프로시저를 호출 하는 다음 예제에서는 <xref:System.Double.IsNaN%2A> 의해 노출 되는 <xref:System.Double> 구조입니다.  
  
     `If Double.IsNaN(result) Then MsgBox("Result is mathematically undefined.")`  
  
-   **암시적 공유 합니다.** 사용할 수 없습니다는 `Shared` 한정자는 [Const 문](../../../visual-basic/language-reference/statements/const-statement.md), 암시적으로 상수는 공유 합니다. 마찬가지로, 지정할 모듈 또는 인터페이스의 멤버를 선언할 수 없습니다 `Shared`, 없어도 암시적으로 공유 합니다.  
  
## <a name="behavior"></a>동작  
  
-   **저장소입니다.** 만들 해당 클래스 또는 구조체의 인스턴스를 개수에 관계 없이 한 번만 공유 변수 또는 이벤트 메모리에 저장 됩니다. 마찬가지로, 공유 프로시저 또는 속성이 하나의 지역 변수 집합을 보유합니다.  
  
-   **인스턴스 변수를 통해 액세스 합니다.** 요소에 액세스 하는 공유의 해당 클래스 또는 구조체의 특정 인스턴스를 포함 하는 변수 이름으로 정규화 하 여는 것이 불가능 합니다. 이 일반적으로 예상 대로 작동 하지만 컴파일러에서 경고 메시지를 생성 하 고 변수 대신 클래스 또는 구조체 이름 통해 액세스 합니다.  
  
-   **인스턴스 식을 통해에 액세스합니다.** 해당 클래스 또는 구조체의 인스턴스를 반환 하는 식을 통해 공유 요소를 액세스 하는 경우 컴파일러에서 식을 계산 하는 대신 클래스 또는 구조체 이름을 통해 액세스 합니다. 다른 작업으로 인스턴스를 반환 하는 데 식을 사용 하는 경우 예기치 않은 결과가 생성 됩니다. 다음은 이에 대한 예입니다.  
  
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
  
     앞의 예제에서 컴파일러는 경고 메시지를 생성 코드 공유 변수에 액세스할 때마다 `total` 인스턴스를 통해 합니다. 각 경우에는 클래스를 통해 직접 액세스 `shareTotal` 않습니다 인스턴스는 사용 합니다. 프로시저에 대 한 의도 한 호출의 경우 `returnClass`, 즉,에 대 한 호출도 생성 하지 않습니다 `returnClass`이므로 "이라는 함수 returnClass()"를 표시 합니다. 추가 동작이 수행 되지 않습니다.  
  
 `Shared` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.  
  
 [Dim 문](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Event 문](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Operator 문](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [Property 문](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>참고 항목  
 [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)  
 [정적](../../../visual-basic/language-reference/modifiers/static.md)  
 [Visual Basic의 수명](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)  
 [절차](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [구조체](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [개체 및 클래스](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
