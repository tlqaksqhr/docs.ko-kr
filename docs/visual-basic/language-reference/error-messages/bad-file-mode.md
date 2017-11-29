---
title: "파일 모드가 잘못되었습니다."
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID54
ms.assetid: 74891e96-884b-4c8d-872d-cd11ae272372
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a540135727eb97f4df5027e2ded7271e21bb4648
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="bad-file-mode"></a>파일 모드가 잘못되었습니다.
파일 내용을 조작에 사용 된 파일을 연 모드에 적합 해야 합니다. 이 오류가 발생하는 원인은 다음과 같습니다.  
  
-   A `FilePutObject` 또는 `FileGetObject` 문을 순차적 파일을 지정 합니다.  
  
-   A `Print` 이외의 액세스 모드에 대 한 열린 파일을 지정 하는 문을 `Output` 또는 `Append`합니다.  
  
-   `Input` 이외의 액세스 모드에 대 한 열린 파일을 지정 하는 문`Input`  
  
-   읽기 전용 파일에 쓰려고 했습니다.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   확인 `FilePutObject` 및 `FileGetObject` 만 참조 하는 파일에 대 한 열기 `Random` 또는 `Binary` 액세스 합니다.  
  
-   확인 `Print` 중 하나에 대 한 열린 파일을 지정 `Output` 또는 `Append` 액세스 모드입니다. 그렇지 않은 경우 파일에서 데이터를 배치 하는 다른 문을 사용 하거나 적절 한 모드에서 파일을 다시 합니다.  
  
-   확인 `Input` 에 대 한 열린 파일을 지정 `Input`합니다. 그렇지 않은 경우 다른 문을 사용 하 여 데이터 파일에 배치 하거나 적절 한 모드에서 파일을 다시 엽니다.  
  
-   읽기 전용 파일에 작성 하는 경우 파일의 읽기/쓰기 상태를 변경 하거나 쓰려고 시도 하지 마십시오.  
  
-   `My.Computer.FileSystem` 개체에서 사용할 수 있는 기능을 사용합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.FileSystem>  
 [문제 해결: 텍스트 파일 읽기 및 쓰기](../../../visual-basic/developing-apps/programming/drives-directories-files/troubleshooting-reading-from-and-writing-to-text-files.md)
