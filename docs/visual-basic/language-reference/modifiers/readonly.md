---
title: ReadOnly(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ReadOnly
helpviewer_keywords:
- ReadOnly keyword [Visual Basic]
- variables [Visual Basic], read-only
- ReadOnly property
- properties [Visual Basic], read-only
- read-only variables
ms.assetid: e868185d-6142-4359-a2fd-a7965cadfce8
ms.openlocfilehash: e2957bf49292dfcafab8e78f4b997247c34ad279
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="readonly-visual-basic"></a>ReadOnly(Visual Basic)
변수 또는 속성 읽을 수 있지만 기록 되지를 지정 합니다.  
  
## <a name="remarks"></a>설명  
  
## <a name="rules"></a>규칙  
  
-   **선언 컨텍스트입니다.** `ReadOnly`는 모듈 수준에서만 사용할 수 있습니다. 즉, 선언 컨텍스트는 `ReadOnly` 요소 클래스, 구조체 또는 모듈 이어야 하며 원본 파일, 네임 스페이스 또는 프로시저일 수 없습니다.  
  
-   **결합 된 한정자입니다.** 지정할 수 없으며 `ReadOnly` 와 함께 `Static` 같은 선언에 있습니다.  
  
-   **값을 할당 합니다.** 사용 하는 코드는 `ReadOnly` 속성의 값을 설정할 수 없습니다. 하지만 기본 저장소에 액세스할 수 있는 코드를 할당 하거나 언제 든 지 값을 변경할 수 있습니다.  
  
     값을 할당할 수는 `ReadOnly` 변수 선언 또는 정의 된 구조체 또는 클래스의 생성자입니다.  
  
## <a name="when-to-use-a-readonly-variable"></a>읽기 전용 변수를 사용 하는 경우  
 경우에 사용할 수 없습니다는 [Const 문을](../../../visual-basic/language-reference/statements/const-statement.md) 선언 하 고 상수 값을 할당 합니다. 예를 들어는 `Const` 문을 할당 하려면 원하는 데이터 형식을 허용 되지 않거나를 상수 식으로 컴파일 타임에 값을 계산 하는 일을 할 수 있습니다. 하지 컴파일 타임에 값을도 알고 수 있습니다. 이러한 경우에 사용할 수 있습니다는 `ReadOnly` 상수 값을 보유할 변수로 대체 합니다.  
  
> [!IMPORTANT]
>  변수 자체는 경우에 해당 멤버를 변경할 수는 변수의 데이터 형식을 배열 또는 클래스 인스턴스를 같은 참조 형식이 면 `ReadOnly`합니다. 다음은 이에 대한 예입니다.  
  
 `ReadOnly characterArray() As Char = {"x"c, "y"c, "z"c}`  
  
 `Sub changeArrayElement()`  
  
 `characterArray(1) = "M"c`  
  
 `End Sub`  
  
 를 초기화할 때 배열을 가리키는 `characterArray()` "x", "y" 및 "z"입니다. 때문에 변수 `characterArray` 은 `ReadOnly`, 초기화 된 후; 되 해당 값을 변경할 수 없습니다, 새 배열을 할당할 수 없습니다. 그러나 하나 이상의 배열 멤버의 값을 변경할 수 있습니다. 프로시저를 호출한 다음 `changeArrayElement`를 가리키는 배열 `characterArray()` "x", "M" 및 "z"입니다.  
  
 이 프로시저 매개 변수를 선언 하는 비슷한 [ByVal](../../../visual-basic/language-reference/modifiers/byval.md), 하면 프로시저가 호출 인수 자체를 변경할 수는 있지만 해당 멤버를 변경할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 정의 `ReadOnly` 직원이 고용 된 날짜에 대 한 속성. 속성 값을 내부적으로 클래스 저장소는 `Private` 클래스의 내부 변수와 유일한 코드는 해당 값을 변경할 수 있습니다. 그러나 속성은 `Public`, 클래스에 액세스할 수 있는 모든 코드는 속성을 읽을 수 있습니다.  
  
 [!code-vb[VbVbalrKeywords#4](../../../visual-basic/language-reference/codesnippet/VisualBasic/readonly_1.vb)]  
  
 `ReadOnly` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.  
  
 [Dim 문](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Property 문](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a>참고 항목  
 [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md)  
 [키워드](../../../visual-basic/language-reference/keywords/index.md)
