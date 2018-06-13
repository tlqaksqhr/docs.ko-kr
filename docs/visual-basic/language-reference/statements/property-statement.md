---
title: Property Statement
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
ms.openlocfilehash: 3f3ced3f0c441518594820f75243c71fb0c3babd
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/17/2018
ms.locfileid: "34235992"
---
# <a name="property-statement"></a>Property Statement
속성을 저장 하 고 속성의 값을 검색 하는 데 사용 하는 속성 프로시저의 이름을 선언 합니다.  
  
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
  
     선택 사항입니다. 이 속성은 클래스 또는 구조체에는 정의 대 한 기본 속성을 지정 합니다. 기본 속성 매개 변수를 허용 해야 설정 되었고 속성 이름을 지정 하지 않고 검색 될 수 있습니다. 속성으로 선언 하는 경우 `Default`를 사용할 수 없습니다 `Private` 속성 또는 해당 속성 프로시저 중 하나입니다.  
  
-   `accessmodifier`  
  
     선택적 요소는 `Property` 문 중 최대 하나에 `Get` 및 `Set` 문. 다음 중 하나일 수 있습니다.  
  
    -   [공용](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [보호됨](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [전용](../../../visual-basic/language-reference/modifiers/private.md)  
  
    - [Protected Friend](../../language-reference/modifiers/protected-friend.md) 

    - [보호 된 개인](../../language-reference/modifiers/private-protected.md)
  
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
  
     필수. 속성의 이름입니다. 참조 [선언 된 요소 이름](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)합니다.  
  
-   `parameterlist`  
  
     선택 사항입니다. 이 속성의 매개 변수 및의 가능한 추가 매개 변수를 나타내는 지역 변수 이름의 목록이 `Set` 프로시저입니다. 참조 [매개 변수 목록](../../../visual-basic/language-reference/statements/parameter-list.md)합니다.  
  
-   `returntype`  
  
     필요한 경우 `Option``Strict` 은 `On`합니다. 이 속성에서 반환 되는 값의 데이터 형식입니다.  
  
-   `Implements`  
  
     선택 사항입니다. 이 속성의 포함 하는 클래스 또는 구조체에서 구현 되는 인터페이스에 정의 된 하나 이상의 속성을이 속성을 구현 함을 나타냅니다. 참조 [문을 구현](../../../visual-basic/language-reference/statements/implements-statement.md)합니다.  
  
-   `implementslist`  
  
     `Implements`가 제공된 경우 필수입니다. 구현 되는 속성 목록입니다.  
  
     `implementedproperty [ , implementedproperty ... ]`  
  
     각 `implementedproperty`에는 다음과 같은 구문과 요소가 있습니다.  
  
     `interface.definedname`  
  
    |파트|설명|  
    |---|---|  
    |`interface`|필수. 이 속성에 의해 구현 되는 인터페이스의 이름의 클래스 또는 구조체를 포함 합니다.|  
    |`definedname`|필수. 이름에 속성이 정의 된 `interface`합니다.|  
  
-   `Get`  
  
     선택 사항입니다. 속성이 표시 하는 경우 필요한 `WriteOnly`합니다. 시작 된 `Get` 속성의 값을 반환 하는 데 사용 되는 속성 프로시저입니다.  
  
-   `statements`  
  
     선택 사항입니다. 내에서 실행할 문 블록을는 `Get` 또는 `Set` 프로시저입니다.  
  
-   `End Get`  
  
     종료는 `Get` 속성 프로시저입니다.  
  
-   `Set`  
  
     선택 사항입니다. 속성이 표시 하는 경우 필요한 `ReadOnly`합니다. 시작 된 `Set` 속성의 값을 저장 하는 데 사용 되는 속성 프로시저입니다.  
  
-   `End Set`  
  
     종료는 `Set` 속성 프로시저입니다.  
  
-   `End Property`  
  
     이 속성의 정의 종료 합니다.  
  
## <a name="remarks"></a>설명  
 `Property` 문을 속성의 선언을 제공 합니다. 속성을 사용할 수는 `Get` (읽기 전용), 프로시저는 `Set` 프로시저 (쓰기 전용) 또는 두 가지 모두 (읽기-쓰기). 생략할 수 있습니다는 `Get` 및 `Set` 자동 구현 속성을 사용할 때 프로시저입니다. 자세한 내용은 [자동으로 구현된 속성](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md)을 참조하세요.  
  
 사용할 수 있습니다 `Property` 클래스 수준에만 합니다. 즉,는 *선언 컨텍스트* 속성 클래스, 구조체, 모듈 또는 인터페이스를 이어야 하며 소스 파일, 네임 스페이스, 프로시저 또는 블록 수 없습니다. 자세한 내용은 [선언 컨텍스트 및 기본 액세스 수준](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)을 참조하세요.  
  
 기본적으로 속성 공용 액세스를 사용합니다. 액세스 한정자로 속성의 액세스 수준을 조정할 수 있습니다는 `Property` 문과 있습니다 수 필요에 따라 조정 더 제한적인 액세스 수준에 해당 속성 프로시저 중 하나입니다.  
  
 Visual Basic에는 매개 변수를 전달는 `Set` 속성을 할당 하는 동안 프로시저입니다. 에 대 한 매개 변수를 제공 하지 않는 경우 `Set`, 라는 암시적 매개 변수를 사용 하는 통합된 개발 환경 (IDE) `value`합니다. 이 매개 변수 속성에 할당할 값을 보유 합니다. 일반적으로 전용 지역 변수에이 값을 저장 하 고 반환 될 때마다는 `Get` 프로시저를 호출 합니다.  
  
## <a name="rules"></a>규칙  
  
-   **액세스 수준이 혼합된 합니다.** 에 대 한 다른 액세스 수준을 선택적으로 지정할 수 읽기 / 쓰기 속성을 정의 하는 경우는 `Get` 또는 `Set` 프로시저 다르다는 것입니다. 이 작업을 수행 하는 경우 프로시저 액세스 수준을 속성의 액세스 수준 보다 제한적 이어야 합니다. 예를 들어, 속성 선언 된 경우 `Friend`를 선언할 수 있습니다는 `Set` 프로시저 `Private`, 아닌 `Public`합니다.  
  
     정의 하는 경우는 `ReadOnly` 또는 `WriteOnly` 속성, 단일 속성 프로시저 (`Get` 또는 `Set`각각) 모든 속성을 나타냅니다. 속성에 대 한 두 개의 액세스 수준을 설정 되므로 이러한 프로시저에 대 한 다른 액세스 수준을 선언할 수 없습니다.  
  
-   **반환 형식입니다.** `Property` 문은 반환 하는 값의 데이터 형식을 선언할 수 있습니다. 모든 데이터 형식이 나 열거형, 구조체, 클래스 또는 인터페이스의 이름을 지정할 수 있습니다.  
  
     지정 하지 않으면 `returntype`, 속성은 반환 `Object`합니다.  
  
-   **구현입니다.** 이 속성을 사용 하는 경우는 `Implements` 키워드를 포함 하는 클래스나 구조체 있어야는 `Implements` 문 바로 다음의 `Class` 또는 `Structure` 문. `Implements` 각 인터페이스에 지정 된 문에 포함 해야 `implementslist`합니다. 그러나 이름을 인터페이스를 정의 하는 `Property` (에 `definedname`)이이 속성의 이름을와 동일할 필요가 없습니다 (에서 `name`).  
  
## <a name="behavior"></a>동작  
  
-   **속성 프로시저에서 반환 합니다.** 경우는 `Get` 또는 `Set` 문을 호출한 다음 문이 실행 계속 프로시저가 호출 코드에 반환 되 면 합니다.  
  
     `Exit Property` 및 `Return` 문은 속성 프로시저를 즉시 종료 합니다. 개수에 관계 없이 `Exit Property` 및 `Return` 문은 프로시저에서 아무 곳 이나 나타날 수 있으며 함께 사용할 수 있습니다 `Exit Property` 및 `Return` 문.  
  
-   **값을 반환 합니다.** 값을 반환 하는 `Get` 프로시저, 속성 이름에 값을 할당 하거나 포함 한 `Return` 문. 다음 예제에서는 속성 이름에 반환 값을 할당 `quoteForTheDay` 다음 사용 하 여는 `Exit Property` 문 실행 합니다.  
  
     [!code-vb[VbVbalrStatements#27](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_1.vb)]  
  
     [!code-vb[VbVbalrStatements#28](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_2.vb)]  
  
     사용 하는 경우 `Exit Property` 값을 할당 하지 않고 `name`, `Get` 프로시저가 속성의 데이터 형식에 대 한 기본값을 반환 합니다.  
  
     `Return` 문을 동시에 할당 된 `Get` 프로시저 반환 값의 절차를 종료 합니다. 다음 예제에서는이 보여 줍니다.  
  
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
