---
title: Distinct 절(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryDistinct
helpviewer_keywords:
- Distinct clause [Visual Basic]
- Distinct statement [Visual Basic]
- queries [Visual Basic], Distinct
ms.assetid: 86f42614-0d8f-4ffc-b888-ce8a37a8d36a
ms.openlocfilehash: 4b0ce12f6361d3dc6e5cc3601e96fc3a9bcf3841
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603979"
---
# <a name="distinct-clause-visual-basic"></a>Distinct 절(Visual Basic)
후속 쿼리 절에 중복 값을 제거 하 여 현재 범위 변수 값을 제한 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Distinct  
```  
  
## <a name="remarks"></a>설명  
 사용할 수는 `Distinct` 절 고유 항목의 목록을 반환 합니다. `Distinct` 절로 인해 쿼리 중복 되는 쿼리 결과 무시 하도록 합니다. `Distinct` 절이 모두 반환 하 여 지정 된 필드에 대 한 중복 값에 적용 된 `Select` 절. 하지 않으면 `Select` 절이 지정 된 `Distinct` 절에서 식별 된 쿼리의 범위 변수가 적용 됩니다는 `From` 절. 범위 변수는 변경할 수 없는 형식 없는 경우 형식의 모든 멤버에는 기존 쿼리 결과 일치 하는 경우 쿼리가 쿼리 결과 무시만 합니다.  
  
## <a name="example"></a>예제  
 다음 쿼리 식은 고객 목록을 고객 주문 목록과 결합합니다. `Distinct` 절이 고유한 고객 이름 목록을 반환 하 고 주문 날짜를 포함 합니다.  
  
 [!code-vb[VbSimpleQuerySamples#20](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/distinct-clause_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic의 LINQ 소개](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [쿼리](../../../visual-basic/language-reference/queries/queries.md)  
 [From 절](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Select 절](../../../visual-basic/language-reference/queries/select-clause.md)  
 [Where 절](../../../visual-basic/language-reference/queries/where-clause.md)
