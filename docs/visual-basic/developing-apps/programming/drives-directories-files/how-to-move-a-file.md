---
title: "방법: Visual Basic에서 파일 이동 | Microsoft Docs"
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
  - "파일, 이동"
ms.assetid: 53a7457b-5815-41ad-b37d-28537c1fb77a
caps.latest.revision: 20
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 20
---
# 방법: Visual Basic에서 파일 이동
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

`My.Computer.FileSystem.MoveFile` 메서드를 사용하여 파일을 다른 폴더로 이동할 수 있습니다. 대상 구조체가 없는 경우 새로 만듭니다.  
  
### 파일을 이동하려면  
  
-   `MoveFile` 메서드를 사용하여 소스 파일과 대상 파일의 위치 및 파일 이름을 지정하여 파일을 이동합니다. 이 예제에서는 이름이 `test.txt`인 파일을 `TestDir1`에서 `TestDir2`로 이동합니다. 여기서는 대상 파일 이름이 소스 파일 이름과 동일하더라도 대상 파일 이름을 지정했습니다.  
  
     [!code-vb[VbVbcnMyFileSystem#24](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/visualbasic/how-to-move-a-file_1.vb)]  
  
### 파일을 이동하고 이름을 바꾸려면  
  
-   `MoveFile` 메서드를 사용하여 소스 파일 이름과 위치, 대상 위치 및 대상 위치에서의 새 이름을 지정하여 파일을 이동합니다. 이 예제에서는 이름이 `test.txt`인 파일을 `TestDir1`에서 `TestDir2`로 이동하고 이름을 `nexttest.txt`로 바꿉니다.  
  
     [!code-vb[VbVbcnMyFileSystem#25](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/visualbasic/how-to-move-a-file_2.vb)]  
  
## 강력한 프로그래밍  
 다음 조건에서 예외가 발생합니다.  
  
-   빈 문자열이거나, 공백만 포함하거나, 잘못된 문자를 포함하거나, 경로가 장치 경로인 경우\(\\\\.\\로 시작됨\)와 같은 여러 가지 이유 중 하나로 경로가 올바르지 않은 경우\(<xref:System.ArgumentException>\)  
  
-   경로가 `Nothing`이기 때문에 올바르지 않은 경우\(<xref:System.ArgumentNullException>\)  
  
-   `destinationFileName`이 `Nothing`이거나 빈 문자열인 경우\(<xref:System.ArgumentNullException>\)  
  
-   소스 파일이 잘못되었거나 존재하지 않는 경우\(<xref:System.IO.FileNotFoundException>\)  
  
-   조합된 경로가 기존 디렉터리를 가리키거나, 대상 파일이 이미 있고 `overwrite`가 `False`로 설정되었거나, 대상 디렉터리에 있는 동일한 이름의 파일이 사용 중이거나, 사용자에게 파일에 액세스할 권한이 없는 경우\(<xref:System.IO.IOException>\)  
  
-   경로의 파일 이름이나 디렉터리 이름에 콜론\(:\)이 있거나 이름의 형식이 잘못된 경우\(<xref:System.NotSupportedException>\)  
  
-   `showUI`가 `True`로 설정되고, `onUserCancel`이 `ThrowException`으로 설정되고, 사용자가 작업을 취소했거나 지정되지 않은 I\/O 오류가 발생한 경우\(<xref:System.OperationCanceledException>\)  
  
-   경로가 시스템 정의 최대 길이를 초과하는 경우\(<xref:System.IO.PathTooLongException>\)  
  
-   경로를 보는 데 필요한 권한이 사용자에게 없는 경우\(<xref:System.Security.SecurityException>\)  
  
-   사용자에게 필요한 권한이 없는 경우\(<xref:System.UnauthorizedAccessException>\)  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.MoveFile%2A>   
 [How to: Rename a File](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-rename-a-file.md)   
 [How to: Create a Copy of a File in a Different Directory](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-create-a-copy-of-a-file-in-a-different-directory.md)   
 [방법: 파일 경로의 구문 분석](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)