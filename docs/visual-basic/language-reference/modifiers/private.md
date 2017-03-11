---
title: "Private (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Private"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Private keyword"
  - "Private keyword, syntax"
ms.assetid: aba74a2e-5824-4613-bf63-b9ec7787f4e6
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# Private (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

하나 이상의 선언된 프로그래밍 요소를 포함된 모든 형식을 비롯하여 해당 선언 컨텍스트에서만 액세스할 수 있도록 지정합니다.  
  
## 설명  
 프로그래밍 요소가 소유권이 있는 기능이거나 기밀 데이터를 포함할 경우에는 액세스를 최대한 엄격하게 제한해야 할 수 있습니다.  해당 요소를 정의하는 모듈, 클래스 또는 구조체에서만 액세스할 수 있도록 하여 액세스를 최대한 제한할 수 있습니다.  이러한 방식으로 요소에 대한 액세스를 제한하려면 `Private`를 사용하여 선언하면 됩니다.  
  
## 규칙  
  
-   **선언 컨텍스트.** `Private` 키워드는 모듈 수준에서만 사용할 수 있습니다.  즉, `Private` 요소의 선언 컨텍스트는 모듈, 클래스 또는 구조체여야 하며, 소스 파일, 네임스페이스, 인터페이스 또는 프로시저일 수는 없습니다.  
  
## 동작  
  
-   **액세스 수준.** 선언 컨텍스트 내의 모든 코드에서 해당 `Private` 요소에 액세스할 수 있습니다.  여기에는 열거형의 할당식이나 중첩된 클래스 같은 포함된 형식 내의 코드가 포함됩니다.  선언 컨텍스트 외부의 코드에서는 해당 `Private` 요소에 액세스할 수 없습니다.  
  
-   **액세스 한정자** 액세스 수준을 지정하는 키워드를 *액세스 한정자*라고 합니다.  액세스 한정자를 비교한 내용을 보려면 [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)을 참조하십시오.  
  
 `Private` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.  
  
 [Class 문](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [Const 문](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [Declare 문](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Delegate 문](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [Dim 문](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Enum 문](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [Event 문](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Interface 문](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [Property 문](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Structure 문](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## 참고 항목  
 [Public](../../../visual-basic/language-reference/modifiers/public.md)   
 [Protected](../../../visual-basic/language-reference/modifiers/protected.md)   
 [Friend](../../../visual-basic/language-reference/modifiers/friend.md)   
 [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)   
 [Procedures](../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Structures](../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Objects and Classes](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)