---
title: Take While 절(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryTakeWhile
helpviewer_keywords:
- queries [Visual Basic], Take While
- Take While clause [Visual Basic]
- Take While statement [Visual Basic]
ms.assetid: db8f9f2f-fc9f-4a6c-b0b8-1bf048147e11
ms.openlocfilehash: 181cc641bb12329c898cc3bb226ea49f0836e979
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2018
ms.locfileid: "42932029"
---
# <a name="take-while-clause-visual-basic"></a>Take While 절(Visual Basic)
지정된 조건이 `true`이면 컬렉션의 요소를 포함하고 나머지 요소를 무시합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Take While expression  
```  
  
## <a name="parts"></a>요소  
  
|용어|정의|  
|---|---|  
|`expression`|필수. 에 대 한 요소를 테스트 하는 조건을 나타내는 식입니다. 식을 반환 해야 합니다는 `Boolean` 값 또는 이와 동일한 기능 같은 `Integer` 으로 계산 되는 `Boolean`합니다.|  
  
## <a name="remarks"></a>설명  
 합니다 `Take While` 일까 지 제공 된 쿼리 결과의 시작 부분에서 요소를 포함 하는 절 `expression` 반환 `false`합니다. 후 합니다 `expression` 반환 `false`, 나머지 모든 요소를 무시 하는 쿼리. `expression` 나머지 결과 대해 무시 됩니다.  
  
 `Take While` 절에서 다른 합니다 `Where` 절에는 `Where` 쿼리에서 특정 조건을 충족 하는 모든 요소를 포함 하려면 절을 사용할 수 있습니다. `Take While` 절 조건이 충족 되지 않은 첫 번째 시간 까지만 요소를 포함 합니다. `Take While` 절은 순서가 지정 된 쿼리 결과 사용 하 여 작업할 때 가장 유용 합니다.  
  
## <a name="example"></a>예  
 다음 코드 예제에서는 `Take While` 절 순서 없이 첫 번째 고객을 찾을 때까지 결과를 검색 합니다.  
  
 [!code-vb[VbSimpleQuerySamples#2](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/take-while-clause_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic의 LINQ 소개](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [쿼리](../../../visual-basic/language-reference/queries/index.md)  
 [Select 절](../../../visual-basic/language-reference/queries/select-clause.md)  
 [From 절](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Take 절](../../../visual-basic/language-reference/queries/take-clause.md)  
 [Skip While 절](../../../visual-basic/language-reference/queries/skip-while-clause.md)  
 [Where 절](../../../visual-basic/language-reference/queries/where-clause.md)
