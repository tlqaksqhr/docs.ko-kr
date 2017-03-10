---
title: "Generic parameters used as optional parameter types must be class constrained | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc32124"
  - "bc32124"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC32124"
ms.assetid: 55aa8b2a-9ce3-4620-a710-2f9b0feb6143
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# Generic parameters used as optional parameter types must be class constrained
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

프로시저는 참조 형식으로 제한되지 않는 형식 매개 변수를 사용하는 선택적 매개 변수로 선언됩니다.  
  
 각 선택적 매개 변수에 대해 항상 기본값을 제공해야 합니다.  매개 변수가 참조 형식인 경우 선택적 값은 모든 참조 형식에 올바른 값인 `Nothing`이어야 합니다.  하지만 매개 변수가 값 형식이면 해당 형식은 Visual Basic에서 미리 정의한 기본 데이터 형식이어야 합니다.  이유는 사용자 정의 구조체와 같은 합성 값 형식에는 올바른 기본값이 없기 때문입니다.  
  
 선택적 매개 변수에 형식 매개 변수를 사용할 때 잘못된 기본값으로 값 형식이 되는 것을 방지하기 위해 참조 형식이 되도록 해야 합니다.  즉 형식 매개 변수를 `Class` 키워드나 특정 클래스의 이름으로 제한해야 합니다.  
  
 **오류 ID:** BC32124  
  
### 이 오류를 해결하려면  
  
-   참조 형식만 받아들이도록 제한하거나 선택적 매개 변수에 참조 형식을 사용하지 않습니다.  
  
## 참고 항목  
 [Visual Basic의 제네릭 형식](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [Type List](../../../visual-basic/language-reference/statements/type-list.md)   
 [Class Statement](../../../visual-basic/language-reference/statements/class-statement.md)   
 [Optional Parameters](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)   
 [Structures](../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Nothing](../../../visual-basic/language-reference/nothing.md)