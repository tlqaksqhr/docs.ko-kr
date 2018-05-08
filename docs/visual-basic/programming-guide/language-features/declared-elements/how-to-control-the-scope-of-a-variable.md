---
title: '방법: 변수의 범위 제어(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], scope
- declared elements [Visual Basic], scope
- visibility [Visual Basic], declared elements
- variables [Visual Basic], visibility
- scope [Visual Basic], declared elements
- scope [Visual Basic], variables
- scope [Visual Basic], Visual Basic
- declared elements [Visual Basic], visibility
- visibility [Visual Basic], variables
ms.assetid: 44b7f62a-cb5c-4d50-bce9-60ae68f87072
ms.openlocfilehash: 6e8d1178398711226b88fee7e6defd5162b91fcb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-control-the-scope-of-a-variable-visual-basic"></a>방법: 변수의 범위 제어(Visual Basic)
변수는 일반적으로 *범위*, 또는 참조를 선언 하면 영역 전체에 대 한 표시 합니다. 경우에 따라 변수의 *액세스 수준* 해당 범위에 영향을 줄 수 있습니다.  
  
 자세한 내용은 참조 [Visual Basic의 범위](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)합니다.  
  
## <a name="scope-at-block-or-procedure-level"></a>프로시저 수준 또는 블록 범위  
  
#### <a name="to-make-a-variable-visible-only-within-a-block"></a>변수는 블록 내 에서만 볼 수 있도록 하려면  
  
-   위치는 [Dim 문](../../../../visual-basic/language-reference/statements/dim-statement.md) 는 시작 하 고 간의 선언문 해당 블록의 예를 들어 종료 사이 변수에 대 한는 `For` 및 `Next` 설명의는 `For` 루프입니다.  
  
     블록 내 에서만 변수를 참조할 수 있습니다.  
  
#### <a name="to-make-a-variable-visible-only-within-a-procedure"></a>변수는 프로시저 내 에서만 볼 수 있도록 하려면  
  
-   위치는 `Dim` 프로시저 내에 있는 블록 외부에서 변수에 대 한 문을 (예:는 `With`... `End With` 블록).  
  
     절차에 포함 된 모든 블록을 포함 하 여 프로시저 내 에서만 변수를 참조할 수 있습니다.  
  
## <a name="scope-at-module-or-namespace-level"></a>모듈 또는 Namespace 수준 범위  
 편의 위해 제공 되는 단일 용어에 대 한 *모듈 수준* 모듈, 클래스 및 구조체에 동일 하 게 적용 됩니다. 모듈 수준 변수의 액세스 수준은 해당 범위를 결정합니다. 모듈, 클래스 또는 구조체를 포함 하는 네임 스페이스 범위를도 영향을 줍니다.  
  
#### <a name="to-make-a-variable-visible-throughout-a-module-class-or-structure"></a>변수를 전체 모듈, 클래스 또는 구조체에서 볼 수 있도록 하려면  
  
1.  위치는 `Dim` 프로시저 외부 모듈, 클래스 또는 구조체 내에서 변수에 대 한 문을 합니다.  
  
2.  포함는 [개인](../../../../visual-basic/language-reference/modifiers/private.md) 키워드는 `Dim` 문.  
  
3.  가 아니라 하지만 모듈, 클래스 또는 구조체 내에서 변수를 참조할 수 밖에 있습니다.  
  
#### <a name="to-make-a-variable-visible-throughout-a-namespace"></a>변수 네임 스페이스 전체에서 볼 수 있도록 하려면  
  
1.  위치는 `Dim` 프로시저 외부 모듈, 클래스 또는 구조체 내에서 변수에 대 한 문을 합니다.  
  
2.  포함는 [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) 또는 [공용](../../../../visual-basic/language-reference/modifiers/public.md) 키워드는 `Dim` 문.  
  
3.  어디에서 나 변수를 참조할 수 모듈, 클래스 또는 구조체를 포함 하는 네임 스페이스 내의 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 모듈 수준에서 변수를 선언 하 고 모듈 내의 코드를 참조할 수를 제한 합니다.  
  
```  
Module demonstrateScope  
    Private strMsg As String  
    Sub initializePrivateVariable()  
        strMsg = "This variable cannot be used outside this module."  
    End Sub  
    Sub usePrivateVariable()  
        MsgBox(strMsg)  
    End Sub  
End Module  
```  
  
 모듈에 정의 된 모든 프로시저 앞의 예제에서 `demonstrateScope` 를 참조할 수는 `String` 변수 `strMsg`합니다. 경우는 `usePrivateVariable` 프로시저가 호출을 문자열 변수의 내용을 표시 합니다. `strMsg` 대화 상자에서.  
  
 위의 예제에서는 문자열 변수를 다음과 같이 변경 하면 `strMsg` 선언의 네임 스페이스에 있는 모든 코드에서 참조할 수 있습니다.  
  
```  
Public strMsg As String  
```  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 실수로 동일한 이름 가진 다른 변수 참조에 대 한 더 적은 기회 변수의 좁을수록 범위 참조 일치 문제를 최소화할 수 있습니다.  
  
## <a name="net-framework-security"></a>.NET Framework 보안  
 변수의 범위 좁을수록를 사용 하 여 악성 코드가 부적절 하 게 가능성이 줄어듭니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic의 범위](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)  
 [Visual Basic의 수명](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)  
 [Visual Basic의 액세스 수준](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [변수](../../../../visual-basic/programming-guide/language-features/variables/index.md)  
 [변수 선언](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [Dim 문](../../../../visual-basic/language-reference/statements/dim-statement.md)
