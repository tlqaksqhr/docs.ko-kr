---
title: "How to: Dial Modems Attached to Serial Ports in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "modems, dialing"
  - "serial ports, dialing"
  - "My.Computer.Ports object"
ms.assetid: 3834db40-f431-45f1-b671-dc91787164b6
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Dial Modems Attached to Serial Ports in Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

이 항목에서는 `My.Computer.Ports`를 사용하여 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서 모뎀으로 전화 접속하는 방법을 설명합니다.  
  
 일반적으로 모뎀은 컴퓨터의 직렬 포트 중 하나에 연결됩니다.  응용 프로그램이 모뎀과 통신하려면 적절한 직렬 포트로 명령을 보내야 합니다.  
  
### 모뎀으로 전화 접속하려면  
  
1.  모뎀이 연결된 직렬 포트를 확인합니다.  이 예제에서는 모뎀이 COM1에 있는 것으로 가정합니다.  
  
2.  `My.Computer.Ports.OpenSerialPort` 메서드를 사용하여 포트에 대한 참조를 가져옵니다.  자세한 내용은 <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>를 참조하십시오.  
  
     `Using` 블록을 사용하면 예외가 생성되는 경우에도 응용 프로그램에서 직렬 포트를 닫을 수 있습니다.  직렬 포트를 조작하는 모든 코드는 이 블록이나 `Try...Catch...Finally` 블록 안에 있어야 합니다.  
  
     [!code-vb[VbVbalrMyComputer#28](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-dial-modems-attached-to-serial-ports_1.vb)]  
  
3.  `DtrEnable` 속성을 설정하여 컴퓨터가 모뎀으로부터 들어오는 전송을 받을 준비가 되었음을 지정합니다.  
  
     [!code-vb[VbVbalrMyComputer#29](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-dial-modems-attached-to-serial-ports_2.vb)]  
  
4.  <xref:System.IO.Ports.SerialPort.Write%2A> 메서드를 사용하여 직렬 포트를 통해 전화 걸기 명령과 전화 번호를 모뎀으로 보냅니다.  
  
     [!code-vb[VbVbalrMyComputer#30](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-dial-modems-attached-to-serial-ports_3.vb)]  
  
## 예제  
 [!code-vb[VbVbalrMyComputer#27](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-dial-modems-attached-to-serial-ports_4.vb)]  
  
 이 코드 예제는 IntelliSense 코드 조각으로도 사용할 수 있습니다.  이 코드 조각은 코드 조각 선택기의 **연결 및 네트워킹**에 있습니다.  자세한 내용은 [코드 조각](/visual-studio/ide/code-snippets)를 참조하십시오.  
  
## 코드 컴파일  
 이 예제에는 <xref:System?displayProperty=fullName> 네임스페이스에 대한 참조가 필요합니다.  
  
## 강력한 프로그래밍  
 이 예제에서는 모뎀이 COM1에 연결되어 있는 것으로 가정합니다.  사용자가 사용 가능한 포트 목록에서 원하는 직렬 포트를 선택할 수 있도록 코드를 작성하는 것이 좋습니다.  자세한 내용은 [How to: Show Available Serial Ports](../Topic/How%20to:%20Show%20Available%20Serial%20Ports%20in%20Visual%20Basic.md)를 참조하십시오.  
  
 이 예제에서는 `Using` 블록을 사용하여 응용 프로그램에서 예외를 throw하는 경우에도 포트를 닫도록 합니다.  자세한 내용은 [Using Statement](../../../../visual-basic/language-reference/statements/using-statement.md)을 참조하십시오.  
  
 이 예제에서는 응용 프로그램이 모뎀으로 전화 접속한 후 직렬 포트의 연결을 해제합니다.  실제로 사용자는 모뎀과 데이터를 주고 받으려고 할 것입니다.  자세한 내용은 [How to: Receive Strings From Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-receive-strings-from-serial-ports.md)를 참조하십시오.  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.Devices.Ports>   
 <xref:System.IO.Ports.SerialPort?displayProperty=fullName>   
 [How to: Send Strings to Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-send-strings-to-serial-ports.md)   
 [How to: Receive Strings From Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-receive-strings-from-serial-ports.md)   
 [How to: Show Available Serial Ports](../Topic/How%20to:%20Show%20Available%20Serial%20Ports%20in%20Visual%20Basic.md)