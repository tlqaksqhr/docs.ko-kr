---
title: HAVING (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b5d52d97-8372-4335-beac-2d0b79dc3707
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 92949205801e5bc498fdaaa67c2fa228140a2eb5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="having-entity-sql"></a>HAVING (Entity SQL)
그룹이나 집계에 대한 검색 조건을 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
[ HAVING search_condition ]  
```  
  
## <a name="arguments"></a>인수  
 `search_condition`  
 그룹이나 집계에 대해 충족해야 하는 검색 조건을 지정합니다. HAVING을 GROUP BY ALL과 함께 사용하면 HAVING 절이 ALL을 재정의합니다.  
  
## <a name="remarks"></a>설명  
 HAVING 절은 그룹화 결과에 추가 필터링 조건을 지정하는 데 사용됩니다. 쿼리 식에 GROUP BY 절이 지정되지 않으면 암시적인 단일 집합 그룹이 선택됩니다.  
  
> [!NOTE]
>  HAVING에만 사용할 수 있습니다는 [선택](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md) 문. 때 [GROUP BY](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md) 는 HAVING을 사용 하지는 WHERE 절 처럼 작동 합니다.  
  
 HAVING 절은 GROUP BY 연산 이후에 적용된다는 점을 제외하고는 WHERE 절과 비슷하게 작동합니다. 다시 말해서, HAVING 절은 다음 예제와 같이 그룹화 별칭 및 집계만 참조합니다.  
  
```  
SELECT Name, SUM(o.Price * o.Quantity) AS Total FROM orderLines AS o GROUP BY o.Product AS Name  
HAVING SUM(o.Quantity) > 1  
```  
  
 위 예에서는 제품 두 개 이상이 포함된 그룹으로만 제한되었습니다.  
  
## <a name="example"></a>예  
 다음 Entity SQL 쿼리에서는 HAVING 및 GROUP BY 연산자를 사용하여 그룹이나 집계에 대한 검색 조건을 지정합니다. 쿼리는 AdventureWorks Sales 모델을 기반으로 합니다. 이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.  
  
1.  절차에 따라 [하는 방법: PrimitiveType 결과 반환 하는 쿼리 실행](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)합니다.  
  
2.  다음 쿼리를 `ExecutePrimitiveTypeQuery` 메서드에 인수로 전달합니다.  
  
 [!code-csharp[DP EntityServices Concepts 2#HAVING](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#having)]  
  
## <a name="see-also"></a>참고 항목  
 [엔터티 SQL 참조](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [쿼리 식](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)
