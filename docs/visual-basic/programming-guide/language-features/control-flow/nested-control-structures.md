---
title: "Nested Control Structures (Visual Basic) | Microsoft Docs"
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
  - "Visual Basic code, control flow"
  - "control structures, nested"
  - "conditional statements, nested"
  - "statements [Visual Basic], control flow"
  - "control flow, nested control statements"
  - "structures, nested control"
  - "nested control statements"
ms.assetid: cf60b061-65d9-44a8-81f2-b0bdccd23a05
caps.latest.revision: 20
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 20
---
# Nested Control Structures (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

예를 들면 `For...Next` 루프 내의 `If...Then...Else` 블록과 같이 다른 제어문 내부에 제어문을 둘 수 있습니다.  다른 제어문 내부에 있는 제어문을 *중첩* 제어문이라고 합니다.  
  
## 중첩 수준  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 제어 구조를 원하는 수준만큼 중첩할 수 있습니다.  일반적으로 각각의 본문을 들여쓰기하여 중첩 구조를 보다 읽기 쉽게 합니다.  IDE\(통합 개발 환경\) 편집기에서는 이 작업을 자동으로 수행합니다.  
  
 다음 예제의 `sumRows` 프로시저는 매트릭스에 있는 각 행의 양의 요소를 모두 더합니다.  
  
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
  
 위의 예제에서 첫 번째 `Next` 문은 안쪽 `For` 루프를 닫고, 마지막 `Next` 문은 바깥쪽 `For` 루프를 닫습니다.  
  
 마찬가지로 중첩 `If` 문에서 `End If` 문은 앞에서 가장 가까운 `If` 문에 자동으로 적용됩니다.  중첩 `Do` 루프도 비슷한 방식이며, 가장 안쪽의 `Do` 문이 가장 안쪽의 `Loop` 문에 대응됩니다.  
  
> [!NOTE]
>  대부분의 제어 구조에서는 키워드를 클릭하면 구조의 모든 키워드가 강조 표시됩니다.  예를 들어 `If...Then...Else` 구문에서 `If`를 클릭하면 구문에서 `If`, `Then`, `ElseIf`, `Else`및 `End If`의 모든 인스턴스가 강조 표시됩니다.  강조 표시된 이전 키워드나 다음 키워드로 이동하려면 Ctrl\+Shift\+아래쪽 화살표 또는 Ctrl\+Shift\+위쪽 화살표를 누릅니다.  
  
## 다른 종류의 제어 구조 중첩  
 제어 구조를 다른 종류의 제어 구조에 중첩할 수 있습니다.  다음 예제에서는 `For Each` 루프 내에 `With` 블록을 사용하고, `With` 블록 내에 중첩 `If` 블록을 사용합니다.  
  
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
  
## 제어 구조 겹치기  
 제어 구조는 겹칠 수 없습니다.  즉, 모든 중첩 구조는 다음의 가장 안쪽 구조 내에 완전히 포함되어야 합니다.  예를 들어, 다음과 같은 배치는 안쪽 `With` 블록이 종료되기 전에 `For` 루프가 종료되므로 올바르지 않습니다.  
  
 ![잘못된 중첩의 그래픽 다이어그램](../../../../visual-basic/programming-guide/language-features/control-flow/media/nestexampleinvalid.png "NestExampleInvalid")  
For 및 With 구조의 잘못된 중첩  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 컴파일러에서는 이렇게 겹치는 제어 구조를 감지하고 컴파일 타임 오류를 발생시킵니다.  
  
## 참고 항목  
 [Control Flow](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)   
 [Decision Structures](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)   
 [Loop Structures](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)   
 [Other Control Structures](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)