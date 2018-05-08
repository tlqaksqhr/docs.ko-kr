---
title: New 연산자(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.new
- vb.NewConstraint
helpviewer_keywords:
- constraints, Visual Basic generic types
- generics [Visual Basic], constraints
- constraints, New keyword [Visual Basic]
- New constraint
- New keyword [Visual Basic]
ms.assetid: d7d566d7-fe0e-4336-91f7-641a542de4d0
ms.openlocfilehash: 0fe511b2c16681d7bab7eeda7c121fcbbaa2f5dd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="new-operator-visual-basic"></a>New 연산자(Visual Basic)
소개는 `New` 절을 새 개체 인스턴스를 만드는 형식 매개 변수에 생성자 제약 조건을 지정 하거나 식별 한 `Sub` 클래스 생성자와 프로시저입니다.  
  
## <a name="remarks"></a>설명  
 선언 또는 대입문에 `New` 절은 인스턴스를 만들 수 있는 정의 된 클래스를 지정 해야 합니다. 이 클래스에서 호출 코드에 액세스할 수 있는 하나 이상의 생성자를 노출 해야 한다는 것을 의미 합니다.  
  
 사용할 수는 `New` 선언 문 또는 대입문 절. 문이 실행 될 때 제공한 인수를 전달 하며, 지정된 된 클래스의 적절 한 생성자를 호출 합니다. 다음 예제에서는이의 인스턴스를 만들어 한 `Customer` 두 명의 생성자가 클래스, 매개 변수를 사용 하 고 다른 하나는 문자열 매개 변수를 사용 합니다.  
  
 [!code-vb[VbVbalrKeywords#11](../../../visual-basic/language-reference/codesnippet/VisualBasic/new-operator_1.vb)]  
  
 배열은 클래스, 이므로 `New` 다음 예제에 나와 있는 것 처럼 새 배열 인스턴스를 만들 수 있습니다.  
  
 [!code-vb[VbVbalrKeywords#12](../../../visual-basic/language-reference/codesnippet/VisualBasic/new-operator_2.vb)]  
  
 공용 언어 런타임 (CLR)를 throw 한 <xref:System.OutOfMemoryException> 메모리가 부족 한 새 인스턴스를 만드는 경우 오류가 발생 합니다.  
  
> [!NOTE]
>  `New` 키워드는 또한 형식 매개 변수 목록에 지정 된 형식 액세스 가능한 매개 변수가 없는 생성자를 노출 해야 합니다. 형식 매개 변수 및 제약 조건에 대 한 자세한 내용은 참조 [유형 목록](../../../visual-basic/language-reference/statements/type-list.md)합니다.  
  
 생성자를 클래스에 대 한 프로시저를 만들려면 설정의 이름을 `Sub` 프로시저에는 `New` 키워드입니다. 자세한 내용은 참조 [개체 수명: 개체가 만들어지고 소멸 되는 하는 방법을](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)합니다.  
  
 `New` 키워드는 다음 컨텍스트에서 사용할 수 있습니다.  
  
 [Dim 문](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Of](../../../visual-basic/language-reference/statements/of-clause.md)  
  
 [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.OutOfMemoryException>  
 [키워드](../../../visual-basic/language-reference/keywords/index.md)  
 [형식 목록](../../../visual-basic/language-reference/statements/type-list.md)  
 [Visual Basic의 제네릭 형식](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [개체 수명: 개체가 만들어지고 제거되는 방법](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
