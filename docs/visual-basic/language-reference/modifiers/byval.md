---
title: ByVal(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.ByVal
- ByVal
helpviewer_keywords:
- ByVal keyword [Visual Basic], contexts
- ByVal keyword [Visual Basic]
ms.assetid: 1eaf4e58-b305-4785-9e3d-e416b9c75598
ms.openlocfilehash: 076289ff303dce58f036d6c7cb1505b151da19f6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33602985"
---
# <a name="byval-visual-basic"></a>ByVal(Visual Basic)
호출된 된 프로시저 또는 속성 호출 코드의 기반이 되는 변수 값을 변경할 수 없는 방식으로 인수가 전달 되도록 지정 합니다.  
  
## <a name="remarks"></a>설명  
 `ByVal` 한정자는 다음 컨텍스트에서 사용할 수 있습니다.  
  
 [Declare 문](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Operator 문](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [Property 문](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="example"></a>예제  
 다음 예제에서는 `ByVal` 매개 변수는 참조 형식 인수를 가진 메커니즘을 전달 합니다. 예에서 인수는 `c1`, 클래스의 인스턴스 `Class1`합니다. `ByVal` 절차의 코드는 참조 인수를 내부 값을 변경 하는 것을 금지 `c1`, 액세스할 수 있는 필드와 속성을 보호 되지 않습니다 되지만 `c1`합니다.  
  
 [!code-vb[VbVbalrKeywords#10](../../../visual-basic/language-reference/codesnippet/VisualBasic/byval_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [키워드](../../../visual-basic/language-reference/keywords/index.md)  
 [값 또는 참조로 인수 전달](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-value-and-by-reference.md)
