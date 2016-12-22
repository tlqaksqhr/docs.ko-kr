---
title: "Logging Information from the Application (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Log object"
  - "My.Log object"
  - "applications [Visual Basic], logging information from"
  - "logging"
  - "My.Application.Log object"
  - "examples [Visual Basic], logging application information"
ms.assetid: 8bf4f047-22d6-48d6-aec5-93b98ad5b8e8
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Logging Information from the Application (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

이 단원에는 `My.Application.Log` 또는 `My.Log` 개체를 사용하여 응용 프로그램의 정보를 기록하는 방법과 응용 프로그램의 로깅 기능을 확장하는 방법을 설명하는 항목이 포함되어 있습니다.  
  
 `Log` 개체는 응용 프로그램의 로그 수신기에 정보를 쓰는 메서드를 제공하고 `Log` 개체의 고급 속성인 `TraceSource`는 자세한 구성 정보를 제공합니다.  `Log` 개체는 응용 프로그램의 구성 파일에 따라 구성됩니다.  
  
 `My.Log` 개체는 ASP.NET 응용 프로그램에만 사용할 수 있습니다.  클라이언트 응용 프로그램의 경우 `My.Application.Log`를 사용합니다.  자세한 내용은 <xref:Microsoft.VisualBasic.Logging.Log>를 참조하십시오.  
  
## 작업  
  
|To|참조|  
|--------|--------|  
|이벤트 정보를 응용 프로그램의 로그에 씁니다.|[방법: 로그 메시지 쓰기](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md)|  
|예외 정보를 응용 프로그램의 로그에 씁니다.|[How to: Log Exceptions](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md)|  
|응용 프로그램이 시작될 때와 종료될 때 추적 정보를 응용 프로그램의 로그에 씁니다.|[방법: 응용 프로그램이 시작 또는 종료될 때 메시지 기록](../Topic/How%20to:%20Log%20Messages%20When%20the%20Application%20Starts%20or%20Shuts%20Down%20\(Visual%20Basic\).md)|  
|정보를 텍스트 파일에 쓰도록 `My.Application.Log`를 구성합니다.|[How to: Write Event Information to a Text File](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-event-information-to-a-text-file.md)|  
|정보를 이벤트 로그에 쓰도록 `My.Application.Log`를 구성합니다.|[방법: 응용 프로그램 이벤트 로그에 쓰기](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-to-an-application-event-log.md)|  
|`My.Application.Log`가 정보를 쓰는 위치를 변경합니다.|[연습: My.Application.Log가 정보를 기록하는 위치 변경](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)|  
|`My.Application.Log`가 정보를 쓰는 위치를 확인합니다.|[연습: My.Application.Log가 정보를 기록하는 위치 확인](../Topic/Walkthrough:%20Determining%20Where%20My.Application.Log%20Writes%20Information%20\(Visual%20Basic\).md)|  
|`My.Application.Log`에 대한 사용자 지정 로그 수신기를 만듭니다.|[Walkthrough: Creating Custom Log Listeners](../Topic/Walkthrough:%20Creating%20Custom%20Log%20Listeners%20\(Visual%20Basic\).md)|  
|`My.Application.Log` 로그의 출력을 필터링합니다.|[Walkthrough: Filtering My.Application.Log Output](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md)|  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName>   
 [응용 프로그램 로그 작업](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)   
 [Troubleshooting: Log Listeners](../../../../visual-basic/developing-apps/programming/log-info/troubleshooting-log-listeners.md)