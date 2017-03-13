---
title: "How to: Start an Application and Send it Keystrokes (Visual Basic) | Microsoft Docs"
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
  - "keystrokes, sending"
  - "Shell command example [Visual Basic]"
  - "processes, starting and sending keystrokes"
  - "SendKeys.SendWait examples"
ms.assetid: f1303184-fce4-44fb-88b4-aac5f42d5d77
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# How to: Start an Application and Send it Keystrokes (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

이 예제에서는 `Shell` 함수를 사용하여 계산기 응용 프로그램을 시작한 다음 `My.Computer.Keyboard.SendKeys` 메서드를 사용하여 키 입력을 전송하여 두 숫자를 곱합니다.  
  
## 예제  
 [!code-vb[VbVbalrMyComputer#25](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-start-an-application-and-send-it-keystrokes_1.vb)]  
  
## 강력한 프로그래밍  
 요청한 프로세스 식별자를 가진 응용 프로그램을 찾을 수 없으면 <xref:System.ArgumentException> 예외가 발생합니다.  
  
## .NET Framework 보안  
 `Shell` 함수를 호출하려면 완전 신뢰가 필요합니다\(<xref:System.Security.SecurityException> 클래스\).  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.Devices.Keyboard.SendKeys%2A>   
 <xref:Microsoft.VisualBasic.Interaction.Shell%2A>   
 <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A>