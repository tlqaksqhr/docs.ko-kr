---
title: '방법: 값을 반환하지 않는 프로시저 호출(Visual Basic)'
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
ms.assetid: 259b49a3-a3c1-4254-ba8c-73cdc4127703
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: bb9f13d5387f4a440a7fdd39c5e8f50cb8d56270
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-call-a-procedure-that-does-not-return-a-value-visual-basic"></a>방법: 값을 반환하지 않는 프로시저 호출(Visual Basic)
A `Sub` 프로시저가 호출 코드에 값을 반환 하지 않습니다. 하면 명시적으로 호출 독립 실행형 호출 문을 사용 합니다. 식 내에서 프로시저 이름을 사용 하 여 호출할 수 없습니다.  
  
### <a name="to-call-a-sub-procedure"></a>Sub 프로시저를 호출 하려면  
  
1.  이름을 지정는 `Sub` 프로시저입니다.  
  
2.  프로시저 이름으로 인수 목록을 묶는 괄호를 따릅니다. 인수가 없는 경우에 필요에 따라 괄호를 생략할 수 있습니다. 그러나 괄호를 사용 하는 코드 보다 쉽게 읽을 수 있습니다.  
  
3.  쉼표로 구분 하 여는 괄호 안에 인수 목록에서 인수를 배치 합니다. 와 같은 순서로 인수를 지정 해야 하는 `Sub` 프로시저가 해당 매개 변수를 정의 합니다.  
  
     다음 예제에서는 Visual Basic <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> 함수를 응용 프로그램 창을 활성화 합니다. <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> 창 제목에는 유일한 인수로 사용 합니다. 호출 코드에는 값을 반환 하지 않습니다. 이 예제에서는 throw 메모장 프로세스를 실행 하지 않는 경우는 <xref:System.ArgumentException>합니다. `Shell` 프로시저 응용 프로그램은 지정 된 경로 있는 것으로 가정 합니다.  
  
     [!code-vb[VbVbalrCatRef#11](./codesnippet/VisualBasic/how-to-call-a-procedure-that-does-not-return-a-value_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.Interaction.Shell%2A>  
 <xref:System.ArgumentException>  
 [절차](./index.md)  
 [Sub 프로시저](./sub-procedures.md)  
 [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)  
 [Sub 문](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [방법: 프로시저 만들기](./how-to-create-a-procedure.md)  
 [방법: 값을 반환하는 프로시저 호출](./how-to-call-a-procedure-that-returns-a-value.md)  
 [방법: Visual Basic의 이벤트 처리기를 호출 합니다.](./how-to-call-an-event-handler.md)
