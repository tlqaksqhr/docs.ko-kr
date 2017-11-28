---
title: "방법: Visual Basic에서 디렉터리 만들기"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- directories [Visual Basic], creating
- folders [Visual Basic], creating
ms.assetid: 0351a2ca-24d8-43b5-bb39-9b99e6401cff
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2e4cd94113d77b2f4ff8127c80174107966ef360
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-directory-in-visual-basic"></a>방법: Visual Basic에서 디렉터리 만들기
`My.Computer.FileSystem` 개체의 `CreateDirectory` 메서드를 사용하여 디렉터리를 만듭니다.  
  
 디렉터리가 이미 있는 경우 예외가 throw되지 않습니다.  
  
### <a name="to-create-a-directory"></a>디렉터리를 만들려면  
  
-   디렉터리를 만들어야 하는 위치의 전체 경로를 지정하여 `CreateDirectory` 메서드를 사용합니다. 이 예제에서는 `C:\Documents and Settings\All Users\Documents`에 `NewDirectory` 디렉터리를 만듭니다.  
  
     [!code-vb[VbVbcnMyFileSystem#2](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/how-to-create-a-directory_1.vb)]  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 다음 조건에서 예외가 발생합니다.  
  
-   디렉터리 이름 형식이 잘못된 경우. 예를 들어 잘못된 문자를 포함하거나 공백만으로 이루어져 있습니다(<xref:System.ArgumentException>).  
  
-   만들 디렉터리의 부모 디렉터리가 읽기 전용인 경우(<xref:System.IO.IOException>)  
  
-   디렉터리 이름이 `Nothing`인 경우(<xref:System.ArgumentNullException>)  
  
-   디렉터리 이름이 너무 긴 경우(<xref:System.IO.PathTooLongException>)  
  
-   디렉터리 이름이 콜론 “:”인 경우(<xref:System.NotSupportedException>)  
  
-   사용자에게 디렉터리를 만들 수 있는 권한이 없는 경우(<xref:System.UnauthorizedAccessException>)  
  
-   부분 신뢰 상황에서 사용자에게 권한이 없는 경우(<xref:System.Security.SecurityException>)  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.CreateDirectory%2A>  
 [파일/디렉터리 만들기, 삭제 및 이동](../../../../visual-basic/developing-apps/programming/drives-directories-files/creating-deleting-and-moving-files-and-directories.md)
