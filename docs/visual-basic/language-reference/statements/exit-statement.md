---
title: "Exit Statement (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Exit"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "execution, ending"
  - "files, closing"
  - "programs, quitting"
  - "code, exiting"
  - "Exit statement"
  - "program termination"
  - "execution, stopping"
ms.assetid: 760bfb32-5c3f-4bdb-a432-9a6001c92db7
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# Exit Statement (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

프로시저나 블록을 끝내고 제어를 프로시저 호출이나 블록 정의 다음에 오는 문에 전달합니다.  
  
## 구문  
  
```  
Exit { Do | For | Function | Property | Select | Sub | Try | While }  
```  
  
## 문  
 `Exit Do`  
 `Do` 루프를 즉시 끝낼 때 사용합니다.  `Loop` 문 다음에 오는 문에서 실행이 계속됩니다.  `Exit Do`는 `Do` 루프 내에서만 사용할 수 있습니다.  중첩된 `Do` 루프 내에 `Exit Do`를 사용하면 Exit Do는 가장 안쪽의 루프를 끝내고 중첩 수준이 그 다음으로 높은 루프에 제어를 전달합니다.  
  
 `Exit For`  
 `For` 루프를 즉시 끝낼 때 사용합니다.  `Next` 문 다음에 오는 문에서 실행이 계속됩니다.  `Exit For`는 `For`...`Next` 또는 `For Each`...`Next` 루프 내에서만 사용할 수 있습니다.  중첩된 `For` 루프 내에 `Exit For`를 사용하면 Exit For는 가장 안쪽의 루프를 끝내고 중첩 수준이 그 다음으로 높은 루프에 제어를 전달합니다.  
  
 `Exit Function`  
 `Function` 프로시저를 즉시 끝낼 때 사용합니다.  `Function` 프로시저를 호출한 문 다음에 오는 문에서 실행이 계속됩니다.  `Exit Function`은 `Function` 프로시저 내에서만 사용할 수 있습니다.  
  
 반환 값을 지정하려면 `Exit Function` 문 앞에 있는 줄에 값을 함수 이름으로 지정할 수 있습니다.  반환 값을 지정하고 하나의 문에서 함수를 종료하려면 [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md)를 대신 사용할 수 있습니다.  
  
 `Exit Property`  
 `Property` 프로시저를 즉시 끝낼 때 사용합니다.  `Property` 프로시저를 호출한 문, 즉 속성의 값을 요청하거나 설정한 문에서 실행이 계속됩니다.  `Exit Property` 는 속성의 `Get` 또는 `Set` 프로시저 내에서만 사용할 수 있습니다.  
  
 `Get` 프로시저에 반환 값을 지정하려면 `Exit Property` 문 앞에 있는 줄에 값을 함수 이름으로 지정할 수 있습니다.  반환 값을 지정하고 하나의 문에서 `Get` 프로시저를 종료하려면 `Return` 문을 대신 사용할 수 있습니다.  
  
 `Set` 프로시저에서 `Exit Property` 문은 `Return` 문과 동일합니다.  
  
 `Exit Select`  
 `Select Case` 블록을 즉시 끝낼 때 사용합니다.  `End Select` 문 다음에 오는 문에서 실행이 계속됩니다.  `Exit Select`는 `Select Case` 문 내에서만 사용할 수 있습니다.  
  
 `Exit Sub`  
 `Sub` 프로시저를 즉시 끝낼 때 사용합니다.  `Sub` 프로시저를 호출한 문 다음에 오는 문에서 실행이 계속됩니다.  `Exit Sub`는 `Sub` 프로시저 내에서만 사용할 수 있습니다.  
  
 `Sub` 프로시저에서 `Exit Sub` 문은 `Return` 문과 동일합니다.  
  
 `Exit Try`  
 `Try` 또는 `Catch` 블록을 즉시 끝낼 때 사용합니다.  `Finally` 블록이 있는 경우 해당 블록에서 실행이 계속되고 이 블록이 없는 경우 `End Try` 문 다음에 오는 문에서 실행이 계속됩니다.  `Exit Try`는 `Finally` 블록 내부가 아니라 `Try` 또는 `Catch` 블록 내에서만 사용할 수 있습니다.  
  
 `Exit While`  
 `While` 루프를 즉시 끝낼 때 사용합니다.  `End While` 문 다음에 오는 문에서 실행이 계속됩니다.  `Exit While`은 `While` 루프 내에서만 사용할 수 있습니다.  중첩된 `While` 루프 내에서 `Exit While`을 사용하는 경우 `Exit While`이 발생하는 루프보다 중첩 수준이 하나 위인 루프로 제어를 전달합니다.  
  
## 설명  
 `Exit` 문과 `End` 문을 혼동하지 마십시오.  `Exit` 문은 문의 끝을 정의하지 않습니다.  
  
## 예제  
 다음 예에서는 `index` 변수가 100보다 클 때 루프 조건은 루프를 정지합니다.  하지만 루프에 `If` 문을 사용하면 인덱스 변수가 10보다 커질 때 `Exit Do` 문이 루프를 중단합니다.  
  
 [!code-vb[VbVbalrStatements#133](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/exit-statement_1.vb)]  
  
## 예제  
 다음 예제에서는 함수 이름 `myFunction`에 반환 값을 할당한 다음 `Exit Function` 문을 사용하여 함수에서 반환합니다.  
  
 [!code-vb[VbVbalrStatements#23](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/exit-statement_2.vb)]  
  
## 예제  
 다음 예제에서는 [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md)를 사용하여 반환 값을 지정하고 함수를 종료하는 방법을 보여줍니다.  
  
 [!code-vb[VbVbalrStatements#24](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/exit-statement_3.vb)]  
  
## 참고 항목  
 [Continue Statement](../../../visual-basic/language-reference/statements/continue-statement.md)   
 [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md)   
 [End Statement](../../../visual-basic/language-reference/statements/end-statement.md)   
 [For Each...Next 문](../../../visual-basic/language-reference/statements/for-each-next-statement.md)   
 [For...Next 문](../../../visual-basic/language-reference/statements/for-next-statement.md)   
 [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md)   
 [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md)   
 [Stop Statement](../../../visual-basic/language-reference/statements/stop-statement.md)   
 [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Try...Catch...Finally Statement](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)