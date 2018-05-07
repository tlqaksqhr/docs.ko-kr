---
title: Select 절(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QuerySelect
helpviewer_keywords:
- Select statement [Visual Basic]
- Select clause [Visual Basic]
- queries [Visual Basic], Select
ms.assetid: 27a3f61c-5960-4692-9b91-4d0c4b6178fe
ms.openlocfilehash: 55c1e79b9e8e26483c1b7374a755bf977129169b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="select-clause-visual-basic"></a>Select 절(Visual Basic)
쿼리의 결과 정의합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Select [ var1 = ] fieldName1 [, [ var2 = ] fieldName2 [...] ]  
```  
  
## <a name="parts"></a>요소  
 `var1`  
 선택 사항입니다. 열 식의 결과 참조 하는 데 사용할 수 있는 별칭입니다.  
  
 `fieldName1`  
 필수. 쿼리 결과에 반환할 필드의 이름입니다.  
  
## <a name="remarks"></a>설명  
 사용할 수는 `Select` 쿼리에서 반환 하도록 결과 정의 하는 절. 이렇게 하면 쿼리에 의해 만들어진 새 익명 형식의 멤버를 정의 하거나 하거나 쿼리에 의해 반환 되는 명명 된 형식의 멤버를 대상으로 합니다. `Select` 절이 쿼리에 대 한 필요 하지 않습니다. 되지 않은 경우 `Select` 절을 지정 하면 쿼리는 현재 범위에 대 한 식별 된 범위 변수의 모든 멤버를 기준으로 형식을 반환 합니다. 자세한 내용은 [무명 형식](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)을 참조하세요. 쿼리는 명명 된 형식을 만들면 형식의 결과 반환 합니다 <xref:System.Collections.Generic.IEnumerable%601> 여기서 `T` 생성된 된 형식입니다.  
  
 `Select` 절 현재 범위에 있는 모든 변수를 참조할 수 있습니다. 여기에에서 식별 된 범위 변수는 `From` 절 (또는 `From` 절). 또한 포함 하 여 별칭을 사용 하 여 만든 새 변수는 `Aggregate`, `Let`, `Group By`, 또는 `Group Join` 절 또는 이전 `Select` 절은 쿼리 식에서 합니다. `Select` 절은 정적 값을 포함할 수도 있습니다. 예를 들어 다음 코드 예제를 보여 줍니다 쿼리 식에서 `Select` 절 쿼리 결과 4 개 멤버가 포함 된 새 익명 형식으로 정의: `ProductName`, `Price`, `Discount`, 및 `DiscountedPrice`합니다. `ProductName` 및 `Price` 멤버 값에 정의 된 제품 범위 변수에서 가져옵니다는 `From` 절. `DiscountedPrice` 에 멤버 값이 계산 되는 `Let` 절. `Discount` 멤버는 정적 값입니다.  
  
 [!code-vb[VbSimpleQuerySamples#27](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/select-clause_1.vb)]  
  
 `Select` 절 후속 쿼리 절에 대 한 범위 변수는 새 집합을 도입 하 고 이전 범위 변수는 범위에 더 이상. 마지막 `Select` 절 쿼리 식에서 쿼리의 반환 값을 결정 합니다. 예를 들어 다음 쿼리를 총 500을 초과 하는 모든 고객 주문에 대 한 이름, 주문 ID는 회사를 반환 합니다. 첫 번째 `Select` 절 식별에 대 한 범위 변수는 `Where` 절과 두 번째 `Select` 절. 두 번째 `Select` 절 새 익명 형식으로 쿼리에 의해 반환 되는 값을 식별 합니다.  
  
 [!code-vb[VbSimpleQuerySamples#28](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/select-clause_2.vb)]  
  
 경우는 `Select` 절을 반환 하는 단일 항목 식별, 쿼리 식은 해당 단일 항목의 형식 컬렉션을 반환 합니다. 경우는 `Select` 절 반환할 여러 항목을 식별, 쿼리 식은 선택한 항목을 기반으로 새 익명 형식의 컬렉션을 반환 합니다. 다음 두 쿼리를 기반으로 하는 두 가지 종류의 컬렉션을 반환 하는 예를 들어는 `Select` 절. 첫 번째 쿼리 문자열로 회사 이름의 컬렉션을 반환합니다. 컬렉션을 반환 하는 두 번째 쿼리에서 `Customer` 회사 이름 및 주소 정보로 채워진 개체입니다.  
  
 [!code-vb[VbSimpleQuerySamples#29](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/select-clause_3.vb)]  
  
## <a name="example"></a>예제  
 다음 쿼리는 사용 되는 식은 `From` 범위 변수를 선언 하는 절 `cust` 에 대 한는 `customers` 컬렉션입니다. `Select` 절은 고객 이름 및 ID 값을 선택 하 고 채웁니다는 `CompanyName` 및 `CustomerID` 새 범위 변수는 열입니다. `For Each` 문은 각 반환 된 개체를 반복 하며는 `CompanyName` 및 `CustomerID` 각 레코드에 대 한 열입니다.  
  
 [!code-vb[VbSimpleQuerySamples#30](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/select-clause_4.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic의 LINQ 소개](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [쿼리](../../../visual-basic/language-reference/queries/queries.md)  
 [From 절](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Where 절](../../../visual-basic/language-reference/queries/where-clause.md)  
 [Order By 절](../../../visual-basic/language-reference/queries/order-by-clause.md)  
 [익명 형식](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
