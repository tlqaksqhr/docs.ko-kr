---
title: Join 절(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.QueryJoinIn
- vb.QueryJoin
- vb.QueryJoinOn
helpviewer_keywords:
- queries [Visual Basic], Join
- Join statement [Visual Basic]
- Join clause [Visual Basic]
ms.assetid: 6dd37936-b27c-4e00-98ad-154b23f4de64
ms.openlocfilehash: b1551583079c66d1bf5f6963a42d5d24e518fff3
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2018
ms.locfileid: "42933869"
---
# <a name="join-clause-visual-basic"></a>Join 절(Visual Basic)
두 컬렉션을 단일 컬렉션으로 결합합니다. 조인 연산은 일치 하는 키 기준으로 하며 사용 하 여 `Equals` 연산자입니다.  
  
## <a name="syntax"></a>구문  
  
```  
Join element In collection _  
  [ joinClause _ ]   
  [ groupJoinClause ... _ ]   
On key1 Equals key2 [ And key3 Equals key4 [... ]  
```  
  
## <a name="parts"></a>요소  
 `element`  
 필수. 조인 중인 컬렉션에 대 한 제어 변수입니다.  
  
 `collection`  
 필수. 왼쪽에 식별 된 컬렉션과 결합할 컬렉션을 `Join` 연산자입니다. A `Join` 절의 다른 중첩 될 수 있습니다 `Join` 절 또는 `Group Join` 절.  
  
 `joinClause`  
 선택 사항입니다. 하나 이상의 추가 `Join` 쿼리를 구체화 하는 절을 추가 합니다.  
  
 `groupJoinClause`  
 선택 사항입니다. 하나 이상의 추가 `Group Join` 쿼리를 구체화 하는 절을 추가 합니다.  
  
 `key1` `Equals` `key2`  
 필수. 조인 중인 컬렉션에 대 한 키를 식별 합니다. 사용 해야는 `Equals` 조인 중인 컬렉션에서 키를 비교 하는 연산자입니다. 조인 조건을 사용 하 여 결합할 수 있습니다는 `And` 여러 키를 식별 하는 연산자입니다. `key1` 왼쪽에 있는 컬렉션에서 이어야 합니다는 `Join` 연산자입니다. `key2` 오른쪽에 있는 컬렉션에서 이어야 합니다는 `Join` 연산자입니다.  
  
 조인 조건에 사용 되는 키 컬렉션에서 둘 이상의 항목을 포함 하는 식을 수 있습니다. 그러나 각 키 식에는 해당 컬렉션의 항목만 포함할 수 있습니다.  
  
## <a name="remarks"></a>설명  
 `Join` 절 조인 중인 컬렉션에서 키 값을 일치를 기준으로 하는 두 개의 컬렉션을 결합 합니다. 결과 컬렉션의 왼쪽에 식별 된 컬렉션에서 값의 조합을 포함할 수 있습니다 합니다 `Join` 연산자와에서 식별 된 컬렉션을 `Join` 절. 쿼리는 반환 하 여 지정 된 조건이 결과만 `Equals` 연산자 충족 됩니다. 이 해당 하는 `INNER JOIN` sql에서입니다.  
  
 여러 개 사용할 수 있습니다 `Join` 둘 이상의 컬렉션을 단일 컬렉션으로 조인 하는 쿼리 절.  
  
 없는 컬렉션을 결합 하는 암시적 조인을 수행할 수 있습니다는 `Join` 절. 이렇게 하려면 여러 개 포함 `In` 절에 `From` 절 지정을 `Where` 조인에 사용 하려는 키를 식별 하는 절.  
  
 사용할 수는 `Group Join` 절을 단일 계층 구조 컬렉션으로 결합할 수 있습니다. 비슷합니다는 `LEFT OUTER JOIN` sql에서입니다.  
  
## <a name="example"></a>예  
 다음 코드 예제에서는 고객 목록을 고객의 주문을 결합할 암시적 조인을 수행 합니다.  
  
 [!code-vb[VbSimpleQuerySamples#13](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/join-clause_1.vb)]  
  
## <a name="example"></a>예  
 다음 코드 예제를 사용 하 여 두 컬렉션 조인 된 `Join` 절.  
  
 [!code-vb[VbSimpleQuerySamples#12](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/join-clause_2.vb)]  
  
 이 예제는 다음과 유사한 출력을 생성 합니다.  
  
 `winlogon (968), Windows Logon`  
  
 `explorer (2424), File Explorer`  
  
 `cmd (5136), Command Window`  
  
## <a name="example"></a>예  
 다음 코드 예제를 사용 하 여 두 컬렉션 조인 된 `Join` 두 개의 키 열을 사용 하 여 절.  
  
 [!code-vb[VbSimpleQuerySamples#17](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/join-clause_3.vb)]  
  
 이 예제에서는 다음과 유사한 출력을 생성 합니다.  
  
 `winlogon (968), Windows Logon, Priority = 13`  
  
 `cmd (700), Command Window, Priority = 8`  
  
 `explorer (2424), File Explorer, Priority = 8`  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic의 LINQ 소개](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [쿼리](../../../visual-basic/language-reference/queries/index.md)  
 [Select 절](../../../visual-basic/language-reference/queries/select-clause.md)  
 [From 절](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Group Join 절](../../../visual-basic/language-reference/queries/group-join-clause.md)  
 [Where 절](../../../visual-basic/language-reference/queries/where-clause.md)
