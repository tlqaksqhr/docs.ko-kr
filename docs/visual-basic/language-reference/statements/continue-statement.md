---
title: "Continue Statement (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.continue"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Continue statement [Visual Basic]"
  - "loops, transferring to next iteration"
ms.assetid: 3ad00103-358b-4af3-a3a8-1b9ea0e995d3
caps.latest.revision: 21
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 21
---
# Continue Statement (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

루프의 다음 반복으로 제어가 바로 이동합니다.  
  
## 구문  
  
```  
Continue { Do | For | While }  
```  
  
## 설명  
 `Do`, `For` 또는 `While` 루프 내부에서 해당 루프의 다음 반복으로 이동할 수 있습니다.  제어가 루프 조건 테스트로 바로 전달됩니다. 이는 `For` 또는 `While` 문이나 `Until` 또는 `While` 절을 포함하고 있는 `Do` 또는 `Loop` 문으로 이동하는 것과 같습니다.  
  
 이동이 허용되는 루프 내의 모든 위치에서 `Continue`를 사용할 수 있습니다.  제어의 이동 규칙은 [GoTo Statement](../../../visual-basic/language-reference/statements/goto-statement.md)의 규칙과 같습니다.  
  
 예를 들어, 루프가 `Try` 블록, `Catch` 블록 또는 `Finally` 블록 내에 완전히 포함되어 있는 경우 `Continue`를 사용하여 루프의 외부로 이동할 수 있습니다.  한편 `Try`...`End Try` 구조가 루프 내에 포함되어 있는 경우에는 `Finally` 블록의 외부로 제어를 이동하는 데 `Continue`를 사용할 수 없으며 `Try`...`End Try` 구조의 외부로 완전히 이동하는 경우에만 `Try` 또는 `Catch` 블록의 외부로 이동하는 데 사용할 수 있습니다.  
  
 예를 들어, `Do` 루프가 다른 `Do` 루프 내에 있는 경우처럼 같은 형식의 루프가 중첩되어 있으면 `Continue Do` 문은 이 루프를 포함하고 있는 가장 안쪽의 `Do` 루프의 다음 반복으로 건너뜁니다.  같은 형식을 포함하고 있는 루프의 다음 반복으로 건너뛰는 데 `Continue`를 사용할 수 없습니다.  
  
 예를 들어, `Do` 루프가 `For` 루프 내에 있는 경우처럼 다른 형식의 루프가 중첩되어 있으면 `Continue Do` 또는 `Continue For`를 사용하여 두 루프 중 하나의 다음 반복으로 건너뛸 수 있습니다.  
  
## 예제  
 다음 코드 예제에서는 `Continue While` 문을 사용하여 제수가 0인 경우 배열의 다음 열으로 건너뜁니다.  `Continue While`은 `For` 루프 내부에 있으며  `While col < lastcol` 문으로 이동합니다. 즉, `For` 루프를 포함하고 있는 가장 안쪽의 `While` 루프의 다음 반복으로 이동합니다.  
  
 [!code-vb[VbVbalrStatements#14](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/continue-statement_1.vb)]  
  
## 참고 항목  
 [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md)   
 [For...Next 문](../../../visual-basic/language-reference/statements/for-next-statement.md)   
 [While...End While Statement](../../../visual-basic/language-reference/statements/while-end-while-statement.md)   
 [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)