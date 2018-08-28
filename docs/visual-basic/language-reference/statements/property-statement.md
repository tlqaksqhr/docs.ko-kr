---
title: Property 문 (Visual Basic)
ms.date: 05/12/2018
f1_keywords:
- vb.PropertySet
- vb.Property
- vb.PropertyGet
helpviewer_keywords:
- Property statement [Visual Basic]
- default modifier
- property procedures [Visual Basic], Property statements
- Property keyword [Visual Basic]
ms.assetid: 3155edaf-8ebd-45c6-9cef-11d5d2dc8d38
ms.openlocfilehash: 21ca15d6a6939d884c7e6abedc1f7919be079edd
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/27/2018
ms.locfileid: "42999527"
---
# <a name="property-statement"></a>Property Statement
이름 속성 및 저장 하 고 속성의 값을 검색 하는 데 속성 프로시저를 선언 합니다.  
  
## <a name="syntax"></a>구문  
  
```vb  
[ <attributelist> ] [ Default ] [ accessmodifier ]   
[ propertymodifiers ] [ Shared ] [ Shadows ] [ ReadOnly | WriteOnly ] [ Iterator ]  
Property name ( [ parameterlist ] ) [ As returntype ] [ Implements implementslist ]  
    [ <attributelist> ] [ accessmodifier ] Get  
        [ statements ]  
    End Get  
    [ <attributelist> ] [ accessmodifier ] Set ( ByVal value As returntype [, parameterlist ] )  
        [ statements ]  
    End Set  
End Property  
- or -  
[ <attributelist> ] [ Default ] [ accessmodifier ]   
[ propertymodifiers ] [ Shared ] [ Shadows ] [ ReadOnly | WriteOnly ]   
Property name ( [ parameterlist ] ) [ As returntype ] [ Implements implementslist ]  
```  
  
## <a name="parts"></a>요소  
  
-   `attributelist`  
  
     선택 사항입니다. 이 속성에 적용 되는 특성의 목록 또는 `Get` 또는 `Set` 프로시저입니다. 참조 [특성 목록](../../../visual-basic/language-reference/statements/attribute-list.md)합니다.  
  
-   `Default`  
  
     선택 사항입니다. 이 속성은 클래스 또는 구조체 정의 된 기본 속성을 지정 합니다. 기본 속성 매개 변수를 허용 해야 합니다 설정 및 속성 이름을 지정 하지 않고 검색 될 수 있습니다. 속성으로 선언 하는 경우 `Default`를 사용할 수 없습니다 `Private` 속성 또는 해당 속성 프로시저 중 하나입니다.  
  
