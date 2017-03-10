---
title: "How to: Read From Comma-Delimited Text Files in Visual Basic | Microsoft Docs"
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
  - "files, parsing"
  - "text files, tasks"
  - "reading text files, comma-delimited"
  - "text files, reading"
ms.assetid: a8413fe4-0dba-49c8-8692-44fb67a9ec4f
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# How to: Read From Comma-Delimited Text Files in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

`TextFieldParser` 개체를 사용하면 로그와 같은 구조화된 텍스트 파일을 쉽게 효과적으로 구문 분석할 수 있습니다.  `TextFieldType` 속성은 파일이 구분된 파일인지 텍스트가 고정 너비 필드인 파일인지를 정의합니다.  
  
### 쉼표로 구분된 텍스트 파일을 구문 분석하려면  
  
1.  새 `TextFieldParser`를 만듭니다.  다음 코드에서는 `MyReader`라는 이름의 `TextFieldParser`를 만들고 `test.txt` 파일을 엽니다.  
  
     [!code-vb[VbFileIORead#15](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/visualbasic/how-to-read-from-comma-d_1.vb)]  
  
2.  `TextField` 형식과 구분 기호를 정의합니다.  다음 코드에서는 `TextFieldType` 속성을 `Delimited`로 정의하고 구분 기호를 ","로 정의합니다.  
  
     [!code-vb[VbFileIORead#16](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/visualbasic/how-to-read-from-comma-d_2.vb)]  
  
3.  파일의 필드를 순환하며 검색합니다.  손상된 줄이 있으면 오류가 보고되고 구문 분석은 계속됩니다.  다음 코드에서는 파일을 순환하며 검색하여 각 필드를 차례로 표시하고 형식이 잘못 지정된 모든 필드를 보고합니다.  
  
     [!code-vb[VbFileIORead#17](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/visualbasic/how-to-read-from-comma-d_3.vb)]  
  
4.  `While` 및 `Using` 블록을 `End While` 및 `End Using`으로 닫습니다.  
  
     [!code-vb[VbFileIORead#18](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/visualbasic/how-to-read-from-comma-d_4.vb)]  
  
## 예제  
 이 예제에서는 `test.txt` 파일을 읽습니다.  
  
 [!code-vb[VbFileIORead#19](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/visualbasic/how-to-read-from-comma-d_5.vb)]  
  
## 강력한 프로그래밍  
 다음 조건에서 예외가 발생할 수 있습니다.  
  
-   지정된 형식을 사용하여 행을 구문 분석할 수 없는 경우\(<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>\).  예외 메시지에 예외의 원인이 된 줄이 표시되고 줄에 포함된 텍스트에 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> 속성이 할당됩니다.  
  
-   지정된 파일이 없는 경우\(<xref:System.IO.FileNotFoundException>\)  
  
-   사용자에게 파일에 액세스할 수 있는 충분한 권한이 없는 부분 신뢰 상황인 경우  \(<xref:System.Security.SecurityException>\).  
  
-   경로가 너무 긴 경우\(<xref:System.IO.PathTooLongException>\)  
  
-   파일에 액세스할 수 있는 충분한 권한이 사용자에게 없는 경우\(<xref:System.UnauthorizedAccessException>\)  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser?displayProperty=fullName>   
 [How to: Read From Fixed\-width Text Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-fixed-width-text-files.md)   
 [How to: Read From Text Files with Multiple Formats](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md)   
 [Parsing Text Files with the TextFieldParser Object](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)   
 [Walkthrough: Manipulating Files and Directories in Visual Basic](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-and-directories.md)   
 [Troubleshooting: Reading from and Writing to Text Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)   
 [예외 문제 해결: Microsoft.VisualBasic.FileIO.TextFieldParser.MalformedLineException](../Topic/Troubleshooting%20Exceptions:%20Microsoft.VisualBasic.FileIO.TextFieldParser.MalformedLineException.md)