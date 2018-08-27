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
ms.openlocfilehash: bfaccf470d93a6a72451e7ad8b41e8dbb1171c71
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2018
ms.locfileid: "42932472"
---
# <a name="take-clause-visual-basic"></a>Take 절(Visual Basic)
컬렉션의 시작 위치에서 지정된 수의 연속 요소를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Take count  
```  
  
## <a name="parts"></a>요소  
 `count`  
 필수. 값 또는 반환 된 시퀀스의 요소 수가 계산 되는 식입니다.  
  
## <a name="remarks"></a>설명  
 `Take` 절로 인해 지정 된 수의 결과 목록 시작 지점에서 연속 요소를 포함 하도록 쿼리 합니다. 지정 된 요소를 포함할 수는 `count` 매개 변수입니다.  
  
 사용할 수는 `Take` 절을 `Skip` 쿼리의 모든 세그먼트에서 데이터의 범위를 반환 하는 절. 이 작업을 수행 하려면 범위의 첫 번째 요소의 인덱스를 전달 합니다 `Skip` 절과 범위의 크기를 `Take` 절. 이 경우에 `Take` 후 절을 지정 해야 합니다 `Skip` 절.  
  
 사용 하는 경우는 `Take` 쿼리에서 절 있습니다도 확인 해야 할 수 있도록 순서 대로 결과가 반환 되도록는 `Take` 의도 한 결과 포함 하는 절. 쿼리 결과 정렬 하는 방법에 대 한 자세한 내용은 참조 하세요. [Order By 절](../../../visual-basic/language-reference/queries/order-by-clause.md)합니다.  
  
 사용할 수는 `TakeWhile` 절 제공 된 조건에 따라 특정 요소에만 반환 되도록 지정할 수 있습니다.  
  
## <a name="example"></a>예  
 다음 코드 예제에서는 합니다 `Take` 절과 함께 `Skip` 페이지의 쿼리에서 데이터를 반환 하는 절. GetCustomers 함수 사용을 `Skip` 절까지을 건너뛰고 고객 목록에서 값을 사용 하 여 제공 된 시작 인덱스는 `Take` 절 해당 인덱스 값에서 시작 하는 고객의 페이지를 반환 합니다.  
  
 [!code-vb[VbSimpleQuerySamples#1](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/take-clause_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic의 LINQ 소개](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [쿼리](../../../visual-basic/language-reference/queries/index.md)  
 [Select 절](../../../visual-basic/language-reference/queries/select-clause.md)  
 [From 절](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Order By 절](../../../visual-basic/language-reference/queries/order-by-clause.md)  
 [Take While 절](../../../visual-basic/language-reference/queries/take-while-clause.md)  
 [Skip 절](../../../visual-basic/language-reference/queries/skip-clause.md)
