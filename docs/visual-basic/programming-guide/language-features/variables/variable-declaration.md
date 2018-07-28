---
title: Visual Basic의 변수 선언
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], declaring
- member variables [Visual Basic], declarations
- Dim statement [Visual Basic], variable declaration
- declaring variables [Visual Basic]
- variables [Visual Basic], scope
- variables [Visual Basic], data types
- data types [Visual Basic], variable declarations
- lifetime [Visual Basic], variables
- variables [Visual Basic], lifetime
- access levels [Visual Basic], variables
- scope [Visual Basic], declaration statements
- variables [Visual Basic], access level
- local variables [Visual Basic], declarations
- scope [Visual Basic], variables
ms.assetid: d8f10226-92b1-480f-9f53-df377b2d7e15
ms.openlocfilehash: 6890ddfd8b463cd731ab3d8f39565b50a31a1192
ms.sourcegitcommit: 869b5832b667915ac4a5dd8c86b1109ed26b6c08
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2018
ms.locfileid: "39332735"
---
# <a name="variable-declaration-in-visual-basic"></a>Visual Basic의 변수 선언
이름 및 특성을 지정 하려면 변수를 선언 하면 됩니다. 변수에 대 한 선언문이 합니다 [Dim 문](../../../../visual-basic/language-reference/statements/dim-statement.md)합니다. 해당 위치 및 내용을 변수의 특성을 결정 합니다.  
  
 변수 명명 규칙 및 고려 사항에 대 한 참조 [선언 요소 이름](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)합니다.  
  
## <a name="declaration-levels"></a>선언 수준  
  
### <a name="local-and-member-variables"></a>로컬 및 멤버 변수  
 A *지역 변수* 프로시저 내에서 선언 된 것입니다. A *멤버 변수* ; Visual Basic 형식의 멤버인 모듈 수준에서 해당 클래스, 구조체 또는 모듈의 내부 프로시저 내부가 아니라 클래스, 구조체 또는 모듈 내에서 선언 됩니다.  
  
### <a name="shared-and-instance-variables"></a>공유 및 인스턴스 변수  
 클래스 또는 구조체에서 멤버 변수의 범주 공유 되는 여부에 따라 달라 집니다. 으로 선언 된 경우는 [공유](../../../../visual-basic/language-reference/modifiers/shared.md) 키워드를 *공유 변수에*, 클래스 또는 구조체의 모든 인스턴스 간에 공유 단일 복사본에 있는 및 합니다.  
  
 그는 *인스턴스 변수*, 클래스 또는 구조체의 각 인스턴스에 대해 별도 복사본 만들어집니다. 인스턴스 변수 지정 복사가 클래스 또는 구조체는 만들어진 인스턴스의 수입니다. 다른 인스턴스의 클래스 또는 구조체의 인스턴스 변수 복사본이 무관 합니다.  
  
## <a name="declaring-data-type"></a>데이터 형식 선언  
 합니다 [으로](../../../../visual-basic/language-reference/statements/as-clause.md) 선언 문에 절을 사용 하면 데이터 형식 또는 변수를 선언 하는 개체 형식을 정의할 수 있습니다. 변수에 대 한 다음 형식 중 하나를 지정할 수 있습니다.  
  
-   등의 기본 데이터 형식 `Boolean`, `Long`, 또는 `Decimal`  
  
-   배열 또는 구조체와 같은 복합 데이터 형식  
  
-   개체 유형 또는 응용 프로그램 또는 다른 응용 프로그램에 정의 된 클래스  
  
