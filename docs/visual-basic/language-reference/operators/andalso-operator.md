---
title: AndAlso 연산자(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.AndAlso
- AndAlso
helpviewer_keywords:
- short-circuiting
- AndAlso operator [Visual Basic]
- operators [Visual Basic], short-circuiting
- operators [Visual Basic], conjunction
- short-circuit evaluation
ms.assetid: bbc15191-b374-495b-9b8f-7b8c2f4388eb
ms.openlocfilehash: 549d14cc35d285ac2e4a02a37dd201cc669c5627
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="andalso-operator-visual-basic"></a>AndAlso 연산자(Visual Basic)
두 식에 논리 결합을 단락 (short-circuiting)를 수행 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
result = expression1 AndAlso expression2  
```  
  
## <a name="parts"></a>요소  
  
|용어|정의|  
|---|---|  
|`result`|필수. 임의의 `Boolean` 식입니다. 결과는 `Boolean` 두 식의 비교의 결과입니다.|  
|`expression1`|필수. 임의의 `Boolean` 식입니다.|  
|`expression2`|필수. 임의의 `Boolean` 식입니다.|  
  
## <a name="remarks"></a>설명  
 하나의 논리 연산자를 라고 *단락 (short-circuiting)* 컴파일된 코드는 다른 식의 결과 따라 각 식의 평가 건너뛸 수 있는 경우. 작업의 최종 결과 결정 하는 평가 되는 첫 번째 식의 결과가 두 번째 식을 계산할 필요가 없습니다 때문에 최종 결과 변경할 수 없습니다. 단락 (short-circuiting) 건너뛸 식이 복잡 하거나 프로시저 호출이 포함 된 경우 성능을 향상 시킬 수 있습니다.  
  
 두 식이 모두 `True`, `result` 은 `True`합니다. 다음 표에서 설명 방법을 `result` 결정 됩니다.  
  
|경우 `expression1` 은|및 `expression2` 은|값 `result` 은|  
|---|---|---|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|(계산 되지 않음)|`False`|  
  
## <a name="data-types"></a>데이터 형식  
 `AndAlso` 연산자에 대해서만 정의 되는 [Boolean 데이터 형식](../../../visual-basic/language-reference/data-types/boolean-data-type.md)합니다. Visual Basic로 필요에 따라 각 피연산자를 변환 `Boolean` 에서 모든 작업을 수행 하 고 `Boolean`합니다. Visual Basic에서 변환 하는 숫자 형식으로 결과 할당 하는 경우 `Boolean` 해당 형식으로. 이 예기치 않은 동작이 발생할 수 있습니다. 예를 들어 `5 AndAlso 12` 으로 인해 `–1` 변환할 때 `Integer`합니다.  
  
## <a name="overloading"></a>오버로딩  
 [및 연산자](../../../visual-basic/language-reference/operators/and-operator.md) 및 [IsFalse 연산자](../../../visual-basic/language-reference/operators/isfalse-operator.md) 수 *오버 로드 된*, 클래스 또는 구조체 수 할 해당 명령의 동작은 피연산자의 형식이 있을 때 클래스 또는 구조입니다. 오버 로드는 `And` 및 `IsFalse` 연산자의 동작에 영향을 줍니다는 `AndAlso` 연산자입니다. 코드에서 `AndAlso` 클래스 또는 구조체에 오버 로드에서 `And` 및 `IsFalse`, 다시 정의 된 동작을 이해 해야 합니다. 자세한 내용은 참조 [연산자 프로시저](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `AndAlso` 두 식에 논리 결합을 수행 하는 연산자입니다. 결과는 `Boolean` 전체 식이 있는지 여부를 나타내는 값이 true입니다. 첫 번째 식이 `False`, 두 번째는 평가 되지 않습니다.  
  
 [!code-vb[VbVbalrOperators#24](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/andalso-operator_1.vb)]  
  
 앞 예제의 결과는 `True`, `False`, 및 `False`각각. 계산에 `secondCheck`, 첫 번째는 이미 때문에 두 번째 식을 계산 하지는 `False`합니다. 계산의 두 번째 식이 계산 되는 반면 `thirdCheck`합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 한 `Function` 배열 요소 사이 지정된 된 값을 검색 하는 프로시저입니다. 배열이 비어 또는 배열 길이 초과 된 경우는 `While` 문은 검색 값에 대해 배열 요소를 테스트 하지 않습니다.  
  
 [!code-vb[VbVbalrOperators#25](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/andalso-operator_2.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [논리/비트 연산자 (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)  
 [Visual Basic에서의 연산자 우선 순위](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [기능별 연산자 목록](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [And 연산자](../../../visual-basic/language-reference/operators/and-operator.md)  
 [IsFalse 연산자](../../../visual-basic/language-reference/operators/isfalse-operator.md)  
 [Visual Basic의 논리 및 비트 연산자](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
