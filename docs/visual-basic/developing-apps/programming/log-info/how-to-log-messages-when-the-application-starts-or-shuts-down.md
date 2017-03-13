---
title: "방법: 응용 프로그램이 시작 또는 종료될 때 메시지 기록(Visual Basic) | Microsoft Docs"
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
  - "이벤트 로그, 종료"
  - "My.Application.Log 개체, 로깅"
  - "Startup 이벤트"
  - "이벤트 로그, 시작"
  - "Shutdown 이벤트"
  - "My.Log 개체, 로깅"
ms.assetid: 67624d05-cddf-48b7-8c36-5c99baa4c621
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# 방법: 응용 프로그램이 시작 또는 종료될 때 메시지 기록(Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

`My.Application.Log` 및 `My.Log` 개체를 사용하여 응용 프로그램에서 발생하는 이벤트에 대한 정보를 기록할 수 있습니다. 이 예제에서는 `Startup` 및 `Shutdown` 이벤트에 `My.Application.Log.WriteEntry` 메서드를 사용하여 추적 정보를 쓰는 방법을 보여 줍니다.  
  
### 응용 프로그램의 이벤트 처리기 코드에 액세스하려면  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.**프로젝트** 메뉴에서 **속성**을 선택합니다.  
  
2.  **응용 프로그램** 탭을 클릭합니다.  
  
3.  **응용 프로그램 이벤트 보기** 단추를 클릭하여 코드 편집기를 엽니다.  
  
     그러면 ApplicationEvents.vb 파일이 열립니다.  
  
### 응용 프로그램이 시작될 때 메시지를 기록하려면  
  
1.  코드 편집기에서 ApplicationEvents.vb 파일을 엽니다.**일반** 메뉴에서 **MyApplication 이벤트**를 선택합니다.  
  
2.  **선언** 메뉴에서 **Startup**을 선택합니다.  
  
     주 응용 프로그램이 실행되기 전에 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Startup> 이벤트가 발생합니다.  
  
3.  `Startup` 이벤트 처리기에 `My.Application.Log.WriteEntry` 메서드를 추가합니다.  
  
     [!code-vb[VbVbalrMyApplicationLog#1](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-messages-when-the-application-starts-or-shuts-down_1.vb)]  
  
### 응용 프로그램이 종료될 때 메시지를 기록하려면  
  
1.  코드 편집기에서 ApplicationEvents.vb 파일을 엽니다.**일반** 메뉴에서 **MyApplication 이벤트**를 선택합니다.  
  
2.  **선언** 메뉴에서 **Shutdown**을 선택합니다.  
  
     주 응용 프로그램이 실행된 후 종료되기 전에 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.Shutdown> 이벤트가 발생합니다.  
  
3.  `Shutdown` 이벤트 처리기에 `My.Application.Log.WriteEntry` 메서드를 추가합니다.  
  
     [!code-vb[VbVbalrMyApplicationLog#2](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-messages-when-the-application-starts-or-shuts-down_2.vb)]  
  
## 예제  
 **프로젝트 디자이너**를 사용하여 코드 편집기에서 응용 프로그램 이벤트에 액세스할 수 있습니다. 자세한 내용은 [프로젝트 디자이너, 응용 프로그램 페이지\(Visual Basic\)](/visual-studio/ide/reference/application-page-project-designer-visual-basic)을 참조하세요.  
  
 [!code-vb[VbVbalrMyApplicationLog#3](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-log-messages-when-the-application-starts-or-shuts-down_3.vb)]  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName>   
 <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>   
 <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>   
 [프로젝트 디자이너, 응용 프로그램 페이지\(Visual Basic\)](/visual-studio/ide/reference/application-page-project-designer-visual-basic)   
 [응용 프로그램 로그 작업](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)