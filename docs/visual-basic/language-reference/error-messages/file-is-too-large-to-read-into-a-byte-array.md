---
title: "파일이 너무 커서 바이트 배열로 읽어 들일 수 없습니다."
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: 686630a6-a439-46c7-8d7b-34613ae4c5d8
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2bbdb5a4dcaa22ca84428ef28c8838a6d9a0ee1b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="file-is-too-large-to-read-into-a-byte-array"></a>파일이 너무 커서 바이트 배열로 읽어 들일 수 없습니다.
바이트 배열로 읽을 하려는 파일의 크기는 4GB를 초과 합니다. `My.Computer.FileSystem.ReadAllBytes` 메서드는이 크기를 초과 하는 파일을 읽을 수 없습니다.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   사용 하 여 한 <xref:System.IO.StreamReader> 파일을 읽을 수 있습니다. 자세한 내용은 참조 [기본 사항의.NET Framework 파일 I/O 및 파일 시스템 (Visual Basic)](../../../visual-basic/developing-apps/programming/drives-directories-files/basics-of-net-framework-file-io-and-the-file-system.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.ReadAllBytes%2A>  
 <xref:System.IO.StreamReader>  
 [Visual Basic을 사용한 파일 액세스](../../../visual-basic/developing-apps/programming/drives-directories-files/file-access.md)  
 [방법: StreamReader를 사용하여 파일에서 텍스트 읽기](../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-read-text-from-files-with-a-streamreader.md)
