---
title: "How to: Create a Copy of a File in a Different Directory in Visual Basic | Microsoft Docs"
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
  - "My.Computer.FileSystem.CopyFile method, copying files [Visual Basic]"
  - "files, copying"
  - "CopyFile method, copying files in Visual Basic"
  - "I/O [Visual Basic], copying files"
ms.assetid: 88e2145c-d414-45a5-ad03-6f5d58ecca26
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Create a Copy of a File in a Different Directory in Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

`My.Computer.FileSystem.CopyFile` 메서드를 사용하면 파일을 복사할 수 있습니다.  이 메서드의 매개 변수를 사용하면 기존 파일을 덮어쓰고, 파일 이름을 바꾸고, 작업 진행 상태를 표시하고, 사용자에게 작업을 취소하도록 허용할 수 있습니다.  
  
### 텍스트 파일을 다른 폴더로 복사하려면  
  
-   파일을 복사하려면 `CopyFile` 메서드를 사용하면서 소스 파일 및 대상 디렉터리를 지정합니다.  `overwrite` 매개 변수를 사용하면 기존 파일을 덮어쓸지 여부를 지정할 수 있습니다.  다음 코드 예제에서는 `CopyFile`의 사용 방법을 보여 줍니다.  
  
     [!code-vb[VbFileIOMisc#24](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-create-a-copy-of-a-file-in-a-different-directory_1.vb)]  
  
## 강력한 프로그래밍  
 다음 조건에서 예외가 throw될 수 있습니다.  
  
-   길이가 0인 문자열이거나, 공백만 포함하거나, 잘못된 문자를 포함하거나, \\\\.\\로 시작하는 장치 경로와 같은 여러 가지 이유 중 하나로 경로가 올바르지 않은 경우  \\\) \(<xref:System.ArgumentException>\).  
  
-   시스템에서 절대 경로를 검색할 수 없는 경우\(<xref:System.ArgumentException>\)  
  
-   경로가 `Nothing`이기 때문에 올바르지 않은 경우\(<xref:System.ArgumentNullException>\)  
  
-   소스 파일이 올바르지 않거나 없는 경우\(<xref:System.IO.FileNotFoundException>\)  
  
-   조합된 경로가 기존 디렉터리를 가리키는 경우\(<xref:System.IO.IOException>\)  
  
-   대상 파일이 있고 `overwrite`가 `False`로 설정된 경우\(<xref:System.IO.IOException>\)  
  
-   파일에 액세스할 수 있는 충분한 권한이 사용자에게 없는 경우\(<xref:System.IO.IOException>\)  
  
-   대상 폴더에서 같은 이름의 파일이 사용 중인 경우\(<xref:System.IO.IOException>\)  
  
-   경로의 파일 이름이나 폴더 이름에 콜론\(:\)이 있거나 이름의 형식이 잘못된 경우\(<xref:System.NotSupportedException>\)  
  
-   `ShowUI`가 `True`로 설정되어 있고 `onUserCancel`이 `ThrowException`으로 설정되어 있는데 사용자가 작업을 취소한 경우\(<xref:System.OperationCanceledException>\)  
  
-   `ShowUI`가 `True`로 설정되어 있고 `onUserCancel`이 `ThrowException`으로 설정되어 있는데 지정되지 않은 I\/O 오류가 발생한 경우\(<xref:System.OperationCanceledException>\)  
  
-   경로가 시스템 정의 최대 길이를 초과하는 경우\(<xref:System.IO.PathTooLongException>\)  
  
-   사용자에게 필요한 권한이 없는 경우\(<xref:System.UnauthorizedAccessException>\)  
  
-   경로를 보는 데 필요한 권한이 사용자에게 없는 경우\(<xref:System.Security.SecurityException>\)  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%2A>   
 <xref:Microsoft.VisualBasic.FileIO.UICancelOption>   
 [방법: 특정 패턴의 파일을 디렉터리에 복사](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-copy-files-with-a-specific-pattern-to-a-directory.md)   
 [How to: Create a Copy of a File in the Same Directory](../Topic/How%20to:%20Create%20a%20Copy%20of%20a%20File%20in%20the%20Same%20Directory%20in%20Visual%20Basic.md)   
 [How to: Copy a Directory to Another Directory](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-copy-a-directory-to-another-directory.md)   
 [How to: Rename a File](../Topic/How%20to:%20Rename%20a%20File%20in%20Visual%20Basic.md)