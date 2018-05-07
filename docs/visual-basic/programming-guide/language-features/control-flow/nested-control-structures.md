---
title: 중첩 제어 구조(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, control flow
- control structures [Visual Basic], nested
- conditional statements [Visual Basic], nested
- statements [Visual Basic], control flow
- control flow [Visual Basic], nested control statements
- structures [Visual Basic], nested control
- nested control statements [Visual Basic]
ms.assetid: cf60b061-65d9-44a8-81f2-b0bdccd23a05
ms.openlocfilehash: ec3d4d477290480cdfa0f5b1c88aa82c81040d11
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="nested-control-structures-visual-basic"></a>중첩 제어 구조(Visual Basic)
예를 들어 다른 제어 문의 내부에 제어 문을 배치할 수 있습니다는 `If...Then...Else` 블록 내에 `For...Next` 루프입니다. 다른 컨트롤 문 안에 있는 제어 문을 라고 *중첩*합니다.  
  
## <a name="nesting-levels"></a>중첩 수준  
 Visual Basic의 제어 구조 수준 원하는 만큼 중첩할 수 있습니다. 각각의 본문을 들여쓰 중첩된 구조를 보다 쉽게 읽을 수 있도록 하는 일반적인이 좋습니다. 통합된 개발 환경 (IDE) 편집기 자동으로 수행할 수 있습니다.  
  
 다음 예제에서는 절차 `sumRows` 행렬의 각 행의 양의 요소를 추가 합니다.  
  
```  
Public Sub sumRows(ByVal a(,) As Double, ByRef r() As Double)  
    Dim i, j As Integer  
    For i = 0 To UBound(a, 1)  
        r(i) = 0  
        For j = 0 To UBound(a, 2)  
            If a(i, j) > 0 Then  
                r(i) = r(i) + a(i, j)  
            End If  
        Next j  
    Next i  
End Sub  
```  
  
 앞의 예제에서 첫 번째 `Next` 문을 닫습니다 내부 `For` 루프 및 마지막 `Next` 문을 닫습니다는 외부 `For` 루프입니다.  
  
 마찬가지로 중첩 `If` 문에서 `End If` 문 앞에서 가장 가까운에 자동으로 적용 `If` 문. 중첩 된 `Do` 루프 가장 안쪽의 비슷한 방식으로 `Loop` 가장 안쪽의 일치 하는 문을 `Do` 문.  
  
> [!NOTE]
>  대부분의 제어 구조에 대 한 키워드를 클릭할 때 모든 키워드 구조에서 강조 표시 됩니다. 예를 들어, 클릭 하면 `If` 에 `If...Then...Else` 생성, 함수의 모든 인스턴스의 `If`, `Then`, `ElseIf`, `Else`, 및 `End If` 생성에서의 강조 표시 됩니다. 다음 또는 이전 강조 표시 된 키워드를 이동 하려면 CTRL + SHIFT + 아래쪽 화살표 또는 CTRL + SHIFT + 위쪽 화살표 키를 누릅니다.  
  
## <a name="nesting-different-kinds-of-control-structures"></a>다른 종류의 제어 구조를 중첩합니다.  
 한 가지 다른 종류의 제어 구조를 중첩할 수 있습니다. 다음 예제에서는 `With` 내 차단는 `For Each` 루프와 중첩 `If` 블록 내에서 `With` 블록.  
  
```  
For Each ctl As System.Windows.Forms.Control In Me.Controls  
    With ctl  
        .BackColor = System.Drawing.Color.Yellow  
        .ForeColor = System.Drawing.Color.Black  
        If .CanFocus Then  
            .Text = "Colors changed"  
            If Not .Focus() Then  
                ' Insert code to process failed focus.  
            End If  
        End If  
    End With  
Next ctl  
```  
  
## <a name="overlapping-control-structures"></a>중첩 제어 구조  
 제어 구조를 겹칠 수 없습니다. 즉, 모든 중첩된 구조는 다음 가장 안쪽 구조 내에 완전히 포함 되어야 합니다. 예를 들어 다음과 같은 배치 유효 하지 때문에 `For` 루프가 종료 전에 내부 `With` 블록을 종료 합니다.  
  
 ![잘못 된 중첩의 그래픽 다이어그램](../../../../visual-basic/programming-guide/language-features/control-flow/media/nestexampleinvalid.gif "NestExampleInvalid")  
에 대 한 및 구조에 잘못 된 중첩의  
  
 Visual Basic 컴파일러는 이러한 겹치는 제어 구조를 감지 하 고 컴파일 타임 오류를 발생 시킵니다.  
  
## <a name="see-also"></a>참고 항목  
 [제어 흐름](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)  
 [판단 구조](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)  
 [루프 구조](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [기타 제어 구조](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)
