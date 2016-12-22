---
title: "How to: Read From Fixed-width Text Files in Visual Basic | Microsoft Docs"
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
  - "fixed-width text file"
  - "reading text files, fixed-width"
  - "files, parsing"
  - "text files, tasks"
  - "text files, reading"
ms.assetid: 99be5692-967a-4e85-993e-cd18139a5a69
caps.latest.revision: 24
caps.handback.revision: 24
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Read From Fixed-width Text Files in Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

`TextFieldParser` 개체를 사용하면 로그와 같은 구조화된 텍스트 파일을 쉽게 효과적으로 구문 분석할 수 있습니다.  
  
 `TextFieldType` 속성은 구문 분석된 파일이 구분된 파일인지 텍스트가 고정 너비 필드인 파일인지를 정의합니다.  고정 너비 텍스트 파일에서 마지막 필드는 가변 너비일 수 있습니다.  마지막 필드를 가변 필드로 지정하려면 해당 필드의 너비를 0보다 작거나 같도록 정의합니다.  
  
### 고정 너비 텍스트 파일을 구문 분석하려면  
  
1.  새 `TextFieldParser`를 만듭니다.  다음 코드에서는 `Reader`라는 이름의 `TextFieldParser`를 만들고 `test.log` 파일을 엽니다.  
  
     [!code-vb[VbFileIORead#9](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-fixed-width-text-files_1.vb)]  
  
2.  `TextFieldType` 속성을 `FixedWidth`로 정의하고 너비와 형식을 지정합니다.  다음 코드에서는 첫 번째 텍스트 열은 5자, 두 번째는 10자, 세 번째는 11자 그리고 네 번째는 가변 너비로 각각 정의합니다.  
  
     [!code-vb[VbFileIORead#10](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-fixed-width-text-files_2.vb)]  
  
3.  파일의 필드를 순환하며 검색합니다.  손상된 줄이 있으면 오류가 보고되고 구문 분석은 계속됩니다.  
  
     [!code-vb[VbFileIORead#11](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-fixed-width-text-files_3.vb)]  
  
4.  `While` 및 `Using` 블록을 `End While` 및 `End Using`으로 닫습니다.  
  
     [!code-vb[VbFileIORead#12](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-fixed-width-text-files_4.vb)]  
  
## 예제  
 이 예제에서는 `test.log` 파일을 읽습니다.  
  
 [!code-vb[VbFileIORead#13](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-fixed-width-text-files_5.vb)]  
  
## 강력한 프로그래밍  
 다음 조건에서 예외가 발생할 수 있습니다.  
  
-   지정된 형식을 사용하여 행을 구문 분석할 수 없는 경우\(<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>\).  예외 메시지에 예외의 원인이 된 줄이 표시되고 줄에 포함된 텍스트에 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> 속성이 할당됩니다.  
  
-   지정된 파일이 없는 경우\(<xref:System.IO.FileNotFoundException>\)  
  
-   사용자에게 파일에 액세스할 수 있는 충분한 권한이 없는 부분 신뢰 상황인 경우  \(<xref:System.Security.SecurityException>\).  
  
-   경로가 너무 긴 경우\(<xref:System.IO.PathTooLongException>\)  
  
-   파일에 액세스할 수 있는 충분한 권한이 사용자에게 없는 경우\(<xref:System.UnauthorizedAccessException>\)  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser?displayProperty=fullName>   
 [How to: Read From Comma\-Delimited Text Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md)   
 [How to: Read From Text Files with Multiple Formats](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files-with-multiple-formats.md)   
 [Parsing Text Files with the TextFieldParser Object](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)   
 [Walkthrough: Manipulating Files and Directories in Visual Basic](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-and-directories.md)   
 [Troubleshooting: Reading from and Writing to Text Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)   
 [예외 문제 해결: Microsoft.VisualBasic.FileIO.TextFieldParser.MalformedLineException](../Topic/Troubleshooting%20Exceptions:%20Microsoft.VisualBasic.FileIO.TextFieldParser.MalformedLineException.md)