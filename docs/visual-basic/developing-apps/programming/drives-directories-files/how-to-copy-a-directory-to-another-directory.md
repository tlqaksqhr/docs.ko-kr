---
title: "How to: Copy a Directory to Another Directory in Visual Basic | Microsoft Docs"
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
  - "I/O [Visual Basic], copying directories"
  - "I/O [Visual Basic], copying folders"
  - "folders [Visual Basic], copying"
  - "directories [Visual Basic], copying"
ms.assetid: 2a370bd7-10ba-4219-afc4-4519d031eb6c
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# How to: Copy a Directory to Another Directory in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

디렉터리를 다른 디렉터리에 복사하려면 <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyDirectory%2A> 메서드를 사용합니다.  이 메서드는 디렉터리의 내용과 디렉터리 자체를 복사합니다.  대상 디렉터리가 없으면 새로 만들어집니다.  대상 위치에 같은 이름의 디렉터리가 있고 `overwrite`가 `False`로 설정되어 있으면 두 디렉터리의 내용이 병합됩니다.  작업 도중 디렉터리의 새 이름을 지정할 수 있습니다.  
  
 디렉터리 내에서 파일을 복사할 때 `overwrite`가 `False`로 설정된 경우 병합 도중 해당 파일이 이미 존재함으로 인해 예외가 throw될 수 있습니다.  이러한 예외가 throw되면 이들 예외는 하나의 예외로 통합되며, 이때 파일 또는 디렉터리 경로가 키이고 해당 값에 특정 예외 메시지가 포함된 항목이 `Data` 속성에 저장됩니다.  
  
### 디렉터리를 다른 디렉터리에 복사하려면  
  
-   `CopyDirectory` 메서드를 사용하면서 소스 및 대상 디렉터리 이름을 지정합니다.  다음 예제에서는 `TestDirectory1` 디렉터리를 `TestDirectory2`로 복사하며 기존 파일은 덮어씁니다.  
  
     [!code-vb[VbVbcnMyFileSystem#16](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-copy-a-directory-to-another-directory_1.vb)]  
  
     이 코드 예제는 IntelliSense 코드 조각으로도 사용할 수 있습니다.  이 코드 조각은 코드 조각 선택기의 **파일 시스템 \- 드라이브, 폴더 및 파일 처리**에 있습니다.  자세한 내용은 [코드 조각](/visual-studio/ide/code-snippets)를 참조하십시오.  
  
## 강력한 프로그래밍  
 다음 조건에서 예외가 발생할 수 있습니다.  
  
-   디렉터리에 대해 지정된 새 이름에 콜론\(:\)이나 슬래시\(\\ 또는 \/\)가 포함된 경우\(<xref:System.ArgumentException>\)  
  
-   길이가 0인 문자열이거나, 공백만 포함하거나, 잘못된 문자를 포함하거나, \\\\.\\로 시작하는 장치 경로와 같은 여러 가지 이유 중 하나로 경로가 올바르지 않은 경우  \\\) \(<xref:System.ArgumentException>\).  
  
-   경로가 `Nothing`이기 때문에 올바르지 않은 경우\(<xref:System.ArgumentNullException>\)  
  
-   `destinationDirectoryName`이 `Nothing`이거나 빈 문자열인 경우\(<xref:System.ArgumentNullException>\)  
  
-   소스 디렉터리가 없는 경우\(<xref:System.IO.DirectoryNotFoundException>\)  
  
-   소스 디렉터리가 루트 디렉터리인 경우\(<xref:System.IO.IOException>\)  
  
-   조합된 경로가 기존 파일을 가리키는 경우\(<xref:System.IO.IOException>\)  
  
-   소스 경로와 대상 경로가 같은 경우\(<xref:System.IO.IOException>\)  
  
-   `ShowUI`가 `UIOption.AllDialogs`로 설정되어 있는데 사용자가 작업을 취소했거나 디렉터리에서 하나 이상의 파일을 복사할 수 없는 경우\(<xref:System.OperationCanceledException>\)  
  
-   작업이 순환적인 경우\(<xref:System.InvalidOperationException>\)  
  
-   경로에 콜론\(:\)이 포함된 경우\(<xref:System.NotSupportedException>\)  
  
-   경로가 시스템 정의 최대 길이를 초과하는 경우\(<xref:System.IO.PathTooLongException>\)  
  
-   경로의 파일 이름이나 폴더 이름에 콜론\(:\)이 있거나 이름의 형식이 잘못된 경우\(<xref:System.NotSupportedException>\)  
  
-   경로를 보는 데 필요한 권한이 사용자에게 없는 경우\(<xref:System.Security.SecurityException>\)  
  
-   대상 파일은 있지만 액세스할 수 없는 경우\(<xref:System.UnauthorizedAccessException>\)  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyDirectory%2A>   
 [How to: Find Subdirectories with a Specific Pattern](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-subdirectories-with-a-specific-pattern.md)   
 [How to: Get the Collection of Files in a Directory](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-get-the-collection-of-files-in-a-directory.md)