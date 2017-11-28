---
title: SELECT(Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9a33bd0d-ded1-41e7-ba3c-305502755e3b
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 3123d76d5999d9f7201e1415d6bc4313f9767098
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="select-entity-sql"></a>SELECT(Entity SQL)
쿼리 결과로 반환될 요소를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
SELECT [ ALL | DISTINCT ] [ topSubclause ] aliasedExpr   
      [{ , aliasedExpr }] FROM fromClause [ WHERE whereClause ] [ GROUP BY groupByClause [ HAVING havingClause ] ] [ ORDER BY orderByClause ]  
or  
SELECT VALUE [ ALL | DISTINCT ] [ topSubclause ] expr FROM fromClause [ WHERE whereClause ] [ GROUP BY groupByClause [ HAVING havingClause ] ] [ ORDER BY orderByClause  
```  
  
## <a name="arguments"></a>인수  
 ALL  
 결과 집합에 중복 항목이 나타날 수 있음을 지정합니다. ALL이 기본값입니다.  
  
 DISTINCT  
 결과 집합에 고유한 결과만 나타날 수 있음을 지정합니다.  
  
 VALUE  
 항목 하나만 지정할 수 있으며 행 래퍼를 추가하지 않습니다.  
  
 `topSubclause`  
 쿼리에서 첫 번째로 반환되는 결과의 개수를 나타내며 `top (``expr``)`형태로 표시되는 모든 유효한 식입니다.  
  
 LIMIT 매개 변수는 [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md) 연산자 또한 결과 집합의 처음 n 개의 항목을 선택할 수 있습니다.  
  
 `aliasedExpr`  
 다음 형태의 식입니다.  
  
 `expr`으로 `identifier` &#124;`expr`  
  
 `expr`  
 리터럴 또는 식입니다.  
  
## <a name="remarks"></a>설명  
 SELECT 절에 평가 됩니다는 [FROM](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md), [GROUP BY](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md), 및 [HAVING](../../../../../../docs/framework/data/adonet/ef/language-reference/having-entity-sql.md) 절이 계산 된 합니다. SELECT 절은 현재 범위 내에 있는 항목만 참조할 수 있으며, FROM 절 또는 외부 범위에서 참조할 수 있습니다. GROUP BY 절이 지정된 경우, SELECT 절에서는 GROUP BY 키의 별칭만 참조할 수 있습니다. FROM 절 항목에 대한 참조는 집계 함수에서만 허용됩니다.  
  
 SELECT 키워드 다음에 나오는 하나 이상의 쿼리 식을 나열한 목록은 선택 목록이라고 하고 공식적으로는 프로젝션이라고도 합니다. 가장 일반적인 형태의 프로젝션은 단일 쿼리 식입니다. `member1` 컬렉션에서 `collection1`멤버를 선택하면 다음 예제와 같이 `member1` 의 각 개체에 대한 모든 `collection1`값이 포함된 새로운 컬렉션이 생성됩니다.  
  
```  
SELECT collection1.member1 FROM collection1  
```  
  
 예를 들어 `customers` 가 `Customer` 형식의 `Name` 속성이 포함된 `string`형식의 컬렉션인 경우, `Name` 에서 `customers` 을 선택하면 다음 예제와 같이 문자열 컬렉션이 생성됩니다.  
  
```  
SELECT customers.Name FROM customers AS c  
```  
  
 FULL, INNER, LEFT, OUTER, ON, RIGHT 등의 JOIN 구문을 사용할 수도 있습니다. ON은 내부 조인에 필수적이지만 크로스 조인에는 사용할 수 없습니다.  
  
## <a name="row-and-value-select-clauses"></a>ROW 및 VALUE SELECT 절  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 에서는 두 가지 변형의 SELECT 절을 지원합니다. 하나는 행 선택으로서, SELECT 키워드로 식별됩니다. 이 절은 프로젝션될 값을 하나 이상 지정하는 데 사용됩니다. 반환되는 값 주위에 행 래퍼가 암시적으로 추가되므로, 쿼리 식의 결과는 항상 행의 multiset입니다.  
  
 행의 각 쿼리 식에서는 별칭이 지정되어야 합니다. 별칭이 지정되지 않은 경우[!INCLUDE[esql](../../../../../../includes/esql-md.md)] 에서는 별칭 생성 규칙에 따라 별칭을 생성합니다.  
  
 SELECT 절의 다른 변형은 값 선택으로서, SELECT VALUE 키워드로 식별됩니다. 이 절은 항목 하나만 지정할 수 있으며 행 래퍼를 추가하지 않습니다.  
  
 행 선택은 다음 예제에서 보여 주는 것처럼 항상 VALUE SELECT로 표현할 수 있습니다.  
  
```  
SELECT 1 AS a, "abc" AS b FROM C  
SELECT VALUE ROW(1 AS a, "abc" AS b) FROM C   
```  
  
## <a name="all-and-distinct-modifiers"></a>ALL 및 DISTINCT 한정자  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 에서 지원되는 두 가지 SELECT 절 모두 ALL 한정자나 DISTINCT 한정자의 사양을 허용합니다. DISTINCT 한정자가 지정된 경우, 쿼리 식에서 생성되는 컬렉션에서 중복 항목이 제거됩니다(SELECT 절까지 포함). ALL 한정자가 지정된 경우에는 중복 항목이 제거되지 않으며, ALL이 기본값입니다.  
  
## <a name="differences-from-transact-sql"></a>Transact-SQL과의 차이점  
 Transact-SQL과는 달리, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 에서는 SELECT 절에 * 인수의 사용을 지원하지 않습니다.  대신 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 에서는 다음 예제에서 보여 주는 것처럼 쿼리를 통해 FROM 절에서 컬렉션 별칭을 참조하여 전체 레코드를 프로젝션할 수 있습니다.  
  
```  
SELECT * FROM T1, T2  
```  
  
 위의 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] 쿼리 식은 다음과 같이 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 로 표현됩니다.  
  
```  
SELECT a1, a2 FROM T1 AS a1, T2 AS a2  
```  
  
## <a name="example"></a>예제  
 다음 Entity SQL 쿼리에서는 SELECT 연산자를 사용하여 쿼리에서 반환될 요소를 지정합니다. 쿼리는 AdventureWorks Sales 모델을 기반으로 합니다. 이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.  
  
1.  [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.  
  
2.  다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.  
  
 [!code-csharp[DP EntityServices Concepts 2#LESS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#less)]  
  
## <a name="see-also"></a>참고 항목  
 [쿼리 식](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)  
 [엔터티 SQL 참조](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [맨 위로](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md)