-   `accessmodifier`  
  
     선택적 요소를 `Property` 문 및 중 하나만 `Get` 및 `Set` 문. 다음 중 하나일 수 있습니다.  
  
    -   [공용](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [보호됨](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [전용](../../../visual-basic/language-reference/modifiers/private.md)  
  
    - [Protected Friend](../../language-reference/modifiers/protected-friend.md) 

    - [Private Protected](../../language-reference/modifiers/private-protected.md)
  
     참조 [액세스 수준을 Visual Basic의](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)합니다.  
  
-   `propertymodifiers`  
  
     선택 사항입니다. 다음 중 하나일 수 있습니다.  
  
    -   [오버로드](../../../visual-basic/language-reference/modifiers/overloads.md)  
  
    -   [재정의](../../../visual-basic/language-reference/modifiers/overrides.md)  
  
    -   [재정의 가능](../../../visual-basic/language-reference/modifiers/overridable.md)  
  
    -   [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)  
  
    -   [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)  
  
    -   `MustOverride Overrides`  
  
    -   `NotOverridable Overrides`  
  
-   `Shared`  
  
     선택 사항입니다. 참조 [공유](../../../visual-basic/language-reference/modifiers/shared.md)합니다.  
  
-   `Shadows`  
  
     선택 사항입니다. 참조 [그림자](../../../visual-basic/language-reference/modifiers/shadows.md)합니다.  
  
-   `ReadOnly`  
  
     선택 사항입니다. 참조 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)합니다.  
  
-   `WriteOnly`  
  
     선택 사항입니다. 참조 [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md)합니다.  
  
-   `Iterator`  
  
     선택 사항입니다. 참조 [반복기](../../../visual-basic/language-reference/modifiers/iterator.md)합니다.  
  
-   `name`  
  
     필수. 속성의 이름입니다. 참조 [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)합니다.  
  
-   `parameterlist`  
  
     선택 사항입니다. 이 속성의 매개 변수 및의 추가 매개 변수 수를 나타내는 지역 변수 이름의 목록을 `Set` 프로시저입니다. 참조 [매개 변수 목록](../../../visual-basic/language-reference/statements/parameter-list.md)합니다.  
  
-   `returntype`  
  
     필요한 경우 `Option Strict` 는 `On`합니다. 이 속성에 의해 반환 되는 값의 데이터 형식입니다.  
  
-   `Implements`  
  
     선택 사항입니다. 하나 이상의 속성을이 속성의 포함 하는 클래스 또는 구조체에서 구현 된 인터페이스에 정의 된 각각이이 속성을 구현 함을 나타냅니다. 참조 [문을 구현](../../../visual-basic/language-reference/statements/implements-statement.md)합니다.  
  
-   `implementslist`  
  
     `Implements`가 제공된 경우 필수입니다. 구현 되는 속성 목록입니다.  
  
     `implementedproperty [ , implementedproperty ... ]`  
  
     각 `implementedproperty`에는 다음과 같은 구문과 요소가 있습니다.  
  
     `interface.definedname`  
  
    |파트|설명|  
    |---|---|  
    |`interface`|필수. 이 속성에 의해 구현 된 인터페이스의 이름을 클래스 또는 구조체를 포함 합니다.|  
    |`definedname`|필수. 속성에 정의 된 이름 `interface`합니다.|  
  
-   `Get`  
  
     선택 사항입니다. 속성이 표시 하는 경우 필요한 `WriteOnly`합니다. 시작을 `Get` 속성의 값을 반환 하는 데 사용 되는 속성 프로시저입니다.  
  
-   `statements`  
  
     선택 사항입니다. 내에 실행할 문 블록을 `Get` 또는 `Set` 프로시저입니다.  
  
-   `End Get`  
  
     종료는 `Get` 속성 프로시저입니다.  
  
-   `Set`  
  
     선택 사항입니다. 속성이 표시 하는 경우 필요한 `ReadOnly`합니다. 시작을 `Set` 속성의 값을 저장 하는 데 사용 되는 속성 프로시저입니다.  
  
-   `End Set`  
  
     종료는 `Set` 속성 프로시저입니다.  
  
-   `End Property`  
  
     이 속성의 정의 종료 합니다.  
  
## <a name="remarks"></a>설명  
 `Property` 문을 속성의 선언을 제공 합니다. 속성을 `Get` (읽기 전용), 프로시저를 `Set` 프로시저 (쓰기 전용) 또는 두 가지 모두 (읽기-쓰기). 생략할 수 있습니다 합니다 `Get` 및 `Set` 자동 구현 속성을 사용 하는 경우에 프로시저입니다. 자세한 내용은 [자동으로 구현된 속성](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md)을 참조하세요.  
  
 사용할 수 있습니다 `Property` 클래스 수준에만 합니다. 즉, 합니다 *선언 컨텍스트* 속성 클래스, 구조체, 모듈 또는 인터페이스 여야 하 고 소스 파일, 네임 스페이스, 프로시저 또는 블록일 수 없습니다. 자세한 내용은 [선언 컨텍스트 및 기본 액세스 수준](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)을 참조하세요.  
  
 기본적으로 속성 공용 액세스를 사용합니다. 액세스 한정자를 사용 하 여 속성의 액세스 수준을 조정할 수 있습니다는 `Property` 문 고 필요에 따라 조정할 수는 더 제한적인 액세스 수준에 해당 속성 프로시저 중 하나입니다.  
  
 Visual Basic에 매개 변수를 전달 합니다 `Set` 속성을 할당 하는 동안 프로시저입니다. 매개 변수를 제공 하지 않는 경우 `Set`, 라는 암시적 매개 변수를 사용 하는 통합된 개발 환경 (IDE) `value`합니다. 이 매개 변수 속성에 할당할 값을 보유 합니다. 일반적으로 개인 로컬 변수에이 값을 저장 하 고 반환할 때마다는 `Get` 프로시저를 호출 합니다.  
  
## <a name="rules"></a>규칙  
  
-   **혼합 된 액세스 수준입니다.** 서로 다른 액세스 수준에 대 한 필요에 따라 지정할 수는 읽기 / 쓰기 속성을 정의 하는 경우는 `Get` 또는 `Set` 절차, 하지만 둘 다. 이 작업을 수행 하는 경우 프로시저 액세스 수준 속성의 액세스 수준 보다 더 제한적 이어야 합니다. 예를 들어, 속성 선언 되 면 `Friend`를 선언할 수 있습니다 합니다 `Set` 프로시저 `Private`, 아닌 `Public`합니다.  
  
     정의 하는 경우는 `ReadOnly` 또는 `WriteOnly` 속성을 단일 속성 프로시저 (`Get` 또는 `Set`각각) 모든 속성을 나타냅니다. 속성에 대 한 액세스 수준은 다음 두 설정 되므로 이러한 프로시저에 대 한 다른 액세스 수준을 선언할 수 없습니다.  
  
-   **형식을 반환 합니다.** `Property` 문은 반환 하는 값의 데이터 형식을 선언할 수 있습니다. 모든 데이터 형식 또는 열거형, 구조체, 클래스 또는 인터페이스의 이름을 지정할 수 있습니다.  
  
     지정 하지 않는 경우 `returntype`에서 속성 반환 `Object`합니다.  
  
-   **구현입니다.** 이 속성을 사용 하는 경우는 `Implements` 키워드를 포함 하는 클래스 또는 구조체 있어야를 `Implements` 문 바로 다음 해당 `Class` 또는 `Structure` 문입니다. 합니다 `Implements` 각 인터페이스에 지정 된 문에 포함 해야 `implementslist`합니다. 그러나 사용 되는 인터페이스는 다음과 같이 정의 됩니다. 이름을 합니다 `Property` (에서 `definedname`)이이 속성의 이름으로 동일할 필요가 없습니다 (에서 `name`).  
  
## <a name="behavior"></a>동작  
  
-   **속성 프로시저에서 반환합니다.** 경우는 `Get` 또는 `Set` 프로시저가 호출 코드에 반환 되 면 실행이 문 다음에 호출한 문을 사용 하 여 계속 합니다.  
  
     합니다 `Exit Property` 및 `Return` 문은 속성 프로시저를 즉시 종료 합니다. 임의 개수의 `Exit Property` 하 고 `Return` 문을 프로시저에서 아무 곳 이나 나타날 수 있으며 함께 사용할 수 있습니다 `Exit Property` 및 `Return` 문.  
  
-   **값을 반환 합니다.** 값을 반환 하는 `Get` 프로시저, 속성 이름에 값을 할당 하거나 포함을 `Return` 문입니다. 다음 예제에서는 속성 이름에 반환 값을 할당 `quoteForTheDay` 를 사용 하 여는 `Exit Property` 문을 반환 합니다.  
  
     [!code-vb[VbVbalrStatements#27](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_1.vb)]  
  
     [!code-vb[VbVbalrStatements#28](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_2.vb)]  
  
     사용 하는 경우 `Exit Property` 값을 할당 하지 않고 `name`는 `Get` 프로시저가 속성의 데이터 형식에 대 한 기본값을 반환 합니다.  
  
     `Return` 문은 한 번에 할당 된 `Get` 프로시저 반환 값 및 절차를 종료 합니다. 다음 예제에서는이 보여 줍니다.  
  
     [!code-vb[VbVbalrStatements#27](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_1.vb)]  
  
     [!code-vb[VbVbalrStatements#29](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_3.vb)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 클래스에서 속성을 선언 합니다.  
  
 [!code-vb[VbVbalrStatements#51](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_4.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [자동으로 구현된 속성](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md)  
 [개체 및 클래스](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [Get 문](../../../visual-basic/language-reference/statements/get-statement.md)  
 [Set 문](../../../visual-basic/language-reference/statements/set-statement.md)  
 [매개 변수 목록](../../../visual-basic/language-reference/statements/parameter-list.md)  
 [기본](../../../visual-basic/language-reference/modifiers/default.md)
