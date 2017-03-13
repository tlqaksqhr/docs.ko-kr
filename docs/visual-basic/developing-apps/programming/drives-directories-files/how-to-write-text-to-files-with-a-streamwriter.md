---
title: "How to: Write Text to Files with a StreamWriter in Visual Basic | Microsoft Docs"
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
  - "files, writing to"
  - "text, writing to files"
  - "writing to files, StreamWriter"
ms.assetid: 99762e57-ef46-4dcc-8959-a8f79c22f067
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# How to: Write Text to Files with a StreamWriter in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

이 예제에서는 `My.Computer.FileSystem.OpenTextFileWriter` 메서드를 사용하여 <xref:System.IO.StreamWriter> 개체를 열고 <xref:System.IO.StreamWriter> 클래스의 <xref:System.IO.TextWriter.WriteLine%2A> 메서드를 사용하여 텍스트 파일에 문자열을 씁니다.  
  
## 예제  
 [!code-vb[VbFileIOWrite#5](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files-with-a-streamwriter_1.vb)]  
  
## 강력한 프로그래밍  
 다음 조건에서 예외가 발생할 수 있습니다.  
  
-   파일이 있는데 읽기 전용인 경우\(<xref:System.IO.IOException>\)  
  
-   디스크가 꽉 찬 경우\(<xref:System.IO.IOException>\)  
  
-   경로 이름이 너무 긴 경우\(<xref:System.IO.PathTooLongException>\)  
  
## .NET Framework 보안  
 이 예제에서는 파일이 없는 경우 새 파일을 만듭니다.  응용 프로그램에서 파일을 만들어야 하는 경우, 해당 응용 프로그램에는 폴더에 대한 `Create` 액세스 권한이 필요합니다.  해당 파일이 이미 있으면 응용 프로그램에는 더 낮은 수준의 권한인 `Write` 액세스 권한만 있으면 됩니다.  가능하면 배포하는 동안 파일을 만들고 폴더에 대한 `Create` 권한 대신 파일 하나에 대한 `Read` 권한만 부여하는 것이 안전합니다.  
  
## 참고 항목  
 <xref:System.IO.StreamWriter>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileWriter%2A>   
 [How to: Read from Text Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files.md)   
 [Writing to Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)