---
title: "방법: Visual Basic에서 다른 디렉터리에 파일의 복사본 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- My.Computer.FileSystem.CopyFile method, copying files [Visual Basic]
- files, copying
- CopyFile method, copying files in Visual Basic
- I/O [Visual Basic], copying files
ms.assetid: 88e2145c-d414-45a5-ad03-6f5d58ecca26
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: a51633fa65321325e1ae08c1e03cf2392f771cc9
ms.contentlocale: ko-kr
ms.lasthandoff: 05/22/2017

---
# <a name="how-to-create-a-copy-of-a-file-in-a-different-directory-in-visual-basic"></a>방법: Visual Basic에서 다른 디렉터리에 파일의 복사본 만들기
`My.Computer.FileSystem.CopyFile` 메서드를 사용하면 파일을 복사할 수 있습니다. 해당 매개 변수를 통해 기존 파일을 덮어쓰고, 파일 이름을 바꾸고, 작업의 진행률을 표시하고, 사용자가 작업을 취소할 수 있습니다.  
  
### <a name="to-copy-a-text-file-to-another-folder"></a>텍스트 파일을 다른 폴더로 복사하려면  
  
-   원본 파일과 대상 디렉터리를 지정해서 `CopyFile` 메서드를 사용하여 파일을 복사합니다. `overwrite` 매개 변수를 사용하면 기존 파일을 덮어쓸지 여부를 지정할 수 있습니다. 다음 코드 예제에서는 `CopyFile`을 사용하는 방법을 보여 줍니다.  
  
     [!code-vb[VbFileIOMisc#24](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-create-a-copy-of-a-file-in-a-different-directory_1.vb)]  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 다음 조건에서는 예외가 throw될 수 있습니다.  
  
-   길이가 0인 문자열이거나, 공백만 포함하거나, 잘못된 문자를 포함하거나, 경로가 장치 경로인 경우(\\\\.\\로 시작됨)와 같은 여러 가지 이유 중 하나로 경로가 올바르지 않은 경우(<xref:System.ArgumentException>)  
  
-   시스템이 절대 경로를 검색할 수 없는 경우(<xref:System.ArgumentException>)  
  
-   경로가 `Nothing`이기 때문에 유효하지 않은 경우(<xref:System.ArgumentNullException>)  
  
-   소스 파일이 잘못되었거나 없는 경우(<xref:System.IO.FileNotFoundException>)  
  
-   조합된 경로가 기존 디렉터리를 가리키는 경우(<xref:System.IO.IOException>)  
  
-   대상 파일이 있고 `overwrite`가 `False`로 설정된 경우(<xref:System.IO.IOException>)  
  
-   사용자에게 파일에 액세스할 수 있는 권한이 없는 경우(<xref:System.IO.IOException>)  
  
-   대상 폴더에 있는 동일한 이름의 파일이 사용 중인 경우(<xref:System.IO.IOException>)  
  
-   경로의 파일 이름이나 폴더 이름에 콜론(:)이 있거나 이름의 형식이 잘못된 경우(<xref:System.NotSupportedException>)  
  
-   `ShowUI`가 `True`로 설정되고, `onUserCancel`이 `ThrowException`으로 설정되고, 사용자가 작업을 취소한 경우(<xref:System.OperationCanceledException>)  
  
-   `ShowUI`가 `True`로 설정되고, `onUserCancel`이 `ThrowException`으로 설정되고, 지정되지 않은 I/O 오류가 발생한 경우(<xref:System.OperationCanceledException>)  
  
-   경로가 시스템 정의 최대 길이를 초과하는 경우(<xref:System.IO.PathTooLongException>)  
  
-   사용자에게 필요한 권한이 없는 경우(<xref:System.UnauthorizedAccessException>)  
  
-   경로를 보는 데 필요한 권한이 사용자에게 없는 경우(<xref:System.Security.SecurityException>)  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%2A>   
 <xref:Microsoft.VisualBasic.FileIO.UICancelOption>   
 [방법: 특정 패턴의 파일을 디렉터리에 복사](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-copy-files-with-a-specific-pattern-to-a-directory.md)   
 [방법: 동일한 디렉터리에 파일의 복사본 만들기](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-create-a-copy-of-a-file-in-the-same-directory.md)   
 [방법: 디렉터리를 다른 디렉터리에 복사](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-copy-a-directory-to-another-directory.md)   
 [방법: 파일 이름 바꾸기](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-rename-a-file.md)
