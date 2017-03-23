---
title: "How to: Read From Text Files with Multiple Formats in Visual Basic | Microsoft Docs"
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
  - "TextFieldParser object, reading from a file"
  - "TextFieldType enumeration"
  - "My.Computer.FileSystem.WriteAllText method, parsing structured text files"
  - "WriteAllText method, parsing structured text files"
  - "PeekChars method, determining format of text"
  - "reading text files, multiple formats"
  - "I/O [Visual Basic], reading text files"
  - "text files, reading"
ms.assetid: 8d185eb2-79ca-42cd-95a7-d3ff44a5a0f8
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# How to: Read From Text Files with Multiple Formats in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

<xref:Microsoft.VisualBasic.FileIO.TextFieldParser> 개체를 사용하면 로그와 같은 구조화된 텍스트 파일을 쉽게 효과적으로 구문 분석할 수 있습니다.  `PeekChars` 메서드를 사용하여 파일을 구문 분석하면서 각 줄의 형식을 확인함으로써 여러 형식이 포함된 파일을 처리할 수 있습니다.  
  
### 여러 형식의 텍스트 파일을 구문 분석하려면  
  
1.  testfile.txt 텍스트 파일을 프로젝트에 추가합니다.  텍스트 파일에 다음 내용을 추가합니다.  
  
    ```  
    Err  1001 Cannot access resource.  
    Err  2014 Resource not found.  
    Acc  10/03/2009User1      Administrator.  
    Err  0323 Warning: Invalid access attempt.  
    Acc  10/03/2009User2      Standard user.  
    Acc  10/04/2009User2      Standard user.  
    ```  
  
2.  예상 형식과 오류가 보고될 때 사용되는 형식을 정의합니다.  각 배열의 마지막 항목이 \-1이므로 마지막 필드는 가변 너비 필드로 간주됩니다.  이는 배열의 마지막 항목이 0보다 작거나 같을 때 발생합니다.  
  
     [!code-vb[VbFileIORead#4](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-text-files-with-multiple-formats_1.vb)]  
  
3.  너비와 형식을 정의하여 새 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> 개체를 만듭니다.  
  
     [!code-vb[VbFileIORead#5](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-text-files-with-multiple-formats_2.vb)]  
  
4.  행을 순환하며 검색하여 읽기 전에 형식을 테스트합니다.  
  
     [!code-vb[VbFileIORead#6](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-text-files-with-multiple-formats_3.vb)]  
  
5.  콘솔에 오류를 씁니다.  
  
     [!code-vb[VbFileIORead#7](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-text-files-with-multiple-formats_4.vb)]  
  
## 예제  
 다음은 `testfile.txt` 파일에서 읽는 전체 예제입니다.  
  
 [!code-vb[VbFileIORead#8](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-read-from-text-files-with-multiple-formats_5.vb)]  
  
## 강력한 프로그래밍  
 다음 조건에서 예외가 발생할 수 있습니다.  
  
-   지정된 형식을 사용하여 행을 구문 분석할 수 없는 경우\(<xref:Microsoft.VisualBasic.FileIO.MalformedLineException>\).  예외 메시지에 예외의 원인이 된 줄이 표시되고 줄에 포함된 텍스트에 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.ErrorLine%2A> 속성이 할당됩니다.  
  
-   지정된 파일이 없는 경우\(<xref:System.IO.FileNotFoundException>\)  
  
-   사용자에게 파일에 액세스할 수 있는 충분한 권한이 없는 부분 신뢰 상황인 경우  \(<xref:System.Security.SecurityException>\).  
  
-   경로가 너무 긴 경우\(<xref:System.IO.PathTooLongException>\)  
  
-   파일에 액세스할 수 있는 충분한 권한이 사용자에게 없는 경우\(<xref:System.UnauthorizedAccessException>\)  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser?displayProperty=fullName>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.PeekChars%2A>   
 <xref:Microsoft.VisualBasic.FileIO.MalformedLineException>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.EndOfData%2A>   
 <xref:Microsoft.VisualBasic.FileIO.TextFieldParser.TextFieldType%2A>   
 [How to: Read From Comma\-Delimited Text Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-comma-delimited-text-files.md)   
 [How to: Read From Fixed\-width Text Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-fixed-width-text-files.md)   
 [Parsing Text Files with the TextFieldParser Object](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)