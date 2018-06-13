---
title: IsNot 연산자(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.isnot
helpviewer_keywords:
- IsNot operator [Visual Basic]
ms.assetid: 8dd2bcdb-0166-48a2-9094-60dfb448f36c
ms.openlocfilehash: babee364d350ca84a8379f675acc4b5c87f98303
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603316"
---
# <a name="isnot-operator-visual-basic"></a>IsNot 연산자(Visual Basic)
두 개체 참조 변수를 비교합니다.  
  
## <a name="syntax"></a>구문  
  
```  
result = object1 IsNot object2  
```  
  
## <a name="parts"></a>요소  
 `result`  
 필수. `Boolean` 값입니다.  
  
 `object1`  
 필수. 모든 `Object` 변수 또는 식입니다.  
  
 `object2`  
 필수. 모든 `Object` 변수 또는 식입니다.  
  
## <a name="remarks"></a>설명  
 `IsNot` 연산자 두 개체 참조가 서로 다른 개체 참조 하는지 여부를 결정 합니다. 그러나 값 비교를 수행 하지 않습니다. 경우 `object1` 및 `object2` 정확히 동일한 개체 인스턴스를 둘 다 참조 `result` 은 `False`그렇지 않은 경우 `result` 은 `True`합니다.  
  
 `IsNot` 반대 되는 `Is` 연산자입니다. 이점은 `IsNot` 는 것을 피할 수 있는 복잡 한 구문이 `Not` 및 `Is`를 읽기 어려울 수 있습니다.  
  
 사용할 수는 `Is` 및 `IsNot` 모두 초기 바인딩 및 런타임에 바인딩된 개체를 테스트 하는 연산자입니다.  
  
> [!NOTE]
>  `IsNot` 식에서 반환 된 비교 연산자를 사용할 수 없습니다는 `TypeOf` 연산자입니다. 를 대신 사용 해야는 `Not` 및 `Is` 연산자입니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 모두를 사용 하는 `Is` 연산자 및 `IsNot` 연산자 동일한 비교를 수행 합니다.  
  
 [!code-vb[VbVbalrOperators#29](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/isnot-operator_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [Is 연산자](../../../visual-basic/language-reference/operators/is-operator.md)  
 [TypeOf 연산자](../../../visual-basic/language-reference/operators/typeof-operator.md)  
 [Visual Basic에서의 연산자 우선 순위](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [방법: 두 개체가 동일한지 테스트](../../../visual-basic/programming-guide/language-features/operators-and-expressions/how-to-test-whether-two-objects-are-the-same.md)
