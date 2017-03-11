---
title: "How to: Call a Procedure that Does Not Return a Value (Visual Basic) | Microsoft Docs"
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
  - "procedure calls, returning values"
  - "Visual Basic code, procedures"
  - "procedures, calling"
ms.assetid: 259b49a3-a3c1-4254-ba8c-73cdc4127703
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# How to: Call a Procedure that Does Not Return a Value (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

`Sub` 프로시저는 호출 코드에 값을 반환하지 않습니다.  독립 실행형 호출 문을 사용하여 프로시저를 명시적으로 호출합니다.  식 내에서 프로시저 이름을 사용하여 프로시저를 호출할 수는 없습니다.  
  
### Sub 프로시저를 호출하려면  
  
1.  이름이 지정 된 `Sub` 절차.  
  
2.  프로시저 이름 다음에 인수 목록을 괄호로 묶어 지정합니다.  인수가 없으면 괄호를 생략해도 됩니다.  그러나 괄호를 사용하면 코드가 읽기 쉬워집니다.  
  
3.  인수 목록의 인수를 괄호로 묶고 쉼표로 구분합니다.  `Sub` 프로시저에서 해당 매개 변수를 정의하는 순서와 동일한 순서대로 인수를 지정해야 합니다.  
  
     다음 예제에서는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> 함수를 호출하여 응용 프로그램 창을 활성화합니다.  <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A>는 창 제목을 단독 인수로 사용합니다.  그리고 호출 코드에 값을 반환하지 않습니다.  메모장 프로세스를 실행하고 있지 않을 경우 이 예제는 <xref:System.ArgumentException>을 throw합니다.  `Shell` 프로시저에서는 응용 프로그램이 지정된 경로에 있는 것으로 간주합니다.  
  
     [!code-vb[VbVbalrCatRef#11](../../../../visual-basic/programming-guide/language-features/procedures/codesnippet/visualbasic/how-to-call-a-procedure-_1_1.vb)]  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.Interaction.Shell%2A>   
 <xref:System.ArgumentException>   
 [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Sub Procedures](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Sub Statement](../../../../visual-basic/language-reference/statements/sub-statement.md)   
 [How to: Create a Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-create-a-procedure.md)   
 [How to: Call a Procedure That Returns a Value](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-a-procedure-that-returns-a-value.md)   
 [How to: Call an Event Handler in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-event-handler.md)