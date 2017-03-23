---
title: "Shadows (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Shadows"
  - "shadows"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "shadowing"
  - "duplicate names"
  - "scope, shadowing"
  - "Shadows keyword"
  - "names, shadowing"
ms.assetid: 6bf687cd-0544-4797-b51b-911125ec57c6
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# Shadows (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

선언된 프로그래밍 요소가 기본 클래스에서 같은 이름의 요소나 오버로드된 요소 집합을 다시 선언하고 숨기도록 지정합니다.  
  
## 설명  
 숨김\(*이름으로 숨김*이라고도 함\)의 목적은 클래스 멤버의 정의를 유지하는 것입니다.  기본 클래스에서는 이미 정의한 요소와 같은 이름의 요소를 만드는 경우가 있을 수 있습니다.  이러한 경우 `Shadows` 한정자를 사용하면 클래스를 통한 참조가 새 기본 클래스 요소 대신 이미 정의한 멤버로 확인됩니다.  
  
 숨김과 재정의는 둘 다 상속된 요소를 다시 정의하지만 두 방식에는 큰 차이가 있습니다.  자세한 내용은 [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)를 참조하십시오.  
  
## 규칙  
  
-   **선언 컨텍스트.** `Shadows`는 클래스 수준에서만 사용할 수 있습니다.  즉, `Shadows` 요소의 선언 컨텍스트가 클래스여야 하며 소스 파일, 네임스페이스, 인터페이스, 모듈, 구조체 또는 프로시저일 수는 없습니다.  
  
     하나의 선언문에서는 하나의 숨기는 요소만 선언할 수 있습니다.  
  
-   **결합 한정자.** 하나의 선언에서 `Shadows`를 `Overloads`, `Overrides` 또는 `Static`과 함께 지정할 수 없습니다.  
  
-   **요소 형식.** 다른 요소를 사용하여 선언된 모든 요소를 숨길 수 있습니다.  다른 속성이나 프로시저를 사용하여 특정 속성이나 프로시저를 숨기는 경우 매개 변수 및 반환 형식이 기본 클래스 속성 또는 프로시저의 매개 변수 및 반환 형식과 일치하지 않아도 됩니다.  
  
-   **액세스.** 일반적으로 기본 클래스의 숨겨진 요소를 숨기는 파생 클래스에서는 해당 요소를 사용할 수 없습니다.  그러나 다음 고려 사항이 적용됩니다.  
  
    -   숨기는 요소가 해당 요소를 참조하는 코드에서 액세스할 수 없는 요소인 경우 참조는 숨겨진 요소로 확인됩니다.  예를 들어, `Private` 요소가 기본 클래스 요소를 숨기면 `Private` 요소에 대한 액세스 권한이 없는 코드에서는 기본 클래스 요소에 대신 액세스합니다.  
  
    -   요소를 숨기는 경우 기본 클래스의 형식을 사용하여 선언된 개체를 통해 숨겨진 요소에 계속 액세스할 수 있습니다.  또한 `MyBase`를 통해 액세스할 수도 있습니다.  
  
 `Shadows` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.  
  
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
 [Shared](../../../visual-basic/language-reference/modifiers/shared.md)   
 [Static](../../../visual-basic/language-reference/modifiers/static.md)   
 [Private](../../../visual-basic/language-reference/modifiers/private.md)   
 [Me, My, MyBase, and MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)   
 [Inheritance Basics](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)   
 [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)   
 [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)   
 [Overloads](../../../visual-basic/language-reference/modifiers/overloads.md)   
 [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md)   
 [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md)   
 [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)