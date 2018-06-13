---
title: Interface 문(Visual Basic)
ms.date: 05/12/2018
f1_keywords:
- vb.Interface
helpviewer_keywords:
- interface statement [Visual Basic]
- interfaces [Visual Basic], interface definition
ms.assetid: 8997af73-bda3-4f79-bd41-ca396b610260
ms.openlocfilehash: 31ff9211034438e225494b916045acd07c37810f
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/17/2018
ms.locfileid: "34233914"
---
# <a name="interface-statement-visual-basic"></a>Interface 문(Visual Basic)
인터페이스의 이름을 선언 하 고 인터페이스를 구성 하는 멤버의 정의 소개 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
[ <attributelist> ] [ accessmodifier ] [ Shadows ] _  
Interface name [ ( Of typelist ) ]  
    [ Inherits interfacenames ]  
    [ [ modifiers ] Property membername ]  
    [ [ modifiers ] Function membername ]  
    [ [ modifiers ] Sub membername ]  
    [ [ modifiers ] Event membername ]  
    [ [ modifiers ] Interface membername ]  
    [ [ modifiers ] Class membername ]  
    [ [ modifiers ] Structure membername ]  
End Interface  
```  
  
## <a name="parts"></a>요소  
  
|용어|정의|  
|---|---|  
|`attributelist`|선택 사항입니다. 참조 [특성 목록](../../../visual-basic/language-reference/statements/attribute-list.md)합니다.|  
|`accessmodifier`|선택 사항입니다. 다음 중 하나일 수 있습니다.<br /><br /> -   [공개](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [보호](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [개인](../../../visual-basic/language-reference/modifiers/private.md)<br />-  [Protected Friend](../../language-reference/modifiers/protected-friend.md)<br/>- [보호 된 개인](../../language-reference/modifiers/private-protected.md)<br /><br /> 참조 [액세스 수준을 Visual Basic의](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)합니다.|  
|`Shadows`|선택 사항입니다. 참조 [그림자](../../../visual-basic/language-reference/modifiers/shadows.md)합니다.|  
|`name`|필수. 이 인터페이스의 이름입니다. 참조 [선언 된 요소 이름](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)합니다.|  
|`Of`|선택 사항입니다. 제네릭 인터페이스는 임을 지정 합니다.|  
|`typelist`|사용 하는 경우 필요는 [의](../../../visual-basic/language-reference/statements/of-clause.md) 키워드입니다. 이 인터페이스에 대 한 형식 매개 변수의 목록입니다. 필요에 따라 각 형식 매개 변수에 선언할 수 변형을 사용 하 여 `In` 및 `Out` 제네릭 한정자입니다. 참조 [목록을 입력](../../../visual-basic/language-reference/statements/type-list.md)합니다.|  
|`Inherits`|선택 사항입니다. 이 인터페이스에서 특성 및 다른 인터페이스 또는 인터페이스의 멤버를 상속 함을 나타냅니다. 참조 [Inherits 문](../../../visual-basic/language-reference/statements/inherits-statement.md)합니다.|  
|`interfacenames`|사용 하는 경우 필요는 `Inherits` 문. 이 인터페이스가 파생 되는 인터페이스의 이름입니다.|  
|`modifiers`|선택 사항입니다. 정의 되는 인터페이스 멤버에 대 한 적절 한 한정자입니다.|  
|`Property`|선택 사항입니다. 인터페이스의 구성원 인 속성을 정의 합니다.|  
|`Function`|선택 사항입니다. 정의 `Function` 프로시저 인터페이스의 멤버입니다.|  
|`Sub`|선택 사항입니다. 정의 `Sub` 프로시저 인터페이스의 멤버입니다.|  
|`Event`|선택 사항입니다. 이벤트 인터페이스의 멤버를 정의 합니다.|  
|`Interface`|선택 사항입니다. 이 인터페이스에서 중첩 되는 인터페이스를 정의 합니다. 중첩 된 인터페이스 정의로 종료 되어야는 `End Interface` 문.|  
|`Class`|선택 사항입니다. 인터페이스의 멤버는 클래스를 정의 합니다. 멤버 클래스 정의로 종료 되어야는 `End Class` 문.|  
|`Structure`|선택 사항입니다. 구조체는 인터페이스의 멤버를 정의 합니다. 멤버 구조 정의 끝나야 합니다는 `End Structure` 문.|  
|`membername`|각 속성, 프로시저, 이벤트, 인터페이스, 클래스 또는 인터페이스의 멤버로 정의 된 구조체에 필요 합니다. 멤버의 이름입니다.|  
|`End Interface`|종료는 `Interface` 정의 합니다.|  
  
## <a name="remarks"></a>설명  
 *인터페이스* 속성 및 프로시저 클래스 및 구조체를 구현할 수와 같은 멤버 집합을 정의 합니다. 인터페이스의 내부 작업이 아니라는 멤버의 서명만 정의합니다.  
  
 클래스 또는 구조체는 인터페이스에서 정의 된 모든 멤버에 대 한 코드를 제공 하 여 인터페이스를 구현 합니다. 마지막으로, 응용 프로그램에서 해당 클래스 또는 구조체 인스턴스를 만들 때 개체 있으며 메모리에서 실행 합니다. 자세한 내용은 참조 [개체 및 클래스](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) 및 [인터페이스](../../../visual-basic/programming-guide/language-features/interfaces/index.md)합니다.  
  
 사용할 수 있습니다 `Interface` 네임 스페이스 또는 모듈 수준에만 합니다. 즉,는 *선언 컨텍스트* 인터페이스 소스 파일, 네임 스페이스, 클래스, 구조체, 모듈 또는 인터페이스를 이어야 하며 블록 또는 프로시저일 수 없습니다. 자세한 내용은 [선언 컨텍스트 및 기본 액세스 수준](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)을 참조하세요.  
  
 기본적으로 인터페이스 [Friend](../../../visual-basic/language-reference/modifiers/friend.md) 액세스 합니다. 액세스 한정자로 액세스 수준을 조정할 수 있습니다. 자세한 내용은 참조 [액세스 수준을 Visual Basic의](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)합니다.  
  
## <a name="rules"></a>규칙  
  
-   **중첩 인터페이스.** 내에서 다른 하나의 인터페이스를 정의할 수 있습니다. 외부 인터페이스는 *인터페이스를 포함 하*, 내부 인터페이스 라고 하 고는 *중첩된 인터페이스*합니다.  
  
-   **멤버 선언입니다.** 인터페이스의 구성원으로 속성 또는 프로시저를 선언 하는 경우 정의 하는는 *서명* 해당 속성이 나 프로시저의 합니다. 여기에 (속성 또는 프로시저) 요소 형식, 해당 매개 변수 및 매개 변수 형식 및 반환 형식이 포함 됩니다. 이 인해 멤버 정의 사용 하 여 한 줄의 코드 및와 같은 종료 문은 `End Function` 또는 `End Property` 인터페이스에 올바르지 않습니다.  
  
     반면, 열거형 또는 구조체 또는 중첩 된 클래스 또는 인터페이스를 정의할 때 데이터 멤버를 포함 하는 데 필요한 됩니다.  
  
-   **멤버 한정자입니다.** 모듈 멤버를 정의할 때 액세스 한정자를 사용할 수 없습니다 하거나 지정할 수 [Shared](../../../visual-basic/language-reference/modifiers/shared.md) 또는 프로시저 한정자를 제외 하 고 [오버 로드](../../../visual-basic/language-reference/modifiers/overloads.md)합니다. 모든 멤버를 선언할 수 [그림자](../../../visual-basic/language-reference/modifiers/shadows.md), 사용할 수 있습니다 [기본](../../../visual-basic/language-reference/modifiers/default.md) 속성을 정의할 때와 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md) 또는 [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md)합니다.  
  
-   **상속.** 인터페이스를 사용 하는 경우는 [Inherits 문은](../../../visual-basic/language-reference/statements/inherits-statement.md), 하나 이상의 기본 인터페이스를 지정할 수 있습니다. 동일한 이름 가진 멤버를 정의 하는 경우에 두 인터페이스에서 상속할 수 있습니다. 이렇게 하면 구현 코드는 구현 하는 멤버를 지정 하려면 이름 한정을 사용 해야 합니다.  
  
     인터페이스는 더 제한적인 액세스 수준 가진 다른 인터페이스에서 상속할 수 없습니다. 예를 들어 한 `Public` 인터페이스에서 상속할 수 없습니다는 `Friend` 인터페이스입니다.  
  
     인터페이스 내에 중첩 된 인터페이스에서 상속할 수 없습니다.  
  
-   **구현입니다.** 클래스를 사용 하는 경우는 [구현](../../../visual-basic/language-reference/statements/implements-clause.md) 이 인터페이스를 구현 하는 문은 인터페이스 내에서 정의 된 모든 멤버를 구현 해야 합니다. 또한 각 서명에 구현 코드의이 인터페이스에 정의 된 해당 서명이 일치 해야 합니다. 그러나 구현 코드의 멤버의 이름을 인터페이스에 정의 된 멤버 이름과 일치 하지 않아도 됩니다.  
  
     와 프로시저를 지정할 수 없습니다 프로시저를 구현 하는 클래스에서는 때 `Shared`합니다.  
  
-   **기본 속성입니다.** 인터페이스는 최대 하나의 속성으로 지정할 수는 *기본 속성*, 속성 이름을 사용 하지 않고 참조할 수 있습니다. 이러한 속성으로 선언 하 여 지정 된 [기본](../../../visual-basic/language-reference/modifiers/default.md) 한정자.  
  
     이 인터페이스를 none을 상속 하는 경우에 기본 속성을 정의할 수 있도록 의미를 확인 합니다.  
  
## <a name="behavior"></a>동작  
  
-   **액세스 수준입니다.** 모든 인터페이스 멤버를 암시적으로 사용할 [공용](../../../visual-basic/language-reference/modifiers/public.md) 액세스 합니다. 멤버를 정의할 때 액세스 한정자를 사용할 수 없습니다. 하지만 인터페이스를 구현 하는 클래스는 구현 된 각 멤버에 대 한 액세스 수준의 선언할 수 있습니다.  
  
     클래스 인스턴스를 변수에 할당할 경우 해당 멤버의 액세스 수준을 변수의 데이터 형식을 구현 하는 클래스 또는 인터페이스에 있는 인지에 종속 될 수 있습니다. 다음은 이에 대한 예입니다.  
  
     [!code-vb[VbVbalrStatements#39](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/interface-statement_1.vb)]  
  
     클래스 멤버를 통해 액세스 하는 경우 `varAsInterface`, 공용 액세스 권한이 있습니다. 그러나 통해 멤버에 액세스 하는 경우 `varAsClass`, `Sub` 프로시저 `doSomething` 액세스 가능성은 private입니다.  
  
-   **범위입니다.** 범위 전체에서 네임 스페이스, 클래스, 구조체 또는 모듈에에서는 인터페이스가입니다.  
  
     모든 인터페이스 멤버의 범위는 전체 인터페이스입니다.  
  
-   **수명입니다.** 인터페이스 하지 않으며 자체는 수명이 하지도 멤버입니다. 클래스는 인터페이스 및 개체를 구현 하는 경우 만들어집니다의 인스턴스로 해당 클래스, 개체에 실행 되는 응용 프로그램 내에서 수명. 자세한 내용은의 "수명" 참조 [Class 문](../../../visual-basic/language-reference/statements/class-statement.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `Interface` 이라는 인터페이스를 정의 하는 문을 `thisInterface`,으로 구현 되어야 하는 `Property` 문 및 `Function` 문.  
  
 [!code-vb[VbVbalrStatements#40](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/interface-statement_2.vb)]  
  
 `Property` 및 `Function` 문 블록으로 끝나는 정의 하지 않습니다 `End Property` 및 `End Function` 인터페이스 내에서. 인터페이스는 해당 멤버의 서명만 정의 합니다. 전체 `Property` 및 `Function` 블록 구현 하는 클래스에 표시 `thisInterface`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [인터페이스](../../../visual-basic/programming-guide/language-features/interfaces/index.md)  
 [Class 문](../../../visual-basic/language-reference/statements/class-statement.md)  
 [Module 문](../../../visual-basic/language-reference/statements/module-statement.md)  
 [Structure 문](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [Property 문](../../../visual-basic/language-reference/statements/property-statement.md)  
 [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Visual Basic의 제네릭 형식](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [제네릭 인터페이스의 가변성](../../programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)  
 [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)  
 [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
