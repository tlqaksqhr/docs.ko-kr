---
title: "Protected (Visual Basic) | Microsoft Docs"
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
  - "vb.Protected"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Protected Friend keyword combination"
  - "Protected keyword, and Friend"
  - "Protected keyword, syntax"
  - "Protected access modifier"
  - "Protected keyword"
ms.assetid: 74ad3d56-309f-49d2-b60c-1d0157d010e8
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Protected (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

하나 이상의 선언된 프로그래밍 요소를 고유한 클래스나 파생 클래스에서만 액세스할 수 있도록 지정합니다.  
  
## 설명  
 경우에 따라서는 클래스에서 선언된 프로그래밍 요소가 중요한 데이터나 제한된 코드를 포함하기 때문에 해당 요소에 대한 액세스를 제한하는 것이 필요할 수 있습니다.  그러나 클래스를 상속할 수 있으며 파생 클래스의 계층이 예상될 경우에는 이러한 파생 클래스에서 데이터나 코드에 액세스해야 할 수 있습니다.  이러한 경우 기본 클래스와 모든 파생 클래스에서 요소를 액세스할 수 있도록 할 수 있습니다.  이러한 방식으로 요소에 대한 액세스를 제한하려면 `Protected`를 사용하여 선언하면 됩니다.  
  
## 규칙  
  
-   **선언 컨텍스트.** `Protected`는 클래스 수준에서만 사용할 수 있습니다.  즉, `Protected` 요소의 선언 컨텍스트는 클래스여야 하며 소스 파일, 네임스페이스, 인터페이스, 모듈, 구조체 또는 프로시저일 수는 없습니다.  
  
-   **결합 한정자.** 하나의 선언에서 `Protected` 한정자를 [Friend](../../../visual-basic/language-reference/modifiers/friend.md) 한정자와 함께 사용할 수 있습니다.  이러한 방식으로 함께 사용하면 동일한 어셈블리의 모든 위치, 고유한 클래스 및 파생 클래스에서 선언된 요소에 액세스할 수 있습니다.  클래스의 멤버에만 `Protected Friend`를 지정할 수 있습니다.  
  
## 동작  
  
-   **액세스 수준.** 클래스의 모든 코드에서 해당 요소에 액세스할 수 있습니다.  기본 클래스에서 파생된 모든 클래스의 코드는 기본 클래스의 모든 `Protected` 요소에 액세스할 수 있습니다.  파생을 통해 생성된 모든 것도 마찬가지입니다.  즉, 클래스가 기본 클래스의 `Protected` 요소에 액세스할 수 있음을 의미합니다.  
  
     Protected 액세스는 Friend 액세스의 상위 집합 또는 하위 집합이 아닙니다.  
  
-   **액세스 한정자** 액세스 수준을 지정하는 키워드를 *액세스 한정자*라고 합니다.  액세스 한정자를 비교한 내용을 보려면 [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)을 참조하십시오.  
  
 `Protected` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.  
  
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
 [Friend](../../../visual-basic/language-reference/modifiers/friend.md)   
 [Private](../../../visual-basic/language-reference/modifiers/private.md)   
 [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)   
 [Procedures](../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Structures](../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Objects and Classes](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)