---
title: "Bad DLL calling convention | Microsoft Docs"
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
  - "vbrID49"
dev_langs: 
  - "VB"
ms.assetid: 7c7def45-b0ab-450f-ad3f-4383dfd9aed7
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Bad DLL calling convention
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

DLL\(동적 연결 라이브러리\)로 전달되는 인수는 루틴에서 필요한 인수와 정확히 일치해야 합니다.  호출 규칙에서는 숫자, 형식 및 인수의 순서를 다룹니다.  현재 프로그램에서 잘못된 인수의 형식 또는 개수가 전달되고 있는 DLL의 루틴을 호출하고 있습니다.  
  
### 이 오류를 해결하려면  
  
1.  모든 인수 형식이 호출하고 있는 루틴의 선언에 지정된 것과 동일한지 확인합니다.  
  
2.  호출하고 있는 루틴의 선언에 나타난 것과 같은 개수의 인수를 전달하고 있는지 확인합니다.  
  
3.  DLL 루틴에서 인수를 값으로 전달해야 하는 경우 루틴의 선언에서 이러한 인수가 `ByVal`로 지정되었는지 확인합니다.  
  
## 참고 항목  
 [Error Types](../../../visual-basic/programming-guide/language-features/error-types.md)   
 [Call Statement](../../../visual-basic/language-reference/statements/call-statement.md)   
 [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md)