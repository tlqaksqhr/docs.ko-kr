---
title: "Module Statement | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "Module"
  - "vb.Module"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "modules, classes"
  - "modules"
  - "Module statement"
  - "modules, declaring"
  - "standard modules"
  - "classes [Visual Basic], vs. modules"
  - "declarations, modules"
ms.assetid: a1243afc-14a5-45df-95d5-51118aeac362
caps.latest.revision: 24
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 24
---
# Module Statement
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

모듈 이름을 선언하고 모듈에 포함되는 변수, 속성, 이벤트 및 프로시저의 정의를 소개합니다.  
  
## 구문  
  
```  
[ <attributelist> ] [ accessmodifier ]  Module name  
    [ statements ]  
End Module  
```  
  
## 요소  
 `attributelist`  
 선택적 요소.  자세한 내용은 [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md)를 참조하십시오.  
  
 `accessmodifier`  
 선택적 요소.  다음 중 하나일 수 있습니다.  
  
-   [Public](../../../visual-basic/language-reference/modifiers/public.md)  
  
-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
 자세한 내용은 [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)를 참조하십시오.  
  
 `name`  
 필수 요소.  이 모듈의 이름입니다.  [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)를 참조하십시오.  
  
 `statements`  
 선택적 요소.  이 모듈의 변수, 속성, 이벤트, 프로시저 및 중첩 형식을 정의하는 문입니다.  
  
 `End Module`  
 `Module` 정의를 끝냅니다.  
  
## 설명  
 `Module` 문은 해당 네임스페이스에서 사용 가능한 참조 형식을 정의합니다.  *표준 모듈*이라고도 하는 *모듈* 은 클래스와 유사하지만 몇 가지 중요한 차이가 있습니다.  모든 모듈은 인스턴스가 하나이며 변수에 모듈을 만들거나 할당할 필요가 없습니다.  모듈은 상속 또는 구현 인터페이스를 지원하지 않습니다.  모듈은 클래스 또는 구조체와 같은 의미의 *형식*이 아니므로 프로그래밍 요소가 모듈의 데이터 형식을 갖도록 선언할 수 없습니다.  
  
 `Module`은 네임스페이스 수준에서만 사용할 수 있습니다.  즉, 모듈에 대한 *선언 컨텍스트*는 소스 파일 또는 네임스페이스이어야 하며 클래스, 구조체, 모듈, 인터페이스, 프로시저 또는 블록일 수 없습니다.  다른 모듈 또는 다른 형식 내에서 모듈을 중첩할 수 없습니다.  자세한 내용은 [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)을 참조하십시오.  
  
 모듈은 사용자의 프로그램과 수명이 동일합니다.  모듈의 멤버는 모두 `Shared`이므로 이들 또한 해당 프로그램과 수명이 동일합니다.  
  
 모듈은 기본적으로 [Friend](../../../visual-basic/language-reference/modifiers/friend.md) 액세스입니다.  액세스 한정자를 사용하여 액세스 수준을 조정할 수 있습니다.  자세한 내용은 [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)을 참조하십시오.  
  
 모듈의 모든 멤버는 암시적 `Shared`입니다.  
  
## 클래스 및 모듈  
 이 두 요소는 매우 유사하지만 몇 가지 중요한 면에서 서로 다릅니다.  
  
-   **용어.** 이전 버전의 Visual Basic에서는 두 가지 모듈 형식인 *클래스 모듈*\(.cls 파일\)과 *표준 모듈*\(.bas 파일\)을 인식합니다.  현재 버전에서는 이러한 *클래스*와 *모듈*을 각각 호출합니다.  
  
-   **공유 멤버.** 클래스 멤버가 공유 멤버인지 또는 인스턴스 멤버인지 제어할 수 있습니다.  
  
-   **개체 지향.** 클래스는 개체 지향적이지만 모듈은 그렇지 않습니다.  따라서 클래스만 개체로 인스턴스화될 수 있습니다.  자세한 내용은 [Objects and Classes](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)를 참조하십시오.  
  
## 규칙  
  
-   **한정자.** 모든 모듈 멤버는 암시적 [Shared](../../../visual-basic/language-reference/modifiers/shared.md)입니다.  멤버를 선언할 때 `Shared` 키워드를 사용할 수 없으며 멤버의 공유 상태를 변경할 수 없습니다.  
  
-   **상속.** 모듈은 모든 모듈이 상속되는 <xref:System.Object> 이외의 다른 형식에는 상속될 수 없습니다.  특히 하나의 모듈은 다른 모듈에서 상속할 수 없습니다.  
  
     <xref:System.Object>를 지정하려는 경우에도 모듈 정의에 [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md)을 사용할 수 없습니다.  
  
-   **기본 속성.** 모듈에서 기본 속성을 정의할 수 없습니다.  자세한 내용은 [Default](../../../visual-basic/language-reference/modifiers/default.md)을 참조하십시오.  
  
## 동작  
  
-   **액세스 수준.** 모듈 내에서는 각 멤버만의 액세스 수준으로 각 멤버를 선언할 수 있습니다.  모듈 멤버는 변수 및 상수를 제외하고 기본적으로 [Public](../../../visual-basic/language-reference/modifiers/public.md) 액세스이며 변수 및 상수는 기본적으로 [Private](../../../visual-basic/language-reference/modifiers/private.md) 액세스입니다.  모듈에 모듈 멤버의 액세스보다 더 제한된 액세스가 있는 경우 지정된 모듈 액세스 수준이 사용됩니다.  
  
-   **범위.** 모듈은 해당 네임스페이스의 범위 내에 있습니다.  
  
     모든 모듈 멤버의 범위는 전체 모듈입니다.  모든 멤버는 *형식 승격*을 거치게 됩니다. 그러면 멤버의 범위가 모듈을 포함하는 네임스페이스로 확장됩니다.  자세한 내용은 [Type Promotion](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md)를 참조하십시오.  
  
-   **한정자.** 한 프로젝트에 여러 모듈을 사용할 수 있으며 둘 이상의 모듈에서 같은 이름으로 멤버를 선언할 수 있습니다.  그러나 참조가 해당 모듈 외부의 것인 경우 적절한 모듈 이름으로 이러한 멤버에 대한 모든 참조를 한정해야 합니다.  자세한 내용은 [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)을 참조하십시오.  
  
## 예제  
 [!code-vb[VbVbalrStatements#69](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/module-statement_1.vb)]  
  
## 참고 항목  
 [Class Statement](../../../visual-basic/language-reference/statements/class-statement.md)   
 [Namespace Statement](../../../visual-basic/language-reference/statements/namespace-statement.md)   
 [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md)   
 [Interface Statement](../../../visual-basic/language-reference/statements/interface-statement.md)   
 [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md)   
 [Type Promotion](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md)