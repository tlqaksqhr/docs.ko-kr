---
title: NotOverridable(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.NotOverridable
- NotOverridable
helpviewer_keywords:
- sealed methods [Visual Basic]
- NotOverridable keyword [Visual Basic]
- properties [Visual Basic], redefining
- elements [Visual Basic], sealed
- sealed [elements VB]
- procedures [Visual Basic], overriding
- procedures [Visual Basic], redefining
- overriding
- methods [Visual Basic], sealed
- properties [Visual Basic], overriding
ms.assetid: 66ec6984-f5f5-4857-b362-6a3907aaf9e0
ms.openlocfilehash: 3fae1a4b587c379dbc459cbc973982851e713785
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33600755"
---
# <a name="notoverridable-visual-basic"></a>NotOverridable(Visual Basic)
파생된 클래스에서 속성 또는 프로시저를 재정의할 수 없음을 지정 합니다.  
  
## <a name="remarks"></a>설명  
 `NotOverridable` 파생된 클래스에서 재정의 되는 속성 또는 메서드를 방지 하는 한정자입니다.  [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md) 파생된 클래스에서 재정의 되도록 클래스에서 속성 또는 메서드를 허용 하는 한정자입니다. 자세한 내용은 [상속 기본 사항](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)을 참조하세요.  
  
 경우는 `Overridable` 또는 `NotOverridable` 한정자를 지정 하지 않으면, 기본 설정 속성 또는 메서드의 기본 클래스 속성 또는 메서드의 재정의 하는 여부에 따라 달라 집니다. 속성 또는 메서드는 기본 클래스 속성 또는 메서드를 재정의 하는 경우 기본 설정은입니다 `Overridable`, 그렇지 않으면는 `NotOverridable`합니다.  
  
 재정의할 수 없는 요소 라고도 *봉인* 요소입니다.  
  
 속성 또는 프로시저 선언문에서만 `NotOverridable`를 사용할 수 있습니다. 지정할 수 있습니다 `NotOverridable` 속성이 나 다른 속성 또는 프로시저와 함께만에서 즉, 재정의 하는 프로시저에 대해서만 `Overrides`합니다.  
  
## <a name="combined-modifiers"></a>결합 된 한정자  
 지정할 수 없으며 `Overridable` 또는 `NotOverridable` 에 대 한 한 `Private` 메서드.  
  
 지정할 수 없습니다 `NotOverridable` 와 함께 `MustOverride`, `Overridable`, 또는 `Shared` 같은 선언에 있습니다.  
  
## <a name="usage"></a>용도  
 `NotOverridable` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.  
  
 [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Property 문](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>참고 항목  
 [한정자](../../../visual-basic/language-reference/modifiers/index.md)  
 [상속 기본 사항](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)  
 [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)  
 [재정의 가능](../../../visual-basic/language-reference/modifiers/overridable.md)  
 [재정의](../../../visual-basic/language-reference/modifiers/overrides.md)  
 [키워드](../../../visual-basic/language-reference/keywords/index.md)  
 [Visual Basic의 숨김 기능](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
