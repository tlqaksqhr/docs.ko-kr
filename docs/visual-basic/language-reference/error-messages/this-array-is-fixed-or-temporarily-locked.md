---
title: "This array is fixed or temporarily locked (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrID10"
dev_langs: 
  - "VB"
ms.assetid: de6713a6-51d7-4edb-8515-d5fb544e2091
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# This array is fixed or temporarily locked (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

이 오류가 발생하는 원인은 다음과 같습니다.  
  
-   `ReDim`을 사용하여 고정 크기 배열 요소 개수를 변경하려고 했습니다.  
  
-   한 요소가 프로시저에 인수로 전달된 모듈 수준 동적 배열의 차원을 다시 지정하려고 했습니다.  요소가 전달되면 프로시저에 있는 참조 매개 변수에 메모리가 다시 할당되지 못하도록 배열이 잠깁니다.  
  
-   배열을 포함하고 있는 `Variant` 변수에 값을 할당하려고 했지만 `Variant`가 현재 잠겨 있습니다.  
  
### 이 오류를 해결하려면  
  
1.  배열이 프로시저에 선언된 경우 `ReDim`을 사용하여 고정 크기가 아닌 동적 배열을 만들거나 배열이 모듈 수준에서 선언된 경우 요소 개수를 지정하지 않고 배열을 선언합니다.  
  
2.  모듈의 프로시저에서 모두 요소가 표시되는데 굳이 요소를 전달해야 할 필요가 있는지 확인합니다.  
  
3.  `Variant`를 잠그고 있는 것을 확인하여 잠금을 해제합니다.  
  
## 참고 항목  
 [배열](../../../visual-basic/programming-guide/language-features/arrays/index.md)