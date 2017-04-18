---
title: "방법: Visual Basic에서 이벤트 처리기를 호출 합니다. | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic code, procedures
- event handlers, calling
- event handlers
- procedures, event handlers
- procedures, calling
ms.assetid: 72e18ef8-144e-40df-a1f4-066a57271e28
caps.latest.revision: 19
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: c5b300feca3415d1283d24179795a4ae92c61e52
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-call-an-event-handler-in-visual-basic"></a>방법: Visual Basic에서 이벤트 처리기 호출
*이벤트* 작업 또는 항목은 — 들면 마우스 클릭 이나 신용 한도 초과-응답 하 고 코드를 작성할 수 있는 일부 프로그램 구성 요소에 의해 인식 되어 있습니다. *이벤트 처리기* 이벤트에 응답 하기 위해 작성 하는 코드입니다.  
  
 이벤트 처리기가 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 는 `Sub` 프로시저입니다. 그러나 호출 하지 않으면 일반적으로 동일한 다른 방식으로 `Sub` 프로시저입니다. 대신, 이벤트에 대 한 처리기로 프로시저를 식별 합니다. 이렇게 하려면 사용 하 여는 [처리](../../../../visual-basic/language-reference/statements/handles-clause.md) 절 및 [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) 변수 또는 [AddHandler 문](../../../../visual-basic/language-reference/statements/addhandler-statement.md)합니다. 사용 하는 `Handles` 절에서 이벤트 처리기를 선언 하는 기본 방법은 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]합니다. 이 방법은 통합된 개발 환경 (IDE)에서 프로그래밍할 때 이벤트 처리기는 디자이너에 의해 기록 됩니다. `AddHandler` 문에 런타임에 동적으로 이벤트를 발생 시키기에 적합 합니다.  
  
 이벤트가 발생할 때 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 자동으로 이벤트 처리기 프로시저를 호출 합니다. 이벤트에 대 한 액세스 권한이 있는 모든 코드를 사용 하면 실행 하 여 발생 하는 [RaiseEvent 문](../../../../visual-basic/language-reference/statements/raiseevent-statement.md)합니다.  
  
 동일한 이벤트와 둘 이상의 이벤트 처리기를 연결할 수 있습니다. 일부 경우에는 이벤트 처리기를 분리할 수 있습니다. 자세한 내용은 참조 [이벤트](../../../../visual-basic/programming-guide/language-features/events/index.md)합니다.  
  
### <a name="to-call-an-event-handler-using-handles-and-withevents"></a>핸들 및 WithEvents를 사용 하 여 이벤트 처리기를 호출 하려면  
  
1.  이벤트 선언 되었는지 확인 되는 [Event 문](../../../../visual-basic/language-reference/statements/event-statement.md)합니다.  
  
2.  모듈 또는 클래스에서 개체 변수를 사용 하 여 수준 선언 된 [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) 키워드입니다. `As` 절이이 변수에 대 한 이벤트를 발생 시키는 클래스를 지정 해야 합니다.  
  
3.  이벤트 처리의 선언에 `Sub` 프로시저를 추가 [처리](../../../../visual-basic/language-reference/statements/handles-clause.md) 절을 지정 하는 `WithEvents` 변수 및 이벤트 이름입니다.  
  
4.  이벤트가 발생할 때 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 자동으로 호출 된 `Sub` 프로시저입니다. 코드에서 사용할 수는 `RaiseEvent` 이벤트를 발생 하는 문입니다.  
  
     다음 예제에서는 이벤트를 정의 및 `WithEvents` 이벤트를 발생 시키는 클래스를 참조 하는 변수입니다. 이벤트 처리 `Sub` 프로시저는 한 `Handles` 절을 지정 하는 클래스와 이벤트를 처리 합니다.  
  
     [!code-vb[VbVbcnProcedures #&4;](./codesnippet/VisualBasic/how-to-call-an-event-handler_1.vb)]  
  
### <a name="to-call-an-event-handler-using-addhandler"></a>AddHandler를 사용 하 여 이벤트 처리기를 호출 하려면  
  
1.  이벤트 선언 되었는지 확인 되는 `Event` 문입니다.  
  
2.  실행 프로그램 [AddHandler 문](../../../../visual-basic/language-reference/statements/addhandler-statement.md) 이벤트 처리를 동적으로 연결할 `Sub` 이벤트와 프로시저입니다.  
  
3.  이벤트가 발생할 때 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 자동으로 호출 된 `Sub` 프로시저입니다. 코드에서 사용할 수는 `RaiseEvent` 이벤트를 발생 하는 문입니다.  
  
     다음 예제에서는 정의 `Sub` 를 처리 하는 절차는 <xref:System.Windows.Forms.Form.Closing>폼의 이벤트.</xref:System.Windows.Forms.Form.Closing> 다음 사용 하 여는 [AddHandler 문](../../../../visual-basic/language-reference/statements/addhandler-statement.md) 연결 하는 `catchClose` <xref:System.Windows.Forms.Form.Closing>.</xref:System.Windows.Forms.Form.Closing> 에 대 한 이벤트 처리기와 프로시저  
  
     [!code-vb[VbVbcnProcedures #&5;](./codesnippet/VisualBasic/how-to-call-an-event-handler_2.vb)]  
  
     실행 하 여 이벤트에서 이벤트 처리기를 분리할 수는 [RemoveHandler 문](../../../../visual-basic/language-reference/statements/removehandler-statement.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [프로시저](./index.md)   
 [Sub 프로시저](./sub-procedures.md)   
 [Sub 문](../../../../visual-basic/language-reference/statements/sub-statement.md)   
 [AddressOf 연산자](../../../../visual-basic/language-reference/operators/addressof-operator.md)   
 [방법: 프로시저 만들기](./how-to-create-a-procedure.md)   
 [방법: 값을 반환하지 않는 프로시저 호출](./how-to-call-a-procedure-that-does-not-return-a-value.md)
