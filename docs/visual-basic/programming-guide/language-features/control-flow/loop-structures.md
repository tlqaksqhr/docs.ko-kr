---
title: "Loop Structures (Visual Basic) | Microsoft Docs"
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
  - "control flow, loops"
  - "For keyword [Visual Basic], loop structures"
  - "loops"
  - "loop structures"
  - "statements [Visual Basic], loop"
  - "Do statement, Do loops"
  - "conditional statements, loop structures"
ms.assetid: ecacb09b-a4c9-42be-98b2-a15d368b5db8
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# Loop Structures (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 루프 구조를 사용하면 한 줄 이상의 코드를 반복해서 실행할 수 있습니다.  조건이 `True` 또는 `False`일 때까지 루프 구조에서 지정된 횟수만큼 또는 컬렉션의 각 요소에 대해 한 번씩 문을 반복할 수 있습니다.  
  
 다음 그림에서는 조건이 true가 될 때까지 문의 집합을 실행하는 루프 구조를 보여 줍니다.  
  
 ![Do...Until 루프의 순서도](../../../../visual-basic/programming-guide/language-features/control-flow/media/dountilloop.gif "DoUntilLoop")  
조건이 true가 될 때까지 문의 집합 실행  
  
## While 루프  
 `While`...`End While` 구문은 `While` 문에 지정된 조건이 `True`인 동안 문의 집합을 실행합니다.  자세한 내용은 [While...End While Statement](../../../../visual-basic/language-reference/statements/while-end-while-statement.md)을 참조하십시오.  
  
## Do 루프  
 `Do`...`Loop` 구문을 사용하면 루프 구조의 시작 부분이나 끝 부분에서 조건을 테스트할 수 있습니다.  조건이 `True` 상태인 동안 루프를 반복할지 또는 조건이 `True`가 될 때까지 루프를 반복할지 여부를 지정할 수도 있습니다.  자세한 내용은 [Do...Loop Statement](../../../../visual-basic/language-reference/statements/do-loop-statement.md)을 참조하십시오.  
  
## For 루프  
 `For`...`Next` 구문은 루프를 횟수만큼 수행합니다.  이 구문은 *카운터*라고도 하는 루프 제어 변수를 사용하여 반복을 추적합니다.  이 카운터에 대한 시작 값과 끝 값을 지정하고, 하나의 반복에서 다음 반복으로 증가하는 정도를 선택적으로 지정할 수 있습니다.  자세한 내용은 [For...Next 문](../../../../visual-basic/language-reference/statements/for-next-statement.md)을 참조하십시오.  
  
## For Each 루프  
 `For Each`...`Next` 구문은 컬렉션의 각 요소에 대해 문의 집합을 한 번 실행합니다.  루프 제어 변수는 지정하지만, 시작 값과 끝 값을 결정할 필요는 없습니다.  자세한 내용은 [For Each...Next 문](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)을 참조하십시오.  
  
## 참고 항목  
 [Control Flow](../../../../visual-basic/programming-guide/language-features/control-flow/index.md)   
 [Decision Structures](../../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)   
 [Other Control Structures](../../../../visual-basic/programming-guide/language-features/control-flow/other-control-structures.md)   
 [Nested Control Structures](../../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)