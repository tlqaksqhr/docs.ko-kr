---
title: "Exit 문(Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Exit
helpviewer_keywords:
- execution [Visual Basic], ending
- files [Visual Basic], closing
- programs [Visual Basic], quitting
- code, exiting
- Exit statement [Visual Basic]
- program termination
- execution [Visual Basic], stopping
ms.assetid: 760bfb32-5c3f-4bdb-a432-9a6001c92db7
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2df63ecbf0605d07296e1692f18b1b015e27cd03
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="exit-statement-visual-basic"></a>Exit 문(Visual Basic)
프로시저 또는 블록을 종료 하 고 프로시저 호출 또는 블록 정의 다음 문으로 제어를 즉시 전달 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Exit { Do | For | Function | Property | Select | Sub | Try | While }  
```  
  
## <a name="statements"></a>문  
 `Exit Do`  
 즉시 끝내는 `Do` 을 반복 합니다. 실행이 계속 다음 문으로 `Loop` 문. `Exit Do`내 에서만 사용할 수는 `Do` 루프입니다. 사용할 경우 내에 중첩 `Do` 루프, `Exit Do` 가장 안쪽 루프를 끝내 고 중첩 다음으로 높은 수준으로 제어를 전달 합니다.  
  
 `Exit For`  
 즉시 끝내는 `For` 을 반복 합니다. 실행이 계속 다음 문으로 `Next` 문. `Exit For`내 에서만 사용할 수는 `For`... `Next` 또는 `For Each`... `Next` 루프입니다. 사용할 경우 내에 중첩 `For` 루프, `Exit For` 가장 안쪽 루프를 끝내 고 중첩 다음으로 높은 수준으로 제어를 전달 합니다.  
  
 `Exit Function`  
 즉시 끝내는 `Function` 나타나는 프로시저입니다. 실행이 계속 호출 하는 문을 다음 문으로 `Function` 프로시저입니다. `Exit Function`내 에서만 사용할 수는 `Function` 프로시저입니다.  
  
 반환 값을 지정 하려면 값 앞에 줄에 함수 이름에 할당할 수 있습니다는 `Exit Function` 문. 반환 값 할당 exit 하나의 문에서 함수를 대신 사용할 수 있습니다는 [Return 문을](../../../visual-basic/language-reference/statements/return-statement.md)합니다.  
  
 `Exit Property`  
 즉시 끝내는 `Property` 나타나는 프로시저입니다. 호출한 문의 실행이 계속는 `Property` 프로시저, 즉, 요청 하거나 속성의 값을 설정 합니다. `Exit Property`속성의 내 에서만 사용할 수 `Get` 또는 `Set` 프로시저입니다.  
  
 반환 값을 지정 하는 `Get` 프로시저, 함수 이름 앞에 있는 줄에 값을 할당할 수 있습니다는 `Exit Property` 문. 반환 값 및 종료를 할당 하는 `Get` 하나의 문에서 프로시저를 대신 사용할 수 있습니다는 `Return` 문.  
  
 에 `Set` 프로시저는 `Exit Property` 문을 같습니다는 `Return` 문.  
  
 `Exit Select`  
 즉시 끝내는 `Select Case` 나타나는 것을 차단 합니다. 실행이 계속 다음 문으로 `End Select` 문. `Exit Select`내 에서만 사용할 수는 `Select Case` 문.  
  
 `Exit Sub`  
 즉시 끝내는 `Sub` 나타나는 프로시저입니다. 실행이 계속 호출 하는 문을 다음 문으로 `Sub` 프로시저입니다. `Exit Sub`내 에서만 사용할 수는 `Sub` 프로시저입니다.  
  
 에 `Sub` 프로시저는 `Exit Sub` 문을 같습니다는 `Return` 문.  
  
 `Exit Try`  
 즉시 끝내는 `Try` 또는 `Catch` 나타나는 것을 차단 합니다. 실행이 계속는 `Finally` 블록 있는 경우, 또는 문 다음의 `End Try` 문. `Exit Try`내 에서만 사용할 수는 `Try` 또는 `Catch` 블록 내부가 아니라는 `Finally` 블록입니다.  
  
 `Exit While`  
 즉시 끝내는 `While` 을 반복 합니다. 실행이 계속 다음 문으로 `End While` 문. `Exit While`내 에서만 사용할 수는 `While` 루프입니다. 사용할 경우 내에 중첩 `While` 루프, `Exit While` 제어 루프 위에 중첩된 수준이 하나 있는 루프를 전달 여기서 `Exit While` 발생 합니다.  
  
## <a name="remarks"></a>설명  
 혼동 하지 마십시오. `Exit` 으로 문을 `End` 문. `Exit`문의 끝을 정의 하지 않습니다.  
  
## <a name="example"></a>예제  
 루프 조건에서 다음 예제에서는 루프를 중지 때는 `index` 변수는 100을 초과 합니다. 그러나 `If` 루프에 문을 지정 하면는 `Exit Do` 문의 인덱스 변수는 10 보다 큰 경우에 루프를 중지 합니다.  
  
 [!code-vb[VbVbalrStatements#133](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/exit-statement_1.vb)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 함수 이름에 반환 값을 할당 `myFunction`, 다음 사용 하 여 `Exit Function` 함수에서 반환할 수 있습니다.  
  
 [!code-vb[VbVbalrStatements#23](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/exit-statement_2.vb)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 [Return 문을](../../../visual-basic/language-reference/statements/return-statement.md) 반환 값을 할당 하는 함수를 종료 하려면.  
  
 [!code-vb[VbVbalrStatements#24](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/exit-statement_3.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [Continue 문](../../../visual-basic/language-reference/statements/continue-statement.md)  
 [Do...Loop 문](../../../visual-basic/language-reference/statements/do-loop-statement.md)  
 [End 문](../../../visual-basic/language-reference/statements/end-statement.md)  
 [For Each...Next 문](../../../visual-basic/language-reference/statements/for-each-next-statement.md)  
 [For...Next 문](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Return 문](../../../visual-basic/language-reference/statements/return-statement.md)  
 [Stop 문](../../../visual-basic/language-reference/statements/stop-statement.md)  
 [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Try...Catch...Finally 문](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
