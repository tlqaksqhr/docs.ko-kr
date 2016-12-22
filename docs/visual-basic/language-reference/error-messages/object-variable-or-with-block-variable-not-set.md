---
title: "Object variable or With block variable not set | Microsoft Docs"
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
  - "vbrID91"
dev_langs: 
  - "VB"
ms.assetid: 2f03e611-f0ed-465c-99a2-a816e034faa3
caps.latest.revision: 9
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Object variable or With block variable not set
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

잘못된 변수를 참조하고 있습니다.  개체 변수를 만들려면 개체 변수를 선언한 다음 `Set` 문을 사용하여 개체 변수에 올바른 참조를 할당합니다.  마찬가지로 `With` 문 진입점을 실행하여 `With...End With` 블록을 초기화해야 합니다.  
  
### 이 오류를 해결하려면  
  
1.  개체 변수가 올바른 개체를 참조하는지 확인하여 해당 개체에 대한 참조를 지정하거나 다시 지정합니다.  
  
2.  `Nothing`으로 설정된 개체 변수를 사용하지 않도록 합니다.  
  
3.  `Add References` 대화 상자에서 개체가 설명된 개체 라이브러리를 선택했는지 확인합니다.  
  
4.  `With` 문 진입점을 실행하여 `With` 블록을 초기화했는지 확인합니다.  
  
## 참고 항목  
 [Object Variable Declaration](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)   
 [With...End With Statement](../../../visual-basic/language-reference/statements/with-end-with-statement.md)