---
title: Aggregate 절(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryAggregateIn
- vb.QueryAggregate
- vb.QueryAggregateInto
helpviewer_keywords:
- Aggregate clause [Visual Basic]
- Aggregate statement [Visual Basic]
- queries [Visual Basic], Aggregate
ms.assetid: 1315a814-5db6-4077-b34b-b141e11cc0eb
ms.openlocfilehash: 1db4b7fdcf9c8a38c2c49eca9d874eccea90ab1d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="aggregate-clause-visual-basic"></a>Aggregate 절(Visual Basic)
컬렉션에 하나 이상의 집계 함수를 적용 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Aggregate element [As type] In collection _  
  [, element2 [As type2] In collection2, [...]]  
  [ clause ]  
  Into expressionList  
```  
  
## <a name="parts"></a>요소  
  
|용어|정의|  
|---|---|  
|`element`|필수. 컬렉션의 요소를 반복 하는 데 사용 하는 변수입니다.|  
|`type`|선택 사항입니다. `element`의 형식입니다. 형식이 지정 되지 않은, 하는 경우의 형식 `element` 에서 유추 `collection`합니다.|  
|`collection`|필수. 작동 하도록 컬렉션을 나타냅니다.|  
|`clause`|선택 사항입니다. 하나 이상의 절을 같은 쿼리는 `Where` aggregate 절 또는 절을 적용 하 여 쿼리 결과를 구체화할 절.|  
|`expressionList`|필수. 하나 이상의 쉼표로 구분 된 식 컬렉션에 적용할 집계 함수를 식별 하는입니다. 쿼리 결과 대 한 멤버 이름을 지정 하는 집계 함수에 별칭을 적용할 수 있습니다. 별칭이 없는 제공 되는 경우 집계 함수의 이름이 사용 됩니다. 예제를 보려면이 항목의 뒷부분에 나오는 집계 함수에 대 한 섹션을 참조 합니다.|  
  
## <a name="remarks"></a>설명  
 `Aggregate` 쿼리에서 집계 함수를 포함 하도록 절을 사용할 수 있습니다. 집계 함수는 값의 집합에 대해 검사 및 계산을 수행 하 고 단일 값을 반환 합니다. 쿼리 결과 형식의 멤버를 사용 하 여 계산 된 값에 액세스할 수 있습니다. 사용할 수 있는 표준 집계 함수는는 `All`, `Any`, `Average`, `Count`, `LongCount`, `Max`, `Min`, 및 `Sum` 함수입니다. 이러한 함수는 SQL에서 집계에 익숙한 개발자에 게 익숙한입니다. 이 항목의 다음 섹션에서 설명 합니다.  
  
 집계 함수의 결과 쿼리 결과 형식의 필드와 쿼리 결과에 포함 됩니다. 집계 값을 보유 하는 쿼리 결과 형식의 멤버의 이름을 지정 하려면 집계 함수 결과 대 한 별칭을 제공할 수 있습니다. 별칭이 없는 제공 되는 경우 집계 함수의 이름이 사용 됩니다.  
  
 `Aggregate` 절 쿼리를 시작 하거나 추가 절로 쿼리에 포함할 수 있습니다. 경우는 `Aggregate` 절 쿼리를 시작, 결과 단일 값에 지정 된 집계 함수의 결과로 생성 되는 `Into` 절. 둘 이상의 집계 함수에 지정 된 경우는 `Into` 절 쿼리 결과에서 각 집계 함수를 참조 하는 별도 속성과 함께 단일 형식을 반환는 `Into` 절. 경우는 `Aggregate` 절이 쿼리에 추가 절로 포함로 쿼리 컬렉션에서 반환 되는 형식에는 결과에서 각 집계 함수를 참조 하는 별도 속성이 포함 된 `Into` 절.  
  
## <a name="aggregate-functions"></a>집계 함수  
 다음 목록은 함께 사용할 수 있는 표준 집계 함수는 `Aggregate` 절.  
  
|함수|설명|  
|---|---|  
|`All`|반환 `true` 컬렉션의 모든 요소가 지정된 된 조건이; 충족 하는 경우는 그렇지 않으면 반환 `false`합니다. 예를 들면 다음과 같습니다.<br /><br /> [!code-vb[VbSimpleQuerySamples#5](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_1.vb)]|  
|`Any`|반환 `true` ; 지정된 된 조건을 만족 하는 컬렉션의 요소가 같지 않으면 반환 `false`합니다. 예를 들면 다음과 같습니다.<br /><br /> [!code-vb[VbSimpleQuerySamples#6](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_2.vb)]|  
|`Average`|컬렉션 또는 컬렉션의 모든 요소에 대해 제공 하는 계산 식에 있는 모든 요소의 평균을 계산 합니다. 예를 들면 다음과 같습니다.<br /><br /> [!code-vb[VbSimpleQuerySamples#7](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_3.vb)]|  
|`Count`|컬렉션에 있는 요소의 수를 계산합니다. 선택적으로 제공할 수 `Boolean` 만 조건을 만족 하는 컬렉션에 있는 요소의 수를 계산 하는 식입니다. 예를 들면 다음과 같습니다.<br /><br /> [!code-vb[VbSimpleQuerySamples#8](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_4.vb)]|  
|`Group`|결과로 그룹화 된 쿼리 결과를 참조 한 `Group By` 또는 `Group Join` 절. `Group` 함수는 경우에 유효는 `Into` 절은 `Group By` 또는 `Group Join` 절. 자세한 내용 및 예제에 대 한 참조 [그룹 By 절](../../../visual-basic/language-reference/queries/group-by-clause.md) 및 [Group Join 절](../../../visual-basic/language-reference/queries/group-join-clause.md)합니다.|  
|`LongCount`|컬렉션에 있는 요소의 수를 계산합니다. 선택적으로 제공할 수 `Boolean` 만 조건을 만족 하는 컬렉션에 있는 요소의 수를 계산 하는 식입니다. 결과 `Long`합니다. 예를 들어 참조는 `Count` 집계 함수입니다.|  
|`Max`|컬렉션에서 최대값을 계산 하거나 컬렉션에서 모든 요소에 대해 제공된 된 식을 계산 합니다. 예를 들면 다음과 같습니다.<br /><br /> [!code-vb[VbSimpleQuerySamples#9](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_5.vb)]|  
|`Min`|컬렉션에서 최소 값을 계산 하거나 컬렉션에서 모든 요소에 대해 제공된 된 식을 계산 합니다. 예를 들면 다음과 같습니다.<br /><br /> [!code-vb[VbSimpleQuerySamples#10](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_6.vb)]|  
|`Sum`|컬렉션에 있는 모든 요소의 합계를 계산 하거나 컬렉션에서 모든 요소에 대해 제공된 된 식을 계산 합니다. 예를 들면 다음과 같습니다.<br /><br /> [!code-vb[VbSimpleQuerySamples#15](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_7.vb)]|  
  
## <a name="example"></a>예제  
 다음 코드 예제를 사용 하는 방법을 보여 줍니다는 `Aggregate` 쿼리 결과에 집계 함수를 적용 하는 절.  
  
 [!code-vb[VbSimpleQuerySamples#4](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_8.vb)]  
  
## <a name="creating-user-defined-aggregate-functions"></a>사용자 정의 집계 함수 만들기  
 확장 메서드를 추가 하 여 쿼리 식에서 사용자 지정 집계 함수를 포함할 수 있습니다는 <xref:System.Collections.Generic.IEnumerable%601> 유형입니다. 사용자 지정 메서드는 계산 또는 집계 함수에서 참조 하는 열거 가능한 컬렉션에서 작업을 수행할 수 있습니다. 확장 메서드에 대한 자세한 내용은 [확장 메서드](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)를 참조하세요.  
  
 예를 들어 다음 코드 예제에서는 숫자 컬렉션을의 중앙값을 계산 하는 사용자 정의 집계 함수를 보여 줍니다. 두 개의 오버 로드가 `Median` 확장 메서드. 첫 번째 오버 로드를 입력으로 받아들입니다, 형식의 컬렉션 `IEnumerable(Of Double)`합니다. 경우는 `Median` 형식의 쿼리 필드에 대 한 집계 함수가 호출 될 `Double`,이 메서드가 호출 됩니다. 두 번째 오버 로드는 `Median` 메서드는 모든 제네릭 형식을 전달할 수 있습니다. 제네릭 오버 로드는 `Median` 참조 하는 두 번째 매개 변수를 사용 하는 메서드는 `Func(Of T, Double)` (컬렉션)에서 형식에 대 한 값 형식의 해당 값으로 프로젝트에 람다 식을 `Double`합니다. 다음의 다른 오버 로드를 중앙값에 대 한 계산을 위임는 `Median` 메서드. 람다 식에 대한 자세한 내용은 [람다 식](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)을 참조하세요.  
  
 [!code-vb[VbSimpleQuerySamples#18](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_9.vb)]  
  
 다음 코드 예제에서는 간단한 쿼리를 호출 하는 `Median` 형식의 컬렉션에 대해 함수 집계 `Integer`, 및 형식의 컬렉션 `Double`합니다. 호출 하는 쿼리는 `Median` 형식의 컬렉션에 대해 함수 집계 `Double` 호출의 오버 로드는 `Median` 형식의 컬렉션을 입력으로 허용 하는 메서드 `Double`합니다. 호출 하는 쿼리는 `Median` 형식의 컬렉션에 대해 함수 집계 `Integer` 의 제네릭 오버 로드를 호출는 `Median` 메서드.  
  
 [!code-vb[VbSimpleQuerySamples#19](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_10.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic의 LINQ 소개](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [쿼리](../../../visual-basic/language-reference/queries/queries.md)  
 [Select 절](../../../visual-basic/language-reference/queries/select-clause.md)  
 [From 절](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Where 절](../../../visual-basic/language-reference/queries/where-clause.md)  
 [Group By 절](../../../visual-basic/language-reference/queries/group-by-clause.md)