-   A [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 클래스와 같이 <xref:System.Windows.Forms.Label> 또는 <xref:System.Windows.Forms.TextBox>  
  
-   인터페이스와 같은 입력 <xref:System.IComparable> 또는 <xref:System.IDisposable>  
  
 데이터 형식 반복할 필요 없이 하나의 문에서 여러 변수를 선언할 수 있습니다. 다음 문에서 변수 `i`, `j`, 및 `k` 형식으로 선언 된 `Integer`, `l` 하 고 `m` 으로 `Long`, 및 `x` 및 `y` 로`Single`:  
  
```  
Dim i, j, k As Integer  
' All three variables in the preceding statement are declared as Integer.  
Dim l, m As Long, x, y As Single  
' In the preceding statement, l and m are Long, x and y are Single.  
```  
  
 데이터 형식에 대 한 자세한 내용은 참조 하세요. [데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/index.md)합니다. 개체에 대 한 자세한 내용은 참조 하세요. [개체 및 클래스](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) 하 고 [구성 요소를 사용 하 여 프로그래밍](http://msdn.microsoft.com/library/d4d4fcb4-e0b8-46b3-b679-7ee0026eb9e3)합니다.  
  
## <a name="local-type-inference"></a>지역 형식 유추  
 *형식 유추* 없이 선언 된 지역 변수의 데이터 형식을 결정 하는 데 사용 되는 `As` 절. 컴파일러는 초기화 식의 형식에서 변수의 형식을 유추합니다. 이 옵션을 사용 하면 형식을 명시적으로 지정 하지 않고 변수를 선언할 수 있습니다. 다음 예제에서는 둘 다 `num1` 및 `num2` 정수로 강력 하 게 형식화 됩니다.  
  
 [!code-vb[VbVbalrTypeInference#1](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/variable-declaration_1.vb)]  
  
 지역 형식 유추를 사용 하려는 경우 `Option Infer` 으로 설정 되어 있어야 `On`합니다. 자세한 내용은 [지역 형식 유추](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) 및 [Option Infer 문](../../../../visual-basic/language-reference/statements/option-infer-statement.md)을 참조하세요.  
  
## <a name="characteristics-of-declared-variables"></a>선언 된 변수 특성  
 합니다 *수명* 변수의 기간 자신이 하는 동안 사용할 수 있습니다. 일반적으로 변수 (예: 프로시저 또는 클래스) 선언 하는 요소는 계속 존재으로 존재 합니다. 변수는 포함 하는 요소의 수명을 넘도록 기존 계속 하지 않아도, 선언에 특별히 무언가를 할 필요가 없습니다. 변수를 포함 하는 해당 요소 보다 더 오래 유지 하려면 필요한 경우 포함할 수 있습니다는 `Static` 나 `Shared` 키워드 해당 `Dim` 문. 자세한 내용은 [Visual Basic의 수명](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)합니다.  
  
 합니다 *범위* 변수의 이름을 한정 하지 않고 변수를 참조할 수 있는 모든 코드의 집합입니다. 변수의 범위는 선언 된 위치에서 결정 됩니다. 지정된 된 지역에 있는 코드의 이름을 정규화 하지 않고도 해당 영역에 정의 된 변수를 사용할 수 있습니다. 자세한 내용은 [Visual Basic의 범위](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)합니다.  
  
 변수의 *액세스 수준* 액세스할 수 있는 권한을 가진 코드의 범위입니다. 액세스 한정자에 의해 결정 되기 (같은 [공개](../../../../visual-basic/language-reference/modifiers/public.md) 또는 [개인](../../../../visual-basic/language-reference/modifiers/private.md))에서 사용 하는 `Dim` 문입니다. 자세한 내용은 [액세스 수준을 Visual Basic의](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: 새 변수 만들기](../../../../visual-basic/programming-guide/language-features/variables/how-to-create-a-new-variable.md)  
 [방법: 변수 값 저장 및 검색](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md)  
 [데이터 형식](../../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [보호됨](../../../../visual-basic/language-reference/modifiers/protected.md)  
 [Friend](../../../../visual-basic/language-reference/modifiers/friend.md)  
 [정적](../../../../visual-basic/language-reference/modifiers/static.md)  
 [선언 요소의 특징](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)  
 [지역 형식 유추](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Option Infer 문](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
