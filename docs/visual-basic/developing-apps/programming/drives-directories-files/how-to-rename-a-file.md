---
title: "How to: Rename a File in Visual Basic | Microsoft Docs"
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
  - "I/O [Visual Basic], renaming files"
  - "files, renaming"
ms.assetid: 0ea7e0c8-2cb2-4bf5-a00d-7b6e3c08a3bc
caps.latest.revision: 21
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 21
---
# How to: Rename a File in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

`My.Computer.FileSystem` 개체의 `RenameFile` 메서드를 사용하여 현재 위치, 파일 이름 및 새 파일 이름을 지정함으로써 파일 이름을 바꿉니다.  이 메서드는 파일을 이동하는 데 사용할 수 없습니다. 파일을 이동하고 이름을 바꾸려면 `MoveFile` 메서드를 사용하십시오.  
  
### 파일 이름을 바꾸려면  
  
-   파일 이름을 바꾸려면 `My.Computer.FileSystem.RenameFile` 메서드를 사용합니다.  이 예제에서는 `Test.txt`라는 파일의 이름을 `SecondTest.txt`로 바꿉니다.  
  
     [!code-vb[VbVbcnMyFileSystem#9](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/visualbasic/how-to-rename-a-file_1.vb)]  
  
 이 코드 예제는 IntelliSense 코드 조각으로도 사용할 수 있습니다.  이 코드 조각은 코드 조각 선택기의 **파일 시스템 \- 드라이브, 폴더 및 파일 처리**에 있습니다.  자세한 내용은 [코드 조각](/visual-studio/ide/code-snippets)를 참조하십시오.  
  
## 강력한 프로그래밍  
 다음 조건에서 예외가 발생할 수 있습니다.  
  
-   길이가 0인 문자열이거나, 공백만 포함하거나, 잘못된 문자를 포함하거나, \\\\.\\로 시작하는 장치 경로와 같은 여러 가지 이유 중 하나로 경로가 올바르지 않은 경우  \\\) \(<xref:System.ArgumentException>\).  
  
-   `newName`에 경로 정보가 포함된 경우\(<xref:System.ArgumentException>\)  
  
-   경로가 `Nothing`이기 때문에 올바르지 않은 경우\(<xref:System.ArgumentNullException>\)  
  
-   `newName`이 `Nothing`이거나 빈 문자열인 경우\(<xref:System.ArgumentNullException>\)  
  
-   소스 파일이 올바르지 않거나 없는 경우\(<xref:System.IO.FileNotFoundException>\)  
  
-   `newName`에 지정된 이름을 갖는 파일이나 디렉터리가 이미 있는 경우\(<xref:System.IO.IOException>\)  
  
-   경로가 시스템 정의 최대 길이를 초과하는 경우\(<xref:System.IO.PathTooLongException>\)  
  
-   경로의 파일 이름이나 디렉터리 이름에 콜론\(:\)이 있거나 이름의 형식이 잘못된 경우\(<xref:System.NotSupportedException>\)  
  
-   경로를 보는 데 필요한 권한이 사용자에게 없는 경우\(<xref:System.Security.SecurityException>\)  
  
-   사용자에게 필요한 권한이 없는 경우\(<xref:System.UnauthorizedAccessException>\)  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.RenameFile%2A>   
 [방법: 파일 이동](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-move-a-file.md)   
 [Creating, Deleting, and Moving Files and Directories](../../../../visual-basic/developing-apps/programming/drives-directories-files/creating-deleting-and-moving-files-and-directories.md)   
 [How to: Create a Copy of a File in the Same Directory](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-create-a-copy-of-a-file-in-the-same-directory.md)   
 [How to: Create a Copy of a File in a Different Directory](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-create-a-copy-of-a-file-in-a-different-directory.md)