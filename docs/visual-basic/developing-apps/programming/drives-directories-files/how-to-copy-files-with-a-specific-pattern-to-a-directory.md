---
title: "방법: Visual Basic에서 특정 패턴의 파일을 디렉터리에 복사 | Microsoft Docs"
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
  - "My.Computer.FileSystem.CopyFile 메서드, 파일 복사 [Visual Basic]"
  - "파일, 복사"
  - "CopyFile 메서드, Visual Basic에서 파일 복사"
  - "I/O [Visual Basic], 파일 복사"
ms.assetid: f205d2ad-bbe5-4d55-8a40-acda21aa82dd
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 방법: Visual Basic에서 특정 패턴의 파일을 디렉터리에 복사
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

<xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A> 메서드는 파일의 경로 이름을 나타내는 읽기 전용 문자열 컬렉션을 반환합니다.`wildCards` 매개 변수를 사용하여 특정 패턴을 지정할 수 있습니다.  
  
 일치하는 파일이 없으면 빈 컬렉션이 반환됩니다.  
  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%2A> 메서드를 사용하여 파일을 디렉터리로 복사할 수 있습니다.  
  
### 특정 패턴의 파일을 디렉터리로 복사하려면  
  
1.  `GetFiles` 메서드를 사용하여 파일 목록을 반환합니다. 이 예제에서는 지정된 디렉터리에 있는 .rtf 파일을 모두 반환합니다.  
  
     [!code-vb[VbFileIOMisc#36](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-copy-files-with-a-specific-pattern-to-a-directory_1.vb)]  
  
2.  `CopyFile` 메서드를 사용하여 파일을 복사합니다. 이 예제에서는 `testdirectory`라는 디렉터리로 파일을 복사합니다.  
  
     [!code-vb[VbVbcnMyFileSystem#88](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-copy-files-with-a-specific-pattern-to-a-directory_2.vb)]  
  
3.  `Next` 문으로 `For` 문을 닫습니다.  
  
     [!code-vb[VbVbcnMyFileSystem#89](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-copy-files-with-a-specific-pattern-to-a-directory_3.vb)]  
  
## 예제  
 위 코드 조각의 완전한 형식인 다음 예제에서는 지정된 디렉터리의 모든 .rtf 파일을 `testdirectory`라는 이름의 디렉터리로 복사합니다.  
  
 [!code-vb[VbFileIOMisc#37](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-copy-files-with-a-specific-pattern-to-a-directory_4.vb)]  
  
## .NET Framework 보안  
 다음 조건에서 예외가 발생합니다.  
  
-   빈 문자열이거나, 공백만 포함하거나, 잘못된 문자를 포함하거나, 경로가 장치 경로인 경우\(\\\\.\\로 시작됨\)와 같은 여러 가지 이유 중 하나로 경로가 올바르지 않은 경우\(<xref:System.ArgumentException>\)  
  
-   경로가 `Nothing`이기 때문에 올바르지 않은 경우\(<xref:System.ArgumentNullException>\)  
  
-   디렉터리가 없는 경우\(<xref:System.IO.DirectoryNotFoundException>\)  
  
-   디렉터리가 기존 파일을 가리키는 경우\(<xref:System.IO.IOException>\)  
  
-   경로가 시스템 정의 최대 길이를 초과하는 경우\(<xref:System.IO.PathTooLongException>\)  
  
-   경로의 파일 이름이나 디렉터리 이름에 콜론\(:\)이 있거나 이름의 형식이 잘못된 경우\(<xref:System.NotSupportedException>\)  
  
-   경로를 보는 데 필요한 권한이 사용자에게 없는 경우\(<xref:System.Security.SecurityException>\) 사용자에게 필요한 권한이 없는 경우\(<xref:System.UnauthorizedAccessException>\)  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%2A>   
 <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A>   
 [How to: Find Subdirectories with a Specific Pattern](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-subdirectories-with-a-specific-pattern.md)   
 [Troubleshooting: Reading from and Writing to Text Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)   
 [How to: Get the Collection of Files in a Directory](../Topic/How%20to:%20Get%20the%20Collection%20of%20Files%20in%20a%20Directory%20in%20Visual%20Basic.md)