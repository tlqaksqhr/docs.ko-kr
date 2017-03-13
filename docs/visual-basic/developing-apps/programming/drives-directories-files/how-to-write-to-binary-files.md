---
title: "How to: Write to Binary Files in Visual Basic | Microsoft Docs"
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
  - "files, binary access"
  - "WriteAllBytes method"
  - "binary files, writing in Visual Basic"
ms.assetid: 59fae125-de5b-4c96-883c-209f4a55112c
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# How to: Write to Binary Files in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

<xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllBytes%2A> 메서드는 데이터를 이진 파일에 씁니다.  `append` 매개 변수가 `True`이면 데이터가 파일에 추가되고 그렇지 않으면 파일의 데이터가 덮어쓰여집니다.  
  
 파일 이름을 제외한 지정된 경로가 올바르지 않으면 <xref:System.IO.DirectoryNotFoundException> 예외가 throw됩니다.  경로는 올바르지만 파일이 없으면 파일이 만들어집니다.  
  
### 이진 파일에 쓰려면  
  
-   파일 경로와 이름 및 쓸 바이트를 지정하여 `WriteAllBytes` 메서드를 사용합니다.  이 예제에서는 데이터 배열인 `CustomerData`를 `CollectedData.dat`라는 파일에 추가합니다.  
  
     [!code-vb[VbVbcnMyFileSystem#27](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-write-to-binary-files_1.vb)]  
  
## 강력한 프로그래밍  
 다음 조건에서 예외가 발생합니다.  
  
-   길이가 0인 문자열이거나, 공백만 포함하거나, 잘못된 문자가 포함된 경우와 같은 여러 가지 이유 중 하나로 경로가 올바르지 않은 경우  \(<xref:System.ArgumentException>\).  
  
-   경로가 `Nothing`이기 때문에 올바르지 않은 경우\(<xref:System.ArgumentNullException>\)  
  
-   `File`이 존재하지 않는 경로를 가리키는 경우\(<xref:System.IO.FileNotFoundException> 또는 <xref:System.IO.DirectoryNotFoundException>\)  
  
-   다른 프로세스에서 파일을 사용 중이거나 I\/O 오류가 발생한 경우\(<xref:System.IO.IOException>\)  
  
-   경로가 시스템 정의 최대 길이를 초과하는 경우\(<xref:System.IO.PathTooLongException>\)  
  
-   경로의 파일 이름이나 디렉터리 이름에 콜론\(:\)이 있거나 이름의 형식이 잘못된 경우\(<xref:System.NotSupportedException>\)  
  
-   경로를 보는 데 필요한 권한이 사용자에게 없는 경우\(<xref:System.Security.SecurityException>\)  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllBytes%2A>   
 [How to: Write Text to Files](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-write-text-to-files.md)