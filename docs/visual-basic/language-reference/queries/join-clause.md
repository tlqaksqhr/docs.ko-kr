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
ms.openlocfilehash: 2186954ab6536988271629c4feba0a40563bfc3f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603914"
---
# <a name="join-clause-visual-basic"></a>Join 절(Visual Basic)
두 컬렉션을 단일 컬렉션으로 결합합니다. 조인 연산은 일치 하는 키에 기반 하며 사용 하 여 `Equals` 연산자입니다.  
  
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
 필수. 컬렉션의 왼쪽에 식별 된 컬렉션으로 결합 하는 `Join` 연산자입니다. A `Join` 다른에 중첩 절 `Join` 절 또는 `Group Join` 절.  
  
 `joinClause`  
 선택 사항입니다. 하나 이상의 추가 `Join` 는 쿼리를 구체화 하는 절을 추가 합니다.  
  
 `groupJoinClause`  
 선택 사항입니다. 하나 이상의 추가 `Group Join` 는 쿼리를 구체화 하는 절을 추가 합니다.  
  
 `key1` `Equals` `key2`  
 필수. 조인 중인 컬렉션에 대 한 키를 식별 합니다. 사용 해야 합니다는 `Equals` 조인 중인 컬렉션에서 키를 비교 연산자. 사용 하 여 조인 조건을 결합할 수 있습니다는 `And` 여러 키를 식별 하는 연산자입니다. `key1` 왼쪽에 있는 컬렉션에서 이어야 합니다는 `Join` 연산자입니다. `key2` 오른쪽에 있는 컬렉션에서 이어야 합니다는 `Join` 연산자입니다.  
  
 조인 조건에 사용 되는 키 컬렉션에서 둘 이상의 항목을 포함 하는 식을 수 있습니다. 그러나 각 키의 식에는 해당 컬렉션의 항목에만 포함할 수 있습니다.  
  
## <a name="remarks"></a>설명  
 `Join` 절 조인 중인 컬렉션의 키 값을 일치 하는 두 개의 컬렉션을 결합 합니다. 결과 컬렉션의 왼쪽에 식별 된 컬렉션에서 값의 조합이 포함 될 수 있습니다는 `Join` 연산자 및에서 식별 된 컬렉션의 `Join` 절. 쿼리는 반환 하 여 지정 된 조건이 결과만 `Equals` 연산자 충족할 수 있습니다. 이 해당 하는 `INNER JOIN` sql에서 합니다.  
  
 여러 개 사용할 수 있습니다 `Join` 에 둘 이상의 컬렉션을 단일 컬렉션으로 조인 쿼리에서 절.  
  
 결합 하지 않고 컬렉션 암시적 조인을 수행할 수 있습니다는 `Join` 절. 이 위해 여러 개 포함 `In` 절을 프로그램 `From` 절을 지정 하 고는 `Where` 는 조인에 사용 하려는 하는 키를 식별 하는 절.  
  
 사용할 수는 `Group Join` 절 단일 계층 구조 컬렉션으로 결합할 수 있습니다. 이 비슷하지만 `LEFT OUTER JOIN` sql에서 합니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 고객 목록을 고객의 주문을와 결합할 암시적 조인을 수행 합니다.  
  
 [!code-vb[VbSimpleQuerySamples#13](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/join-clause_1.vb)]  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 사용 하 여 두 컬렉션 조인는 `Join` 절.  
  
 [!code-vb[VbSimpleQuerySamples#12](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/join-clause_2.vb)]  
  
 이 예제에는 다음과 유사한 결과가 생성 됩니다.  
  
 `winlogon (968), Windows Logon`  
  
 `explorer (2424), File Explorer`  
  
 `cmd (5136), Command Window`  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 사용 하 여 두 컬렉션 조인는 `Join` 절 두 개의 키 열을 사용 합니다.  
  
 [!code-vb[VbSimpleQuerySamples#17](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/join-clause_3.vb)]  
  
 이 예제에는 다음과 유사한 결과가 생성 됩니다.  
  
 `winlogon (968), Windows Logon, Priority = 13`  
  
 `cmd (700), Command Window, Priority = 8`  
  
 `explorer (2424), File Explorer, Priority = 8`  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic의 LINQ 소개](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [쿼리](../../../visual-basic/language-reference/queries/queries.md)  
 [Select 절](../../../visual-basic/language-reference/queries/select-clause.md)  
 [From 절](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Group Join 절](../../../visual-basic/language-reference/queries/group-join-clause.md)  
 [Where 절](../../../visual-basic/language-reference/queries/where-clause.md)
