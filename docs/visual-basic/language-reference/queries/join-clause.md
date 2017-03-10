---
title: "Join Clause (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.QueryJoinIn"
  - "vb.QueryJoin"
  - "vb.QueryJoinOn"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "queries [Visual Basic], Join"
  - "Join statement"
  - "Join clause"
ms.assetid: 6dd37936-b27c-4e00-98ad-154b23f4de64
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# Join Clause (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

두 개의 컬렉션을 단일 컬렉션으로 결합합니다.  조인 연산은 일치하는 키를 기준으로 하며 `Equals` 연산자를 사용합니다.  
  
## 구문  
  
```  
Join element In collection _  
  [ joinClause _ ]   
  [ groupJoinClause ... _ ]   
On key1 Equals key2 [ And key3 Equals key4 [... ]  
```  
  
## 요소  
 `element`  
 필수 요소.  조인된 컬렉션의 제어 변수입니다.  
  
 `collection`  
 필수 요소.  `Join` 연산자의 왼쪽에서 식별된 컬렉션과 결합할 컬렉션입니다.  `Join` 절은 다른 `Join` 절이나 `Group Join` 절에서 중첩될 수 있습니다.  
  
 `joinClause`  
 선택 사항입니다.  쿼리 조건을 더 구체화하기 위한 하나 이상의 추가 `Join` 절입니다.  
  
 `groupJoinClause`  
 선택 사항입니다.  쿼리 조건을 더 구체화하기 위한 하나 이상의 추가 `Group Join` 절입니다.  
  
 `key1` `Equals` `key2`  
 필수 요소.  조인된 컬렉션의 키를 식별합니다.  조인된 컬렉션에서 키를 비교하려면 `Equals` 연산자를 사용해야 합니다.  `And` 연산자를 사용하여 조인 조건을 결합함으로써 여러 개의 키를 식별할 수 있습니다.  `key1`은 `Join` 연산자의 왼쪽에 있는 컬렉션에서 가져와야 합니다.  `key2`은 `Join` 연산자의 오른쪽에 있는 컬렉션에서 가져와야 합니다.  
  
 조인 조건에 사용되는 키는 컬렉션에서 두 개 이상의 항목을 포함하는 식일 수 있습니다.  하지만 각 키 식에는 해당 컬렉션의 항목만 포함할 수 있습니다.  
  
## 설명  
 `Join` 절은 조인된 컬렉션의 일치하는 키 값을 기준으로 두 개의 컬렉션을 결합합니다.  결과 컬렉션에는 `Join` 연산자의 왼쪽에서 식별된 컬렉션과 `Join` 절에서 식별된 컬렉션에서 가져온 값의 결합이 포함될 수 있습니다.  쿼리는 `Equals` 연산자에 의해 지정된 조건을 충족하는 결과만 반환합니다.  이는 SQL의 `INNER JOIN`과 같습니다.  
  
 한 쿼리에서 여러 `Join` 절을 사용하여 두 개 이상의 컬렉션을 단일 컬렉션으로 조인할 수 있습니다.  
  
 `Join` 절을 사용하지 않고 암시적 조인을 수행하여 컬렉션을 결합할 수 있습니다.  이를 수행하려면 여러 `In` 절을 `From` 절에 포함시키고 조인에 사용할 키를 식별하는 `Where` 절을 지정합니다.  
  
 `Group Join` 절을 사용하여 컬렉션을 단일 계층적 컬렉션으로 결합할 수 있습니다.  이는 SQL의 `LEFT OUTER JOIN`과 유사합니다.  
  
## 예제  
 다음 코드 예제에서는 암시적 조인을 수행하여 주문이 있는 고객의 목록을 결합합니다.  
  
 [!code-vb[VbSimpleQuerySamples#13](../../../visual-basic/language-reference/queries/codesnippet/visualbasic/VbSimpleQuerySamples/QuerySamples1.vb#13)]  
  
## 예제  
 다음 코드 예제에서는 `Join` 절을 사용하여 두 개의 컬렉션을 조인합니다.  
  
 [!code-vb[VbSimpleQuerySamples#12](../../../visual-basic/language-reference/queries/codesnippet/visualbasic/VbSimpleQuerySamples/QuerySamples2.vb#12)]  
  
 이 예제는 다음과 유사한 출력을 생성합니다.  
  
 `winlogon (968), Windows Logon`  
  
 `explorer (2424), File Explorer`  
  
 `cmd (5136), Command Window`  
  
## 예제  
 다음 코드 예제에서는 두 개의 키 열과 함께 `Join` 절을 사용하여 두 개의 컬렉션을 조인합니다.  
  
 [!code-vb[VbSimpleQuerySamples#17](../../../visual-basic/language-reference/queries/codesnippet/visualbasic/VbSimpleQuerySamples/QuerySamples3.vb#17)]  
  
 이 예제는 다음과 유사한 출력을 생성합니다.  
  
 `winlogon (968), Windows Logon, Priority = 13`  
  
 `cmd (700), Command Window, Priority = 8`  
  
 `explorer (2424), File Explorer, Priority = 8`  
  
## 참고 항목  
 [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Queries](../../../visual-basic/language-reference/queries/queries.md)   
 [Select Clause](../../../visual-basic/language-reference/queries/select-clause.md)   
 [From Clause](../../../visual-basic/language-reference/queries/from-clause.md)   
 [Group Join Clause](../../../visual-basic/language-reference/queries/group-join-clause.md)   
 [Where Clause](../../../visual-basic/language-reference/queries/where-clause.md)