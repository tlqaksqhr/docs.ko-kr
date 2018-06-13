---
title: Implements 절(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ImplementsClause
helpviewer_keywords:
- interface implementation [Visual Basic], reimplementation
- interface members [Visual Basic], reimplementation
- interface members [Visual Basic], Implements keyword
- interface members
- members [Visual Basic], reimplementation
- interface implementation [Visual Basic], Implements keyword
- interface members [Visual Basic], implementing
- Implements keyword [Visual Basic]
- Implements statement [Visual Basic], about Implements
- members [Visual Basic], implementing
- members [Visual Basic], Implements keyword
- reimplementation
ms.assetid: 5252cdf9-964d-4fc6-af0f-0449b7126b5a
ms.openlocfilehash: 1e34245ac528e9e2463afbfd07dff91bf693830b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603407"
---
# <a name="implements-clause-visual-basic"></a>Implements 절(Visual Basic)
클래스 또는 구조체 멤버가 인터페이스에 정의 된 멤버에 대 한 구현을 제공 하는 것을 나타냅니다.  
  
## <a name="remarks"></a>설명  
`Implements` 키워드는 동일 하지는 [Implements 문](../../../visual-basic/language-reference/statements/implements-statement.md)합니다. 사용 하면는 `Implements` 문을 클래스 또는 구조체에는 하나 이상의 인터페이스를 구현 하 고 다음 각 멤버에 대해 사용 되도록 지정할는 `Implements` 키워드는 인터페이스와 멤버를 지정 하려면 구현 합니다.

클래스 또는 구조체에서 인터페이스를 구현 하는 경우에 포함 되어야는 `Implements` 문 바로 뒤의 [Class 문](../../../visual-basic/language-reference/statements/class-statement.md) 또는 [Structure 문을](../../../visual-basic/language-reference/statements/structure-statement.md), 모든 멤버를 구현 해야 합니다 인터페이스에서 정의 합니다.

## <a name="reimplementation"></a>다시 구현  
파생된 클래스에서 이미 기본 클래스 구현 하는 인터페이스 멤버를 다시 구현할 수 있습니다. 이 다음과 같은 점에서 기본 클래스 멤버를 재정의와 다릅니다.

- 기본 클래스 멤버 수 하지 않아도 [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md) 다시 구현 되기 위해.
- 다른 이름으로 멤버를 다시 구현할 수 있습니다.

`Implements` 키워드는 다음 컨텍스트에서 사용할 수 있습니다.
- [Event 문](../../../visual-basic/language-reference/statements/event-statement.md)
- [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)
- [Property 문](../../../visual-basic/language-reference/statements/property-statement.md)
- [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>참고 항목  
 [Implements 문](../../../visual-basic/language-reference/statements/implements-statement.md)  
 [Interface 문](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [Class 문](../../../visual-basic/language-reference/statements/class-statement.md)  
 [Structure 문](../../../visual-basic/language-reference/statements/structure-statement.md)
