---
title: Set 문(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Set
helpviewer_keywords:
- property procedures [Visual Basic], Set statements
- Set statement [Visual Basic]
- Set statement [Visual Basic], syntax
- write-only properties
- properties [Visual Basic], write-only
ms.assetid: 9ecc27b4-df84-420d-9075-db25455fb3cd
ms.openlocfilehash: dbc48d14bac54809e4ddd12c87429bf407169950
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="set-statement-visual-basic"></a>Set 문(Visual Basic)
선언 된 `Set` 속성 프로시저는 속성에 값을 할당 하는 데 사용 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
[ <attributelist> ] [ accessmodifier ] Set (ByVal value [ As datatype ])  
    [ statements ]  
End Set  
```  
  
## <a name="parts"></a>요소  
 `attributelist`  
 선택 사항입니다. 참조 [특성 목록](../../../visual-basic/language-reference/statements/attribute-list.md)합니다.  
  
 `accessmodifier`  
 선택 사항 중 하나 에서만에서 `Get` 및 `Set` 이 속성에는 문입니다. 다음 중 하나일 수 있습니다.  
  
-   [보호됨](../../../visual-basic/language-reference/modifiers/protected.md)  
  
-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
-   [전용](../../../visual-basic/language-reference/modifiers/private.md)  
  
-   `Protected Friend`  
  
 참조 [액세스 수준을 Visual Basic의](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)합니다.  
  
 `value`  
 필수. 속성에 대 한 새 값을 포함 하는 매개 변수입니다.  
  
 `datatype`  
 필요한 경우 `Option Strict` 은 `On`합니다. 데이터 형식이 고 `value` 매개 변수입니다. 속성의 데이터 형식으로 지정 된 데이터 형식이 같아야 여기서이 `Set` 문이 선언 됩니다.  
  
 `statements`  
 선택 사항입니다. 다음과 같은 경우 실행 하는 하나 이상의 문을 `Set` 속성 프로시저를 호출 합니다.  
  
 `End Set`  
 필수. 정의 종료는 `Set` 속성 프로시저입니다.  
  
## <a name="remarks"></a>설명  
 모든 속성은 한 `Set` 속성 프로시저 속성이 표시 되어 있지 않으면 `ReadOnly`합니다. `Set` 방법을 사용 하는 속성의 값을 설정 합니다.  
  
 Visual Basic에는 자동으로 속성의 호출 `Set` 프로시저 대입문 속성에 저장할 수 있는 값을 제공 합니다.  
  
 Visual Basic에는 매개 변수를 전달는 `Set` 속성을 할당 하는 동안 프로시저입니다. 에 대 한 매개 변수를 제공 하지 않는 경우 `Set`, 라는 암시적 매개 변수를 사용 하는 통합된 개발 환경 (IDE) `value`합니다. 매개 변수 속성에 할당할 값을 보유 합니다. 일반적으로 전용 지역 변수에이 값을 저장 하 고 반환 될 때마다는 `Get` 프로시저를 호출 합니다.  
  
 속성 선언의 본문에만 속성의 포함 될 수 있습니다 `Get` 및 `Set` 절차 간에 [Property 문](../../../visual-basic/language-reference/statements/property-statement.md) 및 `End Property` 문. 이러한 프로시저 외에 아무 것도 저장할 수 없습니다. 특히, 속성의 현재 값을 저장할 수 없습니다. 다른 속성 프로시저에서 액세스할 수 없으므로 속성 프로시저 중 하나의 내부 저장 하는 경우에 속성 외부에이 값을 저장 해야 합니다. 값을 저장 하는 일반적인 방법입니다는 [개인](../../../visual-basic/language-reference/modifiers/private.md) 속성와 같은 수준에서 선언 된 변수입니다. 정의 해야 합니다는 `Set` 을 적용할 속성 내의 프로시저입니다.  
  
 `Set` 프로시저는 기본적으로 포함 하는 해당 속성의 액세스 수준을 사용 하지 않는 한 `accessmodifier` 에 `Set` 문.  
  
## <a name="rules"></a>규칙  
  
-   **액세스 수준이 혼합된 합니다.** 에 대 한 다른 액세스 수준을 선택적으로 지정할 수 읽기 / 쓰기 속성을 정의 하는 경우는 `Get` 또는 `Set` 프로시저 다르다는 것입니다. 이 작업을 수행 하는 경우 프로시저 액세스 수준을 속성의 액세스 수준 보다 제한적 이어야 합니다. 예를 들어, 속성 선언 된 경우 `Friend`를 선언할 수 있습니다는 `Set` 프로시저 `Private`, 아닌 `Public`합니다.  
  
     정의 하는 경우는 `WriteOnly` 속성에는 `Set` 프로시저 전체 속성을 나타냅니다. 수준에 대 한 다른 액세스를 선언할 수 없습니다 `Set`속성에 대 한 두 개의 액세스 수준을 설정 되므로, 합니다.  
  
## <a name="behavior"></a>동작  
  
-   **속성 프로시저에서 반환 합니다.** 경우는 `Set` 프로시저가 호출 코드에 반환 되 면 저장할 값을 제공 하는 문을 계속 실행 합니다.  
  
     `Set` 속성 프로시저 중 하나를 사용 하 여 반환할 수 있습니다는 [Return 문을](../../../visual-basic/language-reference/statements/return-statement.md) 또는 [Exit 문은](../../../visual-basic/language-reference/statements/exit-statement.md)합니다.  
  
     `Exit Property` 및 `Return` 문은 속성 프로시저를 즉시 종료 합니다. 개수에 관계 없이 `Exit Property` 및 `Return` 문은 프로시저에서 아무 곳 이나 나타날 수 있으며 함께 사용할 수 있습니다 `Exit Property` 및 `Return` 문.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `Set` 문을 속성의 값을 설정 합니다.  
  
 [!code-vb[VbVbalrStatements#55](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/set-statement_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [Get 문](../../../visual-basic/language-reference/statements/get-statement.md)  
 [Property 문](../../../visual-basic/language-reference/statements/property-statement.md)  
 [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [속성 프로시저](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)
