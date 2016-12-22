---
title: "Storing Data to and Reading from the Clipboard (Visual Basic) | Microsoft Docs"
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
  - "Clipboard, storing data to (My.Computer.Clipboard)"
  - "Clipboard, reading from (My.Computer.Clipboard)"
  - "Clipboard"
  - "My.Computer.Clipboard object, tasks"
  - "data [Visual Basic], Clipboard"
  - "reading data, from Clipboard"
ms.assetid: f690119a-4378-4f7d-b20e-d9377ef49496
caps.latest.revision: 21
caps.handback.revision: 21
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Storing Data to and Reading from the Clipboard (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

클립보드는 텍스트 및 이미지와 같은 데이터를 저장하는 데 사용할 수 있습니다.  클립보드는 모든 활성 프로세스에서 공유하므로 여러 프로세스 간에 데이터를 전송하는 데 사용될 수 있습니다.  `My.Computer.Clipboard` 개체를 사용 하 여 클립보드에 쉽게 액세스할 수 및 읽기 및 쓰기 수입니다.  
  
## 클립보드에서 읽기  
 사용은 <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetText%2A> 메서드는 클립보드에 있는 텍스트를 읽을 수 있습니다.  다음 코드에서는 텍스트를 읽고 이 텍스트를 메시지 상자에 표시합니다.  예제가 제대로 실행되려면 클립보드에 저장된 텍스트가 있어야 합니다.  
  
 [!code-vb[VbVbcnMyClipboard#4](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_1.vb)]  
  
 이 코드 예제는 IntelliSense 코드 조각으로도 사용할 수 있습니다.  코드 조각 선택의 **Windows Forms 응용 프로그램** \> **클립보드**에 있습니다.  자세한 내용은 [코드 조각](/visual-studio/ide/code-snippets)를 참조하십시오.  
  
 <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetImage%2A> 메서드를 사용하면 클립보드에서 이미지를 검색할 수 있습니다.  이 예제에서는 먼저 클립보드에 이미지가 있는지 여부를 확인한 후에 이미지를 검색하고 이 이미지를  `PictureBox1`에 할당합니다.  
  
 [!code-vb[VbResourceTasks#16](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_2.vb)]  
  
 이 코드 예제는 IntelliSense 코드 조각으로도 사용할 수 있습니다.  코드 조각 선택의 **Windows Forms 응용 프로그램 \> 클립보드**에 있습니다.자세한 내용은 [코드 조각](/visual-studio/ide/code-snippets)을 참조하십시오.  
  
 클립보드에 저장된 항목은 응용 프로그램을 종료한 후에도 계속 유지됩니다.  
  
## 클립보드에 저장 되는 파일 형식을 결정 합니다.  
 클립보드의 데이터는 텍스트, 오디오 파일 또는 이미지와 같이 여러 가지 다른 형식을 취할 수 있습니다.  클립보드에 있는 파일 종류를 확인하려면 <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsAudio%2A>, <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsFileDropList%2A>, <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsImage%2A> 및 <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsText%2A>와 같은 메서드를 사용할 수 있습니다.  사용자 지정 형식을 확인하려면 <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsData%2A> 메서드를 사용할 수 있습니다.  
  
 `ContainsImage` 함수를 사용하면 클립보드에 포함되어 있는 데이터가 이미지인지 여부를 확인할 수 있습니다.  다음 코드에서는 데이터가 이미지인지 여부를 확인하고 결과를 보고합니다.  
  
 [!code-vb[VbResourceTasks#13](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_3.vb)]  
  
## 클립보드 지우기  
 <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.Clear%2A> 메서드는 클립보드를 지웁니다.  클립보드는 다른 프로세스에서 공유하기 때문에 클립보드를 지우면 여러 프로세스에 영향을 미칠 수 있습니다.  
  
 다음 코드는 `Clear` 메서드를 사용하는 방법을 보여 줍니다.  
  
 [!code-vb[VbVbcnMyClipboard#3](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_4.vb)]  
  
## 클립보드에 쓰기  
 <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetText%2A> 메서드를 사용하여 클립보드에 텍스트를 씁니다.  다음 코드는 클립보드에 "This is a test string"이라는 문자열을 씁니다.  
  
 [!code-vb[VbVbcnMyClipboard#1](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_5.vb)]  
  
 `SetText` 메서드는 형식의 형식 매개 변수를 받아들일 수 <xref:System.Windows.Forms.TextDataFormat>.  다음 코드는 "This is a test string" 문자열을 클립보드에 RTF 텍스트 형식으로 씁니다.  
  
 [!code-vb[VbVbcnMyClipboard#2](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_6.vb)]  
  
 <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetData%2A> 메서드를 사용하여 데이터를 클립보드에 씁니다.  이 예제에서는 `DataObject` `dataChunk`를 클립보드에 사용자 지정 형식 `specialFormat`으로 씁니다.  
  
 [!code-vb[VbVbcnMyClipboard#7](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_7.vb)]  
  
 <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetAudio%2A> 메서드를 사용하여 클립보드에 오디오 데이터를 씁니다.  이 예제에서는 바이트 배열 `musicReader`를 만들고 배열에서 `cool.wav` 파일을 읽은 다음 클립보드에 씁니다.  
  
 [!code-vb[VbResourceTasks#5](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/storing-data-to-and-reading-from-the-clipboard_8.vb)]  
  
> [!IMPORTANT]
>  클립보드에 다른 사용자가 액세스할 수도 있으므로 암호나 기밀 데이터와 같은 중요한 정보를 저장하는 데 클립보드를 사용하지 마십시오.  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy>   
 <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetAudioStream%2A>   
 <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetDataObject%2A>   
 [방법: XML 파일에서 개체 데이터 읽기](../Topic/How%20to:%20Read%20Object%20Data%20from%20an%20XML%20File%20\(C%23%20and%20Visual%20Basic\).md)   
 [방법: XML 파일에 개체 데이터 쓰기](../Topic/How%20to:%20Write%20Object%20Data%20to%20an%20XML%20File%20\(C%23%20and%20Visual%20Basic\).md)