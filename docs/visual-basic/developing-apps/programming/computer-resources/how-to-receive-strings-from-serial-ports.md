---
title: "How to: Receive Strings From Serial Ports in Visual Basic | Microsoft Docs"
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
  - "serial ports, retrieving strings"
  - "strings [Visual Basic], retrieving from serial ports"
  - "My.Resources object"
ms.assetid: 8371ce2c-e1c7-476b-a86d-9afc2614b6b7
caps.latest.revision: 21
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 21
---
# How to: Receive Strings From Serial Ports in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

이 항목에서는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서 `My.Computer.Ports`를 사용하여 컴퓨터의 직렬 포트에서 문자열을 받는 방법에 대해 설명합니다.  
  
### 직렬 포트에서 문자열을 받으려면  
  
1.  반환 문자열을 초기화합니다.  
  
     [!code-vb[VbVbalrMyComputer#38](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/visualbasic/VbVbalrMyComputer/Class2.vb#38)]  
  
2.  문자열을 제공하는 직렬 포트를 확인합니다.  이 예제에서는 `COM1`으로 가정합니다.  
  
3.  `My.Computer.Ports.OpenSerialPort` 메서드를 사용하여 포트에 대한 참조를 가져옵니다.  자세한 내용은 <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>를 참조하십시오.  
  
     `Try...Catch...Finally` 블록을 사용하면 예외가 생성되는 경우에도 응용 프로그램에서 직렬 포트를 닫을 수 있습니다.  직렬 포트를 조작하는 모든 코드는 이 블록 안에 있어야 합니다.  
  
     [!code-vb[VbVbalrMyComputer#39](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/visualbasic/VbVbalrMyComputer/Class2.vb#39)]  
  
4.  더 이상의 줄이 없을 때까지 텍스트 줄을 읽는 `Do` 루프를 만듭니다.  
  
     [!code-vb[VbVbalrMyComputer#40](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/visualbasic/VbVbalrMyComputer/Class2.vb#40)]  
  
5.  <xref:System.IO.Ports.SerialPort.ReadLine%2A> 메서드를 사용하여 직렬 포트에서 다음 텍스트 줄을 읽습니다.  
  
     [!code-vb[VbVbalrMyComputer#41](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/visualbasic/VbVbalrMyComputer/Class2.vb#41)]  
  
6.  `If` 문을 사용하여 <xref:System.IO.Ports.SerialPort.ReadLine%2A> 메서드가 더 이상 텍스트가 없음을 의미하는 `Nothing`을 반환하는지 확인합니다.  `Nothing`을 반환하면 `Do` 루프를 종료합니다.  
  
     [!code-vb[VbVbalrMyComputer#42](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/visualbasic/VbVbalrMyComputer/Class2.vb#42)]  
  
7.  `If` 문에 `Else` 블록을 추가하여 문자열을 실제로 읽은 경우의 대\/소문자를 처리합니다.  이 블록에서는 직렬 포트의 문자열을 반환 문자열에 추가합니다.  
  
     [!code-vb[VbVbalrMyComputer#43](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/visualbasic/VbVbalrMyComputer/Class2.vb#43)]  
  
8.  문자열을 반환합니다.  
  
     [!code-vb[VbVbalrMyComputer#44](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/visualbasic/VbVbalrMyComputer/Class2.vb#44)]  
  
## 예제  
 [!code-vb[VbVbalrMyComputer#37](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/visualbasic/VbVbalrMyComputer/Class2.vb#37)]  
  
 이 코드 예제는 IntelliSense 코드 조각으로도 사용할 수 있습니다.  이 코드 조각은 코드 조각 선택기의 **연결 및 네트워킹**에 있습니다.  자세한 내용은 [코드 조각](/visual-studio/ide/code-snippets)를 참조하십시오.  
  
## 코드 컴파일  
 이 예제에서는 컴퓨터에서 `COM1`을 사용하는 것으로 가정합니다.  
  
## 강력한 프로그래밍  
 이 예제에서는 컴퓨터에서 `COM1`을 사용하는 것으로 가정합니다.  유연성을 높이려면 사용자가 사용 가능한 포트 목록에서 원하는 직렬 포트를 선택할 수 있도록 코드를 작성해야 합니다.  자세한 내용은 [How to: Show Available Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md)를 참조하십시오.  
  
 이 예제에서는 `Try...Catch...Finally` 블록을 사용하여 응용 프로그램에서 포트를 닫고 모든 시간 제한 예외를 catch하도록 합니다.  자세한 내용은 [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)을 참조하십시오.  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.Devices.Ports>   
 <xref:System.IO.Ports.SerialPort?displayProperty=fullName>   
 [How to: Dial Modems Attached to Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-dial-modems-attached-to-serial-ports.md)   
 [How to: Send Strings to Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-send-strings-to-serial-ports.md)   
 [How to: Show Available Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md)