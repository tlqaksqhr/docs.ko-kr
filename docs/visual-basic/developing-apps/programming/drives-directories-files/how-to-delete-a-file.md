---
title: "How to: Delete a File in Visual Basic | Microsoft Docs"
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
  - "Delete method"
  - "files, deleting"
  - "files, manipulating"
  - "File object"
ms.assetid: 4b721769-3e45-4be7-b7fe-b08dc4141b44
caps.latest.revision: 24
caps.handback.revision: 24
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Delete a File in Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

`My.Computer.FileSystem` 개체의 `DeleteFile` 메서드를 사용하면 파일을 삭제할 수 있습니다.  이 메서드에서는 삭제된 파일을 **휴지통**으로 보낼 것인지 여부, 파일 삭제를 사용자에게 확인할 것인지 여부, 사용자가 작업을 취소했을 때 수행할 작업 등의 옵션을 제공합니다.  
  
### 텍스트 파일을 삭제하려면  
  
-   `DeleteFile` 메서드를 사용하여 파일을 삭제합니다.  다음 코드에서는 `test.txt`라는 이름의 파일을 삭제하는 방법을 보여 줍니다.  
  
     [!code-vb[VbVbcnMyFileSystem#22](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-delete-a-file_1.vb)]  
  
### 텍스트 파일을 삭제하고 사용자에게 파일을 삭제할 것인지 확인하려면  
  
-   `DeleteFile` 메서드를 사용하여 `showUI`를 `AllDialogs`로 설정하여 파일을 삭제합니다.  다음 코드에서는 `test.txt`라는 파일을 삭제하고 사용자에게 파일을 삭제할 것인지 확인하는 방법을 보여 줍니다.  
  
     [!code-vb[VbFileIOMisc#9](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-delete-a-file_2.vb)]  
  
### 텍스트 파일을 삭제하고 휴지통으로 보내려면  
  
-   `DeleteFile` 메서드를 사용하여 `recycle` 매개 변수에 `SendToRecycleBin`을 지정하여 파일을 삭제합니다.  다음 코드에서는 `test.txt`라는 파일을 삭제하고 **휴지통**으로 보내는 방법을 보여 줍니다.  
  
     [!code-vb[VbFileIOMisc#10](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-delete-a-file_3.vb)]  
  
## 강력한 프로그래밍  
 다음 조건에서 예외가 발생할 수 있습니다.  
  
-   길이가 0인 문자열이거나, 공백만 포함하거나, 잘못된 문자를 포함하거나, \\\\.\\로 시작하는 장치 경로와 같은 여러 가지 이유 중 하나로 경로가 올바르지 않은 경우  \\\) \(<xref:System.ArgumentException>\).  
  
-   경로가 `Nothing`이기 때문에 올바르지 않은 경우\(<xref:System.ArgumentNullException>\)  
  
-   경로가 시스템 정의 최대 길이를 초과하는 경우\(<xref:System.IO.PathTooLongException>\)  
  
-   경로의 파일 이름이나 폴더 이름에 콜론\(:\)이 있거나 이름의 형식이 잘못된 경우\(<xref:System.NotSupportedException>\)  
  
-   파일이 사용 중인 경우\(<xref:System.IO.IOException>\)  
  
-   경로를 보는 데 필요한 권한이 사용자에게 없는 경우\(<xref:System.Security.SecurityException>\)  
  
-   파일이 없는 경우\(<xref:System.IO.FileNotFoundException>\)  
  
-   사용자에게 파일을 삭제할 권한이 없거나 파일이 읽기 전용인 경우\(<xref:System.UnauthorizedAccessException>\)  
  
-   사용자에게 충분한 권한이 없는 부분 신뢰 상황인 경우\(<xref:System.Security.SecurityException>\)  
  
-   사용자가 작업을 취소했고 `onUserCancel`이 `ThrowException`으로 설정된 경우\(<xref:System.OperationCanceledException>\)  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.FileIO.UICancelOption>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>   
 <xref:Microsoft.VisualBasic.FileIO.UIOption>   
 <xref:Microsoft.VisualBasic.FileIO.RecycleOption>   
 [How to: Get the Collection of Files in a Directory](../Topic/How%20to:%20Get%20the%20Collection%20of%20Files%20in%20a%20Directory%20in%20Visual%20Basic.md)