---
title: TryCast 연산자(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.trycast
- trycast
helpviewer_keywords:
- TryCast keyword [Visual Basic]
ms.assetid: d1ef5d47-fef4-491e-b014-1d910628f65c
ms.openlocfilehash: d8825b8eee35ea514d4001a6a5c1cc5139c67454
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="trycast-operator-visual-basic"></a>TryCast 연산자(Visual Basic)
예외를 throw 하지 않는 형식 변환 작업을 소개 합니다.  
  
## <a name="remarks"></a>설명  
 변환에 실패 하면 `CType` 및 `DirectCast` throw 둘 다는 <xref:System.InvalidCastException> 오류입니다. 응용 프로그램의 성능이 저하 될 수 있습니다. `TryCast` 반환 [Nothing](../../../visual-basic/language-reference/nothing.md)가능한 예외를 처리 하는 대신 테스트 하기만 하면 반환된 된 결과 대해 되도록 `Nothing`합니다.  
  
 사용 된 `TryCast` 키워드 사용 하면 동일한 방식으로 [CType 함수](../../../visual-basic/language-reference/functions/ctype-function.md) 및 [DirectCast 연산자](../../../visual-basic/language-reference/operators/directcast-operator.md) 키워드입니다. 식을 첫 번째 인수 및 두 번째 인수로 변환 하는 형식으로 제공 합니다. `TryCast` 클래스 및 인터페이스와 같은 참조 형식 에서만 작동합니다. 두 형식 간의 상속 또는 구현 관계가 필요합니다. 즉, 한 형식에서 상속 하거나, 다른 구현 해야 합니다.  
  
## <a name="errors-and-failures"></a>오류 및 실패  
 `TryCast` 상속 또는 구현 관계 없는 있는지 검색 하는 경우 컴파일러 오류를 생성 합니다. 하지만 컴파일러 오류가 없다고 성공적인 변환을 보장 하지 않습니다. 원하는 변환이 축소 하는 경우 런타임 시 실패할 수 있습니다. 이 경우 `TryCast` 반환 [Nothing](../../../visual-basic/language-reference/nothing.md)합니다.  
  
## <a name="conversion-keywords"></a>변환 키워드  
 형식 변환 키워드의 비교는 다음과 같습니다.  
  
|키워드|데이터 형식|인수가 관계|런타임 오류|  
|---|---|---|---|  
|[CType 함수](../../../visual-basic/language-reference/functions/ctype-function.md)|모든 데이터 형식|두 데이터 형식 간에 확대 또는 축소 변환을 정의 해야 합니다.|Throw <xref:System.InvalidCastException>|  
|[DirectCast 연산자](../../../visual-basic/language-reference/operators/directcast-operator.md)|모든 데이터 형식|한 형식에서 상속 하거나 다른 형식을 구현 해야|Throw <xref:System.InvalidCastException>|  
|`TryCast`|참조 형식에만|한 형식에서 상속 하거나 다른 형식을 구현 해야|반환 [Nothing](../../../visual-basic/language-reference/nothing.md)|  
  
## <a name="example"></a>예제  
 다음 예제에서는 `TryCast`을 사용하는 방법을 보여 줍니다.  
  
 [!code-vb[VbVbalrKeywords#6](../../../visual-basic/language-reference/codesnippet/VisualBasic/trycast-operator_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [확대 변환과 축소 변환](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [암시적 변환과 명시적 변환](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
