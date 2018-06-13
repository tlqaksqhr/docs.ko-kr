---
title: 입력(값)이 파일의 끝을 넘습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrID62
ms.assetid: 65292704-6e7d-4622-9f50-eb655a59b016
ms.openlocfilehash: abd5f5c6e5df262d1deadd74f0a146a8d436ceb3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33586743"
---
# <a name="input-past-end-of-file"></a>입력(값)이 파일의 끝을 넘습니다.
중 하나는 `Input` 문에서 비어 있는 파일 또는 모든 데이터를 사용 하거나 사용에서 읽고는 `EOF` 파일 함수 이진 액세스를 위해 열렸습니다.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  사용 하 여는 `EOF` 직전 함수는 `Input` 문을 파일의 끝을 검색 합니다.  
  
2.  이진 액세스에 대 한 파일을 열면를 사용 하 여 `Seek` 및 `Loc`합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.FileSystem.Input%2A>  
 <xref:Microsoft.VisualBasic.FileSystem.EOF%2A>  
 <xref:Microsoft.VisualBasic.FileSystem.Seek%2A>  
 <xref:Microsoft.VisualBasic.FileSystem.Loc%2A>
