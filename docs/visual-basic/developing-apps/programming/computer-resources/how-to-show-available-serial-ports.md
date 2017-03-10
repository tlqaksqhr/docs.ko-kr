---
title: "How to: Show Available Serial Ports in Visual Basic | Microsoft Docs"
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
  - "serial ports, availability"
  - "My.Computer.Ports.SerialPortNames property"
  - "My.Computer.Ports object"
  - "ports, serial port availability"
ms.assetid: eaf2ee5a-8103-4e10-a205-ed1d4db120ba
caps.latest.revision: 20
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 20
---
# How to: Show Available Serial Ports in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

이 항목에서는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서 `My.Computer.Ports`를 사용하여 컴퓨터의 사용 가능한 직렬 포트를 표시하는 방법을 보여 줍니다.  
  
 사용자가 사용할 포트를 선택할 수 있도록 하려면 직렬 포트의 이름을 <xref:System.Windows.Forms.ListBox> 컨트롤에 넣습니다.  
  
## 예제  
 이 예제에서는 `My.Computer.Ports.SerialPortNames` 속성에서 반환하는 모든 문자열을 반복 검색합니다.  이들 문자열은 컴퓨터에서 사용할 수 있는 직렬 포트 이름입니다.  
  
 일반적으로 사용자는 사용 가능한 포트 목록에서 응용 프로그램이 사용할 직렬 포트를 선택합니다.  이 예제에서 직렬 포트 이름은 <xref:System.Windows.Forms.ListBox> 컨트롤에 저장됩니다.  자세한 내용은 [ListBox 컨트롤](../Topic/ListBox%20Control%20\(Windows%20Forms\).md)을 참조하십시오.  
  
 [!code-vb[VbVbalrMyComputer#45](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/visualbasic/VbVbalrMyComputer/Class2.vb#45)]  
  
 이 코드 예제는 IntelliSense 코드 조각으로도 사용할 수 있습니다.  이 코드 조각은 코드 조각 선택기의 **연결 및 네트워킹**에 있습니다.  자세한 내용은 [코드 조각](/visual-studio/ide/code-snippets)를 참조하십시오.  
  
## 코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   System.Windows.Forms.dll에 대한 프로젝트 참조가 있어야 합니다.  
  
-   <xref:System.Windows.Forms> 네임스페이스의 멤버에 대한 액세스 권한.  코드에서 멤버 이름을 정규화하지 않는 경우에는 `Imports` 문을 추가합니다.  자세한 내용은 [Imports Statement \(.NET Namespace and Type\)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)을 참조하십시오.  
  
-   폼에 이름이 `ListBox1`인 <xref:System.Windows.Forms.ListBox> 컨트롤이 있어야 합니다.  
  
## 강력한 프로그래밍  
 사용 가능한 직렬 포트 이름을 표시하기 위해 반드시 <xref:System.Windows.Forms.ListBox> 컨트롤을 사용할 필요는 없습니다.  <xref:System.Windows.Forms.ComboBox>나 기타 컨트롤을 대신 사용할 수 있습니다.  응용 프로그램에 사용자의 응답이 필요 없는 경우 <xref:System.Windows.Forms.TextBox> 컨트롤을 사용하여 정보를 표시할 수 있습니다.  
  
> [!NOTE]
>  Windows 98에서 실행되는 경우 `My.Computer.Ports.SerialPortNames`에서 반환되는 포트 이름이 올바르지 않을 수 있습니다.  응용 프로그램 오류를 방지하려면 포트 이름을 사용하여 포트를 열 때 `Try...Catch...Finally` 문 또는 `Using` 문 등과 같은 예외 처리를 사용하십시오.  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.Devices.Ports>   
 [How to: Dial Modems Attached to Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-dial-modems-attached-to-serial-ports.md)   
 [How to: Send Strings to Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-send-strings-to-serial-ports.md)   
 [How to: Receive Strings From Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-receive-strings-from-serial-ports.md)