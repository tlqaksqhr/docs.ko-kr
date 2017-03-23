---
title: "How to: Create a Directory in Visual Basic | Microsoft Docs"
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
  - "directories [Visual Basic], creating"
  - "folders [Visual Basic], creating"
ms.assetid: 0351a2ca-24d8-43b5-bb39-9b99e6401cff
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# How to: Create a Directory in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

`My.Computer.FileSystem` 개체의 `CreateDirectory` 메서드를 사용하여 디렉터리를 만듭니다.  
  
 해당 디렉터리가 이미 있을 경우 예외가 throw되지 않습니다.  
  
### 디렉터리를 만들려면  
  
-   디렉터리를 만들 위치의 전체 경로를 지정하면서 `CreateDirectory` 메서드를 사용합니다.  이 예제에서는 `C:\Documents and Settings\All Users\Documents`에 `NewDirectory` 디렉터리를 만듭니다.  
  
     [!code-vb[VbVbcnMyFileSystem#2](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-create-a-directory_1.vb)]  
  
## 강력한 프로그래밍  
 다음 조건에서 예외가 발생할 수 있습니다.  
  
-   디렉터리 이름의 형식이 잘못된 경우.  예를 들어, 파일 이름에 잘못된 문자가 들어 있거나 파일 이름이 공백인 경우\(<xref:System.ArgumentException>\)  
  
-   만들 디렉터리의 부모 디렉터리가 읽기 전용인 경우\(<xref:System.IO.IOException>\)  
  
-   디렉터리 이름이 `Nothing`인 경우\(<xref:System.ArgumentNullException>\)  
  
-   디렉터리 이름이 너무 긴 경우\(<xref:System.IO.PathTooLongException>\)  
  
-   디렉터리 이름이 콜론 ":"인 경우\(<xref:System.NotSupportedException>\)  
  
-   사용자에게 디렉터리를 만들 권한이 없는 경우\(<xref:System.UnauthorizedAccessException>\)  
  
-   부분 신뢰 상황에서 사용자에게 권한이 부족한 경우\(<xref:System.Security.SecurityException>\)  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.CreateDirectory%2A>   
 [Creating, Deleting, and Moving Files and Directories](../../../../visual-basic/developing-apps/programming/drives-directories-files/creating-deleting-and-moving-files-and-directories.md)