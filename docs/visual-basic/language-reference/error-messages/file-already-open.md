---
title: 파일이 이미 열려 있습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrID55
ms.assetid: d674a0fb-ef16-4cc2-9da7-709a8a07dbea
ms.openlocfilehash: 75a08b411a4afd7ea8e11953f1d465b082faa712
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="file-already-open"></a>파일이 이미 열려 있습니다.
경우에 따라 파일을 닫아야 다른 것 보다 먼저 `FileOpen` 또는 기타 작업이 발생할 수 있습니다. 이 오류의 가능한 원인:  
  
-   순차적 출력 모드 `FileOpen` 이미 열려 있는 파일에 대 한 작업을 실행 했습니다  
  
-   문에서 열려 있는 파일을 참조 합니다.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  문을 실행 하기 전에 파일을 닫습니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.FileSystem.FileOpen%2A>
