---
title: "OVERLAPS(Entity SQL) | Microsoft Docs"
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
ms.assetid: 41743e89-79cb-4d7b-8a27-355b45024b61
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# OVERLAPS(Entity SQL)
두 컬렉션에 공통 요소가 있는지 여부를 확인합니다.  
  
## 구문  
  
```  
  
expression OVERLAPS expression  
```  
  
## 인수  
 `expression`  
 다른 쿼리 식에서 반환된 컬렉션과 비교할 컬렉션을 반환하는 모든 유효한 쿼리 식입니다. 모든 식은 형식이 같거나 기본 형식 또는 파생 형식이 `expression`이어야 합니다.  
  
## 반환 값  
 두 컬렉션에 공통 요소가 있으면 `true`이고, 그렇지 않으면 `false`입니다.  
  
## 설명  
 OVERLAPS는 다음 식과 동일한 기능을 제공합니다``.  
  
 `EXISTS ( expression INTERSECT expression )`  
  
 OVERLAPS는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 집합 연산자 중 하나입니다. 모든 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 집합 연산자는 왼쪽에서 오른쪽으로 계산됩니다.[!INCLUDE[esql](../../../../../../includes/esql-md.md)] 집합 연산자의 우선 순위에 대한 자세한 내용은 [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md) 항목을 참조하세요.  
  
## 예제  
 다음 Entity SQL 쿼리에서는 OVERLAPS 연산자를 사용하여 두 컬렉션에 공통 값이 있는지 여부를 결정합니다. 쿼리는 AdventureWorks Sales 모델을 기반으로 합니다. 이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.  
  
1.  [방법: StructuralType 결과를 반환하는 쿼리 실행](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.  
  
2.  다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.  
  
 [!code-csharp[DP EntityServices Concepts 2#OVERLAPS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#overlaps)]  
  
## 참고 항목  
 [Entity SQL 참조](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)