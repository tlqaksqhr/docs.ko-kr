---
title: "Interface Statement (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Interface"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "interface statement [Visual Basic]"
  - "interfaces, interface definition"
ms.assetid: 8997af73-bda3-4f79-bd41-ca396b610260
caps.latest.revision: 26
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 26
---
# Interface Statement (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

인터페이스의 이름을 선언하고 인터페이스가 구성되는 멤버를 정의합니다.  
  
## 구문  
  
```  
[ <attributelist> ] [ accessmodifier ] [ Shadows ] _  
Interface name [ ( Of typelist ) ]  
    [ Inherits interfacenames ]  
    [ [ modifiers ] Property membername ]  
    [ [ modifiers ] Function membername ]  
    [ [ modifiers ] Sub membername ]  
    [ [ modifiers ] Event membername ]  
    [ [ modifiers ] Interface membername ]  
    [ [ modifiers ] Class membername ]  
    [ [ modifiers ] Structure membername ]  
End Interface  
```  
  
## 요소  
  
|||  
|-|-|  
|용어|정의|  
|`attributelist`|선택적 요소.  [특성 목록](../../../visual-basic/language-reference/statements/attribute-list.md)을 참조하십시오.|  
|`accessmodifier`|선택적 요소.  다음 중 하나일 수 있습니다.<br /><br /> -   [Public](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [Protected](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [Private](../../../visual-basic/language-reference/modifiers/private.md)<br />-   `Protected Friend`<br /><br /> 자세한 내용은 [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)를 참조하십시오.|  
|`Shadows`|선택적 요소.  [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)를 참조하십시오.|  
|`name`|필수 요소.  이 인터페이스의 이름입니다.  [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)를 참조하십시오.|  
|`Of`|선택적 요소.  제네릭 인터페이스임을 지정합니다.|  
|`typelist`|[Of](../../../visual-basic/language-reference/statements/of-clause.md) 키워드를 사용하는 경우 필수적 요소입니다.  이 인터페이스에 대한 형식 매개 변수 목록입니다.  필요한 경우 `In` 및 `Out` 제네릭 한정자를 사용하여 각 형식 매개 변수를 variant로 선언할 수 있습니다.  [형식 목록](../../../visual-basic/language-reference/statements/type-list.md)을 참조하십시오.|  
|`Inherits`|선택적 요소.  이 인터페이스가 다른 인터페이스의 특성과 멤버를 상속함을 나타냅니다.  자세한 내용은 [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md)를 참조하십시오.|  
|`interfacenames`|`Inherits` 문을 사용하는 경우 필수적 요소입니다.  이 인터페이스가 파생되는 인터페이스의 이름입니다.|  
|`modifiers`|선택적 요소.  정의할 인터페이스 멤버에 적합한 한정자입니다.|  
|`Property`|선택적 요소.  인터페이스의 멤버인 속성을 정의합니다.|  
|`Function`|선택적 요소.  인터페이스의 멤버인 `Function` 프로시저를 정의합니다.|  
|`Sub`|선택적 요소.  인터페이스의 멤버인 `Sub` 프로시저를 정의합니다.|  
|`Event`|선택적 요소.  인터페이스의 멤버인 이벤트를 정의합니다.|  
|`Interface`|선택적 요소.  이 인터페이스에서 중첩되는 인터페이스를 정의합니다.  중첩 인터페이스 정의는 `End Interface` 문으로 끝나야 합니다.|  
|`Class`|선택적 요소.  인터페이스의 멤버인 클래스를 정의합니다.  멤버 클래스 정의는 `End Class` 문으로 끝나야 합니다.|  
|`Structure`|선택적 요소.  인터페이스의 멤버인 구조체를 정의합니다.  멤버 구조체 정의는 `End Structure` 문으로 끝나야 합니다.|  
|`membername`|인터페이스의 멤버로 정의된 각 속성, 프로시저, 이벤트, 인터페이스, 클래스 또는 구조체에 필수적 요소입니다.  멤버의 이름입니다.|  
|`End Interface`|`Interface` 정의를 끝냅니다.|  
  
## 설명  
 *인터페이스*는 클래스 및 구조체에서 구현할 수 있는 속성, 프로시저 등과 같은 멤버 집합을 정의합니다.  인터페이스는 멤버의 내부 작업이 아니라 멤버의 시그니처만 정의합니다.  
  
 클래스나 구조체는 인터페이스에 정의된 모든 멤버에 대해 코드를 제공하여 인터페이스를 구현합니다.  응용 프로그램에서 해당 클래스나 구조체로부터 인스턴스를 만들 경우 개체가 메모리에서 실행됩니다.  자세한 내용은 [Objects and Classes](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) 및 [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md)을 참조하십시오.  
  
 `Interface`는 네임스페이스 또는 모듈 수준에서만 사용할 수 있습니다.  즉, 인터페이스에 대한 *선언 컨텍스트*는 소스 파일, 네임스페이스, 클래스, 구조체, 모듈 또는 인터페이스이어야 하며 프로시저나 블록이 될 수 없습니다.  자세한 내용은 [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)을 참조하십시오.  
  
 인터페이스는 기본적으로 [Friend](../../../visual-basic/language-reference/modifiers/friend.md)에 대한 액세스를 허용합니다.  액세스 한정자를 사용하여 액세스 수준을 조정할 수 있습니다.  자세한 내용은 [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)을 참조하십시오.  
  
## 규칙  
  
-   **중첩 인터페이스.** 인터페이스 내에서 다른 인터페이스를 정의할 수 있습니다.  외부 인터페이스를 *포함 인터페이스*, 내부 인터페이스를 *중첩 인터페이스*라고 합니다.  
  
-   **멤버 선언.** 속성이나 프로시저를 인터페이스의 멤버로 선언하면 해당 속성이나 프로시저의 *시그니처*만 정의됩니다.  여기에는 요소 형식\(속성 또는 프로시저\), 매개 변수 및 매개 변수 형식, 반환 형식 등이 포함됩니다.  따라서 멤버 정의에서는 코드 줄이 한 줄만 사용되고 `End Function` 또는 `End Property`와 같은 종료 문은 인터페이스에 사용할 수 없습니다.  
  
     반대로 열거형이나 구조체 또는 중첩 클래스나 인터페이스를 정의하는 경우에는 해당 데이터 멤버가 포함되어야 합니다.  
  
-   **멤버 한정자.** 모듈 멤버를 정의하는 경우에는 액세스 한정자를 사용할 수 없으며 [Overloads](../../../visual-basic/language-reference/modifiers/overloads.md)를 제외한 프로시저 한정자나 [Shared](../../../visual-basic/language-reference/modifiers/shared.md)를 지정할 수도 없습니다.  [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)를 사용하여 모든 멤버를 선언할 수 있으며, 속성을 정의할 때 [Default](../../../visual-basic/language-reference/modifiers/default.md)뿐 아니라 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md) 또는 [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md)를 사용할 수도 있습니다.  
  
-   **상속.** 인터페이스에서 [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md)을 사용하는 경우에는 하나 이상의 기본 인터페이스를 지정할 수 있습니다.  두 인터페이스가 동일한 이름의 멤버를 각각 정의해도 이러한 두 인터페이스에서 상속할 수 있습니다.  상속할 경우 구현하는 코드는 이름 한정을 사용하여 구현하는 멤버를 지정해야 합니다.  
  
     인터페이스는 액세스 수준이 보다 제한적인 다른 인터페이스에서 상속할 수 없습니다.  예를 들어 `Public` 인터페이스는 `Friend` 인터페이스에서 상속할 수 없습니다.  
  
     인터페이스는 해당 인터페이스 내에 중첩된 인터페이스에서 상속할 수 없습니다.  
  
-   **구현.** 클래스에서 [Implements](../../../visual-basic/language-reference/statements/implements-clause.md) 문을 사용하여 이 인터페이스를 구현하는 경우 인터페이스에 정의된 모든 멤버를 구현해야 합니다.  또한 구현 코드의 각 시그니처가 이 인터페이스에 정의된 해당 시그니처와 정확히 일치해야 합니다.  그러나 구현 코드의 멤버 이름은 인터페이스에 정의된 멤버 이름과 일치하지 않아도 됩니다.  
  
     클래스에서 프로시저를 구현하는 경우에는 프로시저를 `Shared`로 지정할 수 없습니다.  
  
-   **기본 속성.** 인터페이스에서는 하나 이상의 속성을 *기본 속성*으로 지정할 수 있습니다. 기본 속성은 속성 이름을 사용하지 않고도 참조할 수 있습니다.  이러한 속성은 [Default](../../../visual-basic/language-reference/modifiers/default.md) 한정자를 통해 선언하여 지정합니다.  
  
     인터페이스는 상속 대상이 없는 경우에만 기본 속성을 정의할 수 있습니다.  
  
## 동작  
  
-   **액세스 수준.** 모든 인터페이스 멤버에는 암시적인 [Public](../../../visual-basic/language-reference/modifiers/public.md) 액세스가 있습니다.  멤버를 정의할 때는 액세스 한정자를 사용할 수 없습니다.  그러나 인터페이스를 구현하는 클래스에서는 구현된 각 멤버에 대한 액세스 수준을 선언할 수 있습니다.  
  
     클래스 인스턴스를 변수에 할당하는 경우 해당 멤버의 액세스 수준은 변수의 데이터 형식이 기본 인터페이스인지 구현 클래스인지에 따라 달라질 수 있습니다.  다음은 이에 대한 예입니다.  
  
     [!code-vb[VbVbalrStatements#39](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/interface-statement_1.vb)]  
  
     `varAsInterface`를 통해 클래스 멤버에 액세스하는 경우 해당 클래스 멤버는 모두 공용 액세스 권한을 가집니다.  그러나 `varAsClass`를 통해 멤버에 액세스하는 경우에는 `Sub` 프로시저 `doSomething`이 전용 액세스 권한을 가집니다.  
  
-   **범위.** 인터페이스는 네임스페이스, 클래스, 구조체 또는 모듈 전체에서 범위 내에 포함됩니다.  
  
     모든 인터페이스 멤버의 범위는 전체 인터페이스입니다.  
  
-   **수명.** 인터페이스 자체와 인터페이스 멤버는 수명을 갖지 않습니다.  클래스에서 인터페이스를 구현하고 개체가 해당 클래스의 인스턴스로 만들어지는 경우에는 개체가 실행되는 응용 프로그램 내에서 수명을 가집니다.  자세한 내용은 [Class Statement](../../../visual-basic/language-reference/statements/class-statement.md)의 "수명"을 참조하십시오.  
  
## 예제  
 다음 예제에서는 `Interface` 문을 사용하여 `thisInterface` 인터페이스를 정의합니다. 이 인터페이스는 `Property` 문 및 `Function` 문으로 구현되어야 합니다.  
  
 [!code-vb[VbVbalrStatements#40](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/interface-statement_2.vb)]  
  
 `Property` 및 `Function` 문은 인터페이스 내에서 `End Property` 및 `End Function`으로 끝나는 블록을 정의하지 않습니다.  인터페이스는 해당 멤버의 시그니처만 정의합니다.  전체 `Property` 및 `Function` 블록은 `thisInterface`를 구현하는 클래스에 표시됩니다.  
  
## 참고 항목  
 [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md)   
 [Class Statement](../../../visual-basic/language-reference/statements/class-statement.md)   
 [Module Statement](../../../visual-basic/language-reference/statements/module-statement.md)   
 [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md)   
 [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md)   
 [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md)   
 [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Visual Basic의 제네릭 형식](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [제네릭 인터페이스의 가변성](../Topic/Variance%20in%20Generic%20Interfaces%20\(C%23%20and%20Visual%20Basic\).md)   
 [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)   
 [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)