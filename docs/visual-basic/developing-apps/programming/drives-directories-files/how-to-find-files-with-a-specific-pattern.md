---
title: "How to: Find Files with a Specific Pattern in Visual Basic | Microsoft Docs"
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
  - "files, finding"
  - "pattern matching"
  - "patterns, matching"
ms.assetid: 25e3b71d-b844-4293-9e4e-f06c5836b5cc
caps.latest.revision: 23
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 23
---
# How to: Find Files with a Specific Pattern in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

<xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A> 메서드는 파일의 경로 이름을 나타내는 읽기 전용 문자열 컬렉션을 반환합니다.  `wildCards` 매개 변수를 사용하여 특정 패턴을 지정할 수 있습니다.  검색에 하위 디렉터리를 포함하려면 `searchType` 매개 변수를 `SearchOption.SearchAllSubDirectories`로 설정합니다.  
  
 지정된 패턴과 일치하는 파일이 없으면 빈 컬렉션이 반환됩니다.  
  
> [!NOTE]
>  사용 하 여 파일 목록을 반환 하는 방법에 대 한 정보는 `DirectoryInfo` 클래스의는 `System.IO` 네임 스페이스를 참조 하십시오 <xref:System.IO.DirectoryInfo.GetFiles%2A>.  
  
### 지정된 패턴의 파일을 찾으려면  
  
-   `GetFiles` 메서드를 사용하면서 검색할 디렉터리의 이름과 경로를 지정하고 패턴을 지정합니다.  다음 예제에서는 디렉터리에서 확장명이 `.dll`인 모든 파일을 찾아서 `ListBox1`에 추가합니다.  
  
     [!code-vb[VbFileIOMisc#4](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-find-files-with-a-specific-pattern_1.vb)]  
  
## .NET Framework 보안  
 다음 조건에서 예외가 발생할 수 있습니다.  
  
-   길이가 0인 문자열이거나, 공백만 포함하거나, 잘못된 문자를 포함하거나, \\\\.\\로 시작하는 장치 경로와 같은 여러 가지 이유 중 하나로 경로가 올바르지 않은 경우  \\\) \(<xref:System.ArgumentException>\).  
  
-   경로가 `Nothing`이기 때문에 올바르지 않은 경우\(<xref:System.ArgumentNullException>\)  
  
-   `directory`가 없는 경우\(<xref:System.IO.DirectoryNotFoundException>\)  
  
-   `directory`가 기존 파일을 가리키는 경우\(<xref:System.IO.IOException>\)  
  
-   경로가 시스템 정의 최대 길이를 초과하는 경우\(<xref:System.IO.PathTooLongException>\)  
  
-   경로의 파일 이름이나 폴더 이름에 콜론\(:\)이 있거나 이름의 형식이 잘못된 경우\(<xref:System.NotSupportedException>\)  
  
-   경로를 보는 데 필요한 권한이 사용자에게 없는 경우\(<xref:System.Security.SecurityException>\)  
  
-   사용자에게 필요한 권한이 없는 경우\(<xref:System.UnauthorizedAccessException>\)  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.GetFiles%2A>   
 [How to: Find Subdirectories with a Specific Pattern](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-subdirectories-with-a-specific-pattern.md)   
 [Troubleshooting: Reading from and Writing to Text Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)   
 [How to: Get the Collection of Files in a Directory](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-get-the-collection-of-files-in-a-directory.md)