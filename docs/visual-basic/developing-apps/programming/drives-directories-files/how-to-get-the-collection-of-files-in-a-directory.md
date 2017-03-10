---
title: "How to: Get the Collection of Files in a Directory in Visual Basic | Microsoft Docs"
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
  - "folders, working with"
  - "files, accessing"
ms.assetid: 6c8ba7e8-dd37-4853-92bf-762b67c98160
caps.latest.revision: 23
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 23
---
# How to: Get the Collection of Files in a Directory in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

<xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A?displayProperty=fullName> 메서드의 오버로드는 디렉터리 내의 파일 이름을 나타내는 문자열의 읽기 전용 컬렉션을 반환합니다.  
  
-   하위 디렉터리를 검색하지 않고 지정된 디렉터리에서 단순 파일 검색을 수행하려면 <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%28System.String%29> 오버로드를 사용합니다.  
  
-   검색을 위한 추가 옵션을 지정하려면 [GetFiles\(String, SearchOption, String\<xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%28System.String%2CMicrosoft.VisualBasic.FileIO.SearchOption%2CSystem.String%5B%5D%29> 오버로드를 사용합니다.  `wildCards` 매개 변수를 사용하면 검색 패턴을 지정할 수 있습니다.  검색에 하위 디렉터리를 포함하려면 `searchType` 매개 변수를 <xref:Microsoft.VisualBasic.FileIO.SearchOption?displayProperty=fullName>로 설정합니다.  
  
 지정한 패턴과 일치하는 파일이 없으면 빈 컬렉션이 반환됩니다.  
  
### 디렉터리의 파일을 나열하려면  
  
-   <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A?displayProperty=fullName> 메서드 오버로드 중 하나를 사용하고 `directory` 매개 변수에서 검색할 디렉터리의 이름과 경로를 제공합니다.  다음 예에서는 디렉터리의 모든 파일을 반환하여  `ListBox1`에 추가합니다.  
  
     [!code-vb[VbVbcnMyFileSystem#32](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/visualbasic/how-to-get-the-collectio_1.vb)]  
  
## 강력한 프로그래밍  
 다음 조건에서 예외가 발생합니다.  
  
-   길이가 0인 문자열이거나, 공백만 포함하거나, 잘못된 문자를 포함하거나, 경로가 장치 경로인 경우\(\\\\.\\로 시작됨\)와 같은 여러 가지 이유 중 하나로 경로가 올바르지 않은  경우\(<xref:System.ArgumentException>\).  
  
-   경로가 `Nothing`이기 때문에 올바르지 않은 경우\(<xref:System.ArgumentNullException>\)  
  
-   `directory`가 없는 경우\(<xref:System.IO.DirectoryNotFoundException>\)  
  
-   `directory`가 기존 파일을 가리키는 경우\(<xref:System.IO.IOException>\)  
  
-   경로가 시스템 정의 최대 길이를 초과하는 경우\(<xref:System.IO.PathTooLongException>\)  
  
-   경로의 파일 이름이나 디렉터리 이름에 콜론\(:\)이 있거나 이름의 형식이 잘못된 경우\(<xref:System.NotSupportedException>\)  
  
-   경로를 보는 데 필요한 권한이 사용자에게 없는 경우\(<xref:System.Security.SecurityException>\)  
  
-   사용자에게 필요한 권한이 없는 경우\(<xref:System.UnauthorizedAccessException>\)  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A>   
 [How to: Find Files with a Specific Pattern](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-files-with-a-specific-pattern.md)   
 [How to: Find Subdirectories with a Specific Pattern](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-subdirectories-with-a-specific-pattern.md)