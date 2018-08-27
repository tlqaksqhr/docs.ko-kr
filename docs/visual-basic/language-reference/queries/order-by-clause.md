---
title: Order By 절(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryOrderBy
- vb.QueryAscending
- vb.QueryDescending
helpviewer_keywords:
- queries [Visual Basic], Order By
- Order By clause [Visual Basic]
- Order By statement [Visual Basic]
ms.assetid: fa911282-6b81-44c7-acfa-46b5bb93df75
ms.openlocfilehash: d4abb5f0b75ae4069c1dbe695a5c810b1f7aa6e1
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2018
ms.locfileid: "42935489"
---
# <a name="order-by-clause-visual-basic"></a>Order By 절(Visual Basic)
쿼리 결과 대 한 정렬 순서를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Order By orderExp1 [ Ascending | Descending ] [, orderExp2 [...] ]  
```  
  
## <a name="parts"></a>요소  
 `orderExp1`  
 필수. 하나 이상의 필드는 현재 쿼리 결과에서 반환 된 값을 정렬 하는 방법을 식별 하는입니다. 필드 이름은 쉼표 (,)로 구분 되어야 합니다. 오름차순 또는 내림차순으로 사용 하 여 정렬 된 것으로 각 필드를 식별할 수 있습니다 합니다 `Ascending` 또는 `Descending` 키워드입니다. 없으면 `Ascending` 또는 `Descending` 키워드를 지정한 경우 기본 정렬 순서는 오름차순입니다. 정렬 순서 필드에는 우선 순위가 왼쪽에서 오른쪽으로 제공 됩니다.  
  
## <a name="remarks"></a>설명  
 사용할 수는 `Order By` 절을 쿼리의 결과 정렬 합니다. `Order By` 절 에서만 현재 범위에 대 한 범위 변수를 기반으로 결과 정렬할 수 있습니다. 예를 들어를 `Select` 절에서는 해당 범위에 대 한 새 반복 변수를 사용 하 여 쿼리 식에 새 범위를 제공 합니다. 범위 변수 앞에 정의 `Select` 쿼리의 절 뒤에 사용할 수 없는 `Select` 절. 따라서에서 사용할 수 없는 필드를 기준으로 결과 정렬 하려는 경우는 `Select` 두어야 절을 `Order By` 하기 전에 절은 `Select` 절. 하나의 쿼리 결과의 일부로 반환 되지 않습니다 필드로 정렬 하려는 경우이 작업을 수행 해야 하는 경우의 예입니다.  
  
 오름차순 또는 내림차순 키를 누른 채 필드의 구현에 의해 결정 됩니다는 <xref:System.IComparable> 필드의 데이터 형식에 대 한 인터페이스입니다. 데이터 형식을 구현 하지 않는 경우는 <xref:System.IComparable> 인터페이스, 정렬 순서는 무시 됩니다.  
  
## <a name="example"></a>예  
 다음 쿼리 식에 사용 된 `From` 범위 변수를 선언 하는 절 `book` 에 대 한를 `books` 컬렉션. `Order By` 절 오름차순 (기본값) 가격으로 쿼리 결과 정렬 합니다. 동일한 가격 책 제목 오름차순으로 정렬 됩니다. 합니다 `Select` 절을 선택 합니다 `Title` 및 `Price` 쿼리에서 반환 된 값으로 속성입니다.  
  
 [!code-vb[VbSimpleQuerySamples#24](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/order-by-clause_1.vb)]  
  
## <a name="example"></a>예  
 다음 쿼리 식에 사용 된 `Order By` 가격을 내림차순으로 쿼리 결과 정렬 하는 절. 동일한 가격 책 제목 오름차순으로 정렬 됩니다.  
  
 [!code-vb[VbSimpleQuerySamples#25](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/order-by-clause_2.vb)]  
  
## <a name="example"></a>예  
 다음 쿼리 식에 사용 된 `Select` 책 제목을 선택, 가격, 날짜, 게시 및 제작 하는 절. 다음 채웁니다 합니다 `Title`, `Price`, `PublishDate`, 및 `Author` 새 범위에 대 한 범위 변수 필드입니다. `Order By` 절 작성자 이름, 책 제목 및 가격에서 새 범위 변수를 정렬 합니다. 각 열 (오름차순) 기본 순서로 정렬 됩니다.  
  
 [!code-vb[VbSimpleQuerySamples#26](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/order-by-clause_3.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic의 LINQ 소개](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [쿼리](../../../visual-basic/language-reference/queries/index.md)  
 [Select 절](../../../visual-basic/language-reference/queries/select-clause.md)  
 [From 절](../../../visual-basic/language-reference/queries/from-clause.md)
