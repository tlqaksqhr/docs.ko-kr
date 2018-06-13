---
title: Class 문(Visual Basic)
ms.date: 05/12/2018
f1_keywords:
- vb.Class
helpviewer_keywords:
- class modules
- Class statement [Visual Basic]
- classes [Visual Basic], fields
- fields [Visual Basic], of classes
- class types [Visual Basic], class statements
- classes [Visual Basic], creating
- classes [Visual Basic], data members
- data members [Visual Basic], of classes
ms.assetid: f2664f38-eb5a-4d4b-a374-1d041521fb6c
ms.openlocfilehash: 1d81ce148e237df6997934f70c294630f6cc7b8d
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/17/2018
ms.locfileid: "34235884"
---
# <a name="class-statement-visual-basic"></a>Class 문(Visual Basic)
클래스의 이름을 선언 하 고 변수, 속성, 이벤트 및 클래스를 구성 하는 프로시저의 정의 소개 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
[ <attributelist> ] [ accessmodifier ] [ Shadows ] [ MustInherit | NotInheritable ] [ Partial ] _  
Class name [ ( Of typelist ) ]  
    [ Inherits classname ]  
    [ Implements interfacenames ]  
    [ statements ]  
End Class  
```  
  
## <a name="parts"></a>요소  
  
|용어|정의|  
|---|---|  
|`attributelist`|선택 사항입니다. 참조 [특성 목록](../../../visual-basic/language-reference/statements/attribute-list.md)합니다.|  
|`accessmodifier`|선택 사항입니다. 다음 중 하나일 수 있습니다.<br /><br /> -   [공개](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [보호](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [개인](../../../visual-basic/language-reference/modifiers/private.md)<br />-   [Protected Friend](../../language-reference/modifiers/protected-friend.md)<br />- [보호 된 개인](../../language-reference/modifiers/private-protected.md)<br/><br/> 참조 [액세스 수준을 Visual Basic의](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)합니다.|  
|`Shadows`|선택 사항입니다. 참조 [그림자](../../../visual-basic/language-reference/modifiers/shadows.md)합니다.|  
|`MustInherit`|선택 사항입니다. 참조 [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md)합니다.|  
|`NotInheritable`|선택 사항입니다. 참조 [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md)합니다.|  
|`Partial`|선택 사항입니다. 클래스의 부분 정의 나타냅니다. 참조 [부분](../../../visual-basic/language-reference/modifiers/partial.md)합니다.|  
|`name`|필수. 이 클래스의 이름입니다. 참조 [선언 된 요소 이름](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)합니다.|  
|`Of`|선택 사항입니다. 제네릭 클래스 임을 지정 합니다.|  
|`typelist`|사용 하는 경우 필요는 [의](../../../visual-basic/language-reference/statements/of-clause.md) 키워드입니다. 이 클래스에 대 한 형식 매개 변수의 목록입니다. 참조 [목록을 입력](../../../visual-basic/language-reference/statements/type-list.md)합니다.|  
|`Inherits`|선택 사항입니다. 이 클래스는 다른 클래스의 멤버를 상속 함을 나타냅니다. 참조 [Inherits 문](../../../visual-basic/language-reference/statements/inherits-statement.md)합니다.|  
|`classname`|사용 하는 경우 필요는 `Inherits` 문. 이 클래스가 파생 되는 클래스의 이름입니다.|  
|`Implements`|선택 사항입니다. 이 클래스의 하나 이상의 인터페이스 멤버를 구현 함을 나타냅니다. 참조 [문을 구현](../../../visual-basic/language-reference/statements/implements-statement.md)합니다.|  
|`interfacenames`|사용 하는 경우 필요는 `Implements` 문. 이 클래스를 구현 하는 인터페이스의 이름입니다.|  
|`statements`|선택 사항입니다. 이 클래스의 멤버를 정의 하는 문입니다.|  
|`End Class`|필수. 종료는 `Class` 정의 합니다.|  
  
## <a name="remarks"></a>설명  
 A `Class` 문은 새 데이터 형식을 정의 합니다. A *클래스* 는 개체 지향 프로그래밍 (OOP)의 기본 빌딩 블록입니다. 자세한 내용은 참조 [개체 및 클래스](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)합니다.  
  
 사용할 수 있습니다 `Class` 네임 스페이스 또는 모듈 수준에만 합니다. 즉,는 *선언 컨텍스트* 클래스 소스 파일, 네임 스페이스, 클래스, 구조체, 모듈 또는 인터페이스를 이어야 하며 블록 또는 프로시저일 수 없습니다. 자세한 내용은 [선언 컨텍스트 및 기본 액세스 수준](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)을 참조하세요.  
  
 클래스의 각 인스턴스 독립적인 수명이 다른 모든 인스턴스. 이 수명에서 만들어질 때 시작 되는 [New 연산자](../../../visual-basic/language-reference/operators/new-operator.md) 절 또는와 같은 함수에 의해 <xref:Microsoft.VisualBasic.Interaction.CreateObject%2A>합니다. 인스턴스를 가리키는 모든 변수로 설정 될 때 끝납니다 [Nothing](../../../visual-basic/language-reference/nothing.md) 또는 다른 클래스의 인스턴스를 합니다.  
  
 클래스는 기본적으로 [Friend](../../../visual-basic/language-reference/modifiers/friend.md) 액세스 합니다. 액세스 한정자로 액세스 수준을 조정할 수 있습니다. 자세한 내용은 참조 [액세스 수준을 Visual Basic의](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)합니다.  
  
## <a name="rules"></a>규칙  
  
-   **중첩입니다.** 하나의 클래스에 다른 클래스를 정의할 수 있습니다. 외부 클래스 라고는 *클래스를 포함 하*, 내부 클래스 라고 하 고는 *중첩 된 클래스*합니다.  
  
-   **상속.** 클래스를 사용 하는 경우는 [Inherits 문은](../../../visual-basic/language-reference/statements/inherits-statement.md), 하나의 기본 클래스 또는 인터페이스를 지정할 수 있습니다. 클래스는 둘 이상의 요소 로부터 상속할 수 없습니다.  
  
     클래스는 더 제한적인 액세스 수준으로 다른 클래스에서 상속할 수 없습니다. 예를 들어 한 `Public` 클래스에서 상속할 수 없습니다는 `Friend` 클래스입니다.  
  
     클래스는 그 안에 중첩 된 클래스에서 상속할 수 없습니다.  
  
-   **구현입니다.** 클래스를 사용 하는 경우는 [Implements 문](../../../visual-basic/language-reference/statements/implements-statement.md)에 지정 하는 모든 인터페이스에 의해 정의 된 모든 멤버를 구현 해야 `interfacenames`합니다. 이 예외는 기본 클래스 멤버의 다시 구현 해야 합니다. 자세한 내용은 "다시 구현"을 참조 [구현](../../../visual-basic/language-reference/statements/implements-clause.md)합니다.  
  
-   **기본 속성입니다.** 클래스는 최대 하나의 속성으로 지정할 수는 *기본 속성*합니다. 자세한 내용은 참조 [기본](../../../visual-basic/language-reference/modifiers/default.md)합니다.  
  
## <a name="behavior"></a>동작  
  
-   **액세스 수준입니다.** 클래스 내에서 액세스 수준으로 각 멤버를 선언할 수 있습니다. 클래스 멤버는 기본적으로 [공용](../../../visual-basic/language-reference/modifiers/public.md) 변수와 상수를 제외 하 고는 기본적으로 액세스 [개인](../../../visual-basic/language-reference/modifiers/private.md) 액세스 합니다. 클래스에 보다 제한적인 해당 멤버 중 하나를 클래스 액세스 수준은 우선적으로 적용 합니다.  
  
-   **범위입니다.** 클래스의 포함 된 네임 스페이스, 클래스, 구조체 또는 모듈 전체에서 범위에는 합니다.  
  
     모든 클래스 멤버의 범위는 전체 클래스입니다.  
  
     **수명입니다.** Visual Basic에서 정적 클래스를 지원 하지 않습니다. 정적 클래스의 해당 하는 기능 모듈에 의해 제공 됩니다. 자세한 내용은 참조 [Module 문](../../../visual-basic/language-reference/statements/module-statement.md)합니다.  
  
     클래스 멤버 선언 방법 및 위치에 따라 수명이 합니다. 자세한 내용은 참조 [Visual Basic의 수명](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)합니다.  
  
-   **검증 합니다.** 클래스 외부 코드 멤버의 이름을 해당 클래스의 이름으로 한 정해야 합니다.  
  
     중첩된 된 클래스 내부에서 코드를 프로그래밍 요소에 대 한 정규화 되지 않은 참조를 만드는 경우 Visual Basic 요소에 대해 먼저 검색 후를 포함 하는 클래스에서에서 중첩된 클래스에서 등 포함 하는 가장 바깥쪽 요소를 합니다.  
  
## <a name="classes-and-modules"></a>클래스와 모듈  
 이 요소는 많은 공통점이 있지만 중요 한 차이가 있습니다.  
  
-   **용어입니다.** 이전 버전의 Visual Basic 모듈의 두 가지 유형의 인식: *클래스 모듈* (.cls 파일) 및 *표준 모듈* (.bas 파일). 현재 버전에서는 이러한 *클래스* 및 *모듈*각각.  
  
-   **공유 멤버입니다.** 클래스의 멤버는 공유 인지 또는 인스턴스 멤버를 제어할 수 있습니다.  
  
-   **개체 방향입니다.** 클래스는 개체 지향적 있지만 모듈이 없습니다. 클래스의 인스턴스가 하나 이상 만들 수 있습니다. 자세한 내용은 참조 [개체 및 클래스](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `Class` 을 클래스와 여러 가지 멤버를 정의 합니다.  
  
 [!code-vb[VbVbalrStatements#62](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/class-statement_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [개체 및 클래스](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [구조체와 클래스](../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)  
 [Interface 문](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [Module 문](../../../visual-basic/language-reference/statements/module-statement.md)  
 [Property 문](../../../visual-basic/language-reference/statements/property-statement.md)  
 [개체 수명: 개체가 만들어지고 제거되는 방법](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)  
 [Visual Basic의 제네릭 형식](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [방법: 제네릭 클래스 사용](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
