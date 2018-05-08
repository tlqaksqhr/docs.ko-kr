---
title: '방법: Visual Basic에서 이벤트 처리기 호출'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- event handlers [Visual Basic], calling
- event handlers
- procedures [Visual Basic], event handlers
- procedures [Visual Basic], calling
ms.assetid: 72e18ef8-144e-40df-a1f4-066a57271e28
ms.openlocfilehash: 4e6aeaee8027e462dcdf80cae34b4b246fd58cf7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-call-an-event-handler-in-visual-basic"></a>방법: Visual Basic에서 이벤트 처리기 호출
*이벤트* 작업이 나 항목은-들면 마우스 클릭 또는 신용 한도 초과-응답 하도록 코드를 작성할 수에 대 한 일부 프로그램 구성 요소가 인식 되어 있습니다. *이벤트 처리기* 이벤트에 응답 하기 위해 작성 하는 코드입니다.  
  
 Visual Basic의 이벤트 처리기는는 `Sub` 프로시저입니다. 그러나 호출 하지 않으면 일반적으로 동일한 다른 방식으로 `Sub` 프로시저입니다. 대신, 이벤트에 대 한 처리기로 프로시저를 식별합니다. 이렇게 하려면 사용 하 여는 [처리](../../../../visual-basic/language-reference/statements/handles-clause.md) 절 및 [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) 변수 또는 [AddHandler 문](../../../../visual-basic/language-reference/statements/addhandler-statement.md)합니다. 사용 하는 `Handles` 절은 Visual Basic의 이벤트 처리기를 선언 하는 기본 방법입니다. 이 방법은 보고서 통합된 개발 환경 (IDE)에서 프로그래밍할 때 디자이너에서 이벤트 처리기를 작성 합니다. `AddHandler` 문에 런타임 시 동적으로 이벤트를 발생 시키기에 적합 합니다.  
  
 이벤트가 발생할 때 Visual Basic에서는 이벤트 처리기 프로시저를 자동으로 호출 합니다. 이벤트에 대 한 액세스 권한이 있는 모든 코드를 실행 하 여 발생 하 게 할 수는 [RaiseEvent 문](../../../../visual-basic/language-reference/statements/raiseevent-statement.md)합니다.  
  
 둘 이상의 이벤트 처리기를 동일한 이벤트와 연결할 수 있습니다. 경우에 따라 이벤트에서 처리기를 분리할 수 있습니다. 자세한 내용은 [이벤트](../../../../visual-basic/programming-guide/language-features/events/index.md)를 참조하세요.  
  
### <a name="to-call-an-event-handler-using-handles-and-withevents"></a>WithEvents와 핸들을 사용 하 여 이벤트 처리기를 호출 하려면  
  
1.  이벤트와 선언 되어 있는지 확인 한 [Event 문](../../../../visual-basic/language-reference/statements/event-statement.md)합니다.  
  
2.  모듈 또는 클래스 개체 변수를 사용 하 여 수준 선언 된 [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) 키워드입니다. `As` 절이이 변수에 대 한 이벤트를 발생 시키는 클래스를 지정 해야 합니다.  
  
3.  이벤트 처리의 선언에 `Sub` 프로시저 추가 [처리](../../../../visual-basic/language-reference/statements/handles-clause.md) 절을 지정 하는 `WithEvents` 변수 및 이벤트 이름입니다.  
  
4.  Visual Basic 자동으로 호출 이벤트가 발생할 때의 `Sub` 프로시저입니다. 코드에서 사용할 수는 `RaiseEvent` 문을 이벤트를 발생 합니다.  
  
     다음 예제에서는 이벤트를 정의 및 `WithEvents` 이벤트를 발생 시키는 클래스를 참조 하는 변수입니다. 이벤트 처리 `Sub` 프로시저는 한 `Handles` 절 클래스와를 처리 하는 이벤트를 지정 합니다.  
  
     [!code-vb[VbVbcnProcedures#4](./codesnippet/VisualBasic/how-to-call-an-event-handler_1.vb)]  
  
### <a name="to-call-an-event-handler-using-addhandler"></a>AddHandler를 사용 하 여 이벤트 처리기를 호출 하려면  
  
1.  이벤트와 선언 되어 있는지 확인 한 `Event` 문.  
  
2.  실행 프로그램 [AddHandler 문](../../../../visual-basic/language-reference/statements/addhandler-statement.md) 이벤트 처리를 동적으로 연결할 `Sub` 이벤트와 프로시저입니다.  
  
3.  Visual Basic 자동으로 호출 이벤트가 발생할 때의 `Sub` 프로시저입니다. 코드에서 사용할 수는 `RaiseEvent` 문을 이벤트를 발생 합니다.  
  
     다음 예제에서는 정의 `Sub` 처리 하는 프로시저는 <xref:System.Windows.Forms.Form.Closing> 폼의 이벤트입니다. 다음 사용 하 여는 [AddHandler 문](../../../../visual-basic/language-reference/statements/addhandler-statement.md) 연결 하는 `catchClose` 에 대 한 이벤트 처리기로 프로시저 <xref:System.Windows.Forms.Form.Closing>합니다.  
  
     [!code-vb[VbVbcnProcedures#5](./codesnippet/VisualBasic/how-to-call-an-event-handler_2.vb)]  
  
     실행 하 여 이벤트에서 이벤트 처리기를 분리할 수 있습니다는 [RemoveHandler 문](../../../../visual-basic/language-reference/statements/removehandler-statement.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [절차](./index.md)  
 [Sub 프로시저](./sub-procedures.md)  
 [Sub 문](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [AddressOf 연산자](../../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [방법: 프로시저 만들기](./how-to-create-a-procedure.md)  
 [방법: 값을 반환하지 않는 프로시저 호출](./how-to-call-a-procedure-that-does-not-return-a-value.md)
