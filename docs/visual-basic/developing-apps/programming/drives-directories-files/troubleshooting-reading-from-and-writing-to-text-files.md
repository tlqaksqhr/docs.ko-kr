---
title: "Troubleshooting: Reading from and Writing to Text Files (Visual Basic) | Microsoft Docs"
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
  - "troubleshooting file I/O"
  - "writing text to files, troubleshooting"
  - "troubleshooting Visual Basic, text files"
  - "I/O [Visual Basic], troubleshooting text files"
  - "writing to files, troubleshooting"
  - "reading text files, troubleshooting"
ms.assetid: a8e9b44d-facb-4718-8c0f-466537171182
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# Troubleshooting: Reading from and Writing to Text Files (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

이 항목에서는 텍스트 파일로 작업할 발생하는 일반적인 문제를 설명하고 각 문제에 대한 해결 방법을 제시합니다.  
  
## 일반적인 문제  
 텍스트 파일로 작업할 때 가장 많이 발생하는 문제에는 보안 예외, 파일 인코딩 또는 잘못된 경로 등이 있습니다.  
  
### 보안 예외  
 보안 오류가 발생하면 <xref:System.Security.SecurityException>이 throw됩니다.  이 예외는 사용자에게 필요한 권한이 없는 경우에 종종 발생하며 권한을 추가하거나 격리된 저장소에서 파일 작업을 함으로써 해결할 수 있습니다.  자세한 내용은 [예외 문제 해결: System.Security.SecurityException](../Topic/Troubleshooting%20Exceptions:%20System.Security.SecurityException.md)을 참조하십시오.  
  
### 파일 인코딩  
 문자 인코딩이라고도 하는 파일 인코딩은 텍스트를 처리할 때 문자를 나타낼 방식을 지정합니다.  텍스트 파일에 예상치 못한 문자가 나타나는 경우는 인코딩이 잘못된 경우입니다.  일반적으로 유니코드가 사용되지만 대부분의 파일에는 처리할 수 있는 언어 문자에 따라 다른 인코딩보다 주로 사용되는 인코딩이 있습니다.  자세한 내용은 [File Encodings](../../../../visual-basic/developing-apps/programming/drives-directories-files/file-encodings.md) 및 <xref:System.Text.Encoding>을 참조하십시오.  
  
### 잘못된 경로  
 파일 경로, 특히 상대 경로를 구문 분석할 때 잘못된 데이터가 지정된 경우가 많습니다.  대부분의 경우 올바른 경로를 지정하여 문제를 수정할 수 있습니다.  자세한 내용은 [방법: 파일 경로의 구문 분석](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)을 참조하십시오.  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>   
 [Reading from Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/reading-from-files.md)   
 [Writing to Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/writing-to-files.md)   
 [Parsing Text Files with the TextFieldParser Object](../../../../visual-basic/developing-apps/programming/drives-directories-files/parsing-text-files-with-the-textfieldparser-object.md)