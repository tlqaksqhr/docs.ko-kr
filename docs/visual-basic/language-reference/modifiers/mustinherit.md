---
title: MustInherit(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- MustInherit
- vb.MustInherit
helpviewer_keywords:
- classes [Visual Basic], abstract
- MustInherit classes [Visual Basic], MustInherit keyword
- abstract classes [Visual Basic], MustInherit class
- MustInherit keyword [Visual Basic]
ms.assetid: b8f05185-90e3-4dd7-adc2-90d852fab5b4
ms.openlocfilehash: 5d622c1cff77a45c8de7772af7efbb73586f4400
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33602842"
---
# <a name="mustinherit-visual-basic"></a>MustInherit(Visual Basic)
클래스를 기본 클래스로 사용할 수 있는지와에서 직접 개체를 만들 수 없음을 지정 합니다.  
  
## <a name="remarks"></a>설명  
 용도 *기본 클래스* (라고도 *추상 클래스*)에서 파생 된 모든 클래스에 공통적인 기능을 정의 하는 것입니다. 파생된 클래스는 공통 요소를 재정의 하지 않아도 저장 됩니다. 경우에 따라이 일반적인 기능은 사용할 수 있는 개체를 만들 수 있을 만큼 완벽 하 고 각 파생된 클래스 누락 된 기능을 정의 합니다. 이 경우 개체를 만들 파생된 클래스 에서만에서 사용 하는 코드를 할 수 있습니다. 사용 하면 `MustInherit` 이 값을 적용 하기 위해 기본 클래스에 있습니다.  
  
 또 다른 용도 `MustInherit` 클래스는 관련된 클래스 집합에 변수를 제한 하는 것입니다. 기본 클래스를 정의 하 고 이러한 모든 관련된 클래스에서 파생 수 있습니다. 기본 클래스는 모든 파생된 클래스에 공통 된 기능을 제공 하지 않아도 되지만 변수에 값을 할당에 대 한 필터 역할도 할 수 있습니다. 기본 클래스로 변수를 선언 하는 사용 하는 코드를 하는 경우 Visual Basic를 사용 하면 파생된 클래스 중 하나에서 해당 변수는 개체에만 할당할 수 있습니다.  
  
 여러.NET Framework 정의 `MustInherit` 클래스, 그중에서 <xref:System.Array>, <xref:System.Enum>, 및 <xref:System.ValueType>합니다. <xref:System.ValueType> 변수를 제한 하는 기본 클래스의 예시입니다. 모든 값 형식에서 파생 <xref:System.ValueType>합니다. 변수를 선언 하는 경우 <xref:System.ValueType>, 값 형식에만 변수에 할당할 수 있습니다.  
  
## <a name="rules"></a>규칙  
  
-   **선언 컨텍스트입니다.** 사용할 수 있습니다 `MustInherit` 에서만 `Class` 문.  
  
-   **결합 된 한정자입니다.** 지정할 수 없으며 `MustInherit` 와 함께 `NotInheritable` 같은 선언에 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에는 강제 상속 및 강제 재정의 모두 보여 줍니다. 기본 클래스 `shape` 변수를 정의 `acrossLine`합니다. 클래스 `circle` 및 `square` 에서 파생 `shape`합니다. 정의 상속 `acrossLine`, 함수를 정의 해야 하지만 `area` 계산 셰이프의 각 종류에 대 한 다르기 때문에 있습니다.  
  
 [!code-vb[VbVbalrKeywords#2](../../../visual-basic/language-reference/codesnippet/VisualBasic/mustinherit_1.vb)]  
  
 선언할 수 `shape1` 및 `shape2` 형식이 되도록 `shape`합니다. 그러나 개체를 만들 수 없습니다 `shape` 함수 기능이 없기 때문에 `area` 이며로 표시 되어 `MustInherit`합니다.  
  
 로 선언 되기 때문에 `shape`, 변수 `shape1` 및 `shape2` 파생된 클래스에서 개체에 제한 되어 `circle` 및 `square`합니다. Visual Basic 없도록 이러한 변수를 다른 개체를 할당할 수는 높은 수준의 형식 안전성을 제공 합니다.  
  
## <a name="usage"></a>사용법  
 `MustInherit` 한정자는이 컨텍스트에서 사용할 수 있습니다.  
  
 [Class 문](../../../visual-basic/language-reference/statements/class-statement.md)  
  
## <a name="see-also"></a>참고 항목  
 [Inherits 문](../../../visual-basic/language-reference/statements/inherits-statement.md)  
 [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md)  
 [키워드](../../../visual-basic/language-reference/keywords/index.md)  
 [상속 기본 사항](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
