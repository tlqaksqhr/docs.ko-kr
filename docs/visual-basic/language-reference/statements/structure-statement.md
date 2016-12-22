---
title: "Structure Statement | Microsoft Docs"
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
  - "vb.Structure"
  - "Structure"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "user-defined types, Structure statement"
  - "compound data types"
  - "Structure keyword"
  - "Structure statement"
  - "UDT (user-defined types)"
  - "types [Visual Basic], user-defined"
ms.assetid: 9bd1deea-2a89-4cdc-812c-6dcbb947c391
caps.latest.revision: 28
caps.handback.revision: 28
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Structure Statement
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

구조체의 이름을 선언하고 구조체를 구성하는 변수, 속성, 이벤트 및 프로시저의 정의를 소개합니다.  
  
## 구문  
  
```  
[ <attributelist> ] [ accessmodifier ] [ Shadows ] [ Partial ] _  
Structure name [ ( Of typelist ) ]  
    [ Implements interfacenames ]  
    [ datamemberdeclarations ]  
    [ methodmemberdeclarations ]  
End Structure  
```  
  
## 요소  
  
|||  
|-|-|  
|용어|정의|  
|`attributelist`|선택적 요소.  [특성 목록](../../../visual-basic/language-reference/statements/attribute-list.md)을 참조하십시오.|  
|`accessmodifier`|선택적 요소.  다음 중 하나일 수 있습니다.<br /><br /> -   [Public](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [Protected](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [Private](../../../visual-basic/language-reference/modifiers/private.md)<br />-   `Protected Friend`<br /><br /> 자세한 내용은 [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)를 참조하십시오.|  
|`Shadows`|선택적 요소.  [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)를 참조하십시오.|  
|`Partial`|선택적 요소.  구조체의 부분 정의를 나타냅니다.  자세한 내용은 [Partial](../../../visual-basic/language-reference/modifiers/partial.md)를 참조하십시오.|  
|`name`|필수 요소.  이 구조체의 이름입니다.  [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)를 참조하십시오.|  
|`Of`|선택적 요소.  이 구조체를 제네릭 구조체로 지정합니다.|  
|`typelist`|[Of](../../../visual-basic/language-reference/statements/of-clause.md) 키워드를 사용하는 경우 필수적 요소입니다.  이 구조체에 대한 형식 매개 변수 목록입니다.  [형식 목록](../../../visual-basic/language-reference/statements/type-list.md)을 참조하십시오.|  
|`Implements`|선택적 요소.  이 구조체가 인터페이스의 멤버를 구현한다는 것을 나타냅니다.  자세한 내용은 [Implements Statement](../../../visual-basic/language-reference/statements/implements-statement.md)를 참조하십시오.|  
|`interfacenames`|`Implements` 문을 사용하는 경우 필수적 요소입니다.  이 구조체가 구현하는 인터페이스의 이름입니다.|  
|`datamemberdeclarations`|필수 요소.  구조체의 *데이터 멤버* 를 선언하는 0 이상의 `Const`, `Dim`, `Enum` 또는 `Event` 문입니다.|  
|`methodmemberdeclarations`|선택적 요소.  구조체의 *메서드 멤버* 로 사용되는 0개 이상의 `Function`, `Operator`, `Property` 또는 `Sub` 프로시저의 선언입니다.|  
|`End Structure`|필수 요소.  `Structure` 정의를 종료합니다.|  
  
## 설명  
 `Structure` 문은 사용자 지정할 수 있는 합성 값 형식을 정의합니다.  *구조체* 는 이전 버전의 Visual Basic에서 지원되던 UDT\(사용자 정의 형식\)를 일반화한 것입니다.  자세한 내용은 [Structures](../../../visual-basic/programming-guide/language-features/data-types/structures.md)을 참조하십시오.  
  
 클래스에서 지원되는 많은 기능이 구조체에서도 지원됩니다.  예를 들어, 구조체는 속성과 프로시저를 포함할 수 있으며 인터페이스를 구현하고 매개 변수화된 생성자를 포함할 수 있습니다.  그러나 상속, 선언 및 용도에 있어 구조체와 클래스 사이에는 상당한 차이가 있습니다.  또한 클래스는 참조 형식이고 구조체는 값 형식입니다.  자세한 내용은 [Structures and Classes](../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)을 참조하십시오.  
  
 `Structure` 는 네임스페이스 수준이나 모듈 수준에서만 사용할 수 있습니다.  즉, 구조체의 *선언 컨텍스트* 는 소스 파일, 네임스페이스, 클래스, 구조체, 모듈 또는 인터페이스이어야 하며 프로시저 또는 블록일 수는 없습니다.  자세한 내용은 [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)을 참조하십시오.  
  
 구조체는 기본적으로 [Friend](../../../visual-basic/language-reference/modifiers/friend.md) 액세스입니다.  액세스 한정자를 사용하여 액세스 수준을 조정할 수 있습니다.  자세한 내용은 [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)을 참조하십시오.  
  
## 규칙  
  
-   **중첩.** 한 구조체 내에 다른 구조체를 정의할 수 있습니다.  외부 구조체를 *포함하는 구조체*라고 하고 내부 구조체를 *중첩 구조체*라고 합니다.  그러나 포함하는 구조체를 통해 중첩 구조체의 멤버에 액세스할 수는 없습니다.  대신 중첩 구조체의 데이터 형식에 대한 변수를 선언해야 합니다.  
  
-   **멤버 선언.** 구조체의 모든 멤버를 선언해야 합니다.  구조체에서는 아무 것도 상속할 수 없으므로 구조체 멤버는 [Protected](../../../visual-basic/language-reference/modifiers/protected.md) 또는 `Protected Friend` 가 될 수 없습니다.  그러나 구조체 자체는 `Protected` 또는 `Protected Friend`가 될 수 있습니다.  
  
     0 개 이상의 비공유 변수 또는 구조체의 비공유 사용자 이벤트를 선언할 수 있습니다.  그 중 일부가 공유되지 않더라도 상수, 속성 또는 프로시저만 사용할 수 없습니다.  
  
-   **초기화.** 구조체의 공유되지 않는 데이터 멤버 값을 해당 선언의 일부로 초기화할 수 없습니다.  구조체의 매개 변수화된 생성자를 사용하여 데이터 멤버를 초기화하거나 구조체의 인스턴스를 만든 다음 해당 멤버에 값을 할당해야 합니다.  
  
-   **상속.** 구조체는 모든 구조체가 상속하는 <xref:System.ValueType> 이외의 형식에 상속될 수 없습니다.  특히 한 구조체는 다른 구조체에 상속될 수 없습니다.  
  
     <xref:System.ValueType>을 지정하는 경우에도 구조체 정의에 [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md) 을 사용할 수 없습니다.  
  
-   **구현.** 구조체에서 [Implements Statement](../../../visual-basic/language-reference/statements/implements-statement.md)을 사용하는 경우 `interfacenames`에 지정한 모든 인터페이스에 의해 정의된 모든 멤버를 구현해야 합니다.  
  
-   **기본 속성.** 구조체는 [Default](../../../visual-basic/language-reference/modifiers/default.md) 한정자를 사용하여 하나의 속성을 해당 *기본 속성*으로 지정할 수 있습니다.  자세한 내용은 [Default](../../../visual-basic/language-reference/modifiers/default.md)을 참조하십시오.  
  
## 동작  
  
-   **액세스 수준.** 구조체 내에서는 각 멤버를 고유한 액세스 수준으로 선언할 수 있습니다.  모든 구조체 멤버는 기본적으로 [Public](../../../visual-basic/language-reference/modifiers/public.md) 액세스입니다.  구조체 자체에 보다 제한된 액세스 수준이 지정되어 있을 경우 액세스 수준을 액세스 한정자로 조정해도 해당 멤버에 대한 액세스가 자동으로 제한됩니다.  
  
-   **범위.** 구조체는 포함하는 해당 네임스페이스, 클래스, 구조체 또는 모듈 전반에서 범위 안에 있습니다.  
  
     모든 구조체 멤버의 범위는 전체 구조체입니다.  
  
-   **수명.** 구조체 자체에는 수명이 없지만  해당 구조체의 각 인스턴스에는 다른 모든 인스턴스와는 독립적인 수명이 있습니다.  
  
     인스턴스의 수명은 인스턴스가 [New Operator](../../../visual-basic/language-reference/operators/new-operator.md) 절로 생성됨과 동시에 시작되고  해당 인스턴스를 보유하는 변수의 수명이 다되면 끝납니다.  
  
     구조체 인스턴스의 수명은 연장할 수 없습니다.  정적 구조체 기능에 대한 근사값은 모듈에서 제공합니다.  자세한 내용은 [Module Statement](../../../visual-basic/language-reference/statements/module-statement.md)을 참조하십시오.  
  
     구조체 멤버는 선언된 방법과 위치에 따라 수명이 달라집니다.  자세한 내용은 [Class Statement](../../../visual-basic/language-reference/statements/class-statement.md)의 "수명"을 참조하십시오.  
  
-   **한정자.** 구조체 외부에 있는 코드는 멤버의 이름을 해당 구조체의 이름으로 한정해야 합니다.  
  
     중첩 구조체 내에 있는 코드가 프로그래밍 요소에 대한 비정규화된 참조를 만들면 Visual Basic에서는 먼저 중첩 구조체에서 요소를 검색하고 이를 포함하는 해당 구조체에서 검색한 다음 계속해서 가장 바깥쪽 포함하는 요소로 범위를 넓혀가며 검색합니다.  자세한 내용은 [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)을 참조하십시오.  
  
-   **메모리 사용.** 모든 복합 데이터 형식과 마찬가지로 해당 멤버의 일반 저장소 할당량을 모두 더하는 것만으로 구조체의 총 메모리 사용량을 정확히 계산할 수는 없습니다.  또한 메모리에서 저장소의 순서가 사용자의 선언 순서와 동일하다고 가정할 수도 없습니다.  구조체의 저장소 레이아웃을 제어해야 할 경우 <xref:System.Runtime.InteropServices.StructLayoutAttribute> 특성을 `Structure` 문에 적용할 수 있습니다.  
  
## 예제  
 다음 예제에서는 `Structure` 문을 사용하여 직원과 관련된 데이터 집합을 정의합니다.  데이터 항목의 민감도를 반영하기 위해 `Public`, `Friend` 및 `Private` 멤버도 사용합니다.  또한 프로시저, 속성 및 이벤트 멤버를 보여 줍니다.  
  
 [!code-vb[VbVbalrStatements#57](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/structure-statement_1.vb)]  
  
## 참고 항목  
 [Class Statement](../../../visual-basic/language-reference/statements/class-statement.md)   
 [Interface Statement](../../../visual-basic/language-reference/statements/interface-statement.md)   
 [Module Statement](../../../visual-basic/language-reference/statements/module-statement.md)   
 [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md)   
 [Const Statement](../../../visual-basic/language-reference/statements/const-statement.md)   
 [Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md)   
 [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md)   
 [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)   
 [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md)   
 [Structures and Classes](../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)