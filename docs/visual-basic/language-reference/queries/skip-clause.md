---
title: Skip 절(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySkip
helpviewer_keywords:
- queries [Visual Basic], Skip
- Skip statement [Visual Basic]
- Skip clause [Visual Basic]
ms.assetid: f00eb172-3907-4c43-9745-d8546ab86234
ms.openlocfilehash: 615f98bf36d29c1f269d6866b1232ad33a5ae2f2
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/25/2018
ms.locfileid: "42925439"
---
# <a name="skip-clause-visual-basic"></a>Skip 절(Visual Basic)
컬렉션에서 지정된 수의 요소를 무시하고 나머지 요소를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Skip count  
```  
  
## <a name="parts"></a>요소  
 `count`  
 필수. 값 또는 표시 하지 않으려면 시퀀스의 요소 수가 계산 되는 식입니다.  
  
## <a name="remarks"></a>설명  
 `Skip` 절로 인해 쿼리 결과 목록 맨 앞에 요소를 무시 하 고 나머지 요소를 반환 합니다. 건너뛸 요소 수로 식별 되는 `count` 매개 변수입니다.  
  
 사용할 수는 `Skip` 절을 `Take` 쿼리의 모든 세그먼트에서 데이터의 범위를 반환 하는 절. 이 작업을 수행 하려면 범위의 첫 번째 요소의 인덱스를 전달 합니다 `Skip` 절과 범위의 크기를 `Take` 절.  
  
 사용 하는 경우는 `Skip` 쿼리에서 절 있습니다도 확인 해야 할 수 있도록 순서 대로 결과가 반환 되도록는 `Skip` 절에서 의도 한 결과 무시 하도록 합니다. 쿼리 결과 정렬 하는 방법에 대 한 자세한 내용은 참조 하세요. [Order By 절](../../../visual-basic/language-reference/queries/order-by-clause.md)합니다.  
  
 사용할 수는 `SkipWhile` 절을 제공 된 조건에 따라 특정 요소에만 무시 됩니다.  
  
## <a name="example"></a>예  
 다음 코드 예제에서는 합니다 `Skip` 절과 함께 `Take` 페이지의 쿼리에서 데이터를 반환 하는 절. `GetCustomers` 함수는 `Skip` 절까지을 건너뛰고 고객 목록에서 값을 사용 하 여 제공 된 시작 인덱스는 `Take` 절 해당 인덱스 값에서 시작 하는 고객의 페이지를 반환 합니다.  
  
 [!code-vb[VbSimpleQuerySamples#1](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/skip-clause_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic의 LINQ 소개](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [쿼리](../../../visual-basic/language-reference/queries/index.md)  
 [Select 절](../../../visual-basic/language-reference/queries/select-clause.md)  
 [From 절](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Order By 절](../../../visual-basic/language-reference/queries/order-by-clause.md)  
 [Skip While 절](../../../visual-basic/language-reference/queries/skip-while-clause.md)  
 [Take 절](../../../visual-basic/language-reference/queries/take-clause.md)
