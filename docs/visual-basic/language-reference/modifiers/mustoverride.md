---
title: MustOverride(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.MustOverride
- MustOverride
helpviewer_keywords:
- virtual elements [Visual Basic], pure
- elements [Visual Basic], pure virtual
- properties [Visual Basic], redefining
- procedures [Visual Basic], overriding
- overriding, MustOverride keyword
- procedures [Visual Basic], redefining
- pure virtual elements [Visual Basic]
- MustOverride keyword [Visual Basic]
- properties [Visual Basic], overriding
ms.assetid: 6e9d9ad6-bb64-433f-b32b-3ef84293bf96
ms.openlocfilehash: 5dabd90d29bc41d017436876af24a67fa87e8e17
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33599872"
---
# <a name="mustoverride-visual-basic"></a>MustOverride(Visual Basic)
이 클래스에서 구현 되지 않은 속성 또는 프로시저 이며 사용 하려면 먼저 파생된 클래스에서 재정의 되어야를 지정 합니다.  
  
## <a name="remarks"></a>설명  
 속성 또는 프로시저 선언문에서만 `MustOverride`를 사용할 수 있습니다. 속성이 나 프로시저를 지정 하는 `MustOverride` 클래스의 멤버 여야 합니다 클래스를 표시 해야 하 고 [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md)합니다.  
  
## <a name="rules"></a>규칙  
  
-   **완료 되지 않은 선언입니다.** 지정 하는 경우 `MustOverride`, 하지 속성 또는 프로시저에 대 한 코드의 모든 줄을 지정 하지 않으면도 `End Function`, `End Property`, 또는 `End Sub` 문.  
  
-   **결합 된 한정자입니다.** 지정할 수 없습니다 `MustOverride` 와 함께 `NotOverridable`, `Overridable`, 또는 `Shared` 같은 선언에 있습니다.  
  
-   **숨기기와 재정의 합니다.** 숨김과 재정의는 둘 다 상속된 요소를 다시 정의하지만 두 방법에는 중요한 차이점이 있습니다. 자세한 내용은 참조 [Visual Basic의 숨김 기능](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)합니다.  
  
-   **대체 조건입니다.** 재정의에서 제외 하 고 사용할 수 없는 요소 라고도 *순수 가상* 요소입니다.  
  
 `MustOverride` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.  
  
 [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Property 문](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>참고 항목  
 [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)  
 [재정의 가능](../../../visual-basic/language-reference/modifiers/overridable.md)  
 [재정의](../../../visual-basic/language-reference/modifiers/overrides.md)  
 [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md)  
 [키워드](../../../visual-basic/language-reference/keywords/index.md)  
 [Visual Basic의 숨김 기능](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
