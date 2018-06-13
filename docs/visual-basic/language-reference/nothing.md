---
title: Nothing(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- Nothing
- vb.Nothing
helpviewer_keywords:
- Nothing keyword [Visual Basic]
- Nothing keyword [Visual Basic], syntax
ms.assetid: 06176e2d-bbf7-4a37-afaa-a86ad21ee99f
ms.openlocfilehash: fb1af7d748faac78b26177af453a0e858f9e97c3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603992"
---
# <a name="nothing-visual-basic"></a>Nothing(Visual Basic)
모든 데이터 형식의 기본 값을 나타냅니다. 기본값은 참조 형식에 대해는 `null` 참조 합니다. 값 형식에 대 한 기본값 값 형식이 nullable 인지에 따라 달라 집니다.  
  
> [!NOTE]
>  Nullable이 아닌 값 형식에 대 한 `Nothing` Visual Basic에서 다릅니다 `null` C#입니다. Visual basic에서는 null이 아닌 값 형식으로의 변수를 설정 하면 `Nothing`, 변수 선언된 된 형식에 대 한 기본 값으로 설정 됩니다. C#에서 nullable이 아닌 값 형식으로의 변수를 할당 하는 경우 `null`, 컴파일 타임 오류가 발생 합니다.  
  
## <a name="remarks"></a>설명  
 `Nothing` 데이터 형식의 기본 값을 나타냅니다. 기본값의 값 형식 또는 참조 형식의 변수 인지에 따라 달라 집니다.  
  
 변수는 *값 형식* 직접 해당 값을 포함 합니다. 값 형식에는 숫자 데이터 형식을 모두 포함 `Boolean`, `Char`, `Date`, 모든 구조 및 모든 열거 합니다. 변수는 *유형을 참조* 메모리에 개체의 인스턴스에 대 한 참조를 저장 합니다. 참조 형식 클래스, 배열, 대리자 및 문자열을 포함 합니다. 자세한 내용은 [Value Types and Reference Types](../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)을 참조하세요.  
  
 변수 값의 경우 입력의 동작 `Nothing` null 허용 데이터 형식의 변수 인지에 따라 다릅니다. Nullable 값 형식을 나타내는, 추가 된 `?` 형식 이름에는 한정자입니다. 할당 `Nothing` nullable 변수를 값으로 설정 `null`합니다. 자세한 내용 및 예제에 대 한 참조 [Nullable 값 형식](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)합니다.  
  
 변수가 null을 허용 하는 값 형식에 있으면 할당 `Nothing` 를 설정 하기 기본 값으로 선언된 된 형식에 대 한 합니다. 해당 형식 가변 멤버에 포함 된 경우 해당 기본값을 모두 설정 됩니다. 다음 예에서는 스칼라 형식에 대 한 방법을 보여 줍니다.  
  
 [!code-vb[VbVbalrKeywords#7](../../visual-basic/language-reference/codesnippet/VisualBasic/nothing_1.vb)]  
  
 할당 된 변수는 참조 형식의 경우 `Nothing` 변수를 설정는 `null` 변수의 형식의 참조 합니다. 로 설정 된 변수는 `null` 참조 개체와 연결 되어 있지 않습니다. 다음은 이에 대한 예입니다.  
  
 [!code-vb[VbVbalrKeywords#8](../../visual-basic/language-reference/codesnippet/VisualBasic/nothing_2.vb)]  
  
 변수는 참조 (또는 nullable 값 형식을) 여부를 확인할 때 `null`, 사용 하지 않는 `= Nothing` 또는 `<> Nothing`합니다. 항상 사용 하 여 `Is Nothing` 또는 `IsNot Nothing`합니다.  
  
 Visual Basic의 문자열에 대해 빈 문자열은 `Nothing`합니다. 따라서 `"" = Nothing` 그렇습니다.  
  
 다음 예제에서는 사용 하는 비교는 `Is` 및 `IsNot` 연산자입니다.  
  
 [!code-vb[VbVbalrKeywords#9](../../visual-basic/language-reference/codesnippet/VisualBasic/nothing_3.vb)]  
  
 사용 하지 않고 변수를 선언 하는 경우는 `As` 절이 속성을 설정 하 고 `Nothing`, 변수 형식이 `Object`합니다. 이 예제는 `Dim something = Nothing`합니다. 컴파일 타임 오류가 발생 하는 예에서 때 `Option Strict` 에 및 `Option Infer` 꺼져 있습니다.  
  
 할당 하면 `Nothing` 하는 개체 변수를 더 이상 참조 개체 인스턴스를 합니다. 이전 인스턴스로 참조 변수를 한 경우로 설정 `Nothing` 인스턴스 자체는 종료 되지 않습니다. 종료 되 고 인스턴스와 및 남은 활성 참조가 없는 가비지 수집기 (GC) 검색 한 후에 연결 된 메모리와 시스템 리소스가 해제 됩니다.  
  
 `Nothing` 와 다른는 <xref:System.DBNull> 초기화 되지 않은 변형 또는 존재 하지 않는 데이터베이스 열을 나타내는 개체입니다.  
  
## <a name="see-also"></a>참고 항목  
 [Dim 문](../../visual-basic/language-reference/statements/dim-statement.md)  
 [개체 수명: 개체가 만들어지고 제거되는 방법](../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)  
 [Visual Basic의 수명](../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)  
 [Is 연산자](../../visual-basic/language-reference/operators/is-operator.md)  
 [IsNot 연산자](../../visual-basic/language-reference/operators/isnot-operator.md)  
 [Nullable 값 형식](../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
