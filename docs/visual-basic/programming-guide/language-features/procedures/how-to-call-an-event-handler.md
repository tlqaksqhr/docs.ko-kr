---
title: "How to: Call an Event Handler in Visual Basic | Microsoft Docs"
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
  - "Visual Basic code, procedures"
  - "event handlers, calling"
  - "event handlers"
  - "procedures, event handlers"
  - "procedures, calling"
ms.assetid: 72e18ef8-144e-40df-a1f4-066a57271e28
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# How to: Call an Event Handler in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

*이벤트*는 특정 프로그램 구성 요소에 의해 인식되어 응답하는 코드를 작성할 수 있도록 하는 동작의 발생으로서 예를 들면 마우스 클릭이나 신용 한도 초과 등이 있습니다.  *이벤트 처리기*는 이벤트에 응답하기 위해 작성하는 코드입니다.  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]의 이벤트 처리기는 `Sub` 프로시저입니다.  그러나 일반적으로 이 프로시저를 다른 `Sub` 프로시저와 같은 방법으로 호출하지는 않습니다.  대신에 이 프로시저를 이벤트에 대한 처리기로 식별합니다.  이렇게 하려면 [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) 절과 [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) 변수를 사용하거나 [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md)을 사용합니다.  `Handles` 절을 사용하는 것은 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서 이벤트 처리기를 선언하는 기본 방법입니다.  IDE\(통합 개발 환경\)에서 프로그래밍하는 경우 디자이너는 이러한 방법으로 이벤트 처리기를 작성합니다.  `AddHandler` 문은 런타임에 이벤트를 동적으로 발생시키는 데 적합합니다.  
  
 이벤트가 발생하면 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 이벤트 처리기 프로시저를 자동으로 호출합니다.  이벤트에 액세스할 수 있는 모든 코드에서 [RaiseEvent Statement](../../../../visual-basic/language-reference/statements/raiseevent-statement.md)을 실행하여 이러한 작업을 수행할 수 있습니다.  
  
 둘 이상의 이벤트 처리기를 동일한 이벤트에 연결할 수 있습니다.  경우에 따라 이벤트에서 처리기를 분리할 수 있습니다.  자세한 내용은 [Events](../../../../visual-basic/programming-guide/language-features/events/events.md)를 참조하십시오.  
  
### Handles 및 WithEvents를 사용하여 이벤트 처리기를 호출하려면  
  
1.  이벤트가 [Event Statement](../../../../visual-basic/language-reference/statements/event-statement.md)으로 선언되는지 확인합니다.  
  
2.  [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) 키워드를 사용하여 모듈 또는 클래스 수준에서 개체 변수를 선언합니다.  이 변수의 `As` 절은 이벤트를 발생시키는 클래스를 지정해야 합니다.  
  
3.  이벤트 처리 `Sub` 프로시저의 선언에서 `WithEvents` 변수와 이벤트 이름을 지정하는 [Handles](../../../../visual-basic/language-reference/statements/handles-clause.md) 절을 추가합니다.  
  
4.  이벤트가 발생하면 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]은 `Sub` 프로시저를 자동으로 호출합니다.  코드에서는 `RaiseEvent` 문을 사용하여 이벤트를 발생시킬 수 있습니다.  
  
     다음 예제에서는 이벤트와 이벤트를 발생시키는 클래스를 참조하는 `WithEvents` 변수를 정의합니다.  이벤트 처리 `Sub` 프로시저는 `Handles` 절을 사용하여 자신이 처리하는 클래스와 이벤트를 지정합니다.  
  
     [!code-vb[VbVbcnProcedures#4](./codesnippet/VisualBasic/how-to-call-an-event-handler_1.vb)]  
  
### AddHandler를 사용하여 이벤트 처리기를 호출하려면  
  
1.  이벤트가 `Event` 문으로 선언되는지 확인합니다.  
  
2.  [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md)을 실행하여 이벤트 처리 `Sub` 프로시저를 이벤트와 동적으로 연결합니다.  
  
3.  이벤트가 발생하면 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]은 `Sub` 프로시저를 자동으로 호출합니다.  코드에서는 `RaiseEvent` 문을 사용하여 이벤트를 발생시킬 수 있습니다.  
  
     다음 예제에서는 폼의 <xref:System.Windows.Forms.Form.Closing> 이벤트를 처리하기 위해 `Sub` 프로시저를 정의합니다.  그런 다음 [AddHandler Statement](../../../../visual-basic/language-reference/statements/addhandler-statement.md)을 사용하여 `catchClose` 프로시저를 <xref:System.Windows.Forms.Form.Closing>에 대한 이벤트 처리기로 연결합니다.  
  
     [!code-vb[VbVbcnProcedures#5](./codesnippet/VisualBasic/how-to-call-an-event-handler_2.vb)]  
  
     [RemoveHandler Statement](../../../../visual-basic/language-reference/statements/removehandler-statement.md)을 실행하여 이벤트에서 이벤트 처리기를 분리할 수 있습니다.  
  
## 참고 항목  
 [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Sub Procedures](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)   
 [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md)   
 [AddressOf Operator](../../../../visual-basic/language-reference/operators/addressof-operator.md)   
 [How to: Create a Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-create-a-procedure.md)   
 [How to: Call a Procedure that Does Not Return a Value](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-a-procedure-that-does-not-return-a-value.md)