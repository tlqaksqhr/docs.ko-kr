---
title: "Arrays declared as structure members cannot be declared with an initial size | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc31043"
  - "bc31043"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC31043"
ms.assetid: 5bd90c71-1b78-444b-91e1-4789451ef085
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Arrays declared as structure members cannot be declared with an initial size
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

배열을 구조체에 선언하는 데 초기 크기를 사용했습니다.  구조체 요소는 초기화할 수 없으며 배열 크기를 선언하는 것은 일종의 초기화에 포함됩니다.  
  
 **오류 ID:** BC31043  
  
### 이 오류를 해결하려면  
  
1.  구조체의 배열을 초기 크기가 지정되지 않은 동적 배열로 선언합니다.  
  
2.  일정한 크기의 배열이 필요할 경우 코드를 실행할 때 동적 배열의 차원을 [ReDim Statement](../../../visual-basic/language-reference/statements/redim-statement.md)로 다시 지정할 수 있습니다.  다음은 이에 대한 예입니다.  
  
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
  
## 참고 항목  
 [배열](../../../visual-basic/programming-guide/language-features/arrays/index.md)   
 [How to: Declare a Structure](../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)