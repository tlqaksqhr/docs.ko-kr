---
title: 숨기기와 재정의의 차이점(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- shadowing, vs. overriding
- overriding, vs. shadowing
ms.assetid: 2d014a0b-7630-407d-8f4e-24bd87987923
ms.openlocfilehash: 94ce3e7fe25b7942730e6e89a53654b03d91c42b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="differences-between-shadowing-and-overriding-visual-basic"></a>숨기기와 재정의의 차이점(Visual Basic)
기본 클래스에서 상속 되는 클래스를 정의할 때 파생된 클래스에서 기본 클래스 요소 중 하나 이상을 재정의 수도 있습니다. 숨기기와 재정의이 목적을 위해 둘 다 사용할 수는 있습니다.  
  
## <a name="comparison"></a>비교  
 숨기기와 재정의 모두 사용 하는 파생된 클래스는 기본 클래스에서 상속 하 고 다른 한 선언 된 요소를 다시 정의 둘 다 합니다. 하지만 두 가지 중요 한 차이점이 있습니다.  
  
 다음 표에서 비교 숨김과 재정의 합니다.  
  
||||  
|---|---|---|  
|비교 지점|섀도잉|재정의|  
|용도|파생된 클래스에서 이미 정의 된 멤버를 소개 하는 이후에 기본 클래스 수정 으로부터 보호|다른 프로시저 또는 같은 호출 시퀀스를 사용 하 여 속성을 구현 하 여 다형성을 함<sup>1</sup>|  
|재정의 되는 요소|선언 된 요소 형식|프로시저만 (`Function`, `Sub`, 또는 `Operator`) 또는 속성|  
|재정의 요소|선언 된 요소 형식|프로시저 또는 같은 호출 시퀀스를 사용 하 여 속성<sup>1</sup>|  
|재정의 요소 액세스 수준|모든 액세스 수준|재정의 된 요소 형식의 액세스 수준을 변경할 수 없습니다.|  
|읽기 및 쓰기 가능성 재정의 요소|모든 조합|또는 쓰기 재정의 된 속성의 가능성을 변경할 수 없습니다.|  
|재정의 통해 제어|기본 클래스 요소 적용 또는 섀도잉 금지 수 없음|기본 클래스 요소를 지정할 수 `MustOverride`, `NotOverridable`, 또는 `Overridable`|  
|키워드 사용|`Shadows` 파생된 클래스에서 권장 `Shadows` 두 가정 `Shadows` 나 `Overrides` 지정<sup>2</sup>|`Overridable` 또는 `MustOverride` 기본 클래스;에 필요한 `Overrides` 파생된 클래스에서 필요한|  
|파생된 클래스에서 파생 된 클래스에서 재정의 되는 요소 상속|에 의해 상속 요소 숨김 추가로 파생 되는 클래스입니다. 숨겨진된 요소는 여전히 숨겨져<sup>3</sup>|상속 된 요소를 재정의 추가로 파생 되는 클래스입니다. 재정의 된 요소는 여전히 재정의|  
  
 <sup>1</sup> 는 *호출 시퀀스* 요소 형식으로 이루어져 (`Function`, `Sub`, `Operator`, 또는 `Property`), 이름, 매개 변수 목록 및 반환 형식입니다. 속성 또는 그 반대로 사용 하 여 프로시저를 재정의할 수 없습니다. 한 종류의 프로시저를 재정의할 수 없습니다 (`Function`, `Sub`, 또는 `Operator`)를 다른 종류입니다.  
  
 <sup>2</sup> 지정 하지 않으면 `Shadows` 또는 `Overrides`, 컴파일러를 사용 하려는 재정의 유형을 확인할 수 있도록 경고 메시지가 발생 합니다. 경고를 무시 하는 경우에 숨김 메커니즘 사용 됩니다.  
  
 <sup>3</sup> 숨기는 요소는 추가 파생된 클래스에서 액세스할 수 없는 경우 숨김은 상속 되지 않습니다. 예를 들어, 숨기는 요소를 선언 하는 경우 `Private`, 파생된 클래스에서 파생 되는 클래스는 섀도잉 요소 대신 원래 요소를 상속 합니다.  
  
## <a name="guidelines"></a>지침  
 일반적으로 다음과 같은 경우에 재정의 사용 합니다.  
  
-   다형 파생된 클래스에 정의 됩니다.  
  
-   동일한 요소 형식과 호출 시퀀스를 적용 하는 컴파일러의 안전성 사용 하는 것이 좋습니다.  
  
 일반적으로 다음과 같은 경우에 그림자를 사용 합니다.  
  
-   기본 클래스에 수정 될 수 있으며 사용자 작업과 동일한 이름을 사용 하는 요소를 정의 예상 합니다.  
  
-   요소 형식 변경 또는 호출 시퀀스의 자유롭게 사용 하는 것이 좋습니다.  
  
## <a name="see-also"></a>참고 항목  
 [선언된 요소 참조](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [Visual Basic의 숨김 기능](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)  
 [방법: 이름이 같은 변수 숨기기](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)  
 [방법: 상속된 변수 숨기기](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)  
 [방법: 파생 클래스에 의해 숨겨진 변수에 액세스](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)  
 [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)  
 [재정의](../../../../visual-basic/language-reference/modifiers/overrides.md)
