---
title: "SET(Entity SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "ESQL"
ms.assetid: 28b4deac-c7e4-4f09-b428-4d352ef2dc94
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# SET(Entity SQL)
SET 식은 중복 요소가 모두 제거된 새 컬렉션을 생성하여 개체 컬렉션을 집합으로 변환하는 데 사용됩니다.  
  
## 구문  
  
```  
  
SET (expression)  
```  
  
## 인수  
 `expression`  
 컬렉션을 반환하는 모든 유효한 쿼리 식입니다.  
  
## 설명  
 집합 식 `SET(c)`는 다음 select 문과 논리적으로 같습니다.  
  
```  
SELECT VALUE DISTINCT c FROM c  
```  
  
 `SET`는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 집합 연산자 중 하나입니다. 모든 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 집합 연산자는 왼쪽에서 오른쪽으로 계산됩니다.[!INCLUDE[esql](../../../../../../includes/esql-md.md)] 집합 연산자의 우선 순위에 대한 자세한 내용은 [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md) 항목을 참조하세요.  
  
## 예제  
 다음 Entity SQL 쿼리에서는 SET 식을 사용하여 개체의 컬렉션을 집합으로 변환합니다. 쿼리는 AdventureWorks Sales 모델을 기반으로 합니다. 이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.  
  
1.  [방법: PrimitiveType 결과를 반환하는 쿼리 실행](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)의 절차를 따릅니다.  
  
2.  다음 쿼리를 `ExecutePrimitiveTypeQuery` 메서드에 인수로 전달합니다.  
  
 [!code-csharp[DP EntityServices Concepts 2#SET](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#set)]  
  
## 참고 항목  
 [Entity SQL 참조](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)