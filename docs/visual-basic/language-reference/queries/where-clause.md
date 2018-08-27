---
title: Where 절(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryWhere
helpviewer_keywords:
- Where statement [Visual Basic]
- queries [Visual Basic], Where
- Where clause [Visual Basic]
ms.assetid: 48b5c2c5-3181-429c-8545-894296798c89
ms.openlocfilehash: de7b4bf3e7dc1145b7e95197c7bd05c66acdabd6
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2018
ms.locfileid: "42934332"
---
# <a name="where-clause-visual-basic"></a>Where 절(Visual Basic)
쿼리에 대 한 필터링 조건을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Where condition  
```  
  
## <a name="parts"></a>요소  
 `condition`  
 필수. 컬렉션의 현재 항목에 대 한 값을 출력 컬렉션에 포함 되는지 여부를 결정 하는 식입니다. 식은 해야 합니다는 `Boolean` 값 또는 해당을 `Boolean` 값입니다. 조건이 평가 되는 경우 `True`요소가 고 그렇지 않으면 쿼리 결과에 포함 된, 쿼리 결과에서 요소 제외 됩니다.  
  
## <a name="remarks"></a>설명  
 `Where` 절 특정 조건을 충족 하는 요소만 선택 하 여 쿼리 데이터를 필터링 할 수 있습니다. 값이 해당 요소는 `Where` 절을 평가 하 `True` ; 쿼리 결과에 포함 된 다른 요소는 제외 됩니다. 에 사용 되는 식을 `Where` 절을 평가 해야 합니다는 `Boolean` 또는 해당 하는 `Boolean`, 등으로 계산 되는 정수 `False` 경우 해당 값은 0입니다. 여러 식을 결합할 수 있습니다는 `Where` 와 같은 논리 연산자를 사용 하 여 절 `And`, `Or`, `AndAlso`, `OrElse`를 `Is`, 및 `IsNot`합니다.  
  
 기본적으로 쿼리 식은 계산 되지 않습니다 액세스 될 때까지-예를 들어 있을 때 데이터 바인딩된 또는의 통해 반복을 `For` 루프입니다. 결과적으로 `Where` 절 쿼리 액세스 될 때까지 평가 되지 않습니다. 외부에서 사용 되는 쿼리에 값이 있는 경우는 `Where` 절에서 적절 한 값을 사용 합니다 `Where` 쿼리가 실행 될 시점에는 절. 쿼리 실행에 대 한 자세한 내용은 참조 하세요. [Your 첫 번째 LINQ 쿼리를 작성 하도록](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md)합니다.  
  
 내에서 함수를 호출할 수는 `Where` 컬렉션의 현재 요소에서 계산 또는 값에 대 한 작업을 수행 하는 절. 함수 호출을 `Where` 절이 정의 된 경우 대신 액세스할 때 즉시 실행 될 쿼리를 발생할 수 있습니다. 쿼리 실행에 대 한 자세한 내용은 참조 하세요. [Your 첫 번째 LINQ 쿼리를 작성 하도록](../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md)합니다.  
  
## <a name="example"></a>예  
 다음 쿼리 식에 사용을 `From` 범위 변수를 선언 하는 절 `cust` 각각에 대해 `Customer` 개체는 `customers` 컬렉션입니다. `Where` 절 범위 변수를 사용 하 여 지정된 된 지역에서 고객에 게 출력을 제한 합니다. `For Each` 루프는 쿼리 결과에서 각 고객의 회사 이름을 표시 합니다.  
  
 [!code-vb[VbSimpleQuerySamples#23](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/where-clause_1.vb)]  
  
## <a name="example"></a>예  
 다음 예제에서는 `And` 하 고 `Or` 의 논리 연산자는 `Where` 절.  
  
 [!code-vb[VbSimpleQuerySamples#31](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/where-clause_2.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic의 LINQ 소개](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [쿼리](../../../visual-basic/language-reference/queries/index.md)  
 [From 절](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Select 절](../../../visual-basic/language-reference/queries/select-clause.md)  
 [For Each...Next 문](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
