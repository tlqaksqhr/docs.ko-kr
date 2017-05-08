---
title: "UNION (Entity SQL) | Microsoft Docs"
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
ms.assetid: df98a4db-b00d-4c8b-bd74-0d285f27e1df
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# UNION (Entity SQL)
두 개 이상의 쿼리 결과를 단일 컬렉션으로 결합합니다.  
  
## 구문  
  
```  
  
          expression  
UNION [ ALL ]  
expression  
```  
  
## 인수  
 `expression`  
 컬렉션과 결합할 컬렉션을 반환하는 모든 유효한 쿼리 식입니다. 모든 식은 형식이 같거나 기본 형식 또는 파생 형식이 `expression`이어야 합니다.  
  
 UNION  
 여러 컬렉션을 결합하여 하나의 컬렉션으로 반환하도록 지정합니다.  
  
 ALL  
 여러 컬렉션을 결합하여 중복된 값이 포함된 하나의 컬렉션으로 반환하도록 지정합니다. 지정하지 않을 경우 중복된 값은 결과 컬렉션에서 제거됩니다.  
  
## 반환 값  
 형식이 같거나 기본 형식 또는 파생 형식이 `expression`인 컬렉션입니다.  
  
## 설명  
 UNION은 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 집합 연산자 중 하나입니다. 모든 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 집합 연산자는 왼쪽에서 오른쪽으로 계산됩니다.[!INCLUDE[esql](../../../../../../includes/esql-md.md)] 집합 연산자의 우선 순위에 대한 자세한 내용은 [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md) 항목을 참조하세요.  
  
## 예제  
 다음 Entity SQL 쿼리에서는 UNION ALL 연산자를 사용하여 두 쿼리의 결과를 하나의 컬렉션으로 결합합니다. 쿼리는 AdventureWorks Sales 모델을 기반으로 합니다. 이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.  
  
1.  [방법: StructuralType 결과를 반환하는 쿼리 실행](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.  
  
2.  다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.  
  
 [!code-csharp[DP EntityServices Concepts 2#UNION](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#union)]  
  
## 참고 항목  
 [Entity SQL 참조](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)