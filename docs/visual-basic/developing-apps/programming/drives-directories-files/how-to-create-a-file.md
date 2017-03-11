---
title: "How to: Create a File in Visual Basic | Microsoft Docs"
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
  - "text files, creating"
  - "files, creating"
ms.assetid: 0253bb6d-5519-4a50-b882-b93ef5cca0d9
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# How to: Create a File in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

이 예제에서는 <xref:System.IO.File> 클래스의 <xref:System.IO.File.Create%2A> 메서드를 사용하여 지정된 경로에 빈 텍스트 파일을 만듭니다.  
  
## 예제  
 [!code-vb[VbFileIOMisc#1](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/visualbasic/how-to-create-a-file_1.vb)]  
  
## 코드 컴파일  
 파일에 쓰려면 `file` 변수를 사용합니다.  
  
## 강력한 프로그래밍  
 파일이 이미 있을 경우에는 기존 파일이 새 파일로 바뀝니다.  
  
 다음 조건에서 예외가 발생할 수 있습니다.  
  
-   경로 이름의 형식이 잘못된 경우.  예를 들어, 파일 이름에 잘못된 문자가 들어 있거나 파일 이름이 공백인 경우\(<xref:System.ArgumentException>\)  
  
-   경로가 읽기 전용인 경우\(<xref:System.IO.IOException>\)  
  
-   경로 이름이 `Nothing`인 경우\(<xref:System.ArgumentNullException>\)  
  
-   경로 이름이 너무 긴 경우\(<xref:System.IO.PathTooLongException>\)  
  
-   경로가 잘못된 경우\(<xref:System.IO.DirectoryNotFoundException>\)  
  
-   경로가 콜론 ":"인 경우\(<xref:System.NotSupportedException>\)  
  
## .NET Framework 보안  
 부분 신뢰 환경에서는 <xref:System.Security.SecurityException>이 throw됩니다.  
  
 <xref:System.IO.File.Create%2A> 메서드를 호출하려면 <xref:System.Security.Permissions.FileIOPermission>이 필요합니다.  
  
 사용자에게 파일을 만들 권한이 없는 경우 <xref:System.UnauthorizedAccessException>이 throw됩니다.  
  
## 참고 항목  
 <xref:System.IO>   
 <xref:System.IO.File.Create%2A>   
 [부분 신뢰 코드에서 라이브러리 사용](../Topic/Using%20Libraries%20from%20Partially%20Trusted%20Code.md)   
 [코드 액세스 보안 기본 사항](../Topic/Code%20Access%20Security%20Basics.md)