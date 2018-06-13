---
title: Shadows(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Shadows
- shadows
helpviewer_keywords:
- shadowing
- duplicate names [Visual Basic]
- scope [Visual Basic], shadowing
- Shadows keyword [Visual Basic]
- names [Visual Basic], shadowing
ms.assetid: 6bf687cd-0544-4797-b51b-911125ec57c6
ms.openlocfilehash: 4ca4ec48ee63b71447056a2c5cb68e8948f27ad0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604655"
---
# <a name="shadows-visual-basic"></a>Shadows(Visual Basic)
선언된 된 프로그래밍 요소는 동일 하 게 명명 된 요소 또는 기본 클래스에서 오버 로드 된 요소 집합을 다시 선언 하 고 숨기도록 지정 합니다.  
  
## <a name="remarks"></a>설명  
 섀도잉의 주요 목적은 (이 라고도 *이름으로 숨김*) 클래스 멤버의 정의 유지 하는 것입니다. 기본 클래스를 이미 정의한 하나로 동일한 이름을 가진 요소를 만드는 경우가 있을 수 있습니다. 이런 경우는 `Shadows` 한정자를 사용 하면 클래스 멤버로 확인 수를 통한 참조가 이미 정의한 대신 새 기본 클래스 요소입니다.  
  
 숨김과 재정의는 둘 다 상속된 요소를 다시 정의하지만 두 방법에는 중요한 차이점이 있습니다. 자세한 내용은 참조 [Visual Basic의 숨김 기능](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)합니다.  
  
## <a name="rules"></a>규칙  
  
-   **선언 컨텍스트입니다.** 사용할 수 있습니다 `Shadows` 클래스 수준에만 합니다. 즉, 선언 컨텍스트는 `Shadows` 요소는 클래스 여야 하며 소스 파일, 네임 스페이스, 인터페이스, 모듈, 구조체 또는 프로시저 일 수 없습니다.  
  
     단일 선언문에서 숨기는 하나의 요소를 선언할 수 있습니다.  
  
-   **결합 된 한정자입니다.** 지정할 수 없습니다 `Shadows` 와 함께 `Overloads`, `Overrides`, 또는 `Static` 같은 선언에 있습니다.  
  
-   **요소 형식입니다.** 모든 종류의 선언된 요소를 다른 종류로 섀도잉할 수 있습니다. 속성이 나 다른 속성 또는 프로시저를 사용 하 여 프로시저를 숨길 경우 매개 변수 및 반환 형식이 없는 기본 클래스 속성 또는 프로시저에 맞게 합니다.  
  
-   **에 액세스합니다.** 기본 클래스에 숨겨진된 요소는 섀도잉하는 파생된 클래스 내에서 일반적으로 사용할 수 없습니다. 그러나 다음 사항을 고려해 야 합니다.  
  
    -   숨기는 요소를 참조 하는 코드에서 액세스할 수 없는 경우 섀도 처리 된 요소에 대 한 참조 확인 됩니다. 예를 들어 경우는 `Private` 요소 기본 클래스 요소를 액세스할 수 있는 권한이 없는 코드를 숨기는 `Private` 요소 기본 클래스 요소에 대신 액세스 합니다.  
  
    -   요소를 숨길 경우 기본 클래스의 형식으로 선언 된 개체를 통해 숨겨진된 요소를 계속 액세스할 수 있습니다. 통해 액세스할 수도 있습니다 `MyBase`합니다.  
  
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
  
## <a name="see-also"></a>참고 항목  
 [공유](../../../visual-basic/language-reference/modifiers/shared.md)  
 [정적](../../../visual-basic/language-reference/modifiers/static.md)  
 [전용](../../../visual-basic/language-reference/modifiers/private.md)  
 [Me, My, MyBase 및 MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 [상속 기본 사항](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)  
 [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)  
 [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)  
 [오버로드](../../../visual-basic/language-reference/modifiers/overloads.md)  
 [재정의 가능](../../../visual-basic/language-reference/modifiers/overridable.md)  
 [재정의](../../../visual-basic/language-reference/modifiers/overrides.md)  
 [Visual Basic의 숨김 기능](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
