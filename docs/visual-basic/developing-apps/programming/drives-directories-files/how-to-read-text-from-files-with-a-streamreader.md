---
title: "How to: Read Text from Files with a StreamReader (Visual Basic) | Microsoft Docs"
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
  - "reading files, text"
  - "text, reading from files"
  - "reading text from files"
  - "files, reading"
ms.assetid: 384033c6-18f9-4d59-9610-36371226558f
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# How to: Read Text from Files with a StreamReader (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

`My.Computer.FileSystem` 개체는 <xref:System.IO.TextReader> 및 <xref:System.IO.TextWriter>를 여는 메서드를 제공합니다.  `OpenTextFileWriter`와 `OpenTextFileReader` 메서드는 **모두** 탭을 선택해야 IntelliSense에 나타나는 고급 메서드입니다.  
  
### 텍스트 판독기로 파일에서 텍스트 줄을 읽으려면  
  
-   `OpenTextFileReader` 메서드를 사용하여 파일을 지정하고 <xref:System.IO.TextReader>를 엽니다.  이 예제에서는 `testfile.txt`라는 파일을 열어서 한 줄을 읽은 다음 메시지 상자에 표시합니다.  
  
     [!code-vb[VbFileIORead#1](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/visualbasic/how-to-read-text-from-fi_1.vb)]  
  
## 강력한 프로그래밍  
 읽는 파일은 텍스트 파일이어야 합니다.  
  
 파일 이름을 바탕으로 파일 내용을 판단하면 안 됩니다.  예를 들어, Form1.vb 파일이 Visual Basic 소스 파일이 아닐 수도 있습니다.  
  
 응용 프로그램에서 데이터를 사용하기 전에 모든 입력을 확인해야 합니다.  파일의 내용이 예상한 내용과 다를 수 있으며 파일을 읽는 메서드가 실패할 수도 있습니다.  
  
## .NET Framework 보안  
 파일을 읽으려면 어셈블리에 <xref:System.Security.Permissions.FileIOPermission> 클래스에서 부여한 권한 수준이 있어야 합니다.  부분 신뢰 컨텍스트에서 실행 중인 경우에는 불충분한 권한 때문에 코드에서 예외를 throw할 수 있습니다.  자세한 내용은 [코드 액세스 보안 기본 사항](../Topic/Code%20Access%20Security%20Basics.md)을 참조하십시오.  사용자도 파일에 대한 액세스 권한이 있어야 합니다.  자세한 내용은 [ACL Technology Overview](http://msdn.microsoft.com/ko-kr/06fbf66d-6f02-4378-b863-b2f12e349045)를 참조하십시오.  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>   
 <xref:System.Windows.Forms.OpenFileDialog>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileWriter%2A>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileReader%2A>   
 [SaveFileDialog 구성 요소](../Topic/SaveFileDialog%20Component%20\(Windows%20Forms\).md)   
 [Reading from Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)