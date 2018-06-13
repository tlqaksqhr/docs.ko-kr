---
title: 파일이 너무 커서 바이트 배열로 읽어 들일 수 없습니다.
ms.date: 07/20/2015
ms.assetid: 686630a6-a439-46c7-8d7b-34613ae4c5d8
ms.openlocfilehash: 1b04d47cab77269a0ce84ef77c162a4401d99d9e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33585927"
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
