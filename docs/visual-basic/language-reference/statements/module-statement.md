---
title: Module 문 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- Module
- vb.Module
helpviewer_keywords:
- modules, classes
- modules
- Module statement [Visual Basic]
- modules, declaring
- standard modules
- classes [Visual Basic], vs. modules
- declarations [Visual Basic], modules
ms.assetid: a1243afc-14a5-45df-95d5-51118aeac362
ms.openlocfilehash: 5628224a08fe5f12cf2a81b179c4998001174354
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2018
ms.locfileid: "42933911"
---
# <a name="module-statement"></a>Module 문
모듈의 이름을 선언 하 고 변수, 속성, 이벤트 및 모듈을 구성 하는 프로시저의 정의 소개 합니다.  
  
## <a name="syntax"></a>구문  
  
```vb 
[ <attributelist> ] [ accessmodifier ]  Module name  
    [ statements ]  
End Module  
```  
  
## <a name="parts"></a>요소  
 `attributelist`  
 선택 사항입니다. 참조 [특성 목록](../../../visual-basic/language-reference/statements/attribute-list.md)합니다.  
  
 `accessmodifier`  
 선택 사항입니다. 다음 중 하나일 수 있습니다.  
  
-   [공용](../../../visual-basic/language-reference/modifiers/public.md)  
  
-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
 참조 [액세스 수준을 Visual Basic의](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)합니다.  
  
 `name`  
 필수. 이 모듈의 이름입니다. 참조 [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)합니다.  
  
 `statements`  
 선택 사항입니다. 변수, 속성, 이벤트, 프로시저 및이 모듈의 중첩 된 형식을 정의 하는 문입니다.  
  
 `End Module`  
 종료는 `Module` 정의 합니다.  
  
## <a name="remarks"></a>설명  
 `Module` 문은 해당 네임 스페이스에서 사용 가능한 참조 형식을 정의 합니다. *모듈* (라고도 *표준 모듈*) 유사 하지만 몇 가지 중요 한 차이가 클래스. 모든 모듈 인스턴스가 하나만 있고 생성 또는 변수에 할당할 필요가 없습니다. 모듈 상속을 지원 하지 않거나 인터페이스를 구현 합니다. 모듈이 *형식* 클래스 또는 구조체는 점에서-모듈의 데이터 형식이 프로그래밍 요소를 선언할 수 없습니다.  
  
 사용할 수 있습니다 `Module` 네임 스페이스 수준 에서만. 즉, 합니다 *선언 컨텍스트* 모듈을 소스 파일이 나 네임 스페이스에 있어야 하 고 클래스, 구조체, 모듈, 인터페이스, 프로시저 또는 블록 수 없습니다. 모든 형식 또는 다른 모듈에서 모듈을 중첩할 수 없습니다. 자세한 내용은 [선언 컨텍스트 및 기본 액세스 수준](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)을 참조하세요.  
  
 모듈에 프로그램 수명과 동일 합니다. 멤버는 모든 `Shared`와 같은 프로그램의 수명 수도 있습니다.  
  
 모듈은 기본적으로 [Friend](../../../visual-basic/language-reference/modifiers/friend.md) 액세스 합니다. 액세스 한정자를 사용 하 여 해당 액세스 수준을 조정할 수 있습니다. 자세한 내용은 [액세스 수준을 Visual Basic의](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)합니다.  
  
 모듈의 모든 멤버는 암시적 `Shared`합니다.  
  
## <a name="classes-and-modules"></a>클래스와 모듈  
 이러한 요소는 비슷한 점이 많이 몇 가지 중요 한 차이점도 있습니다.  
  
-   **용어입니다.** 이전 버전의 Visual Basic 등 두 유형의 모듈로 인식: *클래스 모듈* (.cls 파일) 및 *표준 모듈* (.bas 파일). 현재 버전에서는 이러한 *클래스* 하 고 *모듈*, 각각.  
  
-   **공유 멤버입니다.** 공유 클래스의 멤버 인지 또는 인스턴스 멤버를 제어할 수 있습니다.  
  
-   **개체 방향입니다.** 클래스는 개체 지향 되지만 모듈이 없습니다. 따라서 클래스는 개체로 인스턴스화할 수 있습니다. 자세한 내용은 [개체 및 클래스](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)합니다.  
  
## <a name="rules"></a>규칙  
  
-   **한정자입니다.** 모든 모듈 멤버는 암시적 [공유](../../../visual-basic/language-reference/modifiers/shared.md)합니다. 사용할 수 없습니다는 `Shared` 키워드가 모든 멤버의 공유 상태를 변경할 수 없습니다는 멤버를 선언 하는 경우.  
  
-   **상속.** 이외의 다른 모든 형식에서 상속할 수 없습니다. 모듈 <xref:System.Object>, 모든 모듈에서 상속 합니다. 특히 하나의 모듈에서 다른 상속할 수 없습니다.  
  
     사용할 수 없습니다는 [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md) 지정 하는 데도 모듈 정의 <xref:System.Object>합니다.  
  
-   **기본 속성입니다.** 모듈의 기본 속성을 정의할 수 없습니다. 자세한 내용은 [기본](../../../visual-basic/language-reference/modifiers/default.md)입니다.  
  
## <a name="behavior"></a>동작  
  
-   **액세스 수준입니다.** 모듈 내에서 자신의 액세스 수준 가진 각 멤버를 선언할 수 있습니다. 모듈 멤버를 기본값으로 [공개](../../../visual-basic/language-reference/modifiers/public.md) 변수와 상수를 제외 하 고는 기본적으로 액세스 [개인](../../../visual-basic/language-reference/modifiers/private.md) 액세스 합니다. 모듈에 보다 제한적인 해당 멤버 중 하나를 지정 된 모듈 액세스 수준을 우선적으로 적용 합니다.  
  
-   **범위입니다.** 모듈은 해당 네임 스페이스 범위에서.  
  
     모든 모듈 멤버의 범위는 전체 모듈입니다. 표시 되는 모든 멤버가 *형식 승격*, 모듈을 포함 하는 네임 스페이스를 승격할 해당 범위에 이르게 합니다. 자세한 내용은 [형식 승격](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md)합니다.  
  
-   **정규화 합니다.** 프로젝트에서 여러 모듈을 할 수 있습니다 하 고 둘 이상의 모듈에서 동일한 이름 가진 멤버를 선언할 수 있습니다. 그러나 모듈 외부에서 참조 되는 경우 적절 한 모듈 이름으로 이러한 멤버에 대 한 모든 참조를 정규화 해야 합니다. 자세한 내용은 [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)합니다.  
  
## <a name="example"></a>예  
 [!code-vb[VbVbalrStatements#69](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/module-statement_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [Class 문](../../../visual-basic/language-reference/statements/class-statement.md)  
 [Namespace 문](../../../visual-basic/language-reference/statements/namespace-statement.md)  
 [Structure 문](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [Interface 문](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [Property 문](../../../visual-basic/language-reference/statements/property-statement.md)  
 [형식 승격](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md)
