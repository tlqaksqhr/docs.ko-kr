---
title: From 절(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryFrom
- vb.QueryFromIn
- vb.QueryFromLet
helpviewer_keywords:
- queries [Visual Basic], From
- From clause [Visual Basic]
- From statement [Visual Basic]
ms.assetid: 83e3665e-68a0-4540-a3a3-3d777a0f95d5
ms.openlocfilehash: 71573de48cc51c48291fc4b82a0628d2d0f96caa
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2018
ms.locfileid: "42932490"
---
# <a name="from-clause-visual-basic"></a>From 절(Visual Basic)
하나 이상의 범위 변수 및 쿼리 하는 컬렉션을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
From element [ As type ] In collection [ _ ]  
  [, element2 [ As type2 ] In collection2 [, ... ] ]  
```  
  
## <a name="parts"></a>요소  
  
|용어|정의|  
|---|---|  
|`element`|필수. A *범위 변수* 컬렉션의 요소를 반복 하는 데 사용 합니다. 범위 변수는의 각 멤버에 대 한 참조를 사용 하는 `collection` 쿼리를 반복 하는 대로 `collection`합니다. 열거 가능한 형식 이어야 합니다.|  
|`type`|선택 사항입니다. `element`의 형식입니다. 없으면 `type` 지정 된 형식의 `element` 에서 유추 됩니다 `collection`합니다.|  
|`collection`|필수. 컬렉션을 쿼리할 수를 가리킵니다. 열거 가능한 형식 이어야 합니다.|  
  
## <a name="remarks"></a>설명  
 `From` 절을 사용 하는 쿼리 및 소스 컬렉션에서 요소를 참조 하는 데 사용 되는 변수에 대 한 원본 데이터를 식별 합니다. 이러한 변수 라고 *범위 변수*합니다. `From` 절이 필요한 경우를 제외 하 고 쿼리를 위해는 `Aggregate` 절은 반환에만 결과 집계 쿼리를 식별 하는 데 있습니다. 자세한 내용은 [Aggregate 절](../../../visual-basic/language-reference/queries/aggregate-clause.md)합니다.  
  
 여러 개 지정할 수 있습니다 `From` 조인할 여러 컬렉션을 식별 하는 쿼리 절. 여러 컬렉션 지정 되 면 이러한 반복 하지 독립적으로 또는 관련 되어 조인할 수 있습니다. 사용 하 여 컬렉션을 암시적으로 연결할 수 있습니다 합니다 `Select` 절 또는 명시적으로 사용 하 여 합니다 `Join` 또는 `Group Join` 절. 대신 지정할 수 있습니다 여러 범위 변수 및 컬렉션을 단일에서 `From` 각 관련된 범위 변수와 다른에서 쉼표로 구분 된 컬렉션을 사용 하 여 절. 다음 코드 예제에는 두 구문 옵션을 보여 줍니다는 `From` 절.  
  
 [!code-vb[VbSimpleQuerySamples#21](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/from-clause_1.vb)]  
  
 합니다 `From` 범위의 비슷한 쿼리의 범위를 정의 하는 절을 `For` 루프입니다. 따라서 각 `element` 쿼리의 범위에 범위 변수는 고유한 이름이 있어야 합니다. 여러 개 지정할 수 있으므로 `From` 쿼리의 경우 후속 절 `From` 절에 범위 변수를 참조할 수는 `From` 하거나 절은 이전에 범위 변수를 참조할 수 `From` 절. 예를 들어, 다음 예제에서는 중첩 된 `From` 절 있는 두 번째 절에 있는 컬렉션은 속성을 기준으로 첫 번째 절의 범위 변수입니다.  
  
 [!code-vb[VbSimpleQuerySamples#22](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/from-clause_2.vb)]  
  
 각 `From` 절 쿼리를 구체화 하는 추가 쿼리 절 조합 올 수 있습니다. 다음과 같은 방법으로 쿼리를 구체화할 수 있습니다.  
  
-   여러 컬렉션을 사용 하 여 암시적으로 결합 합니다 `From` 및 `Select` 절 또는 명시적으로 사용 하 여 합니다 `Join` 또는 `Group Join` 절.  
  
-   사용 된 `Where` 절 쿼리 결과를 필터링 합니다.  
  
-   사용 하 여 결과 정렬 된 `Order By` 절.  
  
-   사용 하 여 비슷한 결과 함께 그룹화 된 `Group By` 절.  
  
-   사용 하 여는 `Aggregate` 절에 집계 함수는 전체 쿼리 결과 대 한 평가를 식별 합니다.  
  
-   사용 된 `Let` 절 값인 컬렉션 대신 식에 의해 결정 됩니다 하는 반복 변수를 도입 합니다.  
  
-   사용 하 여는 `Distinct` 절에 중복 되는 쿼리 결과 무시 합니다.  
  
-   사용 하 여 반환할 결과 부분을 식별 합니다 `Skip`, `Take`를 `Skip While`, 및 `Take While` 절.  
  
## <a name="example"></a>예  
 다음 쿼리 식에 사용을 `From` 범위 변수를 선언 하는 절 `cust` 각각에 대해 `Customer` 개체는 `customers` 컬렉션입니다. `Where` 절 범위 변수를 사용 하 여 지정된 된 지역에서 고객에 게 출력을 제한 합니다. `For Each` 루프는 쿼리 결과에서 각 고객의 회사 이름을 표시 합니다.  
  
 [!code-vb[VbSimpleQuerySamples#23](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/from-clause_3.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [쿼리](../../../visual-basic/language-reference/queries/index.md)  
 [Visual Basic의 LINQ 소개](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [For Each...Next 문](../../../visual-basic/language-reference/statements/for-each-next-statement.md)  
 [For...Next 문](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [Select 절](../../../visual-basic/language-reference/queries/select-clause.md)  
 [Where 절](../../../visual-basic/language-reference/queries/where-clause.md)  
 [Aggregate 절](../../../visual-basic/language-reference/queries/aggregate-clause.md)  
 [Distinct 절](../../../visual-basic/language-reference/queries/distinct-clause.md)  
 [Join 절](../../../visual-basic/language-reference/queries/join-clause.md)  
 [Group Join 절](../../../visual-basic/language-reference/queries/group-join-clause.md)  
 [Order By 절](../../../visual-basic/language-reference/queries/order-by-clause.md)  
 [Let 절](../../../visual-basic/language-reference/queries/let-clause.md)  
 [Skip 절](../../../visual-basic/language-reference/queries/skip-clause.md)  
 [Take 절](../../../visual-basic/language-reference/queries/take-clause.md)  
 [Skip While 절](../../../visual-basic/language-reference/queries/skip-while-clause.md)  
 [Take While 절](../../../visual-basic/language-reference/queries/take-while-clause.md)
