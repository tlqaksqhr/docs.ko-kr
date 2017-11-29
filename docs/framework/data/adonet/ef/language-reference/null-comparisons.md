---
title: "null 비교"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: ef88af8c-8dfe-4556-8b56-81df960a900b
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: fefbd3894063c0298a7ad5110ed6867408869107
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="null-comparisons"></a>null 비교
데이터 소스의 `null` 값은 값을 알 수 없음을 나타냅니다. [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] 쿼리에서는 특정 계산이나 비교가 유효한 데이터 또는 Null이 아닌 데이터를 가진 행에서만 수행되도록 Null 값을 확인할 수 있습니다. 그러나 CLR Null 의미 체계는 데이터 소스의 Null 의미 체계와 다를 수 있습니다. 대부분의 데이터베이스는 세 개의 값으로 구성된 논리 버전을 사용하여 Null 비교를 처리합니다. 즉, Null 값에 대한 비교는 `true` 또는 `false`가 되지 않고 `unknown`이 됩니다. ANSI Null은 이렇게 구현되는 경우가 많지만 항상 그런 것은 아닙니다.  
  
 기본적으로 SQL Server에서 Null은 Null과 같음 비교는 Null 값을 반환합니다. 다음 예제에서는 `ShipDate`가 Null인 행은 결과 집합에서 제외되고 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] 문에서 0개 행을 반환합니다.  
  
```  
-- Find order details and orders with no ship date.  
SELECT h.SalesOrderID  
FROM Sales.SalesOrderHeader h  
JOIN Sales.SalesOrderDetail o ON o.SalesOrderID = h.SalesOrderID  
WHERE h.ShipDate IS Null  
```  
  
 Null은 Null과 같음 비교에서 true를 반환하는 CLR Null 의미 체계와 이 동작은 전혀 다릅니다.  
  
 다음 LINQ 쿼리는 CLR로 표현되지만 데이터 소스에서 실행됩니다. CLR 의미 체계가 데이터 소스에서 반영될 것이라는 보장이 없으므로 예상 동작을 결정할 수 없습니다.  
  
 [!code-csharp[DP L2E Conceptual Examples#JoinOnNull](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#joinonnull)]
 [!code-vb[DP L2E Conceptual Examples#JoinOnNull](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#joinonnull)]  
  
## <a name="key-selectors"></a>키 선택기  
 A *키 선택기* 요소에서 키를 추출 하는 표준 쿼리 연산자에 사용 되는 함수입니다. 키 선택기 함수에서 식을 상수와 비교할 수 있습니다. 식을 Null 상수와 비교하거나 두 개의 Null 상수를 비교하면 CLR Null 의미 체계가 표시됩니다. 데이터 소스에서 Null 값을 가진 두 개의 열을 비교하면 저장소 Null 의미 체계가 표시됩니다. 키 선택기는 <xref:System.Linq.Queryable.GroupBy%2A>과 같은 대부분의 그룹화 및 정렬 표준 쿼리 연산자에서 발견되며, 쿼리 결과를 정렬하거나 그룹화하는 기준 키를 선택하는 데 사용됩니다.  
  
## <a name="null-property-on-a-null-object"></a>Null 개체의 Null 속성  
 [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)]에서 Null 개체의 속성은 Null입니다. CLR에서 Null 개체의 속성을 참조하려고 하면 <xref:System.NullReferenceException>이 발생합니다. LINQ 쿼리에 Null 개체의 속성이 필요한 경우 일관성 없는 동작이 발생할 수 있습니다.  
  
 예를 들어, 다음 쿼리에서 `NewProduct`로의 캐스팅은 명령 트리 계층에서 수행되며, 이로 인해 `Introduced` 속성이 Null이 될 수 있습니다. <xref:System.DateTime> 비교가 true가 되도록 데이터베이스에서 Null 비교를 정의한 경우 해당 행이 포함됩니다.  
  
 [!code-csharp[DP L2E Conceptual Examples#CastResultsIsNull](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#castresultsisnull)]
 [!code-vb[DP L2E Conceptual Examples#CastResultsIsNull](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#castresultsisnull)]  
  
## <a name="passing-null-collections-to-aggregate-functions"></a>Null 컬렉션을 집계 함수에 전달  
 [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)]지 원하는 컬렉션을 전달 하면 `IQueryable` 데이터베이스에서 집계 함수에 집계 작업이 수행 됩니다. 메모리에 수행된 된 쿼리의와 데이터베이스에서 수행 된 쿼리의 결과에 차이점이 있을 수 있습니다. 메모리 내 쿼리의 경우와 일치 하지 않는 경우 쿼리가 0을 반환 합니다. 데이터베이스에서 동일한 쿼리가 `null`을 반환합니다. 경우는 `null` 값이 LINQ 집계 함수로 전달 되는, 예외가 throw 됩니다. 허용 가능한 하도록 `null` 유형과 null 허용 형식으로 쿼리 결과 수신 하는 형식의 속성 값을 캐스팅 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [LINQ to Entities 쿼리 식](../../../../../../docs/framework/data/adonet/ef/language-reference/expressions-in-linq-to-entities-queries.md)
