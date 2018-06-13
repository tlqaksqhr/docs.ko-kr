---
title: '방법: 두 개체가 동일한지 확인(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- testing [Visual Basic], objects
- objects [Visual Basic], comparing
- object variables [Visual Basic], determining identity
ms.assetid: 7829f817-0d1f-4749-a707-de0b95e0cf5c
ms.openlocfilehash: bbcac2fc51e57427b125ec2f5e68f017a60186d8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650100"
---
# <a name="how-to-determine-whether-two-objects-are-identical-visual-basic"></a>방법: 두 개체가 동일한지 확인(Visual Basic)
Visual Basic에서는 두 변수는 메모리의 동일한 클래스 인스턴스를 가리킬 경우에 두 개의 변수 참조를의 포인터가 동일한 경우, 즉, 같다고 간주 됩니다. 예를 들어 Windows Forms 응용 프로그램에서는 수 원하는 확인 하려면 비교를 위해 있는지 여부를 현재 인스턴스 (`Me`)와 같은 특정 인스턴스와 같은 `Form2`합니다.  
  
 Visual Basic 포인터를 비교 하려면 두 연산자를 제공 합니다. [Is 연산자](../../../../visual-basic/language-reference/operators/is-operator.md) 반환 `True` 개체가 동일 하면 및 [IsNot 연산자](../../../../visual-basic/language-reference/operators/isnot-operator.md) 반환 `True` 그렇지 않은 경우.  
  
## <a name="determining-if-two-objects-are-identical"></a>두 개체가 동일한 지 확인 합니다.  
  
#### <a name="to-determine-if-two-objects-are-identical"></a>두 개체가 동일한 지 확인 하려면  
  
1.  설정 된 `Boolean` 두 개체를 테스트 하는 식입니다.  
  
2.  테스트 식에서 사용 하 여는 `Is` 연산자 피연산자와 두 개의 개체와 사용 합니다.  
  
     `Is` 반환 `True` 는 개체가 동일한 클래스 인스턴스를 가리킬 경우.  
  
## <a name="determining-if-two-objects-are-not-identical"></a>두 개체가 동일 하지 않은지 확인 합니다.  
 두 개체가 동일 하 고 결합 하 좋지 않을 수 있습니다 하는 경우 작업을 수행 하려는 경우에 따라 `Not` 및 `Is`, 예를 들어 `If Not obj1 Is obj2`합니다. 이러한 경우에 사용할 수 있습니다는 `IsNot` 연산자입니다.  
  
#### <a name="to-determine-if-two-objects-are-not-identical"></a>두 개체가 동일한 지 확인 하려면  
  
1.  설정 된 `Boolean` 두 개체를 테스트 하는 식입니다.  
  
2.  테스트 식에서 사용 하 여는 `IsNot` 연산자 피연산자와 두 개의 개체와 사용 합니다.  
  
     `IsNot` 반환 `True` 개체가 동일한 클래스 인스턴스를 가리키지 않을 경우.  
  
## <a name="example"></a>예제  
 다음 예에서는 쌍을 테스트 `Object` 변수를 동일한 클래스 인스턴스를 가리키는지 확인 합니다.  
  
 [!code-vb[VbVbalrKeywords#14](../../../../visual-basic/language-reference/codesnippet/VisualBasic/how-to-determine-whether-two-objects-are-identical_1.vb)]  
  
 앞의 예제는 다음과 같은 출력을 표시 합니다.  
  
 `objA different from objB? True`  
  
 `objA identical to objC? True`  
  
## <a name="see-also"></a>참고 항목  
 [Object 데이터 형식](../../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [개체 변수](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [개체 변수 값](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)  
 [Is 연산자](../../../../visual-basic/language-reference/operators/is-operator.md)  
 [IsNot 연산자](../../../../visual-basic/language-reference/operators/isnot-operator.md)  
 [방법: 두 개체가 관련이 있는지 확인](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)  
 [Me, My, MyBase 및 MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
