---
title: GROUP BY(Entity SQL)
ms.date: 03/30/2017
ms.assetid: cf4f4972-4724-4945-ba44-943a08549139
ms.openlocfilehash: 3b5edee08afef8418f19df433223818218ae909d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="group-by-entity-sql"></a>GROUP BY(Entity SQL)
쿼리 식([SELECT](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md))을 통해 반환되는 개체가 배치될 그룹을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
[ GROUP BY aliasedExpression [ ,...n ] ]  
```  
  
## <a name="arguments"></a>인수  
 `aliasedExpression`  
 그룹화가 수행되는 유효한 쿼리 식입니다. `expression` 은 속성일 수도 있고 FROM 절을 통해 반환되는 속성을 참조하는 비집계 식일 수도 있습니다. GROUP BY 절의 모든 식은 같지 않음을 비교할 수 있는 형식으로 계산되어야 합니다. 이런 형식은 일반적으로 숫자, 문자열, 날짜와 같은 스칼라 기본 형식입니다. 컬렉션을 기준으로 그룹화할 수 없습니다.  
  
## <a name="remarks"></a>설명  
 SELECT 절에 집계 함수가 포함 된 경우 \<select 목록 >, GROUP BY 각 그룹에 대 한 요약 값을 계산 합니다. GROUP BY가 지정된 경우, 선택 목록 내의 집계가 아닌 식에 있는 모든 속성 이름이 GROUP BY 목록에 포함되어야 하거나 아니면 GROUP BY 식이 선택 목록 식과 정확히 일치해야 합니다.  
  
> [!NOTE]
>  ORDER BY 절이 지정되지 않은 경우에는 GROUP BY 절에 의해 반환되는 그룹에 특정 순서가 없습니다. 데이터에 특정 정렬 순서를 지정하려면 항상 ORDER BY 절을 사용하는 것이 좋습니다.  
  
 명시적으로든 암시적으로든(예: 쿼리에 HAVING 절 사용) GROUP BY 절이 지정된 경우, 현재 범위는 숨겨지고 새로운 범위가 나타납니다.  
  
 그러면 SELECT 절, HAVING 절 및 ORDER BY 절이 FROM 절에 지정된 요소 이름을 참조할 수 없게 됩니다. 그룹화 식 자체만 참조할 수 있습니다. 이렇게 하려면 각 그룹화에 새 이름(별칭)을 할당하면 됩니다. 그룹화 식에 별칭이 지정되지 않은 경우 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 에서는 다음 예제에서 보여 주는 것처럼 별칭 생성 규칙에 따라 별칭을 생성합니다.  
  
 `SELECT g1, g2, ...gn FROM c as c1`  
  
 `GROUP BY e1 as g1, e2 as g2, ...en as gn`  
  
 GROUP BY 절의 식은 동일한 GROUP BY 절에 이전에 정의된 이름을 참조할 수 없습니다.  
  
 그룹화 이름뿐만 아니라 SELECT 절, HAVING 절 및 ORDER BY 절의 집계를 지정할 수도 있습니다. 집계에는 그룹의 각 요소에 대해 계산되는 식이 포함됩니다. 집계 연산자를 이러한 모든 식의 값을 일반적으로(항상 그렇지는 않음) 단일 값으로 줄입니다. 집계 식은 부모 범위에 나타난 원래 요소 이름을 참조하거나 GROUP BY 절에 의해 생성된 새 이름을 참조할 수 있습니다. 집계가 SELECT 절, HAVING 절, ORDER BY 절에 나타나기는 하지만 다음 예제에서 보여 주는 것처럼 그룹화 식과 동일한 범위에서 실제로 계산됩니다.  
  
 `SELECT name, sum(o.Price * o.Quantity) as total`  
  
 `FROM orderLines as o`  
  
 `GROUP BY o.Product as name`  
  
 이 쿼리는 GROUP BY 절을 사용하여 모든 주문 제품에 대해 제품별로 구분된 비용 보고서를 생성합니다. 여기서는 그룹화 식의 일부로서 제품에 이름 `name` 을 지정하며 그런 다음 이 이름을 SELECT 목록에서 참조합니다. 또한, 주문 라인의 가격과 수량을 내부적으로 참조하는 집계 `sum` 을 SELECT 목록에서 지정합니다.  
  
 각 GROUP BY 키 식에는 입력 범위에 대한 참조가 하나 이상 있어야 합니다.  
  
```  
SELECT FROM Persons as P  
GROUP BY Q + P   -- GOOD  
GROUP BY Q   -- BAD  
GROUP BY 1   -- BAD, a constant is not allowed  
```  
  
 GROUP BY 사용 예제는 [HAVING](../../../../../../docs/framework/data/adonet/ef/language-reference/having-entity-sql.md)항목을 참조하세요.  
  
## <a name="example"></a>예제  
 다음 Entity SQL 쿼리에서는 GROUP BY 연산자를 사용하여 쿼리를 통해 반환되는 개체가 배치될 그룹을 지정합니다. 쿼리는 AdventureWorks Sales 모델을 기반으로 합니다. 이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.  
  
1.  절차에 따라 [하는 방법: PrimitiveType 결과 반환 하는 쿼리 실행](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)합니다.  
  
2.  다음 쿼리를 `ExecutePrimitiveTypeQuery` 메서드에 인수로 전달합니다.  
  
 [!code-csharp[DP EntityServices Concepts 2#GROUPBY](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#groupby)]  
  
## <a name="see-also"></a>참고 항목  
 [엔터티 SQL 참조](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [쿼리 식](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)
