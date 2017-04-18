---
title: "THEN(Entity SQL) | Microsoft Docs"
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
ms.assetid: 54222642-23c6-4f61-9861-67caca53ac5f
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# THEN(Entity SQL)
WHEN 절이 `true`로 계산될 때의 결과입니다.  
  
## 구문  
  
```  
  
WHEN when_expression THEN then_expression  
```  
  
## 인수  
 `when_expression`  
 모든 유효한 부울 식입니다.  
  
 `then_expression`  
 컬렉션을 반환하는 모든 유효한 쿼리 식입니다.  
  
## 설명  
 `when_expression`이 `true` 값으로 계산되면 결과는 해당 `then-expression`입니다. 만족되는 WHEN 조건이 없으면 `else-expression`이 계산됩니다. 하지만 `else-expression`이 없으면 결과는 null입니다.  
  
 예제를 보려면 [CASE](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md)를 참조하십시오.  
  
## 예제  
 다음 Entity SQL 쿼리에서는 CASE 식을 사용하여 일련의 `Boolean` 식을 계산합니다. 쿼리는 AdventureWorks Sales 모델을 기반으로 합니다. 이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.  
  
1.  [방법: PrimitiveType 결과를 반환하는 쿼리 실행](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md)의 절차를 따릅니다.  
  
2.  다음 쿼리를 `ExecutePrimitiveTypeQuery` 메서드에 인수로 전달합니다.  
  
 [!code-csharp[DP EntityServices Concepts 2#CASE_WHEN_THEN_ELSE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#case_when_then_else)]  
  
## 참고 항목  
 [CASE](../../../../../../docs/framework/data/adonet/ef/language-reference/case-entity-sql.md)   
 [Entity SQL 참조](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)