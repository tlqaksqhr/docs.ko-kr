---
title: "Class Statement (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Class"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "class modules"
  - "Class statement"
  - "classes [Visual Basic], fields"
  - "fields, of classes"
  - "class types, class statements"
  - "classes [Visual Basic], creating"
  - "classes [Visual Basic], data members"
  - "data members, of classes"
ms.assetid: f2664f38-eb5a-4d4b-a374-1d041521fb6c
caps.latest.revision: 29
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 29
---
# Class Statement (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

클래스의 이름을 선언하고 클래스가 구성하는 변수, 속성, 이벤트 및 프로시저의 정의를 소개합니다.  
  
## 구문  
  
```  
[ <attributelist> ] [ accessmodifier ] [ Shadows ] [ MustInherit | NotInheritable ] [ Partial ] _  
Class name [ ( Of typelist ) ]  
    [ Inherits classname ]  
    [ Implements interfacenames ]  
    [ statements ]  
End Class  
```  
  
## 요소  
  
|||  
|-|-|  
|용어|정의|  
|`attributelist`|선택적 요소.  [특성 목록](../../../visual-basic/language-reference/statements/attribute-list.md)을 참조하십시오.|  
|`accessmodifier`|선택적 요소.  다음 중 하나일 수 있습니다.<br /><br /> -   [Public](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [Protected](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [Private](../../../visual-basic/language-reference/modifiers/private.md)<br />-   `Protected Friend`<br /><br /> 자세한 내용은 [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)를 참조하십시오.|  
|`Shadows`|선택적 요소.  [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)를 참조하십시오.|  
|`MustInherit`|선택적 요소.  자세한 내용은 [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md)를 참조하십시오.|  
|`NotInheritable`|선택적 요소.  자세한 내용은 [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md)를 참조하십시오.|  
|`Partial`|선택적 요소.  클래스의 부분 정의를 나타냅니다.  자세한 내용은 [Partial](../../../visual-basic/language-reference/modifiers/partial.md)를 참조하십시오.|  
|`name`|필수 요소.  클래스의 이름입니다.  [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)를 참조하십시오.|  
|`Of`|선택적 요소.  이 클래스가 제네릭 클래스라는 것을 지정합니다.|  
|`typelist`|[Of](../../../visual-basic/language-reference/statements/of-clause.md) 키워드를 사용하는 경우 필수적 요소입니다.  이 클래스에 대한 형식 매개 변수의 목록입니다.  [형식 목록](../../../visual-basic/language-reference/statements/type-list.md)을 참조하십시오.|  
|`Inherits`|선택적 요소.  이 클래스가 다른 클래스의 멤버를 상속한다는 것을 나타냅니다.  자세한 내용은 [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md)를 참조하십시오.|  
|`classname`|`Inherits` 문을 사용하는 경우 필수적 요소입니다.  이 클래스가 파생되는 클래스의 이름입니다.|  
|`Implements`|선택적 요소.  이 클래스에서 하나 이상의 인터페이스 멤버를 구현한다는 것을 나타냅니다.  자세한 내용은 [Implements Statement](../../../visual-basic/language-reference/statements/implements-statement.md)를 참조하십시오.|  
|`interfacenames`|`Implements` 문을 사용하는 경우 필수적 요소입니다.  이 클래스에서 구현하는 인터페이스의 이름입니다.|  
|`statements`|선택적 요소.  이 클래스의 멤버를 정의하는 문입니다.|  
|`End Class`|필수 요소.  `Class` 정의를 끝냅니다.|  
  
## 설명  
 `Class` 문은 새 데이터 형식을 정의합니다.  *클래스*는 OOP\(개체 지향 프로그래밍\)의 기본 빌딩 블록입니다.  자세한 내용은 [Objects and Classes](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)를 참조하십시오.  
  
 `Class`는 네임스페이스 또는 모듈 수준에서만 사용할 수 있습니다.  즉, 클래스에 대한 *선언 컨텍스트*는 소스 파일, 네임스페이스, 클래스, 구조체, 모듈 또는 인터페이스여야 하며 프로시저나 블록일 수 없습니다.  자세한 내용은 [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)을 참조하십시오.  
  
 각 클래스의 인스턴스에는 다른 모든 인스턴스와 독립적인 수명이 있습니다.  이 수명은 해당 인스턴스가 [New Operator](../../../visual-basic/language-reference/operators/new-operator.md) 절이나 <xref:Microsoft.VisualBasic.Interaction.CreateObject%2A>와 같은 함수에 의해 만들어지면 시작되고  인스턴스를 가리키는 모든 변수가 [Nothing](../../../visual-basic/language-reference/nothing.md)이나 다른 클래스의 인스턴스로 설정되면 끝납니다.  
  
 클래스는 기본적으로 [Friend](../../../visual-basic/language-reference/modifiers/friend.md) 액세스입니다.  액세스 한정자를 사용하여 액세스 수준을 조정할 수 있습니다.  자세한 내용은 [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)을 참조하십시오.  
  
## 규칙  
  
-   **중첩.** 하나의 클래스에 다른 클래스를 정의할 수 있습니다.  여기서 외부 클래스를 *포함하는 클래스*라고 하며 내부 클래스를 *중첩 클래스*라고 합니다.  
  
-   **상속.** 클래스에서 [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md)을 사용하는 경우 기본 클래스 또는 인터페이스를 하나만 지정할 수 있습니다.  클래스는 둘 이상의 요소에서 상속될 수 없습니다.  
  
     클래스는 액세스 수준이 보다 제한적인 다른 클래스에서 상속될 수 없습니다.  예를 들어, `Public` 클래스는 `Friend` 클래스에서 상속될 수 없습니다.  
  
     클래스는 해당 클래스 내에 중첩된 클래스에서 상속될 수 없습니다.  
  
-   **구현.** 클래스에서 [Implements Statement](../../../visual-basic/language-reference/statements/implements-statement.md)을 사용하는 경우 `interfacenames`에서 지정한 모든 인터페이스가 정의하는 모든 멤버를 구현해야 합니다.  이 경우 한 가지 예외는 기본 클래스 멤버를 다시 구현하는 것입니다.  자세한 내용은 [Implements](../../../visual-basic/language-reference/statements/implements-clause.md)의 "다시 구현"을 참조하십시오.  
  
-   **기본 속성.** 클래스는 *기본 속성*으로 최대 하나의 속성을 지정할 수 있습니다.  자세한 내용은 [Default](../../../visual-basic/language-reference/modifiers/default.md)을 참조하십시오.  
  
## 동작  
  
-   **액세스 수준.** 클래스 내에서 각 멤버가 고유한 액세스 수준을 갖도록 선언할 수 있습니다.  변수와 상수는 기본적으로 [Private](../../../visual-basic/language-reference/modifiers/private.md) 액세스이지만 클래스 멤버는 기본적으로 [Public](../../../visual-basic/language-reference/modifiers/public.md) 액세스입니다.  클래스의 액세스 수준이 해당 멤버 중 하나의 액세스 수준보다 제한적인 경우 클래스 액세스 수준이 우선적으로 적용됩니다.  
  
-   **범위.** 클래스 범위는 해당 클래스의 포함하는 네임스페이스, 클래스, 구조체 또는 모듈 전체입니다.  
  
     모든 클래스 멤버의 범위는 전체 클래스입니다.  
  
     **수명.** Visual Basic에서는 정적 클래스를 지원하지 않습니다.  모듈에서 정적 클래스와 동등한 기능을 제공합니다.  자세한 내용은 [Module Statement](../../../visual-basic/language-reference/statements/module-statement.md)를 참조하십시오.  
  
     클래스 멤버의 수명은 해당 클래스 멤버를 선언하는 방법과 위치에 따라 다릅니다.  자세한 내용은 [Lifetime in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)을 참조하십시오.  
  
-   **한정자.** 클래스 외부의 코드에서 멤버 이름을 해당 클래스 이름으로 한정해야 합니다.  
  
     중첩 클래스 내부의 코드가 프로그래밍 요소에 대해 한정되지 않은 참조를 만드는 경우 Visual Basic에서는 먼저 중첩 클래스에서 요소를 검색하고, 다음으로 포함하는 클래스에서 요소를 검색하고, 마지막으로 가장 바깥쪽의 포함하는 요소에서 요소를 검색합니다.  
  
## 클래스 및 모듈  
 이 두 요소는 매우 유사하지만 몇 가지 중요한 면에서 서로 다릅니다.  
  
-   **용어.** 이전 버전의 Visual Basic에서는 두 가지 모듈 형식인 *클래스 모듈*\(.cls 파일\)과 *표준 모듈*\(.bas 파일\)을 인식합니다.  현재 버전에서는 이러한 *클래스*와 *모듈*을 각각 호출합니다.  
  
-   **공유 멤버.** 클래스 멤버가 공유 멤버인지 또는 인스턴스 멤버인지 제어할 수 있습니다.  
  
-   **개체 지향.** 클래스는 개체 지향적이지만 모듈은 그렇지 않습니다.  하나 이상의 클래스 인스턴스를 만들 수 있습니다.  자세한 내용은 [Objects and Classes](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)를 참조하십시오.  
  
## 예제  
 다음 예제에서는 `Class` 문을 사용하여 클래스와 여러 멤버를 정의합니다.  
  
 [!code-vb[VbVbalrStatements#62](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/class-statement_1.vb)]  
  
## 참고 항목  
 [Objects and Classes](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)   
 [Structures and Classes](../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)   
 [Interface Statement](../../../visual-basic/language-reference/statements/interface-statement.md)   
 [Module Statement](../../../visual-basic/language-reference/statements/module-statement.md)   
 [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md)   
 [Object Lifetime: How Objects Are Created and Destroyed](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)   
 [Visual Basic의 제네릭 형식](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [방법: 제네릭 클래스 사용](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)