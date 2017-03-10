---
title: "How to: Send Strings to Serial Ports in Visual Basic | Microsoft Docs"
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
  - "ports, sending strings to"
  - "strings [Visual Basic], sending to serial ports"
  - "My.Computer.Ports object"
  - "serial ports, sending strings to"
ms.assetid: 6ebf46cd-b2d0-4b2c-9a1f-be177b22ad52
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# How to: Send Strings to Serial Ports in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

이 항목에서는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서 `My.Computer.Ports`를 사용하여 컴퓨터의 직렬 포트에 문자열을 보내는 방법을 설명합니다.  
  
## 예제  
 이 예제에서는 COM1 직렬 포트로 문자열을 보냅니다.  자신의 컴퓨터에 있는 다른 직렬 포트를 사용해야 하는 경우도 있습니다.  
  
 `My.Computer.Ports.OpenSerialPort` 메서드를 사용하여 포트에 대한 참조를 가져옵니다.  자세한 내용은 <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>를 참조하십시오.  
  
 `Using` 블록을 사용하면 예외가 생성되는 경우에도 응용 프로그램에서 직렬 포트를 닫을 수 있습니다.  직렬 포트를 조작하는 모든 코드는 이 블록이나 `Try...Catch...Finally` 블록 안에 있어야 합니다.  
  
 <xref:System.IO.Ports.SerialPort.WriteLine%2A> 메서드에서 데이터를 직렬 포트로 보냅니다.  
  
 [!code-vb[VbVbalrMyComputer#33](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/visualbasic/VbVbalrMyComputer/Class2.vb#33)]  
  
## 코드 컴파일  
  
-   이 예제에서는 컴퓨터에서 `COM1`을 사용하는 것으로 가정합니다.  
  
## 강력한 프로그래밍  
 이 예제에서는 컴퓨터에서 `COM1`을 사용하는 것으로 가정합니다. 유연성을 높이려면 사용자가 사용 가능한 포트 목록 중 원하는 직렬 포트를 선택할 수 있도록 코드를 작성해야 합니다.  자세한 내용은 [How to: Show Available Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md)를 참조하십시오.  
  
 이 예제에서는 `Using` 블록을 사용하여 응용 프로그램에서 예외를 throw하는 경우에도 포트를 닫도록 합니다.  자세한 내용은 [Using Statement](../../../../visual-basic/language-reference/statements/using-statement.md)을 참조하십시오.  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.Devices.Ports>   
 <xref:System.IO.Ports.SerialPort?displayProperty=fullName>   
 [How to: Dial Modems Attached to Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-dial-modems-attached-to-serial-ports.md)   
 [How to: Show Available Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md)