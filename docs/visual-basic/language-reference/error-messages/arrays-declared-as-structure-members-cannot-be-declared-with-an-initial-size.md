---
title: 구조체 멤버로 선언된 배열은 초기 크기로 선언할 수 없습니다.
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31043
- bc31043
helpviewer_keywords:
- BC31043
ms.assetid: 5bd90c71-1b78-444b-91e1-4789451ef085
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 983154a144a79991c86db5056ad0e0e563a3ba73
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="arrays-declared-as-structure-members-cannot-be-declared-with-an-initial-size"></a>구조체 멤버로 선언된 배열은 초기 크기로 선언할 수 없습니다.
초기 크기는 구조체의 배열을 선언 됩니다. 구조체 요소를 초기화할 수 없습니다 및 초기화의 한 가지 형태는 배열 크기를 선언 합니다.  
  
 **오류 ID:** BC31043  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  동적 (초기 크기 없음)으로 구조에서 배열을 정의 합니다.  
  
2.  배열의 특정 크기, 필요한 경우 차원을 변경할 수 있습니다이 있는 동적 배열을 [ReDim 문을](../../../visual-basic/language-reference/statements/redim-statement.md) 코드를 실행 합니다. 다음은 이에 대한 예입니다.  
  
    ```  
    Structure demoStruct  
        Public demoArray() As Integer  
    End Structure  
    Sub useStruct()  
        Dim struct As demoStruct  
        ReDim struct.demoArray(9)  
        Struct.demoArray(2) = 777  
    End Sub  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [배열](../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [방법: 구조체 선언](../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
