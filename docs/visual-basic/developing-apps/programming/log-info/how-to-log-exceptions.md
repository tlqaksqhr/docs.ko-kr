---
title: "How to: Log Exceptions in Visual Basic | Microsoft Docs"
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
  - "exceptions, logging"
  - "exceptions, tracking"
ms.assetid: a26c60e2-ae39-444a-aebb-33eccadc0eeb
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# How to: Log Exceptions in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

`My.Application.Log` 및 `My.Log` 개체를 사용하여 응용 프로그램에서 발생하는 예외에 대한 정보를 기록할 수 있습니다.  이들 예제에서는 `My.Application.Log.WriteException` 메서드를 사용하여 명시적으로 catch하는 예외와 처리되지 않은 예외를 기록하는 방법을 보여 줍니다.  
  
 추적 정보 로깅에는 `My.Application.Log.WriteEntry` 메서드를 사용합니다.  자세한 내용은 <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>를 참조하십시오.  
  
### 처리된 예외를 기록하려면  
  
1.  예외 정보를 생성할 메서드를 만듭니다.  
  
     [!code-vb[VbVbalrMyApplicationLog#9](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_1.vb)]  
  
2.  `Try...Catch` 블록을 사용하여 예외를 catch합니다.  
  
     [!code-vb[VbVbalrMyApplicationLog#6](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_2.vb)]  
  
3.  예외를 생성할 수 있는 코드를 `Try` 블록에 넣습니다.  
  
     `Dim` 및 `MsgBox` 줄의 주석을 해제하여 <xref:System.NullReferenceException> 예외를 발생시킵니다.  
  
     [!code-vb[VbVbalrMyApplicationLog#7](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_3.vb)]  
  
4.  `Catch` 블록에서 `My.Application.Log.WriteException` 메서드를 사용하여 예외 정보를 씁니다.  
  
     [!code-vb[VbVbalrMyApplicationLog#8](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_4.vb)]  
  
     다음 예제에서는 처리 된 예외를 기록 하기 위한 전체 코드를 보여 줍니다.  
  
     [!code-vb[VbVbalrMyApplicationLog#10](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_5.vb)]  
  
### 처리되지 않은 예외를 기록하려면  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.  **프로젝트** 메뉴에서 **속성**을 선택합니다.  
  
2.  **응용 프로그램** 탭을 클릭합니다.  
  
3.  **응용 프로그램 이벤트 보기** 단추를 클릭하여 코드 편집기를 엽니다.  
  
     그러면 ApplicationEvents.vb 파일이 열립니다.  
  
4.  코드 편집기에서 ApplicationEvents.vb 파일을 엽니다.  **일반** 메뉴에서 **MyApplication 이벤트**를 선택합니다.  
  
5.  **선언** 메뉴에서 **UnhandledException**을 선택합니다.  
  
     주 응용 프로그램이 실행되기 전에 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.UnhandledException> 이벤트가 발생합니다.  
  
6.  `UnhandledException` 이벤트 처리기에 `My.Application.Log.WriteException` 메서드를 추가합니다.  
  
     [!code-vb[VbVbalrMyApplicationLog#4](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_6.vb)]  
  
     다음 예제에서는 처리 되지 않은 예외를 기록 하기 위한 전체 코드를 보여 줍니다.  
  
     [!code-vb[VbVbalrMyApplicationLog#5](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-exceptions_7.vb)]  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName>   
 <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>   
 <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>   
 [응용 프로그램 로그 작업](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)   
 [방법: 로그 메시지 쓰기](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md)   
 [연습: My.Application.Log가 정보를 기록하는 위치 확인](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)   
 [연습: My.Application.Log가 정보를 기록하는 위치 변경](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)