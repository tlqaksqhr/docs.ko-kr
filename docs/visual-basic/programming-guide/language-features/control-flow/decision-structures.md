---
title: "Decision Structures (Visual Basic) | Microsoft Docs"
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
  - "statements [Visual Basic], control flow"
  - "If statement, decision structures"
  - "If statement, If...Then...Else"
  - "control flow, decision structures"
  - "decision structures"
  - "conditional statements, decision structures"
ms.assetid: 2e2e0895-4483-442a-b17c-26aead751ec2
caps.latest.revision: 29
caps.handback.revision: 29
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Decision Structures (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서는 조건을 테스트하고 테스트 결과에 따라 여러 가지 작업을 수행할 수 있습니다.  조건이 true인지 아니면 false인지 그리고 식의 여러 가지 값을 테스트하거나 문을 실행할 때 생성되는 여러 가지 예외를 테스트할 수 있습니다.  
  
 다음 그림에서는 조건이 true인지 테스트하고, true 또는 false의 여부에 따라 각기 다른 작업을 수행하는 판단 구조를 보여 줍니다.  
  
 ![If...Then...Else 생성의 순서도](../../../../visual-basic/programming-guide/language-features/control-flow/media/ifthenelse.gif "IfThenElse")  
조건이 true인 경우와 false인 경우 다른 작업 수행  
  
## If...Then...Else 구문  
 `If...Then...Else` 구문을 사용하면 하나 이상의 조건을 테스트하고 각 조건에 따라 하나 이상의 문을 실행할 수 있습니다.  다음과 같은 방법으로 조건을 테스트하고 작업을 수행할 수 있습니다.  
  
-   조건이 `True`인 경우 하나 이상의 문을 실행합니다.  
  
-   조건이 `False`인 경우 하나 이상의 문을 실행합니다.  
  
-   조건이 `True`인 경우 몇 개의 문을 실행하고, 조건이 `False`인 경우 다른 문을 실행합니다.  
  
-   이전 조건이 `False`인 경우 추가 조건을 테스트합니다.  
  
 이러한 모든 가능성을 제공하는 제어 구조는 [If...Then...Else Statement](../../../../visual-basic/language-reference/statements/if-then-else-statement.md)입니다.  실행할 테스트와 문이 하나인 경우 한 줄 버전을 사용할 수 있습니다.  조건과 작업이 보다 복잡한 경우에는 여러 줄로 이루어진 버전을 사용할 수 있습니다.  
  
## Select...Case 구문  
 `Select...Case` 구문을 사용하면 식을 한 번 계산한 후 사용할 수 있는 각기 다른 값을 기반으로 다양한 문을 실행할 수 있습니다.  자세한 내용은 [Select...Case Statement](../../../../visual-basic/language-reference/statements/select-case-statement.md)을 참조하십시오.  
  
## Try...Catch...Finally 구문  
 `Try...Catch...Finally` 구문을 사용하면 예외를 발생시키는 문이 있을 때 제어를 유지하는 환경에서 여러 문을 실행할 수 있습니다.  서로 다른 예외에 대해 다른 작업을 수행할 수 있습니다.  전체 `Try...Catch...Finally` 구문을 종료하기 전에 어떤 경우에서도 실행되도록 코드 블록을 선택적으로 지정할 수 있습니다.  자세한 내용은 [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)을 참조하십시오.  
  
> [!NOTE]
>  대부분의 제어 구조에서는 키워드를 클릭하면 구조의 모든 키워드가 강조 표시됩니다.  예를 들어 `If...Then...Else` 구문에서 `If`를 클릭하면 구문에서 `If`, `Then`, `ElseIf`, `Else`및 `End If`의 모든 인스턴스가 강조 표시됩니다.  강조 표시된 이전 키워드나 다음 키워드로 이동하려면 Ctrl\+Shift\+아래쪽 화살표 또는 Ctrl\+Shift\+위쪽 화살표를 누릅니다.  
  
## 참고 항목  
 [Control Flow](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)   
 [Loop Structures](../../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)   
 [Other Control Structures](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)   
 [Nested Control Structures](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)   
 [If Operator](../../../../visual-basic/language-reference/operators/if-operator.md)