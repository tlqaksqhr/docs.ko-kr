---
title: 형식 승격(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- declared elements [Visual Basic], scope
- visibility [Visual Basic], declared elements
- Partial keyword [Visual Basic], unexpected results with type promotion
- scope [Visual Basic], declared elements
- scope [Visual Basic], Visual Basic
- type promotion
- declared elements [Visual Basic], visibility
ms.assetid: 035eeb15-e4c5-4288-ab3c-6bd5d22f7051
ms.openlocfilehash: 104fa906fecc5a5bb8704fe3ab839f9f200cf73b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649427"
---
# <a name="type-promotion-visual-basic"></a>형식 승격(Visual Basic)
모듈에는 프로그래밍 요소를 선언 하면 Visual Basic 모듈을 포함 하는 네임 스페이스에 해당 범위를 승격 합니다. 로 알려져 *형식 승격*합니다.  
  
 다음 예제에서는 모듈의 기본 정 및 해당 모듈의 두 명의 멤버를 보여 줍니다.  
  
 [!code-vb[VbVbalrDeclaredElements#1](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_1.vb)]  
  
 내에서 `projModule`프로그래밍, 모듈 수준에서 선언 된 요소 수준이 올라간 `projNamespace`합니다. 앞의 예제에서 `basicEnum` 및 `innerClass` 승격 되 면 하지만 `numberSub` 모듈 수준에서 선언 되지 않았으므로 되지 않습니다.  
  
## <a name="effect-of-type-promotion"></a>형식 승격의 효과  
 형식 승격의 효과 모듈의 이름을 포함 하는 한정 문자열 필요 하지 않습니다. 다음 예제에서는 앞의 예제에서 프로시저에 두 개의 호출 합니다.  
  
 [!code-vb[VbVbalrDeclaredElements#2](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_2.vb)]  
  
 앞의 예제에서 첫 번째 호출 완전 한 한정 문자열을 사용합니다. 그러나이 필요한으로 인해 않습니다 형식 승격 합니다. 두 번째 호출 또한 액세스 모듈의 멤버를 포함 하지 않고 `projModule` 한정 문자열에 있습니다.  
  
## <a name="defeat-of-type-promotion"></a>형식 승격의 무효화  
 네임 스페이스 모듈 멤버와 동일한 이름 가진 멤버가 이미 있으면 형식 승격 해당 모듈 멤버에 대 한 타원를 통과 합니다. 다음 예제에서는 열거형과 동일한 네임 스페이스 내에서 모듈의 기본 정의 보여 줍니다.  
  
 [!code-vb[VbVbalrDeclaredElements#3](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_3.vb)]  
  
 위의 예제에서는 Visual Basic 클래스를 승격할 수 없습니다 `abc` 를 `thisNameSpace` 네임 스페이스 수준에서 동일한 이름 가진 열거형 이미 있기 때문에 있습니다. 에 액세스 하려면 `abcSub`, 정규화 문자열을 사용 해야 `thisNamespace.thisModule.abc.abcSub`합니다. 그러나 클래스 `xyz` 여전히 승격에 액세스할 수 있습니다 및 `xyzSub` 짧은 한정 문자열 `thisNamespace.xyz.xyzSub`합니다.  
  
### <a name="defeat-of-type-promotion-for-partial-types"></a>부분 형식에 대 한 형식 승격의 무효화  
 클래스 또는 모듈 내 구조를 사용 하는 경우는 [부분](../../../../visual-basic/language-reference/modifiers/partial.md) 키워드를 네임 스페이스에 같은 이름의 멤버가 여부 형식 승격 해당 클래스 또는 구조체에 대 한 자동으로 무효화 됩니다. 모듈의 다른 요소는 여전히 형식 승격에 적합 합니다.  
  
 **결과가 발생 합니다.** 부분 정의의 형식 승격의 무효화 예기치 않은 결과 뿐만 아니라 컴파일러 오류도 발생할 수 있습니다. 다음 예제에서는 그 중 하나는 모듈 내 클래스의 기본 부분 정의 보여 줍니다.  
  
 [!code-vb[VbVbalrDeclaredElements#4](../../../../visual-basic/programming-guide/language-features/declared-elements/codesnippet/VisualBasic/type-promotion_4.vb)]  
  
 앞의 예제에서 개발자의 두 개의 부분 정의 병합 하려면 컴파일러 예상 `sampleClass`합니다. 그러나 컴파일러 내 부분 정의 대 한 승격을 고려 하지 않습니다 `sampleModule`합니다. 결과적으로, 두 개의 개별 클래스를 컴파일하려고 시도 이라는 `sampleClass` 로 같지만 서로 다른 한정 경로입니다.  
  
 컴파일러는 정규화된 경로가 동일한 경우에만 부분 정의를 병합합니다.  
  
## <a name="recommendations"></a>권장 사항  
 다음 권장 사항을 바람직한 프로그래밍 관행을 나타냅니다.  
  
-   **고유 이름입니다.** 프로그래밍 요소 이름은 대 한 모든 권한의 사용 하는 경우 항상 이므로 고유 이름을 사용 하는 것이 좋습니다. 동일한 추가 한정 필요 이름과를 읽기 어려울 코드를 만들 수 있습니다. 사소한 오류와 예기치 않은 결과가 발생할 수도 있습니다.  
  
-   **전체 경로입니다.** 모듈 및 동일한 네임 스페이스의 다른 요소와 함께 작업 하는 항상 모든 프로그래밍 요소에 대 한 전체 경로 사용 하는 가장 안전한 방법이입니다. 형식 승격 모듈 멤버에 대 한 타원를 하는 경우 해당 멤버를 완벽 하 게 지정 하지 않으면 다른 프로그래밍 요소를 실수로 액세스할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [Module 문](../../../../visual-basic/language-reference/statements/module-statement.md)  
 [Namespace 문](../../../../visual-basic/language-reference/statements/namespace-statement.md)  
 [부분](../../../../visual-basic/language-reference/modifiers/partial.md)  
 [Visual Basic의 범위](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)  
 [방법: 변수의 범위 제어](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md)  
 [선언된 요소 참조](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
