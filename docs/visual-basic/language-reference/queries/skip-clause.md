---
title: Skip 절(Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.QuerySkip
helpviewer_keywords:
- queries [Visual Basic], Skip
- Skip statement [Visual Basic]
- Skip clause [Visual Basic]
ms.assetid: f00eb172-3907-4c43-9745-d8546ab86234
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 508f3c094df4c834305bcb4a78223c1cee82b1c8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="skip-clause-visual-basic"></a>Skip 절(Visual Basic)
컬렉션에서 지정된 수의 요소를 무시하고 나머지 요소를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Skip count  
```  
  
## <a name="parts"></a>요소  
 `count`  
 필수 요소. 값 또는 건너뛸 시퀀스의 요소 수로 계산 되는 식입니다.  
  
## <a name="remarks"></a>설명  
 `Skip` 절로 인해 쿼리 결과 목록의 시작 부분에 있는 요소를 무시 하 고 나머지 요소를 반환 합니다. 건너뛸 요소 수로 식별 되는 `count` 매개 변수입니다.  
  
 사용할 수 있습니다는 `Skip` 절과 함께 `Take` 절 쿼리 세그먼트에서 데이터의 범위를 반환할 수 있습니다. 이 위해 전달 범위의 첫 번째 요소의 인덱스는 `Skip` 절과 범위의 크기는 `Take` 절.  
  
 사용 하는 경우는 `Skip` 쿼리에서 절을 할 수도 있습니다는 결과 수 있게 하는 순서로 반환 되도록 하는 `Skip` 절에서 의도 한 결과 무시 하도록 합니다. 쿼리 결과 정렬 하는 방법에 대 한 자세한 내용은 참조 [Order By 절](../../../visual-basic/language-reference/queries/order-by-clause.md)합니다.  
  
 사용할 수는 `SkipWhile` 절 제공된 조건에 따라 특정 요소에만 무시를 지정할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 `Skip` 절과 함께 `Take` 절을 페이지에 쿼리에서 데이터를에서 반환 합니다. `GetCustomers` 함수는 `Skip` 절 값을 사용 하 여 인덱스를 지정 된 시작 될 때까지 목록에서 고객을 무시 하는 `Take` 절 해당 인덱스 값에서 시작 하는 고객의 페이지를 반환 합니다.  
  
 [!code-vb[VbSimpleQuerySamples#1](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/skip-clause_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic의 LINQ 소개](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [쿼리](../../../visual-basic/language-reference/queries/queries.md)  
 [Select 절](../../../visual-basic/language-reference/queries/select-clause.md)  
 [From 절](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Order By 절](../../../visual-basic/language-reference/queries/order-by-clause.md)  
 [Skip While 절](../../../visual-basic/language-reference/queries/skip-while-clause.md)  
 [Take 절](../../../visual-basic/language-reference/queries/take-clause.md)
