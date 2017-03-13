---
title: "How to: Write Text to Files in Visual Basic | Microsoft Docs"
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
  - "files, writing to"
  - "text, writing to files"
  - "writing to files"
  - "examples [Visual Basic], text files"
ms.assetid: 304956eb-530d-4df7-b48f-9b4d1f2581a0
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# How to: Write Text to Files in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

<xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A> 메서드를 사용하여 파일에 텍스트를 쓸 수 있습니다.  지정된 파일이 없으면 새로 만들어집니다.  
  
## 절차  
  
#### 파일에 텍스트를 쓰려면  
  
-   파일에 텍스트를 쓰려면 `WriteAllText` 메서드를 사용하면서 쓸 파일 및 텍스트를 지정합니다.  이 예제에서는 `"This is new text."`라는 줄을 `test.txt` 파일에 쓰면서 텍스트를 파일의 기존 텍스트에 추가합니다.  
  
     [!code-vb[VbFileIOWrite#3](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files_1.vb)]  
  
#### 파일에 일련의 문자열을 쓰려면  
  
-   문자열 컬렉션을 순환하며 검색합니다.  `WriteAllText` 메서드를 사용하여 추가할 대상 파일과 문자열을 지정하고 `append`를 `True`로 설정하여 파일에 텍스트를 씁니다.  
  
     이 예제에서는 `Documents and Settings` 디렉터리에 있는 파일의 이름을 `FileList.txt`에 쓰고 가독성을 높이기 위해 각 이름 사이에 캐리지 리턴을 삽입합니다.  
  
     [!code-vb[VbFileIOWrite#4](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-text-to-files_2.vb)]  
  
## 강력한 프로그래밍  
 다음 조건에서 예외가 발생할 수 있습니다.  
  
-   길이가 0인 문자열이거나, 공백만 포함하거나, 잘못된 문자를 포함하거나, \\\\.\\로 시작하는 장치 경로와 같은 여러 가지 이유 중 하나로 경로가 올바르지 않은 경우  \\\) \(<xref:System.ArgumentException>\).  
  
-   경로가 `Nothing`이기 때문에 올바르지 않은 경우\(<xref:System.ArgumentNullException>\)  
  
-   `File`이 존재하지 않는 경로를 가리키는 경우\(<xref:System.IO.FileNotFoundException> 또는 <xref:System.IO.DirectoryNotFoundException>\)  
  
-   다른 프로세스에서 파일을 사용 중이거나 I\/O 오류가 발생한 경우\(<xref:System.IO.IOException>\)  
  
-   경로가 시스템 정의 최대 길이를 초과하는 경우\(<xref:System.IO.PathTooLongException>\)  
  
-   경로의 파일 이름이나 디렉터리 이름에 콜론\(:\)이 있거나 이름의 형식이 잘못된 경우\(<xref:System.NotSupportedException>\)  
  
-   경로를 보는 데 필요한 권한이 사용자에게 없는 경우\(<xref:System.Security.SecurityException>\)  
  
-   디스크가 꽉 찼고 `WriteAllText`에 대한 호출이 실패한 경우\(<xref:System.IO.IOException>\)  
  
 부분 신뢰 컨텍스트에서 실행 중인 경우에는 불충분한 권한 때문에 코드에서 예외를 throw할 수 있습니다.  자세한 내용은 [코드 액세스 보안 기본 사항](../Topic/Code%20Access%20Security%20Basics.md)을 참조하십시오.  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>   
 [How to: Read from Text Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-from-text-files.md)