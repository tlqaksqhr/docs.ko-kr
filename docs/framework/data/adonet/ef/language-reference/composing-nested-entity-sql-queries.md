---
title: "중첩 Entity SQL 쿼리 작성"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 685d4cd3-2c1f-419f-bb46-c9d97a351eeb
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 1946f2b4a2cef8946eb05f995150fafada954d09
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="composing-nested-entity-sql-queries"></a>중첩 Entity SQL 쿼리 작성
[!INCLUDE[esql](../../../../../../includes/esql-md.md)]은 다양한 기능을 가진 언어입니다. 빌딩 블록 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 는 식입니다. 기존 SQL과 달리 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 탭 형식의 결과 집합에 국한 되지 않음: [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 리터럴, 매개 변수 또는 중첩된 식을 가질 수 있는 복잡 한 식 작성을 지원 합니다. 식에서 값을 매개 변수화 또는 다른 식으로 구성 수 있습니다.  
  
## <a name="nested-expressions"></a>중첩된 식  
 중첩된 식은 자신이 반환한 형식의 값이 허용되는 임의의 위치에 놓일 수 있습니다. 예를 들면 다음과 같습니다.  
  
```  
-- Returns a hierarchical collection of three elements at top-level.   
-- x must be passed in the parameter collection.  
ROW(@x, {@x}, {@x, 4, 5}, {@x, 7, 8, 9})  
  
-- Returns a hierarchical collection of one element at top-level.  
-- x must be passed in the parameter collection.  
{{{@x}}};  
```  
  
 중첩 쿼리는 프로젝션 절에 위치할 수 있습니다. 예를 들면 다음과 같습니다.  
  
```  
-- Returns a collection of rows where each row contains an Address entity.  
-- and a collection of references to its corresponding SalesOrderHeader entities.  
SELECT address, (SELECT DEREF(soh)   
                    FROM NAVIGATE(address, AdventureWorksModel.FK_SalesOrderHeader_Address_BillToAddressID) AS soh)   
                    AS salesOrderHeader FROM AdventureWorksEntities.Address AS address  
```  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서 중첩 쿼리는 반드시 괄호로 묶어야 합니다.  
  
```  
-- Pseudo-Entity SQL  
( SELECT …  
FROM … )  
UNION ALL  
( SELECT …  
FROM … );  
```  
  
 다음 예제에서는 식에 올바르게 중첩 하는 방법을 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]: [하는 방법: 공용 구조체의 두 쿼리 정렬](http://msdn.microsoft.com/en-us/853c583a-eaba-4400-830d-be974e735313)합니다.  
  
## <a name="nested-queries-in-projection"></a>프로젝션의 중첩 쿼리  
 프로젝션 절의 중첩 쿼리는 서버의 Cartesian 제품 쿼리로 변환될 수 있습니다. SLQ Server를 비롯한 일부 백엔드 서버에서는 이로 인해 TempDB 테이블이 매우 커질 수 있으므로 서버 성능이 저하될 수 있습니다.  
  
 다음은 이러한 쿼리의 예제입니다.  
  
```  
SELECT c, (SELECT c, (SELECT c FROM AdventureWorksModel.Vendor AS c  ) As Inner2 FROM AdventureWorksModel.JobCandidate AS c  ) As Inner1 FROM AdventureWorksModel.EmployeeDepartmentHistory AS c  
```  
  
## <a name="ordering-nested-queries"></a>중첩 쿼리 순서  
 Entity Framework에서 중첩된 식은 쿼리 내 임의의 위치에 올 수 있습니다. Entity SQL을 사용하면 보다 유연성 있게 쿼리를 작성할 수 있으므로 중첩 쿼리의 순서가 포함된 쿼리를 작성할 수 있습니다. 하지만 중첩 쿼리의 순서는 유지되지 않습니다.  
  
```  
-- The following query will order the results by last name.  
SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorksModel.Contact as C1  
        ORDER BY C1.LastName  
```  
  
```  
-- In the following query, ordering of the nested query is ignored.  
SELECT C2.FirstName, C2.LastName  
    FROM (SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorksModel.Contact as C1  
        ORDER BY C1.LastName) as C2  
```  
  
## <a name="see-also"></a>참고 항목  
 [Entity SQL 개요](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
