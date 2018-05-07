---
title: Take 절(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryTake
helpviewer_keywords:
- Take statement [Visual Basic]
- queries [Visual Basic], Take
- Take clause [Visual Basic]
ms.assetid: 77bf87b2-1476-4456-957f-fee922fbad8c
ms.openlocfilehash: 0dddb411af1b4ee269e091c07553a94589d90b2c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="take-clause-visual-basic"></a>Take 절(Visual Basic)
컬렉션의 시작 위치에서 지정된 수의 연속 요소를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Take count  
```  
  
## <a name="parts"></a>요소  
 `count`  
 필수. 값 또는 반환 되는 시퀀스의 요소 수로 계산 되는 식입니다.  
  
## <a name="remarks"></a>설명  
 `Take` 절로 인해 쿼리를 지정 된 수의 결과 목록에는의 시작 부분부터 연속 요소를 포함 합니다. 요소를 포함 하도록 수가 붙습니다는 `count` 매개 변수입니다.  
  
 사용할 수 있습니다는 `Take` 절과 함께 `Skip` 절 쿼리 세그먼트에서 데이터의 범위를 반환할 수 있습니다. 이 위해 전달 범위의 첫 번째 요소의 인덱스는 `Skip` 절과 범위의 크기는 `Take` 절. 이 경우에 `Take` 뒤에 절을 지정 해야 합니다는 `Skip` 절.  
  
 사용 하는 경우는 `Take` 쿼리에서 절을 할 수도 있습니다는 결과 수 있게 하는 순서로 반환 되도록 하는 `Take` 절에서 의도 한 결과 포함 하도록 합니다. 쿼리 결과 정렬 하는 방법에 대 한 자세한 내용은 참조 [Order By 절](../../../visual-basic/language-reference/queries/order-by-clause.md)합니다.  
  
 사용할 수는 `TakeWhile` 절 제공된 조건에 따라 특정 요소에만 반환 되도록 지정할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 `Take` 절과 함께 `Skip` 절을 페이지에 쿼리에서 데이터를에서 반환 합니다. GetCustomers 사용 하 여 함수는 `Skip` 절 값을 사용 하 여 인덱스를 지정 된 시작 될 때까지 목록에서 고객을 무시 하는 `Take` 절 해당 인덱스 값에서 시작 하는 고객의 페이지를 반환 합니다.  
  
 [!code-vb[VbSimpleQuerySamples#1](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/take-clause_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic의 LINQ 소개](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [쿼리](../../../visual-basic/language-reference/queries/queries.md)  
 [Select 절](../../../visual-basic/language-reference/queries/select-clause.md)  
 [From 절](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Order By 절](../../../visual-basic/language-reference/queries/order-by-clause.md)  
 [Take While 절](../../../visual-basic/language-reference/queries/take-while-clause.md)  
 [Skip 절](../../../visual-basic/language-reference/queries/skip-clause.md)
