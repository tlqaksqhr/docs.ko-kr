---
title: "Public (Visual Basic) | Microsoft Docs"
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
  - "vb.Public"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Public keyword"
  - "Public keyword, syntax"
  - "Public access modifier"
ms.assetid: 284c9e1b-ed23-499b-9bc9-ad87c11485a5
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Public (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

제한 사항에 액세스할 수 없는 하나 이상의 선언된 프로그래밍 요소를 지정합니다.  
  
## 설명  
 클래스 라이브러리와 같은 구성 요소나 구성 요소 집합을 게시하는 경우 어셈블리와 상호 운용하는 모든 코드에서 프로그래밍 요소에 액세스할 수 있도록 설정할 수 있습니다.  요소에 제한 없이 액세스하려면 `Public`을 사용하여 요소를 선언합니다.  
  
 프로그래밍 요소에 대한 액세스를 제한할 필요가 없는 경우에는 공용 액세스가 프로그래밍 요소의 일반적인 수준입니다.  인터페이스, 모듈, 클래스 또는 구조체 내에 선언된 요소의 액세스 수준은 사용자가 별도로 선언하지 않는 한 기본적으로 `Public`입니다.  
  
## 규칙  
  
-   **선언 컨텍스트.** `Public` 키워드는 모듈, 인터페이스 또는 네임스페이스 수준에서만 사용할 수 있습니다.  `Public` 요소의 선언 컨텍스트는 소스 파일, 네임스페이스, 인터페이스, 모듈, 클래스 또는 구조체여야 하며 프로시저일 수는 없습니다.  
  
## 동작  
  
-   **액세스 수준.** 모듈, 클래스 또는 구조체에 액세스할 수 있는 모든 코드는 해당 `Public` 요소에 액세스할 수 있습니다.  
  
-   **기본 액세스.** 프로시저 내의 지역 변수는 기본적으로 공용 액세스이며 이러한 지역 변수에 액세스 한정자를 사용할 수 없습니다.  
  
-   **액세스 한정자** 액세스 수준을 지정하는 키워드를 *액세스 한정자*라고 합니다.  액세스 한정자를 비교한 내용을 보려면 [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)을 참조하십시오.  
  
 `Public` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.  
  
 [Class 문](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [Const 문](../../../visual-basic/language-reference/statements/const-statement.md)  
  
 [Declare 문](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Delegate 문](../../../visual-basic/language-reference/statements/delegate-statement.md)  
  
 [Dim 문](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Enum 문](../../../visual-basic/language-reference/statements/enum-statement.md)  
  
 [Event 문](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Interface 문](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 [Module 문](../../../visual-basic/language-reference/statements/module-statement.md)  
  
 [Operator 문](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [Property 문](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Structure 문](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
 [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## 참고 항목  
 [Protected](../../../visual-basic/language-reference/modifiers/protected.md)   
 [Friend](../../../visual-basic/language-reference/modifiers/friend.md)   
 [Private](../../../visual-basic/language-reference/modifiers/private.md)   
 [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)   
 [Procedures](../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Structures](../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Objects and Classes](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)